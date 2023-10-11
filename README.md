# jupyter-ultisnips-pymolpysnips for Vim or NeoVim

PyMOL Python snippet library to edit live Jupyter notebook cells with Vim or neovim using the UltiSnips plugin and the browser plugin [GhostText web browser extension](https://github.com/fregante/GhostText) and the [GhostText-for-Vim](https://github.com/raghur/vim-ghost) plugin for Vim or the [GhostText-for-NeoVim](https://github.com/subnut/nvim-ghost.nvim) plugin for NeoVim. 


## Installation

UltiSnips is a more recent plugin manager that depends on Python3. 
Vim has to be installed with the option of using Python3 enabled to be able to use UltiSnips. 
The UltiSnips plugin is the snippet handling engine. 
It provides a large number of advanced snippet features. 

However, it does not come with libraries of snippets. 
The snippets must be installed separately. 
The honza/vim-snippets plugin contains snippets for many languages. 
The pml.snippets file can be stored in a mysnippets subfolder of the hidden .vim directory as described below.

UltinSnips can read SnipMate snippets.
Installing and using snippets with UltiSnips
In the following setup, we use the Vundle plugin manager. The PyMOL.snippets could be stored inside the UltiSnips directory, but they would be lost if you delete the UltiSnips directory. To help make sure your snippets are not deleted if the UltiSnips directory ever gets deleted you will want to create a subdirectory called myultisnips at the top level of the .vim directory. Move the PyMOL.snippets file to this subdirectory. We will inform Vim of this location when customizing the .vimrc file for UltiSnips a little further down.


$ cd .vim
$ mkdir myultisnips
In the myultisnips directory, you can add your own snippets and add the UltiSnips snippets provided above in the ultisnippymolsnips folder.

$ cp ~/pymolsnips/ultisnippymolsnips/* .
Because UltiSnips depends on Python3, you may have to install Python3 to be able to use it. You can point UltiSnips to a particular Python3 interpreter with the following command in your .vimrc file. At the top of the file, add:


if has('python3')
endif

## Note

Some snippets depend on some pymolshortcuts.
Add the [pymolshortcuts.py](https://github.com/MooersLab/pymolshortcuts) file to your working directory.
