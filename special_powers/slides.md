!SLIDE subsection
# special powers #

!SLIDE commandline incremental

# Run any git commands

    $ dfm status -s
     M .vimrc

    $ pushd ~/.dotfiles
    ~/.dotfiles ~
    $ git status -s
     M .vimrc
    $ popd
    ~

!SLIDE commandline incremental

# Backups

    $ cat .vimrc
    syntax on

    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Backing up .vimrc.
    INFO:   Symlinking .vimrc (.dotfiles/.vimrc).

    $ cat .vimrc
    set nocompatible
    set bg=dark
    set ts=4 sw=4
    set incsearch

    $ cat .backup/.vimrc 
    syntax on

!SLIDE commandline incremental

# Skipping files

    $ ls -l .dotfiles/README.md 
    -rw-rw-r-- .dotfiles/README.md

    $ cat .dotfiles/.dfminstall
    README.md skip

    $ dfm install
    INFO: Installing dotfiles...

    $ ls README.md
    ls: cannot access README.md: No such file or directory

!SLIDE commandline incremental

# Recursion

    $ ls -l .dotfiles/.ssh/
    -rw-r--r-- config

    $ cat .dotfiles/.dfminstall
    .ssh

    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Symlinking config (../.dotfiles/.ssh/config).

    $ ls -ld .ssh/
    drwx------ .ssh/

    $ ls -l .ssh
    lrwxrwxrwx .ssh/config -> ../.dotfiles/.ssh/config
    -rw-r--r-- .ssh/known_hosts
