The dotfiles check out directly to my $HOME without symlinks or
anything using the method outlined [at this blogpost].

On a new machine, I must

    git clone --bare <git-repo-url> $HOME/dotfiles-public.git
    alias pconfig='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
    pconfig config --local status.showUntrackedFiles no
    pconfig checkout

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
