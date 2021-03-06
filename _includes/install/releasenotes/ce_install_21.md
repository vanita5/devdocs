<div markdown="1">

## Installation and upgrade instructions
You can install Magento Enterprise Edition 2.1 (including a Release Candidate) from either Github or by using Composer. 

<div class="bs-callout bs-callout-warning">
    <p><em>Do not</em> install or upgrade to a Release Candidate on a production system. Upgrade to a Release Candidate on a development system only.</p>
</div>

See one of the following sections:

*	[Install from GitHub](#install-rc-gh)
*	[Install using Composer](#install-rc-composer)
*	[Upgrade existing installations](#upgrade-rc-nosamp)
*	[Upgrade to Magento 2.1 with sample data](#upgrade-rc-samp)

### Install from GitHub {#install-rc-gh}
Before proceeding, please familiarize yourself with these prerequisites, then run

	git clone git@github.com:magento/magento2.git
	cd magento2
	git checkout tags/<version> [-b <version>]

where 

`<version>` is `2.1.0-rc1`, `2.1.0-rc2`, or `2.1.0-rc3`

`[-b <version]` optionally checks out a new branch.

### Install using Composer {#install-rc-composer}
This Release Candidate is available from `repo.magento.com`. Before installing this Release Candidate using Composer, familiarize yourself with the Composer metapackage  <a href="{{ site.gdeurl }}install-gde/prereq/integrator_install.html" target="_blank">prerequisites</a>, then run 

	composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition=<version> <installation directory name>

where `<version>` is `2.1.0-rc1`, `2.1.0-rc2`, or `2.1.0-rc3`

For example, to install Magento CE RC3 in the `magento2` directory:

	composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition=2.1.0-rc3 magento2

## Upgrade existing installations {#upgrade-rc-nosamp}
This section discusses how to upgrade to Magento version 2.1 (including a Release Candidate) *without* sample data.

If you installed optional sample data, see [Upgrade to an RC with sample data](#upgrade-rc-samp) instead.

<div class="bs-callout bs-callout-warning">
    <p><em>Do not</em> upgrade to a Release Candidate on a production system. Upgrade to a Release Candidate on a development system only.</p>
</div>

### Upgrade using the Setup Wizard
Use the instructions in [Start System Upgrade]({{ site.gdeurl }}comp-mgr/upgrader/upgrade-start.html). When prompted to choose a version, choose a Release Candidate.

### Upgrade from the GitHub repository
Developers who contribute to the CE codebase can <a href="{{ site.gdeurl }}comp-mgr/bk-compman-upgrade-guide.html" target="_blank">upgrade manually</a> from the Magento CE GitHub repository.

1.	Go to the <a href="{{ site.gdeurl }}install-gde/install/cli/dev_update-magento.html" target="_blank">Contributing Developers</a> page.

2.	Follow the instructions to pull the updates from the repository and update using Composer.

### Upgrade using the command line
This section discusses how to upgrade to Magento 2.1 (including a Release Candidate) using the command line.

{% collapsible To upgrade to Magento 2.1 using the command line: %}

1.	Log in to your Magento server as, or switch to, the Magento file system owner.
2.	Change to the directory in which you installed the Magento software.

	For example, `cd /var/www/html/magento2`
2.	Enter the following commands in the order shown:

		composer require <product> <version> --no-update
		composer update

	where `<version>` is `2.1.0-rc1`, `2.1.0-rc2`, or `2.1.0-rc3`

	To upgrade to Magento CE 2.1 RC3, enter:

		composer require magento/product-community-edition 2.1.0-rc3 --no-update
		composer update

3.	If prompted, enter your [authentication keys]({{ site.gdeurl }}comp-mgr/prereq/prereq_auth-token.html).
4. Update the database schema and data:

		php bin/magento setup:upgrade

{% endcollapsible %}

## Upgrade to Magento 2.1 with sample data {#upgrade-rc-samp}
This section discusses how to upgrade Magento with optional sample data using the command line.

<div class="bs-callout bs-callout-warning">
    <p>There is a known issue with upgrading Magento with sample data using the Setup Wizard. We're actively working on a solution to this issue.</p>
</div>

{% include install/sampledata/sample-data-rc1-cli.md %}

