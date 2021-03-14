# *POSP Changelog for lavender*

<img src="https://raw.githubusercontent.com/PotatoProject/manifest/dumaloo-release/XDAThread/main.png">

## *v4.0.6 (2021.03.15)*
### *Mainline:*
 - Updated Kernel to Predator X4.4-r1 - 4.4.258
 - Added qrtr blobs

### *Optimizations:*
 - Switched to AIDL Power HAL
 - Switched to audio hal v4
 - Disabled WLAN Firmware loggings
 - Nuked Dirac From Settings + Dirac QS Tile (A new QS for AudioFX itself will be added later)

---------------------------------------

## *v4.0.5 (2021.03.08)*
### *Mainline:*
 - DeviceSettings: Added Clear Speaker
 - ESE:   LA.UM.9.6.2.r1-03300-89xx.0
 - Media: LA.UM.9.6.2.r1-03300-89xx.0
 - WFD:   LA.UM.9.6.2.r1-03300-89xx.0 (WFD stll WIP)
 - GPS:   LA.UM.9.6.2.r1-03300-89xx.0
 - Time:  LA.UM.9.6.2.r1-03300-89xx.0
 - Radio and IMS: LA.UM.9.6.2.r1-03300-89xx.0

### *Fixes:*
 - AudioFX: FixedUp AudioFX (Source)
 - FixedUp Dirac back-end (Tree)
 
### *Optimizations:*
 - Recorder: Set maxinum meida record to 60fps
 - IMS: Allow com.qualcomm.location to run in the background
 - Bluetooth: Disable clean turn on
 - Porps: Set vendor.audio.adm.buffering.ms to 3 
 - Props: Shorten wait time for services exit to optimize shutdown time
 - Rootdir: Add permission for /dev/sp_keymaster_ssr
 - Sepolicy: Adress system_server denials
 - Sepolicy: Address gmscore_app.te denials

### *Source:*
- March patch
- DataSwitchTile tile
- Quick access Wallet (Shows cards on power menu)
- Call recorder added for supported devices
- Improve "Conversation" app list
- Fix AudioFX in Fries
- Add back QS Tile Disco
- The real disco is lurking out there, but where?
- Fixed AOD bug 
- Caffeine tile
- Changed ugly drawables of Advanced reboot
- Multiuser avatar in search bar
- Various misc bug fixes
- Misc bugfixes

---------------------------------------

## *v4.0.3 (2021.02.21)*
### *Mainline:*
 - Add Dirac back-end support (for Fries Dirac)
 - Add support for 240FPS 1/8 slow motion
 - update Telephony overlays from LA.UM.9.2.1.r1-05500-sdm660.0

### *Fixes:*
 - Re-Enable zRAM (2 GB)

### *Optimizations:*
 - Disable V-Sync (Smoother Ui)
 - Move some props into his right path
 - Symlink metadata to existing sessions 
 - Disable foreground prefer_idle & reduce TA boost
 - import Hotword Enrollment blobs
 - Optimize thermal

### *Source:*
- Use fixed row & column in landscape if media is playing
- Fixed lock icon not changing after system icon pack
- Hide lockscreen media art if media is not playing
- PixelPropsUtils (spoofed build fingerprint to redfin for some apps)
- Implement SmartSpace from redfin
- Advanced reboot option
- Dash charging text for OnePlus devices
- Reset battery stats
- Fix crashes in Updater
- Add back initial DiracSound and MiSound support

---------------------------------------

## *v4.0.2 (2021.02.15)*
### *Mainline:*
 - Build enforce
 - Update Kernel to Predator-Stormbreaker-X4.4 - 4.4.257
 - Updated fingerprint from Redfin - RQ1A.210205.004
 - Update telephony from LA.QSSI.11.0.r1-09400-qssi.0 (Now the RIL / VoLTE is way better)
 - Updated blobs from LA.UM.8.2.r1-07400-sdm660.0
 - Updated GPS blobs from LA.UM.9.12.r1-09500-SMxx50.0 to improve GPS accuracy
 - Updated GPS HAL from LA.UM.9.2.r1-01800-SDMxx0.0 to improve GPS accuracy
 - Updated thermal and Widevine blobs from jasmine V11.0.19.0 QDIMIXM

### *Fixes:*
 - Fixed POSP bootanimation lag
 - Fixed Google Recorder
 - [temp] Removed L1 support to fix Netflix crashes
 - Improved idle drain
 - Add support for potato notch city
 - Fixed some issues that reported from the logs
 - (Hopefully) fix the WFD
 - Fixed Offline charing (it was activating the bootanimation at the same time, now it's only the offline charge)

### *Optimizations:*
 - create and symlink a dummy /metadata/apex to get use of the new AOSP Changes for APEX
 - Dropped custom DHCP ranges in TetheringOverlay
 - TetheringOverlay and WifiOverlay now gets signed with default cert
 - Enabled VR high perfomance options
 - Keep biometrics in system-background (more power saving)
 - Bigger QS Tiles by 6% for more check this comment: https://git.io/JtPoQ
 - Better sound recorder
 - Kernel compiled using latest AOSP stable clang
 - Drop support for HMP kernels 
 - Using CAF IMS now (VoLTE)
 - Migrated to Health 2.1 HAL 
 - Changed USB autosusupend delay to 7s in order to fix USB audio device connection issues
 - Configured SQLite to operate in MEMORY mode for a nice SQL perfomance boost
 - Reduce screenshot delay to 0
 - Add hotword input for hotword mic concurrency
 - Add fast input profile for the record concurrency
 - Using QCOM_WLAN HAL instead of AOSP now
 - Redesign FPS
 - Dropped useless Thermal from the Device Settings

### *Source:*
 - Builds will now compile weekly!
 - Merge android-11.0.0_r31
 - February security patch
 - New OTA app
 - LTE <-> 4G icon toggle
 - Roaming indicator toggle
 - VoLTE icon toggle
 - Epic improvements to Fries
 - 3 finger screenshot
 - Pill hide
 - Pill sizes
 - StatusBar Tuner
 - Lockscreen Tuner
 - Navbar Tuner
 - Improvements to DeskClock
 - Disable SafetyNet HW attestation
 - Smoother upload and download animations
 - Temporarily re-add backuptool
 - Add QTI BT for devices that support it
 - Switch to GitHub releases for releases

---------------------------------------

## *v4.0.1 (2020.12.24)*
### *Mainline:*
 - Initial Official Release (Crispy)
 - Updated build fingerprint to Coral RQ1A.201205.008.
 - Updated kernel to Predator-Stormbreaker X4.2 - 4.4.248.
 - Fixed Hotspot with no password.
 - Fixed GBoard extra spacing over the navigation bar.
 - Added new offline charging animation with battery level.
 - Less boot time.

### Notes:
 - Netflix is not working with L1 (crashes),
 - join the support chat to know how to remove L1
 - to get your netflix work for now until we fix it, thank you.

### *Source:*
- RGB accenter is back, and its better (and faster!) than ever :D
- Pick accents your way with 3 different color pickers. You can also choose different accents for dark and light mode.
- Our famous volume panels from Q are back and are baked to perfection!
- Notch City is back, though there are only 2 modes for now. Stay tuned for an update :)
- Added some staple QS tiles including heads-up and NFC, and fixed icons for WiFi.
- Add/remove QS tiles with one click 
- Installing an APK? Package Installer will show you the current and new version.
- Choose your clock styles on lockscreen, in style
- Status bar now shows you your bluetooth device's battery level too
- Accidentally took a screenshot? Delete it right away, without opening Gallery!
- Assistant's animation is now nice and Colorful.
- Choose from 6 battery styles
- Take back control of QS with brightness slider tweaks and QS titles & dimensions 
- Doubletap/Longpress power to toggle Flashlight
- There is now an option to enable lockscreen media art with blur control
- Who needs a power button anyways? Double tap lockscreen or homescreen to sleep
- Skip tracks with volume buttons. (Stop being so lazy, Nico!)
- Pulse ambient display on new music tracks
- Only receive heads-up from messaging and calling apps with Less-boring headsups!
- Permission hub is back so you know when your FBI man is watching you
- Added per app network isolation option with VPN upstreams 
- Dialer and messaging are now dark too. Dark mode all the things!
- Completely de-googlified, with full microG support :D something frooty is on the way too
- No Pixel Launcher? No problem! Swipe left from your home screen for GNow (Needs GApps!)
