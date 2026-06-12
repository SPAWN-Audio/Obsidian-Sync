---
Date: 2026-03-14
Author: Cody Cork
tags:
  - Resource/Apple/macOS/Apps/Utility
---
# Resources

## Doom Emacs

```embed
title: "GitHub - doomemacs/doomemacs: An Emacs framework for the stubborn martian hacker"
image: "https://repository-images.githubusercontent.com/21763822/47152a00-a255-11e9-9ca0-37fec3ef82cc"
description: "An Emacs framework for the stubborn martian hacker - doomemacs/doomemacs"
url: "https://github.com/doomemacs/doomemacs"
favicon: ""
aspectRatio: "50"
```

```embed
title: "GitHub - ianyepan/yay-evil-emacs: 😈 A lightweight literate Emacs config with even better \"better defaults\". Shipped with a custom theme!"
image: "https://opengraph.githubassets.com/7dae5451a3962361f532fa21ecbdf0773e432498bfd288f9f47a924eb03e7fa1/ianyepan/yay-evil-emacs"
description: "😈 A lightweight literate Emacs config with even better \"better defaults\". Shipped with a custom theme! - ianyepan/yay-evil-emacs"
url: "https://github.com/ianyepan/yay-evil-emacs"
favicon: ""
aspectRatio: "50"
```

### Gemini Summary - Customising Doom Emacs
#### Enable the Markdown Module 
Open your `~/.doom.d/init.el` file and ensure `:lang markdown` is uncommented within the `doom!` block. 

```
(doom!
 ...
 :lang
 (markdown +grip) ; Make sure this line is present and uncommented, with the +grip flag for previews
 ...
)
```

After modifying `init.el`, run the following command in your terminal to install the necessary packages:  
`~/.emacs.d/bin/doom sync` or `./doom install` if you are in the `~/.emacs.d/`directory. 

#### Add Configuration for a Rich-Text Feel 
Add the following Emacs Lisp (Elisp) configuration to your `~/.doom.d/config.el` file to hide markup and improve font rendering, making it feel more like a rich-text editor: 

```
(use-package markdown-mode
  :commands gfm-mode markdown-mode
  :mode (("README\\.md\\'" . gfm-mode)
         ("\\.md\\'" . markdown-mode)
         ("\\.markdown\\'" . markdown-mode))
  :custom
  (markdown-header-scaling t)           ; Scales header fonts automatically
  (markdown-hide-urls t)                ; Hides URL link markup, showing only the link description
  (markdown-fontify-code-blocks-natively t) ; Uses native Emacs fontification for code blocks
  ;; Optional: automatically hide markup when the mode is enabled
  (markdown-hide-markup-globally t)
)

;; Command to toggle markup hiding manually (C-c C-x C-m)
(add-hook 'markdown-mode-hook (lambda ()
                                (setq markdown-hide-markup-globally t)
                                (markdown-hide-markup)))
```

#### Install an External Markdown Processor (Optional, for previews) 
For a live, rendered preview in a browser, you need an external Markdown processor installed on your system. 
- **Pandoc** is highly recommended for its powerful conversion capabilities.
    - **macOS:** `brew install pandoc`
    - **Arch Linux:** `pacman -S pandoc`
- Alternatively, you can use `discount` or `multimarkdown`. 

#### Usage and Keybindings
Once set up, you can use these essential commands:

| Action                   | Keybinding (Doom Emacs)                  | Description                                                              |
| ------------------------ | ---------------------------------------- | ------------------------------------------------------------------------ |
| **Toggle Markup Hiding** | `C-c C-x C-m`                            | Hides/shows the raw Markdown markup (e.g., `**bold**` becomes **bold**). |
| **Preview in Browser**   | `<localleader> p` (`SPC m p` by default) | Opens a live preview in your default browser.                            |
| **Bold Selected Text**   | `C-c C-s b`                              | Wraps selected text in `**...**`.                                        |
| **Code Block**           | `C-c C-s c`                              | Formats a selected region as a code block.                               |

This setup leverages Doom Emacs' features to provide a clean, modern Markdown editing experience while retaining the powerful customisation options of Emacs. 

---

## ErgoEmacs

```embed
title: "GitHub - ergoemacs/ergoemacs-mode: ergoemacs-mode"
image: "https://opengraph.githubassets.com/99a1bf3dd5c7455a74da2d8f265558dbc3896484c350880454bfd207c7000f60/ergoemacs/ergoemacs-mode"
description: "ergoemacs-mode. Contribute to ergoemacs/ergoemacs-mode development by creating an account on GitHub."
url: "https://github.com/ergoemacs/ergoemacs-mode"
favicon: ""
aspectRatio: "50"
```


> You could check out ErgoEmacs. Has a bunch of extensions to make it more like a standard app of your OS. Things like ctrl-x ctrl-c ctrl-v cut copy and paste. Also, enable toolbar-mode and menu-mode. Also, try out helm, it's a completion system that replaces the standard minibuffer with a more graphical alternative.
> - [r/emacs - Reddit](https://www.reddit.com/r/emacs/comments/zi615i/basic_customization_to_make_emacs_more_modern/#:~:text=I%20just%20started%20using%20emacs,and%20how%20to%20do%20it%20?)


