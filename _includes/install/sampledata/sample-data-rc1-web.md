<div markdown="1">

These instructions apply to you *only* if all of the following are true:

*	You're using Magento Enterprise Edition (EE)
*	You have installed optional sample data
*	You're upgrading to Magento EE RC1 or Magento EE RC2 from any earlier version using the Setup Wizard

To upgrade to Magento 2 EE RC1 or RC2 with sample data using the Setup Wizard:

{% collapsible Click to expand/collapse content %}

1.	Log in to your Magento server as, or switch to, the [Magento file system owner]({{ site.gdeurl }}install-gde/prereq/file-sys-perms-over.html).
2.	Change to the Magento installation directory.
3.	Open `composer.lock` in a text editor.
4.	Change the following:

	From:

		"type": "magento2-module-customer-balance"

	To:

		"type": "magento2-module"
5.	Save your changes to `composer.lock` and exit the text editor.
6.	Manually clear the `var/cache`, `var/page_cache`, and `var/generation` directories.

	A sample command follows:

		rm -rf var/cache/* var/page_cache/* var/generation/*

### Finish the upgrade
After you set file system permissions, complete your upgrade as discussed in [Start System Upgrade]({{ site.gdeurl }}comp-mgr/upgrader/upgrade-start.html).

{% endcollapsible %}
