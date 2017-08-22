## spacemacs-functions

This is a dumb little piece of elisp that can configurably import only the utility functions provided for us by our dear friends in the Spacemacs community. There are a lot of excellent little helper functions in there for various things, and instead of re-implementing or copying them I decided it would be nice to stay in sync somehow.


### Installation

Arch Linux (AUR): https://aur.archlinux.org/packages/emacs-spacemacs-funcs/
  * You could do `yoaurt -S emacs-spacemacs-funcs` or do it manually (which should be no sweat for an Archie)


NixOS (nixpkgs):
  * Coming soon!


### Configuration

Here's my configuration, using use-package:

```
(use-package spacemacs-funcs
  :config
  (setq dotspacemacs-persistent-server nil)
  (setq spacemacs-funcs-enabled-layers '("spacemacs-base"))
  (spacemacs-funcs-load-layers))
```

You can add to the `spacemacs-funcs-enabled-layers` list whatever spacemacs layers from which you've found useful functions.


#### Gotchas

Depending on the layers you enable, you may have to fake out some variables. Unfortunately, the structure of these utility function files isn't always self-contained or "pure," and may contain references to global variables. For example, in the code above, I had to set `dotspacemacs-persistent-server` to `nil`.

I haven't tried any of the others, because I haven't found a need for them just yet. If you start using this and discover some more concrete examples of these gotchas, by all means edit this README and create a pull request with the details.


### Useful functions

These are the functions I've discovered and found useful personally. YMMV.

#### Buffer text
spacemacs/safe-erase-buffer
spacemacs/safe-revert-buffer
spacemacs/switch-to-scratch-buffer
spacemacs/copy-whole-buffer-to-clipboard

#### File management
spacemacs/rename-current-buffer-file
spacemacs/sudo-edit
spacemacs/show-and-copy-buffer-filename

#### Window navigation
spacemacs/switch-to-minibuffer-window
spacemacs/split-window-vertically-and-switch
spacemacs/split-window-horizontally-and-switch

#### Description
spacemacs/describe-last-keys
spacemacs/describe-system-info

#### Text alignment
spacemacs/align-repeat-ampersand
spacemacs/align-repeat-left-paren
spacemacs/align-repeat-right-paren
spacemacs/align-repeat-comma
spacemacs/align-repeat-decimal
spacemacs/align-repeat-colon
spacemacs/align-repeat-semicolon
spacemacs/align-repeat-equal
spacemacs/align-repeat-backslash
spacemacs/align-repeat-math-oper
spacemacs/align-repeat
spacemacs/align-repeat-bar

#### Text sorting and processing
spacemacs/sort-lines-by-column
spacemacs/sort-lines-by-column-reverse
spacemacs/duplicate-line-or-region
spacemacs/sort-lines
spacemacs/sort-lines-reverse
spacemacs/uniquify-lines
spacemacs/count-words-analysis
