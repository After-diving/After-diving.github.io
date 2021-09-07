# Linux 配置

## vim美化

### vim文件配置

在`cd $user`目录下, 创建一个<b style="background-color:red">.vim</b>文件. `cd .vim`目录下,创建一个<b style="color:red">vimrc</b>文本. 将下面内容拷贝到<b style="color:red">vimrc</b>文本中.

```shell
colorscheme molokai                              " 设置主题
setlocal list
filetype indent on                               " 检测文件类型,并且载入与该类型对应的缩进规则
map <C-n> :NERDTreeToggle<CR>
" hi SpecialKey guifg=darkgrey ctermfg=darkgrey
autocmd BufWritePost $MYVIMRC source $MYVIMRC    " 让vimrc配置立即生效

map <F5> <ESC>:set mouse=ni<CR>
map <F6> <ESC>:set mouse=v<CR>
set nocompatible                                 " 去vi的一致性
set number                                       " 显示行号
set guioptions-=r                                " 隐藏编辑器右侧滚动条
set guioptions-=L                                " 如果窗口垂直分隔，隐藏编辑器左侧滚动条
set guioptions-=b                                " 隐藏编辑器底部滚动条
set guioptions =a                                " 在可视化模式下选中文本,Vim会将所选文本放置到系统的全局寄存器中
set showtabline=0                                " 隐藏顶部标签栏
set guifont=Fira                                 " 设置字体
set showmode                                     " 在底部显示当前处于命令模式还是插入模式
set encoding=utf-8                               " 使用utf-8编码
set t_Co=256                                     " 256色域
set background=dark                              " 设置背景色
set wrap                                         " 设置折行
set autoindent                                   " 自动对齐
set smartindent                                  " 智能选择对
set fileformat=unix                              " 设置以unix的格式保存文件
set tabstop=2                                    " 设置table长度
set shiftwidth=4                                 " 设置当行之间交错时使用4个空格
set expandtab                                    " 自动将tab转换为空格
set softtabstop=2                                " tab转换为多少个空格
set textwidth=80                                 " 设置行宽，即一行显示多少个字符
set showmatch                                    " 显示匹配的括号
set scrolloff=5                                  " 距离顶部和底部5行
set ruler                                        " 在状态栏显示光标的当前位置（位于哪一行哪一列）
set laststatus=2                                 " 是否显示状态栏。0 表示不显示，1 表示只在多窗口时显示，2 表示显示。
set backspace=eol,start,indent                   " 退格键
set mouse=ni                                    " 启用鼠标
set selection=exclusive
set selectmode=mouse,key
set matchtime=2                                  " 短暂跳转到匹配括号的时间
set ignorecase                                   " 搜索时忽略大小写
set incsearch                                    " 输入搜索模式时，每输入一个字符，就自动跳到第一个匹配的结果。
set hlsearch                                     " 高亮搜索项
" set spell spelllang=en_us,cjk                    " 打开英语拼写检查
set nobackup                                     " 不创建备份文件
set noswapfile                                   " 不创建交换文件
set noerrorbells                                 " 出错时，不要发出响声
"set visualbell                                  "  出错时，发出视觉提示，通常是屏幕闪烁
"set autoread                                    "  打开文件监视。如果在编辑过程中文件发生外部改变（比如被别的编辑器编辑了），就会发出提示
set wildmenu                                     " 启用增强模式的命令行补全
set wildmode=longest:list,full                   " 命令模式下，底部操作指令按下 Tab 键自动补全。
set whichwrap+=<,>,h,l
set cursorline                                   " 突出显示当前行
set cursorcolumn                                 " 突出显示当前列
" set clipboard=unnamedplus                        "  共享剪切板
set pastetoggle=<F10>
set helplang=cn                                  " 帮助中文支持
set listchars=tab:--,trail:-                     " tab和空格转换

set completeopt=preview,menu
set completeopt=longest,menu
																								
call plug#begin('~/.vim/plugged')
Plug 'valloric/youcompleteme'
Plug 'itchyny/lightline.vim'
Plug 'Yggdroot/indentLine'
Plug 'preservim/nerdtree'
Plug 'Yggdroot/LeaderF', { 'do': './install.sh' }
Plug 'jiangmiao/auto-pairs'
Plug 'preservim/nerdcommenter'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'godlygeek/tabular'
Plug 'hdima/python-syntax'
Plug 'justinmk/vim-syntax-extra'
Plug 'octol/vim-cpp-enhanced-highlight'
Plug 'luochen1990/rainbow'
Plug 'sillybun/vim-repl'
call plug#end()
																								
																								
" godlygeek/tabular 代码对齐 :Tab/:
" python_syntax
let python_highlight_all = 1
" indentLine configure
let g:indentLine_noConcealCursor = 1
let g:indentLine_color_term = 0
let g:indentLine_char = '|'
"nerdcommenter configure
let g:NERDSpaceDelims = 1
let g:NERDCompactSexyComs = 1
let g:NERDDefaultAlign = 'left'
let g:NERDAltDelims_java = 1
let g:NERDCustomDelimiters = { 'c': { 'left': '/**','right': '*/' } }
let g:NERDCommentEmptyLines = 1
let g:NERDTrimTrailingWhitespace = 1
let g:NERDToggleCheckAllLines = 1
"YouCompleteMe Configure
let g:ycm_global_ycm_extra_conf = '~/.vim/plugged/youcompleteme/third_party/ycmd/.ycm_extra_conf.py'
let g:ycm_confirm_extra_conf = 0
let g:ycm_seed_identifiers_with_syntax = 1
let g:ycm_complete_in_comments = 1
let g:ycm_collect_identifiers_from_comments_and_strings = 0
let g:ycm_complete_in_strings = 1
let g:ycm_collect_identifiers_from_tags_files = 1
let g:ycm_collect_identifiers_from_tags_files = 1
let g:ycm_min_num_of_chars_for_completion = 2
let g:ycm_autoclose_preview_window_after_completion = 1
let g:ycm_cache_omnifunc=0

" let g:ycm_add_preview_to_completeopt = 0
" let g:ycm_show_diagnostics_ui = 0
" let g:ycm_server_log_level = 'info'
" let g:ycm_min_num_identifier_candidate_chars = 2
" let g:ycm_collect_identifiers_from_comments_and_strings = 1
" let g:ycm_complete_in_strings=1

let g:ycm_semantic_triggers =  {
      \ 'c,cpp,python,java,go,erlang,perl': ['re!\w{2}'],
      \ 'cs,lua,javascript': ['re!\w{2}'],
      \ }
autocmd InsertLeave * if pumvisible() == 0|pclose|endif
let g:ycm_seed_identifiers_with_syntax = 1
let g:ycm_use_ultisnips_completer = 1
let g:ycm_goto_buffer_command = 'horizontal-split'
nnoremap <Leader>g :YcmCompleter GoTo<CR>
" rainbow configure
let g:rainbow_active = 1 "0 if you want to enable it later via :RainbowToggle
let g:rainbow_conf = {
\	'guifgs': ['royalblue3', 'darkorange3', 'seagreen3', 'firebrick'],
\	'ctermfgs': ['lightblue', 'lightyellow', 'lightcyan', 'lightmagenta'],
\	'operators': '_,_',
\	'parentheses': ['start=/(/ end=/)/ fold', 'start=/\[/ end=/\]/ fold', 'start=/{/ end=/}/ fold'],
\	'separately': {
\		'*': {},
\		'tex': {
\			'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/'],
\		},
\		'lisp': {
\			'guifgs': ['royalblue3', 'darkorange3', 'seagreen3', 'firebrick', 'darkorchid3'],
\		},
\		'vim': {
\			'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/', 'start=/{/ end=/}/ fold', 'start=/(/ end=/)/ containedin=vimFuncBody', 'start=/\[/ end=/\]/ containedin=vimFuncBody', 'start=/{/ end=/}/ fold containedin=vimFuncBody'],
\		},
\		'html': {
\			'parentheses': ['start=/\v\<((area|base|br|col|embed|hr|img|input|keygen|link|menuitem|meta|param|source|track|wbr)[ >])@!\z([-_:a-zA-Z0-9]+)(\s+[-_:a-zA-Z0-9]+(\=("[^"]*"|'."'".'[^'."'".']*'."'".'|[^ '."'".'"><=`]*))?)*\>/ end=#</\z1># fold'],
\		},
\		'css': 0,
\	}
\}
" 支持在Visual模式下，通过C-y复制到系统剪切板
vnoremap <C-y> "+y
" 支持在normal模式下，通过C-p粘贴系统剪切板
nnoremap <C-p> "*p
" airline configure
" 设置状态栏
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = '|'
" Show just the filename
let g:airline#extensions#tabline#fnamemod = ':t'
let g:airline#extensions#tabline#formatter = 'default'
let g:airline#extensions#tabline#buffer_nr_show = 1
" 映射切换buffer的键位
nnoremap [b :bp<CR>
nnoremap ]b :bn<CR>
let g:airline_theme ='luna'  " 主题
let g:airline_powerline_fonts = 1

"vim repl
let g:repl_program = {
\   'python': 'ipython3',
\   'default': 'bash',
\   'r': 'R',
\   'lua': 'lua',
\   }
let g:repl_predefine_python = {
\   'numpy': 'import numpy as np',
\   'matplotlib': 'from matplotlib import pyplot as plt'
\   }
let g:repl_cursor_down = 1
let g:repl_python_automerge = 1
let g:repl_ipython_version = '7.13'
let g:repl_position = 3
" let g:repl_width = None                           "窗口宽度
" let g:repl_height = None                          "窗口高度
let g:sendtorepl_invoke_key = "<leader>w"          "传送代码快捷键，默认为<leader>w
let g:repl_position = 0                             "0表示出现在下方，1表示出现在上方，2在左边，3在右边
let g:repl_stayatrepl_when_open = 0         "打开REPL时是回到原文件（1）还是停留在REPL窗口中（0）
nnoremap <leader>r :REPLToggle<Cr>
autocmd Filetype python nnoremap<Leader>k <Esc>:REPLDebugStopAtCurrentLine<Cr>
autocmd Filetype python nnoremap <Leader>l <Esc>:REPLPDBN<Cr>
autocmd Filetype python nnoremap <Leader>m <Esc>:REPLPDBS<Cr>
" windows copy
map <F7> : call CopyToWindows()<CR>
map! <F7> <ESC> : call CopyToWindows()<CR>
func! CopyToWindows()
    exec "w"
    exec "!cat % |/mnt/c/Windows/System32/clip.exe"
endfunc

autocmd BufNewFile *.py exec ":call SetPythonTitle()"
func SetPythonTitle()
		call append(0,"######################################################")
    call append(1,"# File Name:    ".expand("%"))
    call append(2,"# Author:       Yuling You")
    call append(3,"# Mail:         yuling.youe@gmail.com")
    call append(4,"# Created Time: ".strftime("%Y-%m-%d",localtime()))
    call append(5,"# Version:     ")
    call append(6,"# Description: ")
    call append(7,"#")
    call append(8,"#####################################################")
    call append(9,"#! /usr/bin/env python3")
    call append(10,"#-*- coding: utf-8 -*-")
endfunc
autocmd BufNewFile * normal G

map <Leader>rr :call CompileRunGcc()<CR>
func! CompileRunGcc()
		exec "w"
		if &filetype == 'c'
				silent exec "!g++ % -o %<"
				exec "!./%<"
        silent exec "!rm -rf %<"
		elseif &filetype == 'cpp'
				silent exec "!g++ % -o %<"
				exec "!./%<"
        silent exec "!rm -rf %<"
		elseif &filetype == 'java'
				silent exec "!javac %"
				exec "!java %<"
        silent exec "!rm -rf %<.class"
		elseif &filetype == 'sh'
				:!time bash %
		elseif &filetype == 'python'
				exec "!python3 %"
        silent exec "!clear"
		elseif &filetype == 'html'
				exec "!firefox % &"
		elseif &filetype == 'go'
"        exec "!go build %<"
				exec "!time go run %"
		elseif &filetype == 'mkd'
				exec "!~/.vim/markdown.pl % > %.html &"
				exec "!firefox %.html &"
		endif
endfunc
```

### vim molokai主题下载

进入<b style="background-color:red">.vim</b>文件, 在目录下创建<b style="color:red">colors</b>文件. 克隆**molokai**文件:

<code>git clone https://github.com/tomasr/molokai.git </code>

将克隆下来的**molokai** 文件里面的<b style="color:red">molokai.vim</b>移动到<b style="color:red">colors</b>文件中.

<pre><code>cd molokai/colors
mv molokai.vim ~/.vim/colors</code></pre>

### vim 升级 8.2

1. 添加 Vim 的 PPA

```c
sudo add-apt-repository ppa:jonathonf/vim
```

2. 开始安装

```c
sudo apt-get update
sudo apt-get install -y vim-gtk3
```

3. 执行 `vim.gtk3 --version` 命令得到：

```c
VIM - Vi IMproved 8.2 (2019 Dec 12, compiled Jun 21 2020 13:13:53)
Included patches: 1-1027
...
```

   ### Cmake 升级

1. 卸载当前旧版本的cmake
   查看当前的cmake版本：cmake --version
   若版本较旧，执行：sudo apt remove cmake，卸载旧版的cmake
   若当前系统无cmake，可跳过这一步。

2. 安装依赖
   sudo apt install build-essential libssl-dev

3. 下载并编译源码
   cmake官方下载地址为：https://cmake.org/download/（我下载的是3.17.0）

4. 执行以下命令解压：
   sudo tar xf cmake-3.17.0.tar.gz
   （这里可直接解压到/usr/local里，这样后面生成的可执行文件会在/usr/local/bin里创建链接）

5. 环境检查、编译和安装

   cd进入解压出来的文件夹，执行：
   sudo ./configure
   sudo make
   sudo make install

6. 创建软链接
   sudo ln -sf /usr/local/bin/*  /usr/bin/

7. 再执行：cmake -version 
   如果出现版本号就代表安装成功。

## .bashrc 文件

```c
# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

# don't put duplicate lines or lines starting with space in the history.
# See bash(1) for more options
HISTCONTROL=ignoreboth

# append to the history file, don't overwrite it
shopt -s histappend

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
HISTSIZE=1000
HISTFILESIZE=2000

# check the window size after each command and, if necessary,
# update the values of LINES and COLUMNS.
shopt -s checkwinsize

# If set, the pattern "**" used in a pathname expansion context will
# match all files and zero or more directories and subdirectories.
#shopt -s globstar

# make less more friendly for non-text input files, see lesspipe(1)
[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

# set variable identifying the chroot you work in (used in the prompt below)
if [ -z "${debian_chroot:-}" ] && [ -r /etc/debian_chroot ]; then
    debian_chroot=$(cat /etc/debian_chroot)
fi

# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color|*-256color) color_prompt=yes;;
esac

# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes

if [ -n "$force_color_prompt" ]; then
    if [ -x /usr/bin/tput ] && tput setaf 1 >&/dev/null; then
	# We have color support; assume it's compliant with Ecma-48
	# (ISO/IEC-6429). (Lack of such support is extremely rare, and such
	# a case would tend to support setf rather than setaf.)
	color_prompt=yes
    else
	color_prompt=
    fi
fi

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
unset color_prompt force_color_prompt

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    ;;
*)
    ;;
esac

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# colored GCC warnings and errors
#export GCC_COLORS='error=01;31:warning=01;35:note=01;36:caret=01;32:locus=01:quote=01'

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

# Add an "alert" alias for long running commands.  Use like so:
#   sleep 10; alert
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'

# Alias definitions.
# You may want to put all your additions into a separate file like
# ~/.bash_aliases, instead of adding them here directly.
# See /usr/share/doc/bash-doc/examples in the bash-doc package.

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# enable programmable completion features (you don't need to enable
# this, if it's already enabled in /etc/bash.bashrc and /etc/profile
# sources /etc/bash.bashrc).
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi
#proxy set
export ClientIP=$(ip addr show eth0 | grep 'inet ' | awk '{print $2}' | cut -f 1 -d '/')
export HostIP=$(cat /etc/resolv.conf | grep 'nameserver' | awk '{print $2}')

showproxy()
{
        echo ''
        echo 'Show Proxy:'
        echo "http_proxy=$http_proxy"
        echo "https_proxy=$https_proxy"
        echo "ftp_proxy=$ftp_proxy"
        echo "ALL_PROXY=$ALL_PROXY"
        echo ''
                                
}

setproxy()
{
        export http_proxy=http://$HostIP:10809/
        export https_proxy=http://$HostIP:10809/
        export ftp_proxy=http://$HostIP:10809/
        export ALL_PROXY=socks5://$HostIP:10808/
        git config --global http.proxy $ALL_PROXY
        git config --global https.proxy $ALL_PROXY
        showproxy
        echo "curl --connect-timeout 5 google.com"
        curl --connect-timeout 5 google.com
                                
}

unsetproxy()
{
        unset https_proxy
        unset http_proxy
        unset ftp_proxy
        unset ALL_PROXY
        git config --global --unset http.proxy
        git config --global --unset https.proxy
        showproxy
        echo "curl --connect-timeout 5 163.com"
        curl --connect-timeout 5 163.com
                                
}
```