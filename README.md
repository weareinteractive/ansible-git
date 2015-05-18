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
#  git_repositories:
#    - accept_hostkey: ...
#      bare: ...
#      clone: ...
#      depth: ...
#      dest: ...
#      force: ...
#      key_file: ...
#      recursive: ...
#      reference: ...
#      refspec: ...
#      remote: ...
#      repo: ...
#      ssh_opts: ...
#      track_submodules: ...
#      pull: ...
#      version: ...
#      mode: ...
#      owner: ...
#      group: ...
#

# apt repository
git_repo: ppa:git-core/ppa
# define package (version)
git_package: git-core
# git global configuration settings
git_config: {}
# list of repositories (http://docs.ansible.com/git_module.html)
git_repositories: []
# optional ssh private key to copy to `/etc/ssh/ssh_git.key`
# and be used as default `git_key_file`
git_key:
# optional default key file to use for git operations
git_key_file:
# optional default accept host key to use for git operations (yes | no)
git_accept_hostkey: no
# optional default update to use for git operations (yes | no)
git_pull: yes
# optional default repository mode
git_mode:
# optional default repository owner
git_owner:
# optional default repository group
git_group:
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
