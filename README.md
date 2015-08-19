# Maintain my Mac with Ansible

Status: alpha

## Prerequests

* Yosemite
* Homebrew
* Ansible

## Installation

```
git clone https://github.com/elmar-hinz/OSX.Me.git
cd OSX.Me
ansible-playbook me.yml
```

## Configuration

`host_vars/localhost.yml` is the place to store your private configuration.

Copy `host_vars/localhost_sample.yml` to `host_vars/localhost.yml` to get started.
Customize to your neeeds. Overwrite the default vars of roles.
`host_vars/localhost.yml`  is excluded from the git repository by `.gitignore`.

## Containes so far

* Bootstrap and maintain a basic system including: 
    * Homebrew
    * Ansible
    * Python
    * Ruby
    * Git
    * Bash
    * iTerm
* Maintain all official Hombrew Completions
* Maintain user defined packages with the package managers:
    * Homebrew
    * Homebrew Caskroom
    * Gem

