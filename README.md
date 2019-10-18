# Ansible weareinteractive.nodejs role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-nodejs.svg)](https://travis-ci.org/weareinteractive/ansible-nodejs)
[![Galaxy](http://img.shields.io/badge/galaxy-weareinteractive.nodejs-blue.svg)](https://galaxy.ansible.com/weareinteractive/nodejs)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-nodejs.svg)](https://github.com/weareinteractive/ansible-nodejs)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-nodejs.svg)](https://github.com/weareinteractive/ansible-nodejs)

> `weareinteractive.nodejs` is an [Ansible](http://www.ansible.com) role which:
>
> * installs nodejs
> * installs global npm packages

**Note:**

> Since Ansible Galaxy supports [organization](https://www.ansible.com/blog/ansible-galaxy-2-release) now, this role has moved from `franklinkim.nodejs` to `weareinteractive.nodejs`!

## Installation

Using `ansible-galaxy`:

```shell
$ ansible-galaxy install weareinteractive.nodejs
```

Using `requirements.yml`:

```yaml
- src: weareinteractive.nodejs
```

Using `git`:

```shell
$ git clone https://github.com/weareinteractive/ansible-nodejs.git weareinteractive.nodejs
```

## Dependencies

* Ansible >= 2.4

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
---
# For more information about default variables see:
# http://www.ansibleworks.com/docs/playbooks_variables.html#id26
#
# node_packages:
#   - less
#   - { name: recess, version: 1.1.9 }

# define version
nodejs_version: "10.x"
# dependencies packages to install package
nodejs_dependencies:
  - apt-transport-https
  - ca-certificates
  - build-essential
  - gnupg
# define package (version)
nodejs_package: nodejs
# global packages to install
nodejs_packages: []
# global packages state (present|latest)
nodejs_packages_state: present
# update all global packages
nodejs_packages_update: no

```


## Usage

This is an example playbook:

```yaml
---

- hosts: all
  become: yes
  roles:
    - weareinteractive.nodejs
  vars:
    nodejs_packages:
      - less
      - { name: recess, version: 1.1.9 }

```


## Testing

```shell
$ git clone https://github.com/weareinteractive/ansible-nodejs.git
$ cd ansible-nodejs
$ make test
```

## Contributing
In lieu of a formal style guide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

*Note: To update the `README.md` file please install and run `ansible-role`:*

```shell
$ gem install ansible-role
$ ansible-role docgen
```

## License
Copyright (c) We Are Interactive under the MIT license.
