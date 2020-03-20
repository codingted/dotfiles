"配置文件.vimrc更改后自动重新载入使设置生效
autocmd! bufwritepost .vimrc source ~/.vimrc

" vundle 管理插件###############START
set nocompatible              " 去除VI一致性,必须
filetype off                  " 必须

" 设置包括vundle和初始化相关的runtime path
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" 另一种选择, 指定一个vundle安装插件的路径
"call vundle#begin('~/some/path/here')

" 让vundle管理插件版本,必须
Plugin 'VundleVim/Vundle.vim'

Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'scrooloose/nerdtree'
Plugin 'tpope/vim-fugitive'
Plugin 'vim-airline/vim-airline'
Plugin 'edkolev/tmuxline.vim'
Plugin 'tpope/vim-surround'
" Plugin 'Valloric/YouCompleteMe'
" Plugin 'pangloss/vim-javascript'
" Plugin 'othree/javascript-libraries-syntax.vim'
Plugin 'posva/vim-vue'
Plugin 'jistr/vim-nerdtree-tabs'
" python ide plugin
Plugin 'tmhedberg/SimpylFold'
Plugin 'vim-scripts/indentpython.vim'
Plugin 'vim-syntastic/syntastic'
" markdown 
Plugin 'godlygeek/tabular'
Plugin 'plasticboy/vim-markdown'
call vundle#end()            " 必须
filetype plugin indent on    " 必须 加载vim自带和插件相应的语法和文件类型相关脚本
" vundle 管理插件#################END
" YCM 配置python语法
let g:ycm_python_binary_path = '/usr/bin/python3'
" python ide config ######START
" Enable folding
set foldmethod=indent
set foldlevel=99

nnoremap <space> za
let g:SimpylFold_docstring_preview=1
" python ide config ######END

" tmuxline
" let g:tmuxline_theme = 'zenburn'
let g:tmuxline_theme = 'airline_visual'
let g:tmuxline_powerline_separators = 0
" separator
let g:tmuxline_separators = {
    \ 'left' : '',
    \ 'left_alt': '>',
    \ 'right' : '',
    \ 'right_alt' : '<',
    \ 'space' : ' '}
" tmux status line
let g:tmuxline_preset = {
      \'a'    : '#S',
      \'c'    : ['#(whoami)', '#(uptime | cut -d " " -f 1,2,3)'],
      \'win'  : ['#I', '#W'],
      \'cwin' : ['#I', '#W', '#F'],
      \'y'    : ['%R', '%a', '%d','%m','%Y'],
      \'z'    : '#H'}
" NERDTree config
"autocmd vimenter * NERDTree
map <F2> :NERDTreeToggle<CR>
map <Leader>n :NERDTreeTabToggle<CR>
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTreeType") &&b:NERDTreeType == "primary") | q | endif
" ctrlp
:helptags ~/.vim/bundle/ctrlp.vim/doc
" let g:ctrlp_map = ',,'
" let g:ctrlp_cmd = 'CtrlP'

" Allow saving of files as sudo when I forgot to start vim using sudo.
cmap w!! w !sudo tee > /dev/null %
" 显示行号
set number
" 显示相对行号
set relativenumber
" 显示标尺
set ruler
" 历史纪录
set history=1000
" 输入的命令显示出来，看的清楚些
set showcmd
" 状态行显示的内容
"set statusline=%F%m%r%h%w\ [FORMAT=%{&ff}]\ [TYPE=%Y]\ [POS=%l,%v][%p%%]\ %{strftime(\"%d/%m/%y\ -\ %H:%M\")}
" 启动显示状态行1，总是显示状态行2
set laststatus=2
" 语法高亮显示
let java_highlight_functions = 1
let python_highlight_all = 1
syntax on

set fileencodings=utf-8,gb2312,gbk,cp936,latin-1
set fileencoding=utf-8
set termencoding=utf-8
set fileformat=unix
set encoding=utf-8
" 配色方案
colorscheme slate
" 指定配色方案是256色
set t_Co=256

" 设置自动补全方案
" set wildmenu
" set wildmode=full
set wildmode=longest,list

" 解决backspace不能使用的问题
set backspace=indent,eol,start
set backspace=2

" 启用自动对齐功能，把上一行的对齐格式应用到下一行
set autoindent

" 依据上面的格式，智能的选择对齐方式，对于类似C语言编写很有用处
set smartindent

" vim禁用自动备份
set nobackup
set nowritebackup
set noswapfile

" 用空格代替tab
set expandtab

" 设置显示制表符的空格字符个数,改进tab缩进值，默认为8，现改为4
set tabstop=4

" 统一缩进为4，方便在开启了et后使用退格(backspace)键，每次退格将删除X个空格
set softtabstop=4

" 设定自动缩进为4个字符，程序中自动缩进所使用的空白长度
set shiftwidth=4

" 设置帮助文件为中文(需要安装vimcdoc文档)
set helplang=cn

" 显示匹配的括号
set showmatch

" 文件缩进及tab个数
au FileType python
    \ set tabstop=4
    \  softtabstop=4
    \  shiftwidth=4
    \  textwidth=79
    \  expandtab
    \  autoindent
    \  fileformat=unix
" au FileType html,python,vim,javascript,shell setl shiftwidth=2
" au FileType html,python,vim,javascript,shell setl tabstop=2
" au FileType java,php setl shiftwidth=4
" au FileType java,php setl tabstop=4
" vim-vue
autocmd FileType vue syntax sync fromstart
autocmd BufRead,BufNewFile *.vue setlocal filetype=vue.html.javascript.css

" 高亮搜索的字符串
set hlsearch

" 检测文件的类型
"filetype on
"filetype plugin on
"filetype indent on

" C风格缩进
set cindent
set completeopt=longest,menu

" 功能设置

" 去掉输入错误提示声音
set noeb
" 自动保存
set autowrite
" 突出显示当前行 
set cursorline
" 突出显示当前列
" set cursorcolumn
"设置光标样式为竖线vertical bar
" Change cursor shape between insert and normal mode in iTerm2.app
"if $TERM_PROGRAM =~ "iTerm"
"let &t_SI = "\<Esc>]50;CursorShape=1\x7" " Vertical bar in insert mode
"let &t_EI = "\<Esc>]50;CursorShape=0\x7" " Block in normal mode
"endif
" 共享剪贴板
set clipboard+=unnamed
"设置快捷键前最，即<Leader>
" let mapleader=";"
" 快速文件缓存
nnoremap <silent> [b :bprevious<CR>
nnoremap <silent> ]b :bnext<CR>
nnoremap <silent> [B :bfirst<CR>
nnoremap <silent> ]B :blast<CR>
"设置快捷键将选中文本块复制到系统剪贴板
map <Leader>y "+y
"设置快捷键将系统剪贴板内容粘帖到vim
map <Leader>p "+p
" json数据格式化
noremap <Leader>j :%!python -m json.tool
" 插入markdown 代码块
noremap <Leader>mc i```sh<Esc>o<Esc>i```<Esc>
" 映射历史命令
"cnoremap <C-p> <Up>
"cnoremap <C-n> <Down>

" 文件被改动时自动载入
set autoread
" 顶部底部保持3行距离
set scrolloff=3
" 光标形状
if has("autocmd")
  au VimEnter,InsertLeave * silent execute '!echo -ne "\e[2 q"' | redraw!
  au InsertEnter,InsertChange *
    \ if v:insertmode == 'i' | 
    \   silent execute '!echo -ne "\e[6 q"' | redraw! |
    \ elseif v:insertmode == 'r' |
    \   silent execute '!echo -ne "\e[4 q"' | redraw! |
    \ endif
  au VimLeave * silent execute '!echo -ne "\e[ q"' | redraw!
endif
