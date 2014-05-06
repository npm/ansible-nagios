Ansible Nagios
==============

Ansible role to install Nagios from source.

Features
--------

* Installs and configures Nagios 4 (not currently available through a PPA).
* Installs the [Pagerduty integration](https://www.pagerduty.com/docs/guides/nagios-integration-guide/)
* Support for Sending Notifications via SES
* Installs NRPE, for performing remote checks.
* Installs a recent build of nagios-plugins.

Configuration
-------------

To get things up and running on an Ubuntu machine, here's the variables you will need to set:

```yaml
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
```

* See `/vars/main.yml` for more configuration options.

Ansible Nagios Config
---------------------

This Ansible role is designed to be used along with, [Ansible-Nagios-Config](http://github.com/npm/ansible-nagios-config)...
Use this role to setup Nagios' configuration.
