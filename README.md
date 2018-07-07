# neosnippet-Cpp
Neosnippet for C/C++

## installation with dein toml

example

```toml
# neosnippet-cpp----------------
[[plugins]]
repo = 'leico/neosnippet-cpp'
on_ft   = ['c', 'cpp']
depends = ['neosnippet.vim']
hook_source = '''
let g:neosnippet#snippets_directory = '~/.config/nvim/dein/repos/github.com/leico/neosnippet-cpp/snippets'
let g:neosnippet#disable_runtime_snippets = { 'c' : 1, 'cpp' : 1 }
'''
```

in vim

```vim
:call dein#install()
```
