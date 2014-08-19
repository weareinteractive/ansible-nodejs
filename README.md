# Ansible Nodejs Role

[![Build Status](https://travis-ci.org/weareinteractive/ansible-nodejs.png?branch=master)](https://travis-ci.org/weareinteractive/ansible-nodejs)
[![Stories in Ready](https://badge.waffle.io/weareinteractive/ansible-nodejs.svg?label=ready&title=Ready)](http://waffle.io/weareinteractive/ansible-nodejs)

> `nodejs` is an [ansible](http://www.ansible.com) role which: 
> 
> * installs nodejs
> * installs global npm packages

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
$ git clone https://github.com/weareinteractive/ansible-nodejs.git
```

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# global packages to install
nodejs_packages: []
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

## Notes

You can use `franklinkim.apt` to add a repository to get the latest `nodejs`:

```
apt_repositories:
  - 'ppa:chris-lea/node.js'
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
