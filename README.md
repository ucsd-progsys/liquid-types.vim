# liquid-types.vim

Vim support for Liquid Typing

+ [LiquidHaskell](https://github.com/ucsd-progsys/liquidhaskell)

## Install

**Step 1.** Add the following to your `.vimrc`

~~~~~
Bundle 'scrooloose/syntastic'
Bundle 'panagosg7/vim-annotations'
let g:vim_annotations_offset = '/.liquid/'
~~~~~

**Step 2.** Copy the following files

~~~~~
cp syntax/haskell.vim ~/.vimrc/syntax/haskell.vim
cp syntax/liquid.vim  ~/.vimrc/bundle/syntastic/syntax_checkers/haskell/liquid.vim
~~~~~

## Run

+ `:SyntasticCheck liquid` runs *liquidhaskell* on the current buffer.

## View

1. **Warnings** will be displayed in the usual error buffer.

2. **Inferred Types** will be displayed when `<F1>` is pressed over an identifier.


## Configure 

You can configure the checker in various ways in your `.vimrc`.

+ To run after **each save**, for *all* Haskell files, add:

~~~~~
let g:syntastic_mode_map = { 'mode': 'active' }
let g:syntastic_haskell_checkers = ['hdevtools', 'hlint', 'liquid']
~~~~~

+ To pass extra options to liquidhaskell add: 

~~~~~
let g:syntastic_haskell_liquid_args = "--diff"
~~~~~

