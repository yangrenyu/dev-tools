# Development Tools  
>*Ultimate Weapons* : PuTTY &amp; VIM &amp; ZSH &amp; SCREEN

- [PuTTY](#putty)
- [VIM](#vim)
- [ZSH & oh-my-zsh](#zsh)
- [SCREEN](#screen)
- [Quick install in Ubuntu](#mquick-install-in-ubuntu)

## PuTTY
#### [How to copy & paste](http://xshaun.github.io/windows%E5%B0%8F%E8%A7%81/2017/04/10/putty%E5%A4%8D%E5%88%B6%E7%B2%98%E8%B4%B4)

#### Color Scheme

+ **Windows**: double click `igvita-desert.reg`    
+ **Linux**: copy `igvita-desert.ubuntu` into `~/.putty/sessions/`


#### How to enable *ssh localhost*
    
    # Linux
    ssh-keygen -t dsa -P '' -f ~/.ssh/id_dsa 
    cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys
    chmod 700 ~/.ssh
    chmod 644 ~/.ssh/authorized_keys

## VIM
Use [The Ultimate vimrc](https://github.com/amix/vimrc)

    # install
    git clone https://github.com/amix/vimrc.git ~/.vim_runtime
    sh ~/.vim_runtime/install_awesome_vimrc.sh

    # update to latest version
    cd ~/.vim_runtime
    git pull --rebase

    # update plugins
    python ~/.vim_runtime/update_plugins.py

But According to my habit, manually add following lines into `~/.vim_runtime/my_configs.vim`
    
    set number 
    set cursorline

#### Issues and Solutions  

Have issues about `Unknown function: pathogen#infect` and `Unknown function: pathogen#helptags`, we can add following lines into `~/.vim_runtime/vimrcs/plugins_config.vim`

    """"""""""""""""""""""""""""""
    " => Load pathogen paths
    """"""""""""""""""""""""""""""
    set nocp
    source ~/.vim_runtime/autoload/pathogen.vim

## ZSH

    apt-get install zsh git curl
    chsh -s $(which zsh)
    sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    # reset ZSH_THEME="ys" in ~/.zshrc

## SCREEN

#### [How to use](http://xshaun.github.io/linux%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4/2017/04/10/Screen%E5%91%BD%E4%BB%A4)

+ **Linux**: copy `screenrc` into `~/.screenrc`


----

## [M]Quick install in Ubuntu
    
    sudo apt-get install git curl putty vim zsh screen
    git clont git@github.com:xshaun/dev-tools.git
    
    mkdir -p ~/.putty/sessions/
    cp ./dev-tools/igvita-desert.ubuntu ~/.putty/sessions/igvita-desert
    
    git clone https://github.com/amix/vimrc.git ~/.vim_runtime
    sh ~/.vim_runtime/install_awesome_vimrc.sh
    cp ./dev-tools/my_configs.vim ~/.vim_runtime/my_configs.vim

    chsh -s $(which zsh)
    sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    cp ./dev-tools/zshrc ~/.zshrc
    
    cp ./dev-tools/screenrc ~/.screenrc

    rm -rf ./dev-tools

