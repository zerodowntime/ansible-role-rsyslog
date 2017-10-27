rsyslog
=========

Install and manage rsyslog configuration

Requirements
------------

This role requires Ansible 2.3 or higher.
Supported platform:
- CentOS
    - 6
    - 7
- Ubuntu
    - 14.04
    - 16.4

Role Variables
--------------

TODO: wypisac zmienne

Dependencies
------------

In Centos host 6 need install `libselinux-python` packages

    yum install libselinux-python

Example Playbook
----------------

TODO: poprawic opis
Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: service_rsyslog }

License
-------

BSD

Author Information
------------------

Krzyszto.Kotewa@ZeroDowntime.pl
