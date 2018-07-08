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

## Usage

### ブラケット、リテラルの展開

以下の様に展開されます。

* `()`
    * `( ${1:#:contents} )${0}`


* `[]`
    * `[ ${1:#:number or contents} ]${0}`



* `{}`
    * `{ ${1:#:contents} }${0}`



* `<>`
    * `< ${1:#:contents} >${0}`



* `''`
    * `'${1:#:charactor}'${0}`



* `""`
    * `"${1:#:string}"${0}`



### キーワードの展開

各種キーワードは以下の様に展開されます。

* [keyword]
    * [keywoard] ${1:#:process}${0}


これら2つのスニペットを組み合わせて利用していきます。

1.  ```c
    typedef
    ```
2.  ```c
    typedef ${1:#:typename} ${2:#:new typename};${0}
    ```
3.  ```c
    typedef struct ${2:#:new typename};${0}
    ```
4.  ```c
    typedef struct ${1:#:typename} ${2:#:variable_or_process}${0} ${2:#:new typename};${0}
    ```
5.  ```c
    typedef struct Container ${2:#:variable_or_process}${0} ${2:#:new typename};${0}
    ```
6.  ```c
    typedef struct Container {} ${0} ${2:#:new typename};${0}
    ```
7.  ```c
    typedef struct _Container { ${1:#:contents} }${0} ${0} ${2:#:new typename};${0}
    ```
8.  ```c
    typedef struct _Container { 
      int x;
      int y;
    }${0} ${0} ${2:#:new typename};${0}
    ```
9.  ```c
    typedef struct _Container { 
      int x;
      int y;
    } ${0} ${2:#:new typename};${0}
    ```
10. ```c
    typedef struct _Container { 
      int x;
      int y;
    } ${2:#:new typename};${0}
    ```
11. ```c
    typedef struct _Container { 
      int x;
      int y;
    } Container;${0}
    ```
12. ```c
    typedef struct _Container { 
      int x;
      int y;
    } Container;
    ```

各種アンカー`${1...}` 、`${2...}` 、 `...` に飛ぶ方法は各種キーマップ設定に従います。

ブラケットの存在が明らかな場合は、最初からブラケットが入力されます。

1.  ```c
    if
    ```
2.  ```c
    if( ${1:#:condition} ) ${2:#:process}
    ```

上記 `if` では `{}` が存在しないパターンもあるので、 `{}` は含めてません。

その他キーワード、展開規則は各スニペットファイルをご覧ください。

