### How to build:

1. Establish [Android build environment](https://source.android.com/setup/initializing) and install [repo](https://source.android.com/docs/setup/develop#installing-repo).

2. Initialize repo:

```
repo init -u https://android.googlesource.com/kernel/manifest -b common-android13-5.15-lts
curl --create-dirs -L -o .repo/local_manifests/manifest_brcm_rpi4.xml -O -L https://raw.githubusercontent.com/raspberry-vanilla/android_kernel_manifest/android-13.0/manifest_brcm_rpi4.xml
```

3. Sync source code:

```
repo sync
```

4. Compile:

```
BUILD_CONFIG=common/build.config.rpi4 build/build.sh
```

Compiled kernel Image, dtbs, and overlays can be found in `out/common/arch/arm64/boot` directory.

Replace existing files in `device/brcm/rpi4-kernel` directory of the Android source tree to include them in Android 13 build. You can also replace existing files in the boot partition of Raspberry Pi 4 Android 13 image.
