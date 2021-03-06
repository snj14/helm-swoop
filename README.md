List the multi lines to another buffer, which is able to squeeze by any words you input. At the same time, the original buffer's cursor is jumping line to line according to moving up and down the line list.

![helm-swoop](https://github.com/ShingoFukuyama/helm-swoop/raw/master/image/helm-swoop.gif)

### Feature

* Squeeze all lines in buffer with your input
* Highlight multiple matched pattern
* Jumping line to line according to list buffer's move
* Cache result until modifies the buffer
* Go back to the last line
* Multi separated line culling
* Culling lines are editable

### Usage

Now helm-swoop has several ways.

* `M-x helm-swoop` when region active
* `M-x helm-swoop` when the cursor is at any symbol
* `M-x helm-swoop` when the cursor is not at any symbol
* `M-3 M-x helm-swoop` or `C-u 5 M-x helm-swoop` multi separated line culling
* During isearch `M-i` to hand the word over to helm-swoop
* While doing `helm-swoop` press [C-c C-e] to edit mode, apply changes to original buffer by [C-x C-s]

It's able to use words within a region or a word at symbol as search query when it called. Also use a keybind you set just type like M-i instead of `M-x helm-swoop`. 

Multiline behavior 
`M-4 M-x helm-swoop` or `C-u 4 M-x helm-swoop`

![helm-swoop2](https://github.com/ShingoFukuyama/helm-swoop/raw/master/image/helm-swoop2.gif)

### Config

```elisp
;; helm from https://github.com/emacs-helm/helm
(require 'helm-config)
(helm-mode 1)

;; Locate the helm-swwop folder to your path
(add-to-list 'load-path "~/.emacs.d/elisp/helm-swoop")
(require 'helm-swoop)

;; Change the keybinds to whatever you like :)
(global-set-key (kbd "M-i") 'helm-swoop)
(global-set-key (kbd "M-I") 'helm-swoop-back-to-last-point)

;; When doing isearch, hand the word over to helm-swoop
(define-key isearch-mode-map (kbd "M-i") 'helm-swoop-from-isearch)
```

### Require

[helm.el](https://github.com/emacs-helm/helm)

##### Optional Require For Japanese input system.

* [migemo.el](https://github.com/emacs-jp/migemo)
* [helm-migemo.el](https://github.com/emacs-helm/helm-migemo)

