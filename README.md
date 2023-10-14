# jupyter-ultisnips-pymolpysnips for Vim or NeoVim

PyMOL Python snippet library to edit live Jupyter notebook cells with Vim or neovim using the UltiSnips plugin and the browser plugin [GhostText web browser extension](https://github.com/fregante/GhostText) and the [GhostText-for-Vim](https://github.com/raghur/vim-ghost) plugin for Vim or the [GhostText-for-NeoVim](https://github.com/subnut/nvim-ghost.nvim) plugin for NeoVim. 


## Installation

UltiSnips is a more recent plugin manager that depends on Python3. 
Vim has to be installed with the option of using Python3 enabled to be able to use UltiSnips. 
The UltiSnips plugin is the snippet handling engine. 
It provides a large number of advanced snippet features. 

However, it does not come with libraries of snippets. 
The snippets must be installed separately. 
The `honza/vim-snippets` plugin contains snippets for many languages. 
The `python_pymol.snippets` file can be stored in a mysnippets subfolder of the hidden `.vim` directory as described below.

UltinSnips can read SnipMate snippets.
Installing and using snippets with UltiSnips
In the following setup, we use the Vundle plugin manager. 
The PyMOL.snippets could be stored inside the UltiSnips directory, but they would be lost if you delete the UltiSnips directory. 
To help make sure your snippets are not deleted if the UltiSnips directory ever gets deleted you will want to create a subdirectory called myultisnips at the top level of the `.vim` directory. 
Move the `python_pymol.snippets` file to this subdirectory. 
We will inform Vim of this location when customizing the `.vimrc` file for UltiSnips a little further down.

```bash
cd .vim
mkdir myultisnips
```

In the myultisnips directory, you can add your own snippets and add the UltiSnips snippets provided above in the `ultisnippymolsnips` folder.

```bash
$ cp ~/pymolsnips/ultisnippymolsnips/* .
```

Because UltiSnips depends on Python3, you may have to install Python3 to be able to use it. 
You can point UltiSnips to a particular Python3 interpreter with the following command in your `.vimrc` file. 
At the top of the file, add:

```bash
if has('python3')
endif
```

In the Vundle plugin section of the `.vimrc` file, add the following lines:

```bash
" Ultisnips requires Vim installed with python.
Plugin 'SirVer/ultisnips'
```

Below the plugin section, add the following:

```bash
" Turn on filetype detection for plugins
filetype plugin on

let g:python3_host_prog = expand('/opt/local/bin/python3.7')

" UltiSnips related commands
let g:UltiSnipsExpandTrigger = ''
let g:UltiSnipsJumpForwardTrigger = ''
let g:UltiSnipsJumpBackwardTrigger = ''
let g:UltiSnipsSnippetDirectories=['/Users/blaine/.vim/my-snippets/Ultisnips','UltiSnips']
```

## Note

Some snippets depend on some `pymolshortcuts.py`.
Add the [pymolshortcuts.py](https://github.com/MooersLab/pymolshortcuts) file to your working directory.

## Related repos

- [jupyterlabpymolpysnips](https://github.com/MooersLab/jupyterlabpymolpysnips) PyMOL Python snippets for use in JupyterLab with the jupyterlab-snippets extension.
- [jupyternbclassicpymolpysnipsplus](https://github.com/MooersLab/jupyternbclassicpymolpysnipsplus)
- [taggedpymolpysnips](https://github.com/MooersLab/taggedpymolpysnips) 
- [taggedpymolpysnipspymolpysnipsplus](https://github.com/MooersLab/taggedpymolpysnipspymolpysnipsplus)
- [jupyter-vsc-pymolpysnips](https://github.com/MooersLab/jupytervsc-pymolpysnips)
- [jupyter-st3-pymolpysnips](https://github.com/MooersLab/jupyter-st3-pymolpysnips)
- [jupyter-emacs-pymolpysnips](https://github.com/MooersLab/jupyter-emacs-pymolpysnips)
- [jupyter-ultisnips-pymolpysnips](https://github.com/MooersLab/jupyter-ultisnips-pymolpysnips)
- [jupyter-snipmate-pymolpysnips](https://github.com/MooersLab/jupyter-snipmate-pymolpysnips)
- [jupyter-neosnippets-pymolpysnips](https://github.com/MooersLab/jupyter-neosnippets-pymolpysnips)
- [jupyter-atom-pymolpysnips](https://github.com/MooersLab/jupyter-atom-pymolpysnips)

