[![Build Status - Master](https://travis-ci.com/juju4/ansible-auditd.svg?branch=master)](https://travis-ci.com/juju4/ansible-auditd)
[![Build Status - Devel](https://travis-ci.com/juju4/ansible-auditd.svg?branch=devel)](https://travis-ci.com/juju4/ansible-auditd/branches)
# Linux auditd ansible role

Ansible role to setup and configure linux auditd
Possible [visualization with R](https://security-plus-data-science.blogspot.ca/2017/05/audit-record-fields-visualized.html).

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.2
 * 2.5

### Operating systems

* Ubuntu 14.04, 16.04, 18.04
* Centos7
* Suse 12.x, 15.x

## Example Playbook

Just include this role in your list.
For example

```
- hosts: all
  roles:
    - juju4.auditd
```

## Variables

Nothing specific for now.

## Continuous integration

This role has a travis basic test (for github), more advanced with kitchen and also a Vagrantfile (test/vagrant).
Default kitchen config (.kitchen.yml) is lxd-based, while (.kitchen.vagrant.yml) is vagrant/virtualbox based.

Once you ensured all necessary roles are present, You can test with:
```
$ gem install kitchen-ansible kitchen-lxd_cli kitchen-sync kitchen-vagrant
$ cd /path/to/roles/juju4.auditd
$ kitchen verify
$ kitchen login
$ KITCHEN_YAML=".kitchen.vagrant.yml" kitchen verify
```
or
```
$ cd /path/to/roles/juju4.auditd/test/vagrant
$ vagrant up
$ vagrant ssh
```

## Troubleshooting & Known issues

* As auditd is linked to the kernel, role will not do any change when executed inside containers.

## References

* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Security_Guide/chap-system_auditing.html
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Security_Guide/sec-starting_the_audit_service.html
* https://github.com/bfuzzy/auditd-attack

## License

BSD 2-clause

