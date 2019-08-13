[![Build Status](https://img.shields.io/travis/ptavares/ansible-role-packer/master.svg?style=flat-square)](https://travis-ci.org/ptavares/ansible-role-packer)
[![Ansible Role](https://img.shields.io/ansible/role/29415.svg)](https://galaxy.ansible.com/ptavares/ansible-role-packer)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/ptavares/ansible-role-packer/blob/master/LICENSE)

ansible-role-packer
=========

Ansible role for installating Packer executable

Requirements
------------

Only test with ansible 2.5 min version

Role Variables
--------------
Available variables are listed below, along with default values (see [defaults/main.yml](https://github.com/ptavares/ansible-role-packer/blob/master/defaults/main.yml)):

### Packer version 

```yaml
# By default, module will download last version
# To specify a version, use this below param
packer_install_version: X.X.X
```
### Download information

```yaml
# Directory where zip will be downloaded before installation
packer_download_location: /tmp/
# Url to packer zip
packer_url: "https://releases.hashicorp.com/packer/{{ packer_install_version | regex_replace('^v', '') }}/packer_{{ packer_install_version | regex_replace('^v', '') }}_linux_amd64.zip"
# Downloaded file name
packer_downloaded_file_name: "packer_{{ packer_install_version | regex_replace('^v', '') }}_linux_amd64.zip"
```

### Installation information

```yaml
# Path where to install packer
packer_execution_path: /usr/local/bin
# Execution file name for packer
packer_execution_file_name: packer
```

Dependencies
------------

No dependencie

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ptavares.ansible_role_packer
```
Inside *`vars/main.yml`*:
- Copy content of [defaults/main.yml](https://github.com/ptavares/ansible-role-packer/blob/master/defaults/main.yml) in your playbook's vars file if needed.
- Customize it as you like (filling role's variables)

License
-------

MIT
