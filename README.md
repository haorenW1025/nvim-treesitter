[![Gitter](https://badges.gitter.im/nvim-treesitter/community.svg)](https://gitter.im/nvim-treesitter/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
# nvim-treesitter
Treesitter configurations and abstraction layer for Neovim.

# Quickstart

## Requirements
  - Neovim [nightly](https://github.com/neovim/neovim#install-from-source)
  - `git` in your path.
  - A C compiler in your path.

## Installation

You can install `nvim-treesitter` with your favorite package manager, or using the default `pack` feature of neovim !

### Using a package manager

Simply add these lines to your `init.vim` :
```vim
Plug 'nvim-treesitter/nvim-treesitter'
```

### Using neovim `pack` feature

We highly recommend reading `:h packages` to learn more about this feature, but you can still follow these steps:
```sh
$ mkdir -p ~/.local/share/nvim/site/pack/nvim-treesitter/start
$ cd ~/.local/share/nvim/site/pack/nvim-treesitter/start
$ git clone https://github.com/nvim-treesitter/nvim-treesitter.git
```

## Adding parsers

Treesitter is using a different _parser_ for every language. It can be quite a pain to install, but fortunately `nvim-treesitter` 
provides two command to tackle this issue:
  - `TSInstall` to install a given parser.
  - `TSInstallInfo` to know which parser is installed.

Let's say you need parsers for `lua`, `c`, and `python`, this is how you do with these commands:
```vim
:TSInstall c
Downloading...
Compiling...
Treesitter parser for c has been installed

:TSInstall lua
Downloading...
Compiling...
Treesitter parser for lua has been installed

:TSInstall python
Downloading...
Compiling...
Treesitter parser for python has been installed
```

Cool, lets see which parsers are installed:
```vim
:TSInstallInfo
csharp     [✗] not installed
html       [✗] not installed
typescript [✗] not installed
c          [✓] installed
swift      [✗] not installed
java       [✗] not installed
python     [✓] installed
cpp        [✗] not installed
lua        [✓] installed
ruby       [✗] not installed
ocaml      [✗] not installed
go         [✗] not installed
rust       [✗] not installed
json       [✗] not installed
javascript [✗] not installed
css        [✗] not installed
julia      [✗] not installed
php        [✗] not installed
bash       [✗] not installed
tsx        [✗] not installed
```

And now you should be able to use every functionnality `nvim-treesitter` provides !

## Features and Roadmap

The goal of `nvim-treesitter` is both to provide a simple and easy way to use the interface for treesitter in neovim,
but also to add some functionnalities to it:
Some of these features are :
  - [ ] Incremental selection
  - [ ] Syntax based code folding
  - [ ] Consistent syntax highlighting

You can find the roadmap [here](https://github.com/nvim-treesitter/nvim-treesitter/projects/1).
The roadmap and all features of this plugin are open to change, and any suggestion will be highly apreciated !

## Troubleshooting
Before doing anything run `:checkhealth nvim_treesitter`. This will help you find where the bug might come from.

### Feature `X` does not work for language `Y`...
First, check the `## Y parser healthcheck` section of `:checkhealth` if you have any warning.
If you do, it's highly possible that this is the cause of the problem.
If everything is okay, then it might be an actual error.

In both cases, feel free to open an issue here.
