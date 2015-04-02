# Ansible Nodejs Role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-nodejs.svg)](https://travis-ci.org/weareinteractive/ansible-nodejs)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/weareinteractive/ansible-nodejs/master/LICENSE)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-nodejs.svg)](https://github.com/weareinteractive/ansible-nodejs)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-nodejs.svg)](https://github.com/weareinteractive/ansible-nodejs)

> `nodejs` is an [ansible](http://www.ansible.com) role which:
>
> * installs nodejs
> * installs global npm packages

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.nodejs
```

Using `requirements.yml`:

```
- src: franklinkim.nodejs
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-nodejs.git
```

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# node_packages:
#   - less
#   - { name: recess, version: 1.1.9 }

# define version
nodejs_version: 0.10
# define package (version)
nodejs_package: nodejs
# global packages to install
nodejs_packages: []
# global packages state (present|latest)
nodejs_packages_state: present
# update all global packages
nodejs_packages_update: no
```

## Example playbook

```
- hosts: all
  sudo: yes
  roles:
    - franklinkim.nodejs
  vars:
    nodejs_packages:
      - less
      - { name: recess, version: 1.1.9 }
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-nodejs.git
$ cd ansible-nodejs
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
Copyright (c) We Are Interactive under the MIT license.
