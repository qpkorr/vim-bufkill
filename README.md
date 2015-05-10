# vim-bufkill
Git repo for http://www.vim.org/scripts/script.php?script_id=1147

## INTRODUCTION
Basic Usage:
When you want to unload/delete/wipe a buffer, use:
  :bun/:bd/:bw to close the window as well (vim command), or
  :BUN/:BD/:BW to leave the window intact (this script).
To move backwards/forwards through recently accessed buffers, use:
  :BB/:BF
To move to the alternate buffer whilst preserving cursor column, use:
  :BA
or override Ctrl-^ via g:BufKillOverrideCtrlCaret
Mappings are also defined.

## DESCRIPTION
This is a script to
a) unload, delete or wipe a buffer without closing the window it was displayed in
b) in its place, display the buffer most recently used in the window, prior
   to the buffer being killed.  This selection is taken from the full list of
   buffers ever displayed in the particular window.
c) allow one level of undo in case you kill a buffer then change your mind
d) allow navigation through recently accessed buffers, without closing them.
e) override the standard Ctrl-^ (Ctrl-6) functionality to maintain the
   correct cursor column position. (Enable via g:BufKillOverrideCtrlCaret)

The inspiration for this script came from
a) my own frustration with vim's lack of this functionality
b) the description of the emacs kill-buffer command in tip #622
   (this script basically duplicates this command I believe,
   not sure about the undo functionality)
c) comments by Keith Roberts when the issue was raised in the
   vim@vim.org mailing list.

## INSTALL DETAILS
The usual pathogen setup - add vim-bufkill directory to $HOME/.vim/bundle
directory.

Use the provided commands/mappings to invoke the functionality
(or redefine them elsewhere to what you want), and set the
User Configurable Variables as desired.  You should be able to make
any customisations to the controls in your vimrc file, such that
updating to new versions of this script won't affect your settings.
