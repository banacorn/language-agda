# language-agda

Syntax highlighting for [Agda](http://agda.readthedocs.io)

I know it's lacking, so read on!

## Revamping with `tree-sitter`

It's not until the mid 2010s when the human realized that, syntax highlighting
should be done in **context-free grammar** rather than **regular expressions**.

I'm currently working on [describing the syntax in context-free grammar](https://github.com/banacorn/tree-sitter-agda) with [tree-sitter](https://github.com/tree-sitter/tree-sitter).
Sit tight!

## How to contribute

1. clone the repo and load it as a development package
2. open the repo in the development mode

```bash
apm develop language-agda
atom -d ~/github/language-agda
```
