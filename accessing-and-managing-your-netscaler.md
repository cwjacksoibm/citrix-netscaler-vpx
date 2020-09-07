---
copyright:
  years: 1994, 2019

lastupdated: "2019-11-13"

keywords: manage, managing, locating, details, portal, device, list

subcollection: citrix-netscaler-vpx
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank_"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Managing your Citrix Netscaler VPX
{: #managing-your-citrix-netscaler-vpx}

{{site.data.keyword.vpx_full}} devices are powerful tools with an array of features that help to enhance and refine your {{site.data.keyword.cloud}} solution in a multitude of ways. You can find the device's information in the {{site.data.keyword.cloud_notm}} Cloud catalog, as well as connect to the device and configure its features.  
{: shortdesc}

## Locating NetScaler details in the IBM Cloud catalog
{: #locating-netscaler-details-in-the-customer-portal}

Citrix NetScaler devices are listed in the Device List, like any other server you have on the {{site.data.keyword.cloud_notm}} platform.

To find the Device List:

1. From your browser, open the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com){:new_window} and log into your account.
2. Select the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) from the top left, then click **Classic Infrastructure**.

You will see your devices, sorted by device name, in the Device List. {{site.data.keyword.vpx_full}} devices have "NetScaler" as the Device Type.

On the left side of the row for your NetScaler, click the arrow to expand the line and show the Username and a masked password for NetScaler management access.

Other details listed in the Device List include:

* Location (data center in which the NetScaler resides)
* Private IP address (which is used to connect to the NetScaler for management functions)
* Start Date (when the machine was ordered and provisioned)

While the Private IP address of the NetScaler is listed in the portal, the Public IP address of the NetScaler is not. This is because management of the NetScaler is done using the Private IP address, and the Public IP addresses for NetScaler devices are used as the device's VIP(s) or Virtual IP(s), which are used for load balancing services.
{: note}

## The Device details screen
{: #the-device-details-screen}

Clicking on the NetScaler's name takes you to the **Device Details** page for the NetScaler, which shows the VLAN on which your NetScaler was deployed, as well as your Public IP addresses for the NetScaler. These IP addresses cannot be used for management, because they are the NetScaler's default Public VIP addresses. You will use these later to associate to a load balancing service.

## Connecting to the NetScaler
{: #connecting-to-the-netscaler}

{{site.data.keyword.cloud_notm}} grants full root access to your NetScaler device. To log into the NetScaler's Management UI, you must be connected to the {{site.data.keyword.cloud_notm}} private network either the IBM Cloud Management VPN, or performing management functions from a remote session on a server within the {{site.data.keyword.cloud_notm}} environment).

To connect from the catalog to the NetScaler's Management UI, click the **Actions** drop-down list in the top right corner of the **Device Details** screen and choose **Manage Device** to launch a new tab or pop-up window in your browser. This routes you to the NetScaler's NSIP (the Private IP address that you saw previously). The page that displays asks for the root username and password for the device. Once you enter the information, it will take you to the NetScaler Management GUI.

Alternatively, you can copy and paste the NetScaler device's private IP into a web browser.

### NetScaler SSH access
{: #netscaler-ssh-access}

You can also connect to the NetScaler device directly using your favorite SSH client. Use the Private IP and login information for the NetScaler device from the Device List page and make sure you are connected to the {{site.data.keyword.cloud_notm}} VPN.

## Caution Regarding HA Configurations and Portal Passwords
{: #ha-config-notice}

While the VPX is expected to be managed by the customer, if customer does not keep their Cloud Portal root username and password consistent with what they have changed it to on the physical device.  **If these are not kept consistent, upgrades and licensing operations can fail resulting in production outages.**  Ensure any administrator tasked with supervision of VPX's is aware of this to avoid unexpected downtime.
