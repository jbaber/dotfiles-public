The dotfiles check out directly to my $HOME without symlinks or
anything using the method outlined [at this blogpost].

On a new machine, I must

    git clone --bare <git-repo-url> $HOME/.cfg
    alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
    config config --local status.showUntrackedFiles no
    config checkout

How to include in local dotfiles
--------------------------------

`.bashrc`:

    source $HOME/.bashrc.public

`.vimrc`:

    source $HOME/.vimrc.public


`.gitconfig`:

    [include]
      path = ~/.gitconfig.public

[at this blogpost]: https://www.atlassian.com/git/tutorials/dotfiles
