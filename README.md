# Ansible Nodejs Role

[![Build Status](https://travis-ci.org/weareinteractive/ansible-role-nodejs.png?branch=master)](https://travis-ci.org/weareinteractive/ansible-role-nodejs)
[![Stories in Ready](https://badge.waffle.io/weareinteractive/ansible-role-nodejs.svg?label=ready&title=Ready)](http://waffle.io/weareinteractive/ansible-role-nodejs)

> `nodejs` is an [ansible](http://www.ansible.com) role which: 
> 
> * installs nodejs
> * configures nodejs
> * enables/disables sites
> * optionally removes default host

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.nodejs
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):

```
$ arm install franklinkim.nodejs
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-role-nodejs.git
```

## Variables

```
# global packages to install
nodejs_packages: []
# apt repository name
nodejs_apt_repository: ppa:chris-lea/node.js
```

## Example playbook

```
- host: all
  roles: 
    - franklinkim.nodejs
  vars:
    nodejs_packages:
      - less
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-role-nodejs.git
$ cd ansible-role-nodejs
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
