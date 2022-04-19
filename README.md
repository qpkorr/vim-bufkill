# vim-bufkill

## Note re github repo

This repo hit some issues, seemingly due to git changes that appear to have broken git subtree push. I mistakenly pushed about 4000 unrelated commits into the repo.  I've tried to fix things with help from github support, but my apologies if any forks or clones got messed up.

## Description

In Vim, trying to unload, delete or wipe a buffer without closing the window or split? You'll like this:

**With bufkill:**

![With bufkill](https://cloud.githubusercontent.com/assets/9512444/10005557/c1c41cc0-60af-11e5-85cc-39503efc7cad.gif)

**Without bufkill (standard Vim behaviour):**

![Without bufkill](https://cloud.githubusercontent.com/assets/9512444/10005696/9fb99f3c-60b0-11e5-9f97-793de9956959.gif)

The inspiration for this script came from:
 * My own frustration with vim's lack of this functionality
 * The description of the emacs kill-buffer command in tip #622 (this script basically duplicates this command I believe, not sure about the undo functionality)
 * Comments by Keith Roberts when the issue was raised in the vim@vim.org mailing list.

*Note: This is the official Git repo which replaces http://www.vim.org/scripts/script.php?script_id=1147*

## Installation

This plugin follows the standard runtime path structure, and as such it can be installed with a variety of plugin managers:

  * [Pathogen][1]
    * `git clone https://github.com/qpkorr/vim-bufkill ~/.vim/bundle/vim-bufkill`

  * [Vundle][2]:
    * `Plugin 'qpkorr/vim-bufkill'`

## Usage

### Unloading/Deleting/Wiping

All of the following keep the window/split intact:

|Action|Command|
|:-----|:------|
|Unload a file from the buffer|`:BUN`|
|Delete a file from the buffer|`:BD`|
|Wipe a file from the buffer|`:BW`|

Notice how the key mappings are the uppercase version of the `:bun` `:bd` `:bw` Vim commands? Easy!

### Moving through buffers

|Action|Command|
|:-----|:------|
|Move backwards through recently accessed buffers|`:BB`|
|Move forwards through recently accessed buffers|`:BF`|
|Move to an alternate buffer and keep the cursor in the same column|`:BA`|

### Options & Mappings

The following would need to be set in your `.vimrc`.

```viml
" Turn off default <leader>bb, <leader>bd, etc. mappings (default: 1)
let g:BufKillCreateMappings = 0

" Override default <C-^> behavior for swapping between alternate buffers (default: 0)
let g:BufKillOverrideCtrlCaret = 1

" Modify the command prefix if it conflicts with other plugins
" The below changes BD to DD, BB to DB, etc. (default: 'B')
let g:BufKillCommandPrefix = 'D'

" If the buffer you want to kill is in many windows, the following option governs what to do (default: 'confirm', options: 'confirm'/'kill'/'cancel')
let g:BufKillActionWhenBufferDisplayedInAnotherWindow = 'kill'
```

You can overide the default mappings within your `/.vimrc` file like so:

```viml
map <C-c> :BD<cr>
```

resulting in being able to delete a file from the buffer via vim-bufkill with <kbd>CTRL</kbd> + <kbd>c</kbd>

## Contributions

Contributions and pull requests are welcome.

A big thanks to Oli Morris for his excellent rewrite of this README file, and creating the animated gifs.
Likewise to Julian Torres for further improvements to the README file.

[1]: https://github.com/tpope/vim-pathogen
[2]: https://github.com/gmarik/vundle
