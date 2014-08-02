# Ansible Git Role

[![Build Status](https://travis-ci.org/weareinteractive/ansible-role-git.png?branch=master)](https://travis-ci.org/weareinteractive/ansible-role-git)
[![Stories in Ready](https://badge.waffle.io/weareinteractive/ansible-role-git.svg?label=ready&title=Ready)](http://waffle.io/weareinteractive/ansible-role-git)

> `git` is an [ansible](http://www.ansible.com) role which: 
> 
> * installs git

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.git
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):

```
$ arm install franklinkim.git
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-role-git.git
```

## Variables

```
# git_config:
#   color:
#     branch: auto
#     diff: auto
#     interactive: auto
#     status: auto
#   push:
#     default: matching
#

# use repo to install latest git
git_latest: no
# lastest git repo path
git_latest_repo: ppa:git-core/ppa
# git global configuration settings
git_config: {}
```

## Example playbook

```
- host: all
  roles: 
    - franklinkim.git
  vars:
    git_latest: yes
    git_config:
      color:
        diff: auto
        branch: auto
        status: auto
        interactive: auto
      push:
        default: matching    
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-role-git.git
$ cd ansible-role-git
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
