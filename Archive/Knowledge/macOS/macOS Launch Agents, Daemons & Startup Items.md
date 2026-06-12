---
tags:
  - Resource/Apple/macOS
Date: 2026-03-03
Author: Cody Cork
Type: Notes
---
# Commands

| Command                                                                                 | Description                                                                                                                                                          |
| --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sfltool dumpbtm`                                                                       | This lists all of the Launch Agents, as well as some of their corresponding information                                                                              |
| `sfltool resetbtm`                                                                      | - This reset database (to clean up uninstalled but still listed apps)<br><br>- Though one person did say that it cleaned everything in the Login Items - be careful! |
| `sudo launchctl bootout system /Library/LaunchDaemons/com.paceap.eden.licensed.plist`   | This is to _UNLOAD_ the Daemon                                                                                                                                       |
| `launchctl bootstrap system /Library/LaunchDaemons/com.paceap.eden.licensed.plist`      | This is to _LAUNCH_ the Daemon                                                                                                                                       |
| `/Library/Frameworks/PACEEdenExperience.framework/Versions/Current/Software Activation` | File Path                                                                                                                                                            |
