## POSP 🥔
<img src="https://raw.githubusercontent.com/PotatoProject/manifest/dumaloo-release/XDAThread/main.png">

This Page is now live on [Notion](https://www.notion.so/etahamad/POSP-Changelogs-for-Redmi-Note-7-lavender-7e698ecf28dd435e995046edc76a49f7) check it out!

---

## v4.2.1 10.07.21'

- [Kernel] Introduce Chips Kernel v1.1 - 4.4.274
    - based on predator stormbreaker x4.6
- [Power HAL] Major improvements
    - [Powerhint] Switched to `sysctl` to control energy aware
        - Energy aware feature control is previously done through debugfs,
        which will be deprecated, so move the control to sysctl.
    - [Powerhint] Bring back `interaction`, without the bugged ones
        - Bugged: `CPULittleClusterMinFreq`
    - [Powerhint] Adjustments
        - `idle_timer`  80 → 64
        - `TASchedtuneBoost` 20 → 10
        - General `LAUNCH`duration 3000 → 2500

---

## v4.2.0 08.06.21'

- [General] Reduced jitter [dc652a7](https://github.com/PotatoDevices/device_xiaomi_sdm660-common/commit/dc652a70533065279b97818eb0e026bf23b24750)
    - Less time opening Twitter photos, etc.

---

## v4.1.6 31.05.21'

- [General] User Build
    - We had some neverallows while tryna to build user builds with potato on lavender, we have removed all of them as device-sepolicy side and legacy-um side :).
- [Audio HAL] Switch to Audio HAL v5
- [SoundTrigger] Update audio configs and enable soundtrigger
    - Well, some people reported that they can't use Ok Google and stuff, this is now completely fixed.
- [Overlays] Don’t enforce RRO for all overlays
    - Fixed /product/overlay.
    - This makes many platform specific overlays with current system API on vendor partition which breaks newer android version compatibilities (broken stuffs in gsis).
- [zRAM] Update and optimize zRAM configuration
    - post_boot: Ensure SLAB_STORE_USER is disabled for zram kmem_caches
    - post_boot: update zRAM setting avoid 32 bit overflow
- [Power HAL] General optimizations
    - Relax memlat from post_boot and let libperfmgr handles it
    - powerhint: Decrease launch boost to 3sec
    - powerhint: Remove interaction boosts
        - Fixes `E: Slow writing to file: '/sys/devices/system/cpu/cpu0/cpufreq/scaling_min_freq' with value: '1113600'`
    - libperfmgr.rc: Let power hal start early
    - libperfmgr.rc: perfmgr now change dex2oat priorities along with overriding readahead to 128KiB after post-boot

---

## v4.1.5 10.05.21'

- [Blobs] Update WFD and Time blobs from LA.UM.9.2.r1-01800-SDMxx0.0
- [Audio HAL] Switch back to audio HAL v6
- [Audio Policy] Add some missing audio routes
- [AudioFX] Drop AudioFX in Fries
- [SurfaceFlinger] Update Frames consistently *~smoother ui*
- [GPS] Localise NTP to improve GPS TTFF
- [GPS] Improved GPS response time
- [WiFi] Disable TDLS OffChannel

 >> `AudioFX:` `Dirac` was buggy, it was not working by default, maybe later i will switch to prebuilt audio hal then `MiSound` will work.

---

## v4.1.4 19.04.21'

- [Kernel] Upstream Kernel to Predator Stormbreaker x4.5 - 4.4.266
- [Power HAL] Tune down schedtune boost *~saves some battery*
- [ART] Configure `dext2oat` for pre-optimization
- [AdaptLaunch] Improved apps launch time by a notable change
- [Overlays] Set fast charging indicator threshold to 10.8W (old was 7.5W)
- [USB] Enable support for USB Audio accessories
- [zRAM] Allocate zRAM values dynamically
- [zRAM] Fined Tune zRAM writeback

>> `zRAM:` *dynamically?* what's that? simple, we just made it 50% insist of a value, which means, for 3GB it will be ~1.3GB and for 4GB it will be ~1.8GB. The reason for why i did this is because zRAM mechanism takes some CPU performance to give you some free RAM, so exact value as google said (50% of your RAM) == balanced performance.

>> `DeviceSettings:`  app has been nuked to match the Stock AOSP lines.

---

## v4.1.3 07.04.21'

- [WLAN] Optimize 5GHz
- [SEPolicy] Fix some camera denials
- [Power HAL] Fix `AUDIO_LAUNCH` log spam
- [Hardware] Build Compiled using msm8998 R HALs

---

## *v4.1.1 (2021.03.30)*

- [DRM] Completely fixed Netflix with L1

>> Launcher: We have switched to Lawnchair as default launcher, but idk how it's gonna affect Pixel Launcher, so if you faced any weird issues with Pixel Launcher, please don't report.

---

## v4.1.0 29.03.21'

- [Kernel] Updated Kernel to `Predator X4.4 - 4.4.263` Release
- [WFD] Fixed Wifi Display
- [GPS] Fixed 3D GPS Navigation "Offline GPS"
- [DRM] Fixed Netflix random reboots with L1
- [Thermal] Switch to wayne thermal blobs
- [Thermal] Loosen up thermal throttling thresholds to fix thermal issues like slow charging charging, etc
- [Overlays] Updated some vibration patterns from pixel 2
- [Overlays] Removed all-caps text for buttons
- [Overlays] Add SimpleDeviceConfig from ProtonAOSP
- [I/O Rap] Improved apps launch time
- [Power HAL] Tune schedtune boost to match redfin SPP2
- [CPU] Add dynamic stune boost and input boost
- [Prop] Optimized shutdown time by a bit
- [SurfaceFlinger] Switched to AOSP SurfaceFlinger "smoother than CAF"
- [General] Switch to sdfat driver for exfat

>> Netflix: Since First Release of A11, Netflix never worked with L1 on lavender, I have done some Initial fixes on it, but i didn't test because i don't have Netflix Account, btw, just test with/out Blur and check if it's Reboots or not.

>> GPS: The reason why offline gps wasn't working is because you was testing it in a closed area like home, etc, just go out, or go to your roof, or any open area and check.

>> Battery: YES, we do improved battery SOT.

---

## v4.0.6 15.03.21'

- [Kernel] Updated Kernel to Predator X4.4-r1 - 4.4.258
- [Blobs] Added qrtr blobs
- [Power HAL] Switched to AIDL Power HAL
- [Audio HAL] Switched to audio hal v4
- [WLAN] Disabled WLAN Firmware loggings
- [AudioFX] Nuked Dirac From Settings + Dirac QS Tile (A new QS for AudioFX itself will be added later)

---

## v4.0.5 08.03.21'

- [DeviceSettings] Added Clear Speaker
- [Blobs] ESE: LA.UM.9.6.2.r1-03300-89xx.0
- [Blobs] Media: LA.UM.9.6.2.r1-03300-89xx.0
- [Blobs] WFD: LA.UM.9.6.2.r1-03300-89xx.0 (WFD stll WIP)
- [Blobs] GPS: LA.UM.9.6.2.r1-03300-89xx.0
- [Blobs] Time: LA.UM.9.6.2.r1-03300-89xx.0
- [Blobs] Radio and IMS: LA.UM.9.6.2.r1-03300-89xx.0
- [AudioFX] FixedUp AudioFX (Source) // FixedUp Dirac back-end (Tree)
- [Recorder] Set maxinum meida record to 60fps
- [IMS] Allow com.qualcomm.location to run in the background
- [Bluetooth] Disable clean turn on
- [Porps] Set [vendor.audio.adm.buffering.ms](http://vendor.audio.adm.buffering.ms/) to 3
- [Props] Shorten wait time for services exit to optimize shutdown time
- [Rootdir] Add permission for /dev/sp_keymaster_ssr
- [Sepolicy] Adress system_server denials
- [Sepolicy] Address gmscore_app.te denials

---

## v4.0.3 21.02.21'

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

---

## v4.0.2 15.02.21'

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
- Bigger QS Tiles by 6% for more check this comment: [https://git.io/JtPoQ](https://git.io/JtPoQ)
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

---

## v4.0.1 24.12.20'

- Initial Official Release (Crispy)
- Updated build fingerprint to Coral RQ1A.201205.008.
- Updated kernel to Predator-Stormbreaker X4.2 - 4.4.248.
- Fixed Hotspot with no password.
- Fixed GBoard extra spacing over the navigation bar.
- Added new offline charging animation with battery level.
- Less boot time.

>> Netflix is not working with L1 (crashes)
