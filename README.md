# Ansible Git Role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-git.svg)](https://travis-ci.org/weareinteractive/ansible-git)
[![Galaxy](http://img.shields.io/badge/galaxy-franklinkim.supervisor-blue.svg)](https://galaxy.ansible.com/list#/roles/1370)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-git.svg)](https://github.com/weareinteractive/ansible-git)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-git.svg)](https://github.com/weareinteractive/ansible-git)

> `git` is an [ansible](http://www.ansible.com) role which:
>
> * installs git
> * configures git

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.git
```

Using `requirements.yml`:

```
- src: franklinkim.git
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-git.git franklinkim.git
```

## Dependencies

* Ansible 1.9

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

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

# apt repository
git_repo: ppa:git-core/ppa
# define package (version)
git_package: git-core
# git global configuration settings
git_config: {}
# optional git user for git operations
git_user:
```

## Example playbook

```
- host: all
  sudo: yes
  roles:
    - franklinkim.git
  vars:
    git_config:
      color:
        diff: auto
        branch: auto
        status: auto
        interactive: auto
      push:
        default: matching
    git_repositories:
      - repo: https://github.com/weareinteractive/ansible-git.git
        dest: /tmp/franklinkim.git
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-git.git
$ cd ansible-git
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
