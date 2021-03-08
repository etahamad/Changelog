# Source Changelog
https://github.com/PotatoProject/vendor_potato/blob/dumaloo-release/CHANGELOG.md

# POSP Changelog for lavender
## v4.0.5 (2021.03.08)
Mainline:
 - DeviceSettings: Added Clear Speaker
 - ESE:   LA.UM.9.6.2.r1-03300-89xx.0
 - Media: LA.UM.9.6.2.r1-03300-89xx.0
 - WFD:   LA.UM.9.6.2.r1-03300-89xx.0 (WFD stll WIP)
 - GPS:   LA.UM.9.6.2.r1-03300-89xx.0
 - Time:  LA.UM.9.6.2.r1-03300-89xx.0
 - Radio and IMS: LA.UM.9.6.2.r1-03300-89xx.0

Fixes:
 - AudioFX: FixedUp AudioFX (Source)
 - FixedUp Dirac back-end (Tree)
 
Optimizations:
 - Recorder: Set maxinum meida record to 60fps
 - IMS: Allow com.qualcomm.location to run in the background
 - APEX: Flatten APEXs for performance
 - Bluetooth: Disable clean turn on
 - Porps: Set vendor.audio.adm.buffering.ms to 3 
 - Props: Shorten wait time for services exit to optimize shutdown time
 - Rootdir: Add permission for /dev/sp_keymaster_ssr
 - Sepolicy: Adress system_server denials
 - Sepolicy: Address gmscore_app.te denials

Notes:
 - Restart SystemUI after Updating

## v4.0.3 (2021.02.21)
Mainline:
 - Add Dirac back-end support (for Fries Dirac)
 - Add support for 240FPS 1/8 slow motion
 - update Telephony overlays from LA.UM.9.2.1.r1-05500-sdm660.0

Fixes:
 - Re-Enable zRAM (2 GB)

Optimizations:
 - Disable V-Sync (Smoother Ui)
 - Move some props into his right path
 - Symlink metadata to existing sessions 
 - Disable foreground prefer_idle & reduce TA boost
 - import Hotword Enrollment blobs
 - Optimize thermal

## v4.0.2 (2021.02.15)
Mainline:
 - Build enforce
 - Update Kernel to Predator-Stormbreaker-X4.4 - 4.4.257
 - Updated fingerprint from Redfin - RQ1A.210205.004
 - Update telephony from LA.QSSI.11.0.r1-09400-qssi.0 (Now the RIL / VoLTE is way better)
 - Updated blobs from LA.UM.8.2.r1-07400-sdm660.0
 - Updated GPS blobs from LA.UM.9.12.r1-09500-SMxx50.0 to improve GPS accuracy
 - Updated GPS HAL from LA.UM.9.2.r1-01800-SDMxx0.0 to improve GPS accuracy
 - Updated thermal and Widevine blobs from jasmine V11.0.19.0 QDIMIXM

Fixes:
 - Fixed POSP bootanimation lag
 - Fixed Google Recorder
 - [temp] Removed L1 support to fix Netflix crashes
 - Improved idle drain
 - Add support for potato notch city
 - Fixed some issues that reported from the logs
 - (Hopefully) fix the WFD
 - Fixed Offline charing (it was activating the bootanimation at the same time, now it's only the offline charge)

Optimizations:
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

## v4.0.1 (2020.12.24)
Mainline:
 - Initial Official Release (Crispy)
 - Updated build fingerprint to Coral RQ1A.201205.008.
 - Updated kernel to Predator-Stormbreaker X4.2 - 4.4.248.
 - Fixed Hotspot with no password.
 - Fixed GBoard extra spacing over the navigation bar.
 - Added new offline charging animation with battery level.
 - Less boot time.

Notes:
 - Netflix is not working with L1 (crashes),
 - join the support chat to know how to remove L1
 - to get your netflix work for now until we fix it, thank you.
