!SLIDE subsection
# special powers #

!SLIDE commandline fixed-top

# Run any git command

    $ dfm status -s
     M .vimrc

!SLIDE commandline fixed-top

# Run any git command

    $ dfm status -s
     M .vimrc

    $ pushd ~/.dotfiles
    ~/.dotfiles ~

!SLIDE commandline fixed-top

# Run any git command

    $ dfm status -s
     M .vimrc

    $ pushd ~/.dotfiles
    ~/.dotfiles ~

    $ git status -s
     M .vimrc

!SLIDE commandline fixed-top

# Run any git command

    $ dfm status -s
     M .vimrc

    $ pushd ~/.dotfiles
    ~/.dotfiles ~

    $ git status -s
     M .vimrc

    $ popd
    ~

!SLIDE commandline fixed-top

# Backups

    $ cat .vimrc
    syntax on

!SLIDE commandline fixed-top

# Backups

    $ cat .vimrc
    syntax on

    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Backing up .vimrc.
    INFO:   Symlinking .vimrc (.dotfiles/.vimrc).

!SLIDE commandline fixed-top

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

!SLIDE commandline fixed-top

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

!SLIDE commandline fixed-top

# Skipping files

    $ ls -l .dotfiles/README.md 
    -rw-rw-r-- .dotfiles/README.md

!SLIDE commandline fixed-top

# Skipping files

    $ ls -l .dotfiles/README.md 
    -rw-rw-r-- .dotfiles/README.md

    $ cat .dotfiles/.dfminstall
    README.md skip

!SLIDE commandline fixed-top

# Skipping files

    $ ls -l .dotfiles/README.md 
    -rw-rw-r-- .dotfiles/README.md

    $ cat .dotfiles/.dfminstall
    README.md skip

    $ dfm install
    INFO: Installing dotfiles...

!SLIDE commandline fixed-top

# Skipping files

    $ ls -l .dotfiles/README.md 
    -rw-rw-r-- .dotfiles/README.md

    $ cat .dotfiles/.dfminstall
    README.md skip

    $ dfm install
    INFO: Installing dotfiles...

    $ ls README.md
    ls: cannot access README.md: No such file or directory

!SLIDE commandline fixed-top

# Recursion

    $ ls -l .dotfiles/.ssh/
    -rw-r--r-- config

!SLIDE commandline fixed-top

# Recursion

    $ ls -l .dotfiles/.ssh/
    -rw-r--r-- config

    $ cat .dotfiles/.dfminstall
    .ssh

!SLIDE commandline fixed-top

# Recursion

    $ ls -l .dotfiles/.ssh/
    -rw-r--r-- config

    $ cat .dotfiles/.dfminstall
    .ssh

    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Symlinking config (../.dotfiles/.ssh/config).

!SLIDE commandline fixed-top

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

!SLIDE commandline fixed-top

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

