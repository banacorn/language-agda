# Syntax highlighting for Agda on Atom

This repository implements syntax highlighting for the [Agda language](http://agda.readthedocs.io) when editing in [Atom](https://atom.io/)

## Usage
This is an Atom package. To use it, you need first to [install Agda](https://agda.readthedocs.io/en/latest/getting-started/installation.html) and Atom.

From the Atom's preferences, you will be able to install this package by searching for `language-agda`. Once the package is installed, open an agda file and you're good to go.

## Color Scheme
You can work in Atom with different themes. Themes are available in Atom under Preferences. Please note that you can set a UI theme (styles outside the editor) that is different from the syntax theme(styles inside the editor).

The final color scheme that you see is defined by the syntax theme that you chose.

As an example, you can check the [syntax spec of one dark theme](https://github.com/atom/atom/blob/master/packages/one-dark-syntax/styles/syntax/_base.less). There you can see how the colors are assigned to the syntax selectors.

## Themes and syntax selectors
Selectors are patterns used to select the kind of element(s) to be styled. The semantics of the selectors are set on the specification of each theme. If two elements belong to the same syntax selector, we will not be able to distinguish them when highlighting. Examples of selectors in one dark theme:
- comments
- entities
- keywords
- constants
- variables
- ...

## Parsing and syntax nodes
We parse syntax nodes from agda files with a grammar.

Before, we were using regular expressions to parse agda files, as shown in the `grammars/agda.cson` file.

Now, we are using the `tree-sitter` parser generator tool. Therefore, the [Agda grammar for the tree-sitter](https://github.com/tree-sitter/tree-sitter-agda) repository was created.

## Assigning syntax nodes to selectors
We assign each of the syntax nodes to one of the selectors in the syntax theme, as shown in the file `grammars/tree-sitter-agda.cson`

## Customization
If you want other colors to be shown within the agda code that you edit in Atom, you must change or tweak your syntax theme in Atom preferences.

## Troubleshooting
If you miss the highlighting of an element that you need to differentiate, it could be because:
- the desired __selector does not exist__ in the theme, the solution would be to contribute to the Atom theme to include it.
- the selector exists but the __parsing does not detect the element__ as a separated node, the solution would be to contribute to the [Agda grammar for tree-sitter](https://github.com/tree-sitter/tree-sitter-agda)
- both selector and node exist but the __node is assigned to the default selector__ (no syntax highlighting), the solution would be to contribute to this repository.

If you see an element highlighted but with the same color as other kinds of elements, then many syntax nodes may be pointing to one selector.

## Issues
Troubleshooting did not help? Please [report any issue](https://github.com/banacorn/language-agda/issues) you may find when using this syntax highlighting.
