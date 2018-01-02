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

Role default Variables
--------------

var name                            | type   | default    | desctiption
----------------------------------- | -----  | ---------- | -------------------------------------------
rsyslog__package_state              | string | present    | State for installated packages: `present`,`latest`
rsyslog__options                    | list   | []         | Options for rsyslogd daemon
rsyslog__modload                    | List   | []         | List of rsyslog loaded extra modules
rsyslog__imudp_port                 | int    | 514        | imudp listen port
rsyslog__imudp_address              | string | 127.0.0.1  | imudp listen address
rsyslog__rules                      | dict   | {}         | List of extra rsyslog.d configs: format key:value


Role Variables
--------------

var name                               | type   | desctiption
-------------------------------------- | -----  | -------------------------------------------
rsyslog__pacakge_name                  | string | Name for installated packages
rsyslog__config_file                   | string | Config file path
rsyslog__confd_dir                     | string | rsyslog.d config dir
rsyslog__daemon_environment_file       | string | rsyslog daemon environment file
rsyslog__daemon_environment_conf_name  | string | rsyslog daemon oprion enviroment name


Dependencies
------------

In Centos host 6 need install `libselinux-python` packages

    yum install libselinux-python

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
    - hosts: all
      roles:
      - { role: service_rsyslog }
```

```
    - hosts: all
      roles:
      - role: service_rsyslog
        rsyslog__rules:
          10-forward: '*.* @192.168.0.10:514'
          50-haproxy: |
            if $programname startswith 'haproxy' then /var/log/haproxy.log
            & stop      
```


License
-------

BSD

Author Information
------------------

Krzyszto.Kotewa@ZeroDowntime.pl
