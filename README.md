# README                                                                                                                    
### This is aria2, a major mode for controlling [aria2c](http://aria2.sourceforge.net/) downloader ###
Currrently supported download types are: bittorrent, magnet, meta4, ftp, http, https files (basically what aria2c supports).
There is no support for changing global or per-download options, but this is planned.

### How does it look like? ###
![aria2-mode.png](https://i.imgur.com/BH67PEy.png)

### How do I get set up? ###

#### El-get ####

```emacs-lisp
  (push
   `(:name aria2
           :type git
           :url "https://github.com/ukaszg/aria2")
   el-get-sources)

  (el-get 'sync '(aria2))
```

#### Packages ####
Avaliable at Melpa [![MELPA](http://melpa.org/packages/aria2-badge.svg)](http://melpa.org/#/aria2)


### Evil bindings ###
Install [evil-collection](https://github.com/emacs-evil/evil-collection) to
enable evil bindings in tabulated-list-mode. On top of that here is a snippet
with bindings specific to aria2:

```emacs-lisp
(evil-collection-inhibit-insert-state 'aria2-mode-map)
(evil-set-initial-state 'aria2-mode-map 'normal)
(evil-collection-define-key 'normal 'aria2-mode-map
  "Q" 'aria2-terminate
  "p" 'aria2-toggle-pause
  "a" 'aria2-add
  "D" 'aria2-remove-download
  "C" 'aria2-clean-removed-download
  (kbd "M-k") 'aria2-move-up-in-list
  (kbd "M-j") 'aria2-move-down-in-list)
```
