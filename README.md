# android_device_xiaomi_cmi
For building TWRP for Xiaomi Mi 10 pro

TWRP device tree for Xiaomi Mi 10 pro

## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Android Q Support

TO-DO:

- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/cmi" name="PitchBlackRecoveryProject/android_device_xiaomi_cmi" remote="github" revision="android-10.0-pre" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_cmi-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/cmi/recovery.img
```

## Other Sources

Precompiled Stock One

## Thanks
