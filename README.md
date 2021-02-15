# dotfiles
Linux configuration dotfiles, kept in this repository, deployed with stow


Keeping all dotfiles in a single repository can be achieved with the help of `stow`.  
`stow` intelligently creates symlinks from the repository to the corresponding location in the user's home.  
The repository should therefore be cloned to `$HOME/<dotfile_repo_folder_name>`.  
From the stow directory, the files in each subfolder (stow package) can be deployed with:  
`stow <folder_name>`

However, `stow` is not able to handle conflicts with existing files in every case.
To make life easier, the script `stow-safe` creates backups of conflicting files during the stow operation.
The script also calls `stow` for all packages in the repository.
The script `stow-home` defaults stowing from "$HOME/.dotfiles" to "$HOME".

## Requirements
`stow`:
- Can be installed as perl module via `capnm Stow` as user
  - `cpanm` can be installed in $HOME with:
    - `wget -O- http://cpanmin.us | perl - -l ~/perl5 App::cpanminus local::lib`
    -  `` eval `perl -I ~/perl5/lib/perl5 -Mlocal::lib` ``
