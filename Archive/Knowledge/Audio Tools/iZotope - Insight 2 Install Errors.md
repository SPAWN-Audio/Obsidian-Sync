---
Date: 2026-03-18
Author: Cody Cork
tags:
  - Resource/Audio/iZotope
  - Resource/Apple/macOS
---
# Resources



# Notes

## Notes from Reddit Threads

> Some specific random notes that might work - pulled from different Reddit Threads

> [!tip] #### Reddit Comment 1
> I finally got a solution to this that worked for me. Download the installer direct from the website, and only install the AAX and AU. Then run it again and install all of them. No idea why but it worked when nothing else I tried would.

- *This one had a comment saying that in **March 2025**, this worked*


> [!tip] #### Reddit Comment 2
> Like some other people on here, I only installed the essentials + AAX + AU and it worked.


---

## Pirate Install - Apps Torrent Ru

> Some notes on installing on Apple Silicone

1. Install
2. Replace AU VST and VST3 K'd

### Solution for ARM / Apple Silicon / Native without Rosetta, example for AU:

- *Paste these commands in Terminal, after you've installed "Ozone 11 (or ANY IZOTOPE plugins)" and "Patched":*

```bash
sudo xcode-select --install
```
- *(if you already have Xcode installed, skip to step 2.)*

```bash
cd /Library/Audio/Plug-Ins/Components
sudo find . -name "iZInsight2AUHook.component" -execdir lipo -extract x86_64 {}/Contents/MacOS/PluginHooksAU -o {}/Contents/MacOS/PluginHooksAU.1 \;
sudo find . -name "iZInsight2AUHook.component" -execdir mv {}/Contents/MacOS/PluginHooksAU.1 {}/Contents/MacOS/PluginHooksAU \;
```

- *REBOOT*
- *After Reboot*

```bash
sudo xattr -cr /Library/Audio/Plug-Ins/Components/iZInsight2AUHook.component
sudo xattr -d -r com.apple.quarantine /Library/Audio/Plug-Ins/Components/iZInsight2AUHook.component
sudo chmod +x /Library/Audio/Plug-Ins/Components/iZInsight2AUHook.component
sudo codesign --force --deep --sign - /Library/Audio/Plug-Ins/Components/iZInsight2AUHook.component
```

### Install Instructions Screenshot
![[iZotope Insight 2 - Install Instructions.png|627x841]]