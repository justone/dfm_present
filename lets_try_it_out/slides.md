!SLIDE subsection
# let's try it out #

!SLIDE bullets incremental

# Step 0

* fork on github
* set up your own master repo

!SLIDE commandline incremental

# Installation

    $ git clone git@github.com:username/dotfiles.git .dotfiles
    Cloning into .dotfiles...
    remote: Counting objects: 1685, done.
    remote: Compressing objects: 100% (830/830), done.
    remote: Total 1685 (delta 714), reused 1632 (delta 689)
    Receiving objects: 100% (1685/1685), 1.19 MiB | 438 KiB/s, done.
    Resolving deltas: 100% (714/714), done.

    $ ./.dotfiles/.bin/dfm
    INFO: Installing dotfiles...
    INFO:   Symlinking .bashrc.load (.dotfiles/.bashrc.load).
    INFO:   Symlinking bin (.dotfiles/bin).
    INFO: Appending loader to .bashrc

!SLIDE commandline incremental

# Adding a file

    $ vi .vimrc
    $ mv .vimrc .dotfiles
    $ dfm install
    INFO: Installing dotfiles...
    INFO:   Symlinking .vimrc (.dotfiles/.vimrc).

    $ dfm add .vimrc
    $ dfm status -s
    A  .vimrc

    $ dfm commit -am 'added vimrc'
    [master 6c12a63] adding vimrc
     1 files changed, 1 insertions(+), 0 deletions(-)
     create mode 100644 .vimrc

    $ dfm push origin master
    Counting objects: 4, done.
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 265 bytes, done.
    Total 3 (delta 1), reused 0 (delta 0)
    To git@github.com:dfmexample/dotfiles.git
       012325a..6c12a63  master -> master

!SLIDE commandline incremental

# Changing a file

    $ vi .vimrc
    $ dfm status -s
     M .vimrc

    $ dfm commit -am 'updated vimrc'
    [master be47490] updated
     1 files changed, 1 insertions(+), 0 deletions(-)

    $ dfm push origin master
    Counting objects: 4, done.
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 301 bytes, done.
    Total 3 (delta 1), reused 0 (delta 0)
    To git@github.com:username/dotfiles.git
       a0d469b..5a745c4  master -> master

!SLIDE commandline incremental

# Getting latest dotfiles

    $ dfm updates
    remote: Counting objects: 5, done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 1), reused 3 (delta 1)
    Unpacking objects: 100% (3/3), done.
    From github.com:username/dotfiles
       5a745c4..012325a  master     -> origin/master
    012325a: updated vimrc

    $ dfm mergeandinstall
    INFO: using merge to bring in changes
    Updating 5a745c4..012325a
    Fast-forward
     .vimrc |    1 +
     1 files changed, 1 insertions(+), 0 deletions(-)
    INFO: re-installing dotfiles
    INFO: Installing dotfiles...
