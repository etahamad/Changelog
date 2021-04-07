## Potato Open Sauce Project or POSP, for short.
<img src="https://raw.githubusercontent.com/PotatoProject/manifest/dumaloo-release/XDAThread/main.png">

This Page is now live on [Notion](https://www.notion.so/etahamad/POSP-Changelogs-for-Redmi-Note-7-lavender-7e698ecf28dd435e995046edc76a49f7) check it out!

## *v4.1.3 (2021.04.06)*
- [WLAN] Optimize 5GHz
- [SEPolicy] Fix some camera denials
- [Power HAL] Fix AUDIO_LAUNCH log spam
- [Hardware] Build Compiled using msm8998 R HALs

## *v4.1.1 (2021.03.30)*
 - [DRM] Completely fixed Netflix with L1

>> Launcher: We have switched to Lawinchair as default launcher, but idk how it's gonna affect Pixel Launcher, so if you faced any weird issues with Pixel Launcher, please don't report.

---------------------------------------

## *v4.1.0 (2021.03.29)*
 - [Kernel] Updated Kernel to Predator X4.4 - 4.4.263 Release
 - [WFD] Fixed Wifi Display
 - [GPS] Fixed 3D GPS Navigation "Offline GPS"
 - [DRM] Fixed Netflix random reboots with L1 
 - [Thermal] Switch to wayne thermal blobs
 - [Thermal] Loosen up thermal throttling thresholds to fix thermal issues like slow charging charging, etc
 - [Overlays] Updated some vibration patterns from pixel 2 
 - [Overlays] Removed all-caps text for buttons
 - [Overlays] Add SimpleDeviceConfig from ProtonAOSP
 - [I/O Rap] Improve apps launch time
 - [Power HAL] Tune schedtune boost to match redfin SPP2
 - [CPU] Add dynamic stune boost and input boost 
 - [Prop] Optimized shutdown time by a bit
 - [SurfaceFlinger] Switched to AOSP SurfaceFlinger "smoother than CAF"
 - [General] Switch to sdfat driver for exfat

>> Netflix: Since First Release of A11, Netflix never worked with L1 on lavender, I have done some *Initial* fixes on it, but i didn't test because i don't have Netflix Account, btw, just test with/out Blur and check if it's Reboots or not.

>> GPS: The reason why offline gps wasn't working is because you was testing it in a closed area like home, etc, just go out, or go to your roof, or any open area and check.

>> Battery: YES, we do improved battery SOT.

## *v4.0.6 (2021.03.15)*
 - [Kernel] Updated Kernel to Predator X4.4-r1 - 4.4.258
 - [Blobs] Added qrtr blobs
 - [Power HAL] Switched to AIDL Power HAL
 - [Audio HAL] Switched to audio hal v4
 - [WLAN] Disabled WLAN Firmware loggings
 - [AudioFX] Nuked Dirac From Settings + Dirac QS Tile (A new QS for AudioFX itself will be added later)

---------------------------------------

## *v4.0.5 (2021.03.08)*
 - [DeviceSettings] Added Clear Speaker
 - [Blobs] ESE:   LA.UM.9.6.2.r1-03300-89xx.0
 - [Blobs] Media: LA.UM.9.6.2.r1-03300-89xx.0
 - [Blobs] WFD:   LA.UM.9.6.2.r1-03300-89xx.0 (WFD stll WIP)
 - [Blobs] GPS:   LA.UM.9.6.2.r1-03300-89xx.0
 - [Blobs] Time:  LA.UM.9.6.2.r1-03300-89xx.0
 - [Blobs] Radio and IMS: LA.UM.9.6.2.r1-03300-89xx.0
 - [AudioFX] FixedUp AudioFX (Source) // FixedUp Dirac back-end (Tree)
 - [Recorder] Set maxinum meida record to 60fps
 - [IMS] Allow com.qualcomm.location to run in the background
 - [Bluetooth] Disable clean turn on
 - [Porps] Set vendor.audio.adm.buffering.ms to 3 
 - [Props] Shorten wait time for services exit to optimize shutdown time
 - [Rootdir] Add permission for /dev/sp_keymaster_ssr
 - [Sepolicy] Adress system_server denials
 - [Sepolicy] Address gmscore_app.te denials

---------------------------------------

## *v4.0.3 (2021.02.21)*
 - [AudioFX] Add Dirac back-end support (for Fries Dirac)
 - [Camera] Add support for 240FPS 1/8 slow motion
 - [Overlay] update Telephony overlay from LA.UM.9.2.1.r1-05500-sdm660.0
 - [zRAM] Re-Enable zRAM (2 GB)
 - [Display] Disable V-Sync (Smoother Ui)
 - [Props]Move some props into his right path
 - [APEX] Symlink metadata to existing sessions 
 - [Kernel] Disable foreground prefer_idle & reduce TA boost
 - [Blobs-GMS] Import Hotword Enrollment blobs
 - [Thermal] Optimized

---------------------------------------

## *v4.0.2 (2021.02.15)*
 - [UX] Build enforce
 - [Kernel] Update to Predator-Stormbreaker-X4.4 - 4.4.257
 - UpdateD Telephony from LA.QSSI.11.0.r1-09400-qssi.0 (Now the RIL / VoLTE is way better)
 - Updated blobs from LA.UM.8.2.r1-07400-sdm660.0
 - Updated GPS blobs from LA.UM.9.12.r1-09500-SMxx50.0 to improve GPS accuracy
 - Updated GPS HAL from LA.UM.9.2.r1-01800-SDMxx0.0 to improve GPS accuracy
 - Updated thermal and Widevine blobs from jasmine V11.0.19.0 QDIMIXM
 - Fixed POSP bootanimation lag
 - Fixed Google Recorder
 - [temp] Removed L1 support to fix Netflix crashes
 - Improved idle drain
 - Add support for potato notch city
 - Fixed some issues that reported from the logs
 - (Hopefully) fix the WFD
 - Fixed Offline charing (it was activating the bootanimation at the same time, now it's only the offline charge)
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

---------------------------------------

## *v4.0.1 (2020.12.24)*
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
