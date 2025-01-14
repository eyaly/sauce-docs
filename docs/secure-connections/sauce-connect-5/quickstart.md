---
id: quickstart
title: Sauce Connect Proxy 5 Quickstart Guide
sidebar_label: Quickstart
---

import useBaseUrl from '@docusaurus/useBaseUrl';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Sauce Connect Proxy is required to run a test on an app or website located behind a firewall. Get up and running with a basic Sauce Connect Proxy tunnel in minutes using the steps below.

## What You'll Need

- A Sauce Labs account ([Log in](https://accounts.saucelabs.com/am/XUI/#login/) or sign up for a [free trial license](https://saucelabs.com/sign-up)).
- If you haven't already, make sure you can access the website or mobile app that you'll be testing from the Sauce Connect Proxy host.
- Check to see if you have any [proxies](/secure-connections/sauce-connect-5/operation/proxies/) that are required to access the public Internet.

## Installing Sauce Connect Proxy

See the [installation instructions](/secure-connections/sauce-connect-5/installation/)

## Starting Sauce Connect Proxy

1. Make sure that the directory containing the `sc` binary (`sc.exe` for Windows) is in the `$PATH`. Otherwise, you will have to specify the path to the binary in the command line, `/path/to/sc`
2. Log in to Sauce Labs.
3. Go to the [**Tunnel Proxies**](https://app.saucelabs.com/tunnels) page.<br/><img src={useBaseUrl('img/sauce-connect/tunnelsPage.png')} alt="Sauce Connect Proxy Tunnels page" width="400"/>
4. Under step 2, **Authenticate & connect**, copy the code snippet.<br/><img src={useBaseUrl('img/sauce-connect/configureAuth.png')} alt="Sauce Connect Proxy Tunnels page snippet" width="300"/>
   <details><summary>What is this?</summary>
   This snippet contains your authentication credentials (username and access key), selects a Sauce Labs Data Center, and applies a name to your tunnel. Optionally, you can rename your tunnel by replacing the value after the <code>--tunnel-name</code> flag.
   </details>
5. Paste the snippet into your terminal but **do not run it**. This snippet is not updated for Sauce Connect Proxy 5, it can only be used to get your username and your access key.
6. Follow the steps in the [setup instructions](/secure-connections/sauce-connect-5/operation/overview/#running-sauce-connect-proxy) to start Sauce Connect Proxy 5 using the username and the access key obtained in the previous step.

## Verify Connection

To confirm your tunnel is up, look for the confirmation message in your terminal:<br/><img src={useBaseUrl('img/sauce-connect/cli-tunnel-confirmation.png')} alt="Sauce Connect Tunnel Success" width="350"/>

Alternatively, you can check your list of active tunnels on the **Tunnel Proxies** page:<br/><img src={useBaseUrl('img/sauce-connect/tunnelsuccess-ui.png')} alt="Sauce Connect Tunnel Success" width="500"/>

## Run Test

With your tunnel up and running, try doing a Live <!--or Automated--> local test.

<Tabs
  defaultValue="Cross-Browser"
  values={[
    {label: 'Cross-Browser', value: 'Cross-Browser'},
    {label: 'Mobile Browser', value: 'Mobile Browser'},
    {label: 'Mobile App', value: 'Mobile App'},
  ]}>

<TabItem value="Cross-Browser">

1. From your terminal or IDE, launch a local instance of your website as you normally would.
2. From Sauce Labs, click **Live** > **Cross Browser** > **Desktop**.
3. In the **URL** field, enter your website's local URL (e.g., `http://localhost:3000`).
4. From the **Sauce Connect Proxy** dropdown, select your tunnel name.
5. Select your desired browser configuration.
6. Click **Start Test** to launch your live test in Sauce Labs.

</TabItem>
<TabItem value="Mobile Browser">

1. From your terminal or IDE, launch a local instance of your site as you normally would.
2. From Sauce Labs, click **Live** > **Cross Browser** > **Mobile Virtual** or **Mobile Real**.
3. Enter the local **URL** for your local website under test (e.g., `http://localhost:3000`)
4. From the **Sauce Connect Proxy** dropdown, select your tunnel name.
5. Select your desired **Mobile Virtual** or **Mobile Real** device configuration.
6. Click **Start Test** to launch your live test in Sauce Labs.

</TabItem>
<TabItem value="Mobile App">

1. From Sauce Labs, click **Live** > **Mobile App**.
2. Click **Upload App** to upload your iOS or Android mobile app file to Sauce Labs.
3. Find your app in the apps list, hover your mouse over it, and click **Choose Device**.
4. To test your app on a real device, click **Mobile Real**. To test it on an emulator or simulator, click **Mobile Virtual**.
5. Select your desired device configuration, including your tunnel name in the **Sauce Connect Proxy** dropdown.
6. Click **Start Test** to launch your live test in Sauce Labs.

</TabItem>
</Tabs>

## Stop Tunnel

When you've finished testing, you can stop your tunnel from the terminal where Sauce Connect is running by entering Ctrl+C.<br/><img src={useBaseUrl('img/sauce-connect/cli-tunnel-stop.png')} alt="Sauce Connect Proxy Tunnels page snippet" width="500"/>

Alternatively, you can go to the **Tunnel Proxies** page and click one of the **Stop Tunnels** buttons.<br/><img src={useBaseUrl('img/sauce-connect/tunnelstop-ui.png')} alt="Sauce Connect Tunnel Stop" width="800"/>

## More Information

- [Sauce Connect Proxy Overview](/secure-connections/sauce-connect/)
- [Sauce Connect Proxy Configuration](/secure-connections/sauce-connect-5/operation/configuration)
- [Sauce Connect Proxy 5 CLI Reference](/dev/cli/sauce-connect-5/)
