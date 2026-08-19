| Command | Description |
| :--- | :--- |
| `adbBlackScreen` | Disables automatic brightness and sets the screen brightness level to zero to create a black screen. |
| `adbBlackScreenOff` | Sets the device screen brightness level to 128 using ADB commands to restore or adjust screen visibility. |
| `adbClick` | Executes an ADB shell command to simulate a tap at specified screen coordinates |
| `adbDisconnect` | Disconnects the active ADB session |
| `adbKeyEvent` | Allows the malware operator to remotely simulate Android key presses by sending ADB input keyevent commands to the connected device. |
| `adbLockAndroidUpdate` | Places an overlay abusing the shell user using the `<am start -n>` command |
| `adbLockNormal` | It shuts off auto-brightness and turns the screen backlight all the way down to 0% using the shell user. |
| `adbLockUpdate` | Same as adbLockAndroidUpdate command |
| `adbScreenshot` | Captures the device screen using ADB, compresses and Base64-encodes the screenshot image, |
| `adbShell` | Allows the malware operator to execute arbitrary shell commands on the connected Android device through ADB |
| `adbStatus` | Checks the current ADB pairing and connection state |
| `adbSwipe` | Simulates touchscreen swipe gestures by executing ADB input swipe commands on the connected Android device, |
| `adbUiTree` | Uses ADB to execute `dumpsys activity top`, allowing it to retrieve details about the currently foreground application and active activity on the Android device |
| `adbUnlock` | Disables and removes the malware’s fake lock screen overlay |
| `addPinTargets` | Dynamically updates targets received from the server |
| `adm` | Request admin rights |
| `admLock` | Turn Off Screen |
| `admLockRule` | Requires a password reset |
| `admPwd` | Attempts to force reset or change the device's screen lock password/PIN |
| `admSet` | Request admin rights |
| `antiDeleteOff` | Sets the shared preference antiDelete value to false |
| `antiDeleteOn` | Sets the shared preference antiDelete value to True |
| `ask_relay` | Sends a relay status message containing the device ID, screen streaming status, and camera service state |
| `autoBoot` | Identifies the device manufacturer and launches corresponding OEM specific Auto start or power management settings to whitelist the application and maintain background execution |
| `autoRequestPerm` | Not implemented |
| `Awake` | Keeps the device awake |
| `back` | Activates the back button using the Accessibility Service |
| `backstage` | Detects the phone brand and opens vendor specific settings to disable battery optimization. So the app can run uninterrupted in the background |
| `black` | Activates a black overlay on the screen |
| `blackB` | Activates a black overlay on the screen |
| `callAcc` | Verifies if Android Accessibility Service is active |
| `callAppSetting` | Opens the app settings |
| `cancelAwake` | Disables device awake mode |
| `cancelWakeup` | Maintains a dimmed screen |
| `capture` | Takes a screenshot |
| `capturePic` | Enables screenshot functionality |
| `catAllViewSwitch` | Enables the malware to automatically identify and interact with permission dialogs, battery optimization prompts, and auto-start configuration screens across a wide range of Android OEMs |
| `clickB` | Clicks within a defined boundary |
| `clickInput` | Selects the input field |
| `clickPoint` | Clicks on a specific point on the screen |
| `closeEnv` | The malware is closing itself, the Accessibility Service and the ForegroundKeepAlive service |
| `closeNewWin` | Close/remove the malware's overlay window. |
| `closeProtect` | Disables OEM-specific pocket mode/accidental touch protection settings to prevent the device from blocking malware interactions. |
| `disableAcc` | Uses ADB shell commands to disable all enabled Accessibility Services and turn off Accessibility. |
| `disableBiometric` | Uses Device Admin privileges to disable biometric unlock (fingerprint and face authentication). |
| `disablePocketMode` | Disables device pocket mode, accidental touch protection, and anti-mistouch features across multiple Android OEMs to prevent touch restrictions |
| `dnd` | Allows the operator to silence the victim's phone |
| `dndOff` | Turns off the dnd mode |
| `dndOn` | Allows the operator to silence the victim's phone |
| `doNotDisturb` | Sets the Do Not Disturb mode on the device |
| `down` | Initializes a new touch gesture at the specified screen coordinates. |
| `enableAcc` | Enables Accessibility Service |
| `enableBiometric` | Enables biometric on the device |
| `fetchIcon` | Retrieves the icon of a specified application |
| `gestureB` | Executes a series of gestures |
| `gestureCapture` | Captures user’s gesture |
| `gestureUnlock` | Performs automated touch gestures on the device |
| `hideLockOverlay` | Hides the lock screen overlay |
| `hideMyMainActivity` | Hides or shows the malware application's launcher icon by enabling/disabling Android activity aliases. |
| `hideShortcuts` | Hides the application icon on the device |
| `home` | Activates the home button using the Accessibility Service |
| `iconAlias` | Enables or disables a specified launcher icon, allowing it to dynamically change or hide its app icon from the device launcher. |
| `iconList` | Collects the list of installed applications that have launcher icons and sends to server |
| `init_data` | Initializes specific application data |
| `inputSend` | Captures text input |
| `installApk` | Downloads and installs an APK |
| `installPermission` | Opens the Android "Install unknown apps" settings page for the malware, prompting the user to grant permission |
| `light` | Removes the fake lock screen overlay view |
| `lightT` | Same as light command |
| `lockAdvance` | Activates a full-screen fake Android lock screen overlay |
| `lockAndroidUpdate` | The malware displays a fake "Android Update" lock overlay and blocks user interactions |
| `lockNormal` | Displays a full-screen black overlay to hide the device screen |
| `lockScreen` | Locks the device screen |
| `lockUpdate` | Displays a full-screen dimmed overlay by reducing screen brightness, obscuring the device's display while malicious actions are performed in the background |
| `logMode` | Modifies the log mode |
| `manualPair` | Initiates Android 11+ wireless ADB pairing using a supplied pairing code and port to establish an authenticated ADB connection |
| `move` | Establishes tap simulation |
| `muteDevice` | Mutes the device |
| `openIntent` | Launches a specified Android intent to open an application, activity, or URL using parameters received from the C2 server |
| `openLayer` | Launches a black overlay activity that loads a C2 provided webpage in a WebView |
| `openUrl` | Open WebPage |
| `openWebHarvester` | Launches a hidden WebView based browser activity to load a C2 provided URL for displaying malicious web content and harvesting user data |
| `openpkg` | Opens a particular app from the device |
| `patternUnlock` | Automatically unclocks the pattern automatically using gestures |
| `permission` | Requests all necessary permissions |
| `permissionB` | Automatically grants permissions |
| `power` | Display the Android power menu |
| `reConn` | Stops the malware's WebSocket-based C2 communication by disconnecting the active session, cancelling reconnection attempts, and resetting the connection state |
| `reOpenMe` | Reopens the application |
| `readAlbumLast` | Retrieves the last album file name |
| `readAlbumList` | Retrieves all album file names |
| `readAlbumThumbnail` | Retrieves thumbnails for all album images |
| `readContactList` | Retrieves all contact information |
| `readSmsList` | Retrieves all SMS messages |
| `realtimeOnOff` | Enables or disables real-time monitoring based on the C2 command |
| `realtimeSet` | Updates the real-time monitoring interval from the C2 command |
| `recent` | Activates the recent button using the Accessibility Service |
| `releaseScreenCapture` | Not Implemented |
| `replacePinTargets` | Update the pin targets received from the server |
| `reqPerList` | Collects the app's permission list with grant status and sends it to the C2 |
| `reqScreenPermission` | Implemented but not complete, still under development |
| `requestfloaty` | Requests permission for floating windows |
| `restartApp` | Restarts an app , from the package name received from the server |
| `restartMe` | Restarts the application |
| `restartSc` | Restarts the Easyclick script service |
| `rightClick` | Activates the back button |
| `screen_relay` | Configures screenshot settings |
| `screenshot` | Takes a screenshot using Accessibility Service |
| `sendAlert` | Sends an alert notification |
| `setAppStyle` | Modifies the domain used to contact the C2 server |
| `setCam` | Captures a photo |
| `setDebugMode` | Sets the debug mode |
| `setDebugOff` | Disables debug mode |
| `setDebugOn` | Enables debug mode |
| `setDisConnect` | Reading a value from the C2, but not implemented completely |
| `setDomain` | Updates the C2 domain from the command, stores it in SharedPreferences, and saves it to dom.txt. |
| `setHideMode` | Sets the hide mode |
| `setSoundVibrate` | Enables or disables device sound/vibration |
| `setWakeup` | Schedules a task to wake up the device |
| `showLockOverlay` | Shows lock overlay on top of the screen |
| `showShortcuts` | Adds an icon to the home screen |
| `silentShot` | Starts screen capture with the requested quality and size, |
| `smartUnlock` | Uses Accessibility Service to unlock the device by simulating PIN/pattern/password input through UI clicks. |
| `startAdbStream` | Starts an ADB based screen streaming loop that periodically captures and sends screen data with configurable quality and interval settings |
| `startAdbTree` | Starts the ADB UI tree monitoring loop with the configured interval |
| `startApk` | Launch an application on the device |
| `startAutoPair` | Enables Wireless ADB, pairs with the device using the pairing code through Accessibility, connects via ADB, and grants the app elevated permissions for persistence/control. |
| `startCam` | Activates the camera |
| `startHD` | Starts an HD screen streaming service |
| `startHDBlack` | Displays a nearly opaque full screen black overlay |
| `startSilentStream` | Starts a silent screen capture stream by stopping ADB capture |
| `startWebRTC` | Implemented but not complete, still under development |
| `stopAdbStream` | Stops adb screen loop |
| `stopAdbTree` | Stops the ADB UI tree monitoring loop |
| `stopCam` | Turns off the camera |
| `stopHD` | Stops HD screen streaming service |
| `stopHDBlack` | Removes the overlay on top of screen |
| `stopScreenRelay` | Implemented but not complete, still under development |
| `stopSilentStream` | Stops the screen capture stream |
| `stopWebRTC` | Implemented but not complete, still under development |
| `swipePwdScreenOff` | Disables enforced password mode |
| `swipePwdScreenOn` | Enforces password entry mode |
| `takeScreen` | Malware takes a screenshot of the victim's device |
| `touchDown` | Initiates a down swipe |
| `touchMove` | Initiates a move swipe |
| `touchOff` | Disables overlay touch interaction |
| `touchOn` | Enables overlay touch interaction |
| `touchPinReplay` | Replays recorded touch coordinates on the target app using AccessibilityService |
| `touchUp` | Initiates an upward swipe |
| `transparent` | Remotely loads an attacker controlled URL inside a full screen WebView activity, enabling the display of malicious web content |
| `uninstallApk` | Uninstalls the application |
| `uninstallShell` | The malware launches the Android package uninstall prompt to remove itself from the victim's device |
| `unlock` | Stops screen capture, disables touch interception, and removes the fake lock screen overlay from the device |
| `up` | Dispatches an Accessibility gesture to simulate a user touch or swipe on the screen |
| `updateApk` | Installs an APK |
| `updatePageRule` | Fetches and updates the active target list and hosted HTML overlay mappings for banking/crypto applications |
| `utPause` | Updates the a flag to indicate that the Accessibility Service is inactive for screen data collection |
| `utResume` | Updates the Accessibility flag to indicate that the Accessibility Service is active for screen and UI data collection |
| `volumeDown` | Decreases the volume in the device |
| `volumeUp` | Increases the volume in the device |
| `wakeup` | Keeps the screen active |
| `walletList` | Uploads the list of installed wallet applications |
| `webrtcIce` | Handles WebRTC ICE candidate information (candidate, SDP media line index, and SDP MID) required to establish a peer-to-peer connection |
| `webrtcOffer` | Processes the SDP offer received from the C2 server to initiate a WebRTC connection |
| `lockV4` | Places System update overlay on top of screen |
| `lockV4Update` | Places System maintenance overlay on top of screen |
| `lockV4AndroidUpdate` | Places system software overlay on top of the screen |