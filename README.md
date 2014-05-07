Ansible Nagios
==============

Ansible role to install Nagios from source.

Features
--------

* Installs and configures Nagios 4 (not currently available through a PPA).
* Installs the [Pagerduty integration](https://www.pagerduty.com/docs/guides/nagios-integration-guide/)
* Support for sending notifications via [SES](http://github.com/npm/notify-by-ses)
* Installs NRPE, for performing remote checks.
* Installs a recent build of nagios-plugins.

Installation
------------

Ansible Nagios has some dependencies on other roles, checkout [librarian-ansible](https://github.com/bcoe/librarian-ansible)
a great tool for managing Ansible dependencies.

Configuration
-------------

To get things up and running on an Ubuntu machine, here are the variables you will need to set:

```yaml
nagios_user: nagiosadmin
nagios_password: nagiosadmin
nagios_host: nagios.example.com
nagios_pagerduty_key: xxxxxxxxxxxxxxxxxxxxx
nagios_admin_email: ops@example.com
nagios_amdin_name: 'Nagios Admin'

nagios_aws_access_key_id: xxxxxxxxxxxxxxxx
nagios_aws_access_key_secret: xxxxxxxxxxxxxxx
nagios_ses_region: email.us-east-1.amazonaws.com

nagios_enable_pagerduty_notifications: true
nagios_enable_ses_notifications: true

legacy: false # set to true, for older builds of Ubuntu like Precise.
```

* See `/vars/main.yml` for more configuration options.

How it Works?
------------

* Create a playbook that references the nagios role.
* Set the appropriate variables.
* Run this role on a clean server.
* You will now be able to access nagios on the host at **https://your-host/nagios**.

Ansible-Nagios-Config
---------------------

This Ansible role is designed to be used along with [Ansible-Nagios-Config](http://github.com/npm/ansible-nagios-config).
Use this role to set up Nagios' configuration.

Compatibility
---------

This role has been tested on the following Linux distributions:

**Ubuntu:**

* Precise.
* Trusty.

Please open an issue if you confirm the role works on other distributions.
