---
Date: 2026-03-16
Author: Cody Cork
tags:
  - Resource/Audio
---
# Resources

```embed
title: "r/Focusrite - Reddit"
image: "https://www.redditstatic.com/icon.png"
description: "18i20 not connecting upon boot"
url: "https://www.reddit.com/r/Focusrite/comments/1hhpwt5/18i20_not_connecting_upon_boot/"
favicon: ""
aspectRatio: "100"
```


# Support Steps

**1.)** Try using another USB cable that's under 2m in length to connect the Scarlett to your, do you experience the same issue with the new cable? Avoid using any adapter and USB hub as same as before.  
   
**2)** Reinstall the driver completely and perform the resets:  
   
**Reinstall driver:**
1. Disconnect the Scarlett
2. Fully uninstall the USB drivers for the Scarlett (Found here [https://support.focusrite.com/hc/en-gb/articles/115003235785-How-to-fully-uninstall-Focusrite-Control-from-your-computer](https://support.focusrite.com/hc/en-gb/articles/115003235785-How-to-fully-uninstall-Focusrite-Control-from-your-computer))
3. Restart your Mac
4. Reinstall the drivers with the Scarlett disconnected. [**Focusrite Control (v3.18.0) - Mac**](https://fael-downloads-prod.focusrite.com/customer/prod/downloads/focusrite-control-3.18.dmg)
5. Restart your Mac
6. Reconnect the Scarlett and test
      
**Reset the audio preferences on your Mac:**
Go to: **Finder > Go** (top menu) **> Computer > Mac HD > Library > Preferences > Audio** and in there please delete the two preference (.plist) files:
- _com.apple.audio.DeviceSettings.plist_ 
- [_com.apple.audio_](http://com.apple.audio/)_.SystemSettings.plist_

Go to:
**Finder > Go** (top menu) **>** Hold down the "Option" (or "Alt") key and click on the **Library** folder that appears **> Preferences**. In there please delete the file:
- [_com.apple.audio_](http://com.apple.audio/)_.AudioMIDISetup.plist_

Note that _'com.apple.audio.AudioMIDISetup.plist'_ might not show up on your Mac. If you do not see this file, go to the next step.

After doing all the above, you need to ensure you **empty your trash** and **restart your Mac**."