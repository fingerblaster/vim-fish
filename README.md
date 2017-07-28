vim-fish
========

This **Vim Plugin** enhances the experience of editing [Fish Shell][] scripts.

[fish]: https://github.com/fish-shell/fish-shell

Notice
------
[Dags plugin][] didn't work for me as intended, so I forked it, applied 
patches and added some customization. 

[Dags plugin]: https://github.com/dag/vim-fish

Features
--------

* Syntax highlighting and filetype detection.
* Automatic indentation of control structures based on keywords.
* Automatic folds for blocks before the `end` keyword.
* Code formatting with `fish_indent` using the `gq` operator.
* Support for the `gf` command.
* Searching for definitions including sourced files using commands like `[i`.
* Keyword lookup of man pages including fish built-ins: `K` command.
* Completions from fish using the `^X^O` (or another completion) command.
* Syntax checking with _quickfix_ using the `:make` command.
* Improved `funced` experience using commands like `S`.
* Mimics `funced` when manually creating new functions.
* Automatic formatting of comments.

Install
-------
Edit your `~/.vimrc` file adding the following to the 

vimplug:
`Plug 'fingerblaster/vim-fish'`

vundle:
`Plugin 'fingerblaster/vim-fish'`

patogen or similar:
`Bundle 'fingerblaster/vim-fish'`

If you don't like those plugin handlers. Download and unpack the `zip` file
inside your `~/.vim/` directory. (Not recommended for inexperienced people)

Setup
-----

Enable syntax and filetype functionality, normally in your `~/.vimrc`:
```vim
syntax enable
filetype plugin indent on
```
If you are already using [VimPLug][] this step is automatically done.

[VimPlug]: https://github.com/junegunn/vim-plug

Make sure you have a [POSIX][] compatible shell; many Vim plugins rely on it. 
Although I myself don't use one and `/bin/fish` is my daily driver.

[POSIX]: https://en.wikipedia.org/wiki/POSIX

```vim
if &shell =~# 'fish$'
    set shell=/bin/sh
endif
```
Next, set some options for the `fish` filetype.  You can do this either by
prefixing each line with `autocmd FileType fish`, or by putting them in your
own `~/.vim/ftplugin/fish.vim` file:

```vim
" Set up :make to use fish for syntax checking.
compiler fish

" Set this to have long lines wrap inside comments.
setlocal textwidth=79

" Enable folding of block structures in fish.
setlocal foldmethod=expr
```

To might also want to tweak settings like `foldlevelstart` and `foldminlines`, 
which you could do either globally or locally as described above.

Goodies
-------

* Code snippets for [SnipMate][]
* Code snippets for [UltiSnips][]
* A syntax checker for [Syntastic][]
* Insertion rules for [endwise][]
* Configuration for [commentary][]
* Patterns for [matchit][]

You don't have to install any of those to use this plugin

[SnipMate]: https://github.com/garbas/vim-snipmate
[UltiSnips]: https://github.com/SirVer/ultisnips
[Syntastic]: https://github.com/scrooloose/syntastic
[endwise]: https://github.com/tpope/vim-endwise
[commentary]: https://github.com/tpope/vim-commentary
[matchit]: http://www.vim.org/scripts/script.php?script_id=39

