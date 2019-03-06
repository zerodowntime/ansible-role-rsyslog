# rsyslog

Installation and configuration of rsyslog software utility.

## Requirements

- Ansible >= 2.3+

### Supported platforms

- EL
  - 6
  - 7
- Ubuntu
  - 14.04
  - 16.04

## Default role variables

| Name | Description | Type | Default | Required |
| -----| ----------- | :--: | :------:| :------: |
| rsyslog__package_state | State of rsyslog package. | string | `present` | True |
| rsyslog__options | Options to add to the initial script for rsyslog daemon. | list | `[]` | True |
| rsyslog__modload | List of rsyslog loaded extra modules. | list | `[]` | False |
| rsyslog__imudp_port | UDP port to be open for rsyslog log input. | int | `514` | False |
| rsyslog__imudp_address | IP source address for rsyslog log input. | my_example_type | `127.0.0.1` | False |
| rsyslog__rules | List of extra rsyslog.d configurations. | list | `{}` | True |

**All default variables are described in [defaults/main.yml](defaults/main.yml) file.**

## Static role variables

This section describes static variables implemented in the role.



### centos variables

| Name | Description | Type | Default |
| -----| :---------: | :--: | ------- |
| rsyslog__pacakge_name | Install rsyslog software utility. | string | `rsyslog` |
| rsyslog__config_file | Path to the rsyslogd configuration file. | string | `/etc/rsyslog.conf` |
| rsyslog__confd_dir | Path to the directory with all the additional configuration files for rsyslog. | string | `/etc/rsyslog.d` |
| rsyslog__daemon_environment_file | Path to the file with additional configuration for rsyslog daemon. | string | `/etc/default/rsyslog` |
| rsyslog__daemon_environment_conf_name | Adding options to the rsyslog daemon on the start. | string | `RSYSLOGD_OPTIONS` |

**All static centos variables are described in [vars/centos.yml](vars/centos.yml)**

### ubuntu variables

| Name | Description | Type | Default |
| -----| :---------: | :--: | ------- |
| rsyslog__pacakge_name | Install rsyslog software utility. | string | `rsyslog` |
| rsyslog__config_file | Path to the rsyslogd configuration file. | string | `/etc/rsyslog.conf` |
| rsyslog__confd_dir | Path to the directory with all the additional configuration files for rsyslog. | string | `/etc/rsyslog.d` |
| rsyslog__daemon_environment_file | Path to the file with additional configuration for rsyslog daemon. | string | `/etc/default/rsyslog` |
| rsyslog__daemon_environment_conf_name | Adding options to the rsyslog daemon on the start. | string | `RSYSLOGD_OPTIONS` |

**All static ubuntu variables are described in [vars/ubuntu.yml](vars/ubuntu.yml)**

## License

[Apache License 2.0](LICENSE)

## Support

ZeroDowntime Team <ansible@zerodowntime.pl>