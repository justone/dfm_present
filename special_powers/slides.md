!SLIDE subsection
# special powers #

!SLIDE commandline

# Run any git commands

    $ dfm status -s
     M .vimrc

    $ pushd ~/.dotfiles
    ~/.dotfiles ~/foo
    $ git status -s
     M .vimrc
    $ popd
    ~/foo

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

    $ cat .dotfiles/.dfminstall
    README.md skip
    t skip

    $ dfm install
    INFO: Installing dotfiles...

    $ ls README.md
    ls: cannot access README.md: No such file or directory

!SLIDE commandline incremental

# Recursion

    $ cat .dotfiles/.dfminstall
    .ssh
    README.md skip
    t skip

    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Symlinking config (../.dotfiles/.ssh/config).

    $ ls -ld .ssh/
    drwx------ .ssh/

    $ ls -l .ssh
    lrwxrwxrwx .ssh/config -> ../.dotfiles/.ssh/config
    -rw-r--r-- .ssh/known_hosts
