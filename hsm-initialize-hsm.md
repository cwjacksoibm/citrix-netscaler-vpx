---

copyright:
  years: 2018
lastupdated: "2019-11-12"

keywords: hsm, security, initialize

subcollection: citrix-netscaler-vpx

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank_"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Initialize IBM Hardware Security Module (HSM)
{: #initialize-ibm-hardware-security-module-hsm-}

Most configurations of the HSM for your {{site.data.keyword.vpx_full}} require initialization of the HSM device. Without this, only certain `show` commands can be executed.
{: shortdesc}

To initialize your device, follow the steps below:

1.	Connect using SSH into the IBM© Hardware Security Module device with the credentials listed in the Control Portal under **Devices > Device List > Expand HSM name**.

	Alternatively, you can use public key authentication. For more information review the [Appliance Administration Guide (page 38) ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://public.dhe.ibm.com/cloud/bluemix/network/vpx/appliance_administration_guide.pdf){:new_window}.

	SSH access is generally enabled and allowed by default. If you have issues connecting with SSH, check your infrastructure routing and security.
  {: note}

2. Execute the `hsm init` command:

	```
	[jpmongehsm2] lunash:>hsm init -l jpmonge

	Please enter a password for the HSM Administrator:
	> ********

	Please re-enter password to confirm:
	> ********

	Please enter a cloning domain to use for initializing this HSM:
	> ********

	Please re-enter cloning domain to confirm:
	> ********

	CAUTION:  Are you sure you wish to initialize this HSM?

	Type 'proceed' to initialize the HSM, or 'quit'
		to quit now.
		> proceed
		'hsm init' successful.

	Command Result : 0 (Success)
  	```

	Where the syntax used is: `hsm init -l <hsmlabel>`

The `-l` parameter or label is a parameter used to assign an identifier to the HSM, and can be any meaningful text or description related to the business, administrator or the role it fulfills. The HSM administrator password will be the designated password for the HSM Security Officer (SO), and is essentially a profile required to create and configure crypto objects, as well as make changes to the HSM environment.

Lastly, the cloning domain is a shared identifier that allows objects to be formed among a group of HSMs. This is typically used for backup and/or HA.

Refer to the [LunaSH Command Reference Guide ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://public.dhe.ibm.com/cloud/bluemix/network/vpx/lunash_command_reference_guide.pdf){: new_window} for all available commands supported in the HSM CLI.
