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
