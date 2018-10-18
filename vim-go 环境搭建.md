### vim-go 环境搭建

#### 一、安装SDK

1.官网下载: <https://golang.org/dl/>

2.安装:解压tar.gz包 运行pkg包进行安装

3.配置环境变量：自定义GOPATH并在 ～/.zshrc 中修改环境变量

```
export GOPATH=/Users/admin/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOBIN
```	

4.source  ~/.zshrc  输入go env查看配置结果

#### 二、安装Vundle

1.git 克隆 Vundle 工程到本地

```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

2.修改.vimrc配置 Plugins 在.vimrc文件中添加如下内容

```
set nocompatible              " be iMproved, required
filetype off                  " required
	
" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')
	
" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'
	
" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}
	
" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```

3.保存后进入 vim 运行命令

```
:PluginInstall
```

###三、安装vim-go

1.git 克隆 vim-go 工程到本地

```
git clone https://github.com/fatih/vim-go.git ~/.vim/bundle/vim-go
```

2.在.vimrc的vundle配置里面加入vim-go

```
" Install Vim-go  
Plugin 'fatih/vim-go'
```

3.保存后进入 vim 运行命令

```
:PluginInstall
```

4.安装 go.tools Binaries 二进制工具 在vim下输入

```
:GoInstallBinaries
```

###四、其他插件
#####实时代码补齐YouCompleteMe
1.在.vimrc的vundle配置里面加入YouCompleteMe

```
:Plugin 'Valloric/YouCompleteMe'
```

2.保存后进入 vim 运行命令

```
:PluginInstall
```
	
3.编译过程需要CMake

```
brew install CMake
```

4.编译YouCompleteMe

```
cd ~/.vim/bundle/YouCompleteMe
./install.sh --gocode-completer
```

#####NERDTree
1.在.vimrc的vundle配置里面加入NERDTree

```
Plugin 'scrooloose/nerdtree'
```

2.保存后进入 vim 运行命令

```
:PluginInstall
```

3.在.vimrc中配置NERDTree

```	
" NERDTree config
" <F2> NERDTree
map <F2> :NERDTreeToggle<CR>
```


	