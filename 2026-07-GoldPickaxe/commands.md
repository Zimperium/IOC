# GoldPickaxe Banking Trojan - Command & Control (C2) Commands

The following table documents the technical commands extracted during the analysis of the GoldPickaxe malware variant. These commands are parsed from the C2 server to dynamically orchestrate malicious capabilities on compromised Android endpoints.

| Command | Description |
| :--- | :--- |
| `mustclose` | Use the accessibility Service to stop the ScreenshotService |
| `four_password` | Spawns a custom 4-digit PIN capture overlay, launching the activity com.sup.hop.ui.activity.LockScreenPwdActivity |
| `disable_face_true` | Disables biometric facial scanning protection loops. |
| `apk_download` | Downloads a secondary APK payload from a URL sent from the C2 server. |
| `system_update_black_true` | Renders a fake "System Update" overlay (black) to block the system_update |
| `mute_deice_true` | Reposible for completely and absolutely muting all audio channels on the infected device. |
| `face_video_judu` | Launch a command that update the UI with Face recognition failed |
| `upload_contacts` | Steals and uploads the entire device address book/contacts. |
| `dark_screen` | Use accessibility service to lock_screen |
| `get_photo_auth` | Requests permissions to capture photos. |
| `open_video_surveillance` | Launches a background service to utilize the device camera without user consent and exfiltrate the captured data to the server |
| `search_file_dowload` | Searches the file system and downloads chosen files to the C2. |
| `open_audio_surveillance` | Remotely initializes silent microphone recording and exfiltrate captured data to the C2 |
| `upload_call_log` | Steals and exfiltrates call_log history. |
| `fingerprint_retry` | Re-Initialize fingerprint fake layout scanning capture. |
| `fingerprint_start` | Initializes fingerprint fake layout scanning capture. |
| `download_vm` | The Server send URL and the force the victims to visit it |
| `test_acc` | Test accessibility it send a value in the field "c" and launch performGlobalAction(X) |
| `overly_img_hide` | Hides custom global graphic overlay layers. |
| `overly_img_show` | Displays a full-screen graphic overlay layer. |
| `enhanced_display_false` | Disble the screen-scraping for an specific user |
| `prohibit_operate_true` | Blocks global user interaction and hard keys via Accessibility Services. |
| `fingerprint_accept` | Allow fingerprint verification authorization. |
| `mute_screenshot` | Take an screenshot and sent to the C&C using |
| `app_icon_hidden_false` | Restores the malware app icon visibility on the home screen launcher. |
| `start_control` | Not implemented |
| `battery_white` | Requests addition to the system battery optimization whitelist. |
| `hidden_icon` | Not implemented |
| `unlock` | Attempts programmatic screen unlock sequences. |
| `uninstall_app` | Forcefully uninstalls targeted software received from the Server |
| `pin_black_true` | Obscures PIN entry fields during automated transactions. |
| `get_app_list` | Enumerates all packages installed on the operating system and leak to the server |
| `quanju_text_close` | Toggles global text scanning configuration states off. |
| `disable_face_false` | Re-enables default biometric face authentication loops. |
| `screen_share_true` | Triggers active video screen sharing using MediaProjection |
| `clone_app` | Instances targeted applications inside a managed virtual sandbox shelter APK |
| `face_video_accept` | Launch a command that update the UI with Face recognition accepted |
| `search_file` | Scans local storage for files matching specified search criteria and stream the results back to the server |
| `accessible_open` | Open the accessibility menu for this specific app directly |
| `open_app` | Launches and focuses a specific targeted application package. |
| `quanju_text` | Persistent Real-Time Accessibility Screen Scraper |
| `black_mask_true` | Applies a full-screen masking window to hide system behavior. |
| `uninstallable_true` | Abuses accessibility to prevent manual uninstallation. |
| `screen_share_false` | Terminates live screen sharing or mirroring services. |
| `upload_sms` | Dumps and exfiltrates the complete text message database. |
| `screen_push_share_false` | Shuts down active high-frequency remote screenshot streaming. |
| `open_overly` | Check if the app has overlay permission and if not open the settings to get it |
| `black_screen_text` | Renders text elements onto a blacked-out screen viewport. |
| `black_screen_true` | Draws a full black canvas across the screen to fake a sleeping device. |
| `area_auth` | Request android.permission.ACCESS_FINE_LOCATION permission |
| `enhanced_display_true` | Launch a background screen-scraping and data exfiltration featurininjection of text using accessibility service |
| `open_google_play_store` | Try to open google play application |
| `back` | Uses accessiblitiy to force BACK navigation click. |
| `home` | Uses accessiblitiy to force HOME click. |
| `task` | Uses accessiblitiy to force RECENTS click |
| `go_detail` | Forces navigation to app detail screens. |
| `click` | Simulates precision touch coordinates sent from server. |
| `app_icon_hidden_true` | Hides the application icon from the home screen launcher. |
| `injection_app` | Injects fake Alert layout from the server that redirect to a webview |
| `prohibit_operate_false` | Restores standard user screen interaction capabilities. |
| `black_screen_false` | Removes full black canvas overlays to restore screen visibility. |
| `local_notification` | Generates a custom notification |
| `get_permission_contacts` | Force to get accepted the contacts permission |
| `setting_page` | Forces navigation directly into system configuration settings panels. |
| `get_permission_sms` | Force to get accepted the SMS permission |
| `short_message_notification` | Open the notifications setting related to the SMS app |
| `screen_push_share_true` | Starts high-frequency automated screenshot capturing . |
| `battery_setting` | Navigates the user to battery configuration |
| `black_mask_false` | Removes full-screen masking boundaries. |
| `close_video_surveillance` | Terminates camera recording. |
| `get_permission_call_log` | Force to get accepted the Call history permission |
| `face_video` | Launches video verification or real-time face feed exfiltration. |
| `upload_idcard` | Targets and uploads scanned identity card images. |
| `gesture_password` | Generates a spoofed lock screen pattern interface to harvest unlock grids. |
| `download_img` | Download an image and store on media |
| `close_audio_surveillance` | Stops microphone audio recording. |
| `uninstallable_false` | Disables structural locks preventing app uninstallation. |
| `wefride` | Not implemented |
| `accessible_close` | Not implemented |
| `input_text` | Programmatically populates active text fields with keystroke injection. |
| `light_screen` | Overrides default timeout constraints to force an active screen lock wake for 5 min |
| `change_brightness` | Modify screen brightness remotely |
| `six_password` | Generates a fake 6-digit PIN input panel to harvest access combinations. |
| `yijian_down` | Swipe-down emulated using the coordinates of the phone |
| `mute_deice` | Disables systemic audio alerts to mask malware actions. |
| `injection_password_app` | Deploys credential harvesting overlays targeting specialized app password prompts. |
| `open_auto_start` | Try to autostart the app once it boot for different manufacturers |
| `modify_resolution` | Not implemented |
| `system_update_black_false` | Destroy fake system update masking view. |
| `mute_deice_false` | Restores standard notification and media volumes. |
| `click_app_password` | Launch a overaly for collecing password payment for an app |
| `pin_black_false` | Removes overlay masks masking PIN entry regions. |
| `background_popup` | Forces application overlays to execute from the background state on different manufacturers |
| `custom_password` | Try to steal the lock using the oepn-source com.github.ihsg.patternlocker.PatternLockerView |
| `battery_system_setting` | This command purpose is to open the device's system Battery settings page |