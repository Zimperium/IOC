

| Command | Description |
| :---- | :---- |
| loading\_modal | Displays a deceptive full-screen loading screen while silently monitoring and automating background interactions |
| liveoverlayblock | Persistent loop that monitors device and UI state and conditionally re-applies or manages a full-screen overlay based on lockscreen status and active window changes. |
| notification\_listen\_disable | Disables notification monitoring |
| notification\_listen\_enabled | Enables notification listening |
| notification\_setting | Triggers a notification related workflow that escalates into device wake-up |
| write\_setting | Abuse the accessibility to grant itself the WRITE\_SETTING permission  |
| disable\_sounds\_and\_vibrations | Disables sounds and vibrations in the phone  |
| distrub\_mode | Sets a “do not disturb” mode |
| distrub\_mode\_enabled | Disables interruptions by enabling Do Not Disturb mode, muting all audio streams, silencing ringer/vibration, and turning off system vibration settings if write access is granted |
| brightness | Disables automatic brightness and sets screen brightness to minimum |
| unlock\_phone | Triggers device unlock related routine using accessibility |
| registration\_update | Registers the device with all basic device info like hardware,model,etc to C2 |
| disabe\_calls | Disables calls on the victims device |
| calls\_block | Enables call blocking by activating a flag that causes the CallScreeningService to reject incoming calls, prevent them from ringing, and suppress call logs and notifications |
| enable\_calls | Enables to receive calls in the device |
| request\_pin | Puts pin overlay on top of the screen |
| main\_activity | Displays a fake “software update” notification with action buttons, sound, vibration, and pending intents to lure user interaction and redirect them back into the app |
| request\_pattern | Puts pattern overlay on top of screen |
| request\_password | Request for device lock password |
| change\_sms | Checks SMS change capability and Android version, rejects on unsupported systems, otherwise triggers an accessibility-driven workflow to change SMS related settings |
| change\_sms\_auto | Triggers an accessibility driven workflow to modify SMS settings automatically, |
| keepscreenonforever | Keeps the screen on using device wakelock |
| keepscreenoff | Stops keeping the device awake and free system resources |
| send\_sms | Sends SMS to a particular phone number with a message received from the server |
| update\_time | Parses a time value from JSON (default 60s), enforces a minimum delay, schedules a timed task, and returns success or error |
| update\_config\_injects | Marks configuration injection update as completed |
| editextnow | Performs text injection into UI fields or remote SMS message upload/exfiltration via HTTP POST, depending on input data. |
| editextnow2 | Performs accessibility based UI element targeting and automated text injection into the active screen |
| startuilogger | Initializes a UI logging system that periodically captures device UI state and transmits it to a remote server |
| stopuilogger | Stops UI logging  |
| tap | Taps at a specific point on the screen |
| longclick | Long clicks on a specific point on the screen |
| swipe | Performs swipe gesture on the screen |
| wakeup | Wakes the device up using wakelock |
| update\_config\_domen | Updates a domain list of C2’s |
| start\_vnc | Starts a background loop that continuously captures screenshots of the victim’s screen |
| stop\_vnc | Stops taking screenshots of the screen |
| push\_send | Sends a notification to the victim |
| btn\_back | Presses back button |
| btn\_home | Presses home button  |
| btn\_recents | Presses recent apps button |
| btn\_notifications | Triggers the Notifications shade action |
| btn\_settings | Opens system quick settings panel  |
| btn\_power\_dialog | Opens system power dialog (power menu) |
| btn\_launchapp | Launches a specific app based on the packagename received form c2 |
| btn\_launchapp2 | Launches a specific app based on the packagename received form c2 and later closes it. |
| appinform2 | Opens the system app details screen for a given package, where the user can view or change app settings |
| btn\_permission\_list | Collects device permission and access status (accessibility, SMS, calls, notifications, system settings) and reports it to a remote server. |
| notification\_clian | Cancels all notifications on the device |
| disable\_red\_alert\_for\_default | Check the language on the device and then abuse accessibility service to   disable notifications and google play protect. |
| allowmodify | Checks/requests “modify system settings” permission and, if allowed, opens the Android system screen where the user can grant WRITE\_SETTINGS access for the app. |
| permissiondnd | Checks whether the app has Do Not Disturb, and if not, opens the system settings page to grant that permission |
| noitificationp | Opens the system Notification Access settings page so the user can grant the app permission to read and monitor notifications |
| smsclient | Requests permission to become the default SMS app using Android’s RoleManager |
| callclient | Requests permission call\_screening |
| appinform | Opens the system App Info (Application Details) screen for the current app package |
| foundsmspoint | Make app is the default SMS default handler using an overlay to identify where the clicks have to be done |
| foundcallpoint | Make is the call default handler using an overlay to identify where the clicks have to be done |
| overlaywake\_false | disables first overlay wake flag |
| overlaywake\_true | enables first overlay wake flag |
| overlaywake2\_false | disables second overlay wake flag |
| overlaywake2\_true | enables second overlay wake flag |
| foundallpoint | ModifySetting using an overlay to to identify where the clicks have to be done |
| close\_all | Closes all recent apps |
| clicktextextract | Locates a UI element by text on the screen and clicks it |
| clicktext | Searches for UI elements by text and simulates a click |
| clickdescextract | searches for UI elements using accessibility labels (content descriptions) and automatically clicks |
| clickdesc | clicks UI elements by matching visible text descriptions |
| textextract | Checks whether a specified text string is present on the victim’s current screen |
| text | Recursively scans the active UI tree using Accessibility APIs to detect whether any visible UI element contains the specified string which is received from c2 |
| descextract | Recursively scans the active UI’s accessibility tree for matching description/content-description text |
| desc | Recursively traverses the active UI’s Accessibility tree to check whether any element’s content description contains that string  |
| update\_prefix | The malware processes an update\_prefix command that sanitizes and stores a new dynamic prefix in SharedPreferences |
| enter\_pattern | Schedules an automated pattern input by preparing the UI state, calculating screen dimensions |
| show\_black\_overlay | Shows black screen overlay on top of screen |
| hide\_black\_overlay | Hides black screen overlay from top of screen |
| make\_overlay\_not\_touchable | Makes overlay non interactive to the victim  |
| make\_overlay\_touchable | Makes the overlay view user interactable |
| hard\_stop\_overlay\_now | Removes the overlay window by updating its flags and detaching it from the WindowManager. |
| reset\_app\_list | Resets and updates its monitored application list by fetching a package list from a remote server |
| enter\_point | Schedules a delayed automated tap action at a specified screen coordinate. |
| stop\_keyloger | Stops extracting the keystrokes of victim |
| start\_keyloger | Starts extracting keystrokes of victim |
| copyclipboard | Copies clipboard data of victim and replaces it with attacker replaced input  |
| startoverlay16 | Activates and manages an overlay that sits on top of the screen |
| open\_google\_play\_protect | Launches the Google Play Services security settings |
| open\_my\_app\_activity | Disables a security flag and relaunches the app’s MainActivity |
| hide\_app | Triggers an internal routine intended to hide or conceal the app’s presence on the device.  |
| hide\_overlay\_16 | Hides the overlay on top of screen |
| show\_loading\_overlay | Shows loading overlay to the victim |
| show\_loading\_overlay\_dont | enables a loading overlay, updates stored preferences, triggers overlay animation, and manages its WindowManager visibility and touch state |
| liveoverlay16 | Place an overlay |
| overlay\_point | Get a specific point sent from the server on the overlay |
| stop\_start\_grabber | stops the active automation/grabber process |
| start\_uilogger\_loop | Continuously scans the UI and sends data to server |
| volumeup | Increases the volume in the device |
| volumedown | Decreases the volume in the device |
| mutevolume | Mutes the device |
| protectorgoogle\_disable | disables the app’s internal “Google protector”/protection flag |
| protectorgoogle\_enable | Enables the app’s internal “Google protector”/protection flag  |
| liveoverlay | Checks the screen size, computes the center point, and if the overlay is active, it performs an automated tap at the center of the screen |
| sms\_overlay\_16 | Overlay used for getting the SMS default handler  |
| call\_overlay\_16 | Overlay used for getting the Call default handler  |
| update\_slots | collects SIM/telephony subscription details |
| set\_slots | Reads a "slot" value from json(defaulting to 0 if missing/invalid) and stores it as the active SIM/telephony slot index in the app’s internal state |
| update\_points | Update the points where the accessibility would perform some click or actions. |
| dontstoploadingoverlay | keeps the loading overlay enabled by setting a flag in SharedPreferences |
| unlocktraker | activate unlock-tracking behavior by setting internal flag as true |
| up\_swipe | Performs swipe up gesture |
| down\_swipe | Performs down swipe gesture |
| right\_swipe | Performs right swipe gesture |
| left\_swipe | Performs left swipe gesture |
| disable\_google\_play | Disables google play  |
| get\_contact | Scans the active screen’s UI tree using Accessibility services, filtering out common WhatsApp interface labels and matching time-like patterns, to extract or monitor relevant on screen text while ignoring normal UI elements. |
| enable\_second\_label | switches or hides app entry points |
| loading\_screenshot | checks that either an overlay or accessibility view is active, then triggers a delayed screenshot/processing flow where a UI capture routine is executed |
| get\_last\_sms | Gets last sms from the device |
| set\_status\_packet | Updates the local SQLite database entry for a given app package, changing its monitored status in the monitored\_apps table |
| set\_url\_packet | Updates the local monitored\_apps database by setting or modifying the URL field for a specific package entry |
| inject\_block | Enables a blocking overlay state by updating SharedPreferences flags to hide web content overlays and keep the main overlay active, |
| inject\_unlock | disables the overlay blocking state |
| open\_url | constructs a dynamic URL using device and  server parameters and opens it inside an in app WebView |
| close\_url | Closes the in app webview |
| click\_editext | locates an EditText element by its index in the Accessibility node list and simulates a tap |
| overlay2 | enables the overlay mode, stores its state in preferences, and schedules a delayed sequence that performs automated gesture actions |
| overlay\_point\_ok | enables an overlay, places a marker at specified screen coordinates, and schedules a delayed automated interaction at that location |
| open\_website | extracts a URL string from the payload, normalizes it by ensuring an http/https prefix, and opens it |
| permission\_all\_files | Checks if the app has full file access permission and, if not, opens the system settings screen to request “All files access” permission |
| gplay\_full | updates the database by changing all monitored app entries with status 2 to status 3\. |
| gplay\_full\_disable | updates the database by changing all monitored app entries with status 3 back to status 2, effectively toggling the app’s tracking/monitoring state |
| showpinlockoverlay | Shows the pin lock overlay on top of screen |
| showpatternlockoverlay | Shows pattern lock overlay on top of screen |

