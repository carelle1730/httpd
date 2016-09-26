# apache

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/apache/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/apache.svg?branch=master)](https://travis-ci.org/ansiblebit/apache)

[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-apache/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-apache/)

[Ansible][ansible] role to setup [Apache HTTP server][apache].


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Yakkety | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Xenial  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Vivid   | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

- ansible >= 2.0


## Role Variables

- **debug**: flag to run debug tasks.
- **apache_build_dependencies**: list of packages needed to build [apache][apache].
- **apache_dir**: symlink to the enabled [apache][apache] installation.
- **apache_dir_cache**: directory for [apache][apache] cache.
- **apache2_dir_configuration**: directory for [apache][apache] configuration.
- **apache_dir_envvars**: .
- **apache_dir_install**: directory where [apache][apache] will be installed.
- **apache_build_options**: option to be passed to `configure`.
- **apache_dir_modules**: directory where [apache][apache] modules are located.
- **apache_dir_source**: directory where to build [apache][apache].
- **apache_download_url**: the URL for the tarball.
- **apache_download_url_asc**: the URL for the tarball PGP signature.
- **apache_download_url_md5**: the URL for the tarball MD5 checksum.
- **apache_modules**: list of [apache][apache] modules.
- **apache_modules_enabled**: list of enabled [apache][apache] modules.
- **apache_tarball**: filename of the tarball.
- **apache_user**: user under which apache will be running.
- **apache_version**: the [apache][apache] version to be installed.


## Dependencies

None.


## Playbooks

    - hosts: servers
      roles:
         - role: ansiblebit.apache


## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
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

- [Apache > HTTP Server > Documentation > Version 2.4 > Compiling and Installing](https://httpd.apache.org/docs/current/install.html)
- [Apache > HTTP Server > Documentation > Version 2.4 > Programs > configure - Configure the source tree](https://httpd.apache.org/docs/current/programs/configure.html)
- [Verifying Apache HTTP Server Releases](http://httpd.apache.org/dev/verification.html)


[ansible]:  https://ansible.com/    "Ansible"
[apache]:   http://httpd.apache.org/    "Apache HTTP server"
