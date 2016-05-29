# Prerequisites
* Pathogen, the plugin manager
* [Powerline patched fonts](https://github.com/powerline/fonts) and set one up in your terminal

# Colors
* [solarized](https://github.com/altercation/vim-colors-solarized)

# Plugins
* [airline](https://github.com/vim-airline/vim-airline)

# .vim/vimrc
```vimml
syntax enable
set background=dark
let g:solarized_term = 1
colorscheme solarized

set relativenumber
set number

let g:airline#extensions#tabline#enabled = 1
let g:airline_powerline_fonts = 1

set laststatus=2 " Always display the statusline in all windows
set showtabline=2 " Always display the tabline, even if there is only one tab
set noshowmode " Hide the default mode text (e.g. -- INSERT -- below the statusline)

" Auto add empty line
function! AddLastLine()
    if getline('$') !~ "^$"
        call append(line('$'), '')
    endif
endfunction

autocmd BufWritePre * call AddLastLine()

execute pathogen#infect()
filetyp plugin indent on

noremap  <Up> ""
noremap! <Up> <Esc>
noremap  <Down> ""
noremap! <Down> <Esc>
noremap  <Left> ""
noremap! <Left> <Esc>
noremap  <Right> ""
noremap! <Right> <Esc>
```
