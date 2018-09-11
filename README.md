# language-agda

Syntax highlighting for [Agda](http://agda.readthedocs.io)


## Enable `tree-sitter`

The original grammar for Agda is somewhat lacking because it's written in **regular expressions**. However, with [tree-sitter](https://github.com/tree-sitter/tree-sitter), we can now [describe
the grammar](https://github.com/tree-sitter/tree-sitter-agda) with **context-free grammar**, which significantly improves the quality of syntax-highlighting and code-folding.

![tree-sitter](https://i.imgur.com/7Pfmqjv.png)

To enable `tree-sitter`, which is still experimental for the time being, go to `Settings > Core`, and enable the checkbox saying *Use Tree Sitter Parsers* at the bottom of the page.

*Note: this whole tree-sitter thing is still experimental, but, how bad can it be? 😉*

## Problems on Windows

If you are getting problems saying something like `prebuild-install WARN install No prebuilt binaries found` on Windows, running this (as Administrator) might will help (thank @MatthijsBlom and @rjstone):

```
npm install --global --production windows-build-tools
```

## How to contribute

1. clone the repo and load it as a development package
2. open the repo in the development mode

```bash
apm develop language-agda
atom -d ~/github/language-agda
```
