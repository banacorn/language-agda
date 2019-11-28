# language-agda

Syntax highlighting for [Agda](http://agda.readthedocs.io) with [tree-sitter](https://github.com/tree-sitter/tree-sitter) and  [context-free grammar](https://github.com/tree-sitter/tree-sitter-agda)

![tree-sitter](https://i.imgur.com/7Pfmqjv.png)

## Note

If you are getting errors like **Failed to load a language-agda package grammar** after upgrading Atom, please **uninstall** and then **reinstall** the package.

## Why does my Agda look so dull?

That's probably because the version of Atom or language-agda you are using is too old.
Humans were (and still are) highlighting source codes with regular expressions until very very recently.
Please consider upgrading them to the latest version.
If you are getting some scary error during the upgrade, please **uninstall** and then reinstall language-agda

## How to contribute

1. clone the repo and load it as a development package
2. open the repo in the development mode

```bash
apm develop language-agda
atom -d ~/github/language-agda
```
