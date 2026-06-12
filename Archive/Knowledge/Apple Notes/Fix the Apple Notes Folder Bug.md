---
Date: 2026-03-18
Author: Cody Cork
tags:
  - Resource/Apple/Notes
---
# Resources

```embed
title: "Apple Notes expands all folders on launch… - Apple Community"
image: "https://discussions.apple.com/assets/avatar/aa21e0dd528ca94a0f763b6abdaf7524/bd796753cc66dd6deef7b718300c59b1473b0f54a92574c7fc76bdbf728ecc6d"
description: "Since upgrading tomacOS 26, every time I openApple Notes, the sidebar launches withevery folder and subfolder expanded."
url: "https://discussions.apple.com/thread/256216467?sortBy=rank"
favicon: ""
aspectRatio: "98.4375"
```

# Notes

- Close Apple Notes.
- Open Finder & go to folder: `~/Library/Containers/com.apple.Notes/Data/Library/Preferences/`
- Find the file: `com.apple.Notes.plist`
	- Move it to your Desktop.
	- Restart your Mac and open Notes. If the behaviour stabilises, you can delete the file from your Desktop.
![[Apple Notes - Fix Folder Bug.png]]