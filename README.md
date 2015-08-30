# Maintain my Mac with Ansible

Status: beta

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

`config.yml` is the place to store your configuration.

Simply copy `config.sample.yml` to `config.yml` to get started.
Customize to your neeeds. Overwrite the default vars of roles.
Hint `config.yml` is excluded from the git repository by .gitignore.

## Contains so far

* Bootstrap and maintain a basic system including: 
    * Homebrew
    * Ansible
    * Python
    * Ruby
    * Node.js
    * Git
    * Bash
    * iTerm
* Maintain user defined packages with the package managers:
    * Npm
    * Homebrew
    * Homebrew Caskroom
    * Gem
* Maintain all official Hombrew Completions
* Maintain user dotfiles in a Git repository

## Custom role

You can create a custom role in `roles/private/`.
The directory `private/` is just a dummy 
to stop ansible from complaining.

See `private/README.md`.

## Dotfile management 

* The Dotfile management is skipped until you define the variable 
  `dotfiles_repository` in `host_vars/localhost.yml`
* `dotfiles_repository` should point to your git dotfiles repository 
  i.e. https://github.com/your-name/dotfiles.git
* It is cloned into `~/.my.dotfiles` by default.
* Cloning is done recursivly to pull submodules like vim bundles.

The principle is simple: 

**Every dotted file and dotted directory is symlinked into your home directory.**

```
	~/.my.dotfiles/.vimrc -> ~/.vimrc
	~/.my.dotfiles/.vim/ -> ~/.vim
```

Details:

* Only files and directories and symlinks (sic!) on the top level are symlinked. 
* No recursion or similar magic.
* Excluded: 
	* `.git`
	* `.gitignore`
	* `.gitmodules`
	* `.DS_Store`
* Security: 
	* It refuses to change existing files or directories in `~/` to symlinks.
	* By this you are forced to cleanup/backup your existing dotfiles before. 
* Risk: 
	* **However, it changes existing symlinks without warning.**
    * A limited risk, but you should be aware of it.

