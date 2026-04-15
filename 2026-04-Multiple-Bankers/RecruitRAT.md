# RecruitRat Command Reference

| Command | Description |
| :--- | :--- |
| **avnc** | Create a VNC session via websocket and allow the attackers to control the device remotely with different “VNC commands”. |
| **Perform user Actions** | Includes: swipeDown, swipeLeft, swipeUp, Swipe2, Swipe, swipeRight, Home, Back, recent. |
| **permission** | Auto-accept permissions. |
| **overlay_show** | Add View (Show overlay). |
| **overlay_hide** | Remove View (Hide overlay). |
| **Open application** | Open a specific application. |
| **Click** | Perform a click action. |
| **Long_click** | Perform a long click action. |
| **vnc** | Take screenshots of the device and send to the attacker. |
| **Bright** | Adjust screen brightness levels. |
| **Loud** | Adjust audio volume levels. |
| **Unlock** | Allow the attacker to unlock the device remotely (PIN, password, pattern). |
| **Clipboard** | Replace the content of the victim's clipboard. |
| **Stop** | Attacker stops the communication. |
| **Text** | Inject text on editable views present on the display. |
| **botAddSmsList** | Collect a list of SMS on the device and send to the C2 in JSON format using RC4. |
| **getGates** | Write the C2 address to SharedPreferences (Default: https://joodyallen[.]art). |
| **google_auth** | Abuse Accessibility Service to steal 2FA codes from Google Authenticator. |
| **inject** | Detect targeted packageNames and open a webview HTML overlay with a JS interface. |
| **injectZip** | Downloads/unzips fake layouts (HTML) for targeted apps and PIN stealing. |
| **inject_lock** | Open a local webview using one of the stored HTML files. |
| **openAccessibility** | Open Accessibility Settings remotely. |
| **open_url** | Open a specific URL on the device. |
| **reset_lock** | Clear all lock-related information in Shared Preferences. |
| **screen_power** | Trigger a wake lock to ensure the device does not go to sleep. |
| **send_ussd** | Send USSD commands programmatically (can lead to premium service subscriptions). |
| **show_overlay** | Show a specific overlay using the WindowManager API. |
| **terminal_command** | Spawns a standard Android shell (sh) to execute arbitrary commands. |
