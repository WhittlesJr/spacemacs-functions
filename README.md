## spacemacs-functions

This is a dumb little piece of elisp that can configurably import only the utility functions provided for us by our dear friends in the Spacemacs community. There are a lot of excellent little helper functions in there for various things, and instead of re-implementing or copying them I decided it would be nice to stay in sync somehow.

### Installation

Arch Linux (AUR): https://aur.archlinux.org/packages/emacs-spacemacs-funcs/
  * You could do `yoaurt -S emacs-spacemacs-funcs` or do it manually (which should be no sweat for an Archie)


NixOS (nixpkgs):
  * Coming soon!


### Configuration

Here's my configuration, using use-package.

```
(use-package spacemacs-funcs
  :config
  (setq dotspacemacs-persistent-server nil)
  (setq spacemacs-funcs-enabled-layers '("spacemacs-base"))
  (spacemacs-funcs-load-layers))
```

You can add to the `spacemacs-funcs-enabled-layers` list whatever spacemacs layers you want functions from.


#### Gotchas

Depending on the layers you enable, you may have to fake out some variables. Unfortunately, the structure of these utility function files isn't always self-contained or "pure," and may references to global variables. For example, in the code above, I had to set `dotspacemacs-persistent-server` to `nil`.
