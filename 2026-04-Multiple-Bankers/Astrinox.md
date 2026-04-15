# Astrinox Command Reference

| Command | Description |
| :--- | :--- |
| **home** | Programmatically presses the Home button. |
| **back** | Programmatically presses the Back button. |
| **recents** | Opens the Recent Apps screen. |
| **blackScreen** | Toggles a full-screen black overlay. |
| **blackScreen_updating** | Shows a fake Android update overlay. |
| **layout_updates_start** | Starts continuous streaming of UI/layout data. |
| **openApp** | Launches a specific application. |
| **showNotification** | Displays a notification to the victim. |
| **forceReconnect** | Forces the WebSocket connection to restart. |
| **enableNeverSleep** | Acquires wake locks to keep device awake indefinitely. |
| **unlockDevice** | Wakes and unlocks the device (including pattern drawing). |
| **lockDevice** | Locks the device remotely using accessibility actions. |
| **mute** | Toggles Mute/Do Not Disturb state. |
| **getClipboard / setClipboard** | Read or write device clipboard data. |
| **startScreenSharing** | Starts screen sharing with specified quality/params. |
| **startVncScreenSharing** | Starts VNC-specific screen sharing. |
| **getInstalledApps** | Retrieves all installed applications. |
| **getDeviceState** | Collects state info (VNC, camera, sharing, etc.). |
| **getKeyguardInfo** | Collects lock screen type (PIN, Pattern, etc.). |
| **startCamera / stopCamera** | Controls remote camera streaming. |
| **listCameras** | Lists available cameras on the device. |
| **getPatternLockStatus** | Retrieves status of pattern lock monitoring. |
| **resetPatternLock** | Resets the pattern lock. |
| **startSmsCollection** | Collects SMS messages from the device. |
| **getPermissions** | Checks status of various critical permissions. |
| **requestPermission** | Requests specific permissions (Accessibility, SMS, etc.). |
| **enableHtmlInjection** | Enables persistent HTML injection for credential stealing. |
| **addHtmlInjectionConfig** | Adds an injection rule for a specific package. |
| **enablePatternLock** | Enables monitoring of Android pattern lock usage. |
| **tap / swipe** | Remote screen interaction via coordinates. |
| **switchClient** | Switches the active C2 client session. |
| **uninstallPackage** | Uninstalls a specific package. |
| **enableUninstallProtection** | Prevents the malware from being uninstalled. |
| **androidHandshake** | Initial connection protocol with the C2. |
| **keylog_batch** | Logs every keystroke on the device. |
| **blockApp** | Hides specific apps with an "App Blocked" overlay. |
| **unblockApp** | Removes the app block overlay. |
| **setLockType** | Sets the deception method (PIN, Pattern, Password). |
| **getLockStatus** | Comprehensive report on hijacking and lock state. |
