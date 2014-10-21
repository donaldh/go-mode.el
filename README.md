This is go-mode, the Emacs mode for editing Go code.

It is a complete rewrite of the go-mode that shipped with Go 1.0.3 and
before, and was part of Go 1.1 until Go 1.3. Beginning with Go 1.4,
editor integration will not be part of the Go distribution anymore,
making this repository the canonical place for go-mode.


# Features

In addition to normal features, such as fontification and indentation,
and close integration with familiar Emacs functionality (for example
syntax-based navigation like `beginning-of-defun`), go-mode comes with
the following extra features to provide an improved experience:

- Integration with `gofmt` by providing a command of the same name,
  and `gofmt-before-save`, which can be used in a hook to format Go
  buffers before saving them.
  - Setting the `gofmt-command` variable also allows using
    `goimports`.
- Integration with `godoc` via the functions `godoc` and
  `godoc-at-point`.
- Integration with the Playground
  - `go-play-buffer` and `go-play-region` to send code to the
    Playground
  - `go-download-play` to download a Playground entry into a new
    buffer
- Managing imports
  - A function for jumping to the file's imports (`go-goto-imports`)
  - A function for adding imports, including tab completion
    (`go-import-add`, bound to `C-c C-a`)
  - A function for removing or commenting unused imports
    (`go-remove-unused-imports`)
- Integration with godef
  - `godef-describe` (`C-c C-d`) to describe expressions
  - `godef-jump` (`C-c C-j`) and `godef-jump-other-window` (`C-x 4 C-c
    C-j`) to jump to declarations
  - This requires you to install godef via `go get
  code.google.com/p/rog-go/exp/cmd/godef`.
- Basic support for imenu (functions and variables)
- Built-in support for displaying code coverage as calculated by `go
  test` (`go-coverage`)

# Installation

Put go-mode.el into a directory of your choice and add an instruction in the 
Emacs init file to load it 

     (add-to-list 'load-path "/place/where/you/put/it/")

From within Emacs, run M-x update-file-autoloads, point it at the
go-mode.el file and tell it to generate a go-mode-load.el file.

To the Emacs init file add

     (require 'go-mode-load)

Restart Emacs.

# Other extensions

There are several third party extensions that can enhance the Go
experience in Emacs.

## Syntax/error checking

There are two ways of using flymake with Go:

1. [goflymake](https://github.com/dougm/goflymake), which internally
uses `go build` to capture all errors that a regular compilation would
also produce
2. [flymake-go](http://marmalade-repo.org/packages/flymake-go) for a
more lightweight solution that only uses `gofmt` and as such is only
able to catch syntax errors. Unlike goflymake, however, it does not
require an additional executable.

Additionally, there is
[flycheck](https://github.com/flycheck/flycheck), a modern replacement
for flymake, which comes with built-in support for Go. In addition to
using `go build` or `gofmt`, it also has support for `go vet`,
`golint` and `errcheck`.

## Auto completion

For auto completion, take a look at
[gocode](https://github.com/nsf/gocode).

## eldoc

https://github.com/syohex/emacs-go-eldoc provides eldoc functionality
for go-mode.

## Snippets

I maintain a set of YASnippet snippets for go-mode at
https://github.com/dominikh/yasnippet-go

## Integration with errcheck

https://github.com/dominikh/go-errcheck.el provides integration with
[errcheck](https://github.com/kisielk/errcheck).

# Donations

I am accepting donations for go-mode, but it has to be said that even
though I am its primary developer, there are several third party
contributions with varying complexity. Donations would be towards me,
Dominik Honnef, and not go-mode as a whole.

<a href='http://www.pledgie.com/campaigns/21377'><img alt='Click here to lend your support to: go-mode.el and make a donation at www.pledgie.com !' src='http://www.pledgie.com/campaigns/21377.png?skin_name=chrome' border='0' /></a>
