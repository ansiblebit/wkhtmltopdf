# wkhtmltopdf

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/wkhtmltopdf/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/wkhtmltopdf.svg?branch=master)](https://travis-ci.org/ansiblebit/wkhtmltopdf)

[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-wkhtmltopdf/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-wkhtmltopdf/)


[Ansible][ansible] role to install [wkhtmltopdf].

This repo was a fork of [AerisCloud/ansible-wkhtmltopdf] but,
currently,
it has diverged significantly from the original work.


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Yakkety | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Xenial  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Wily    | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

- ansible >= 2.0


## Role Variables

- **debug**: flag to run debug tasks.
- **wkhtmltopdf_dir_src**: directory where to store the source tarball.
- **wkhtmltopdf_slug**: git repository slug to be cloned.
- **wkhtmltopdf_user**: account used to build the software.
- **wkhtmltopdf_version**: version to be installed.
- **wkhtmltopdf_mm_version**: major and minor version to be installed (no need to define).


## Dependencies

- [ansiblebit/git]


## Playbooks

    - hosts: servers
      vars:
        see tests/vars/vagrant.yml
    
      roles:
         - role: ansiblebit.wkhtmltopdf


## Tags

- **configuration**: configuration tasks.
- **build**: build tasks.
- **debug**: task to debug role variables.
- **validation**: task to validate role variables.


## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```
$ tox
```

To run tests for `trusty64`:

```
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```


## Links

- [wkhtmltopdf]
- [AerisCloud/ansible-wkhtmltopdf]


[ansible]:  https://ansible.com/    "Ansible"
[ansiblebit/git]:  https://github.com/ansiblebit/git    "ansiblebit/git"
[AerisCloud/ansible-wkhtmltopdf]: https://AerisCloud/ansible-wkhtmltopdf "AerisCloud/ansible-wkhtmltopdf"
[wkhtmltopdf]: http://wkhtmltopdf.org/  "wkhtmltopdf"
