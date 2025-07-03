# Realme sm6375 (10 Pro / 9 Pro / 9 5G / Q5) kernel from LineageOS added KSUN + SuSFS with factory spoofing

- Fork of kernel for sm6375 from LineageOS with added KSUN Nightly which is root solution and hiding by SuSFS with spoofing as real device real device RMX3661 model with Realme UI 6.0 (Android 15) matching 1:1.
- All features, except OverlaysFS Auto Kstat Support on SuSFS, proceed into an invisible root experience for all apps, including Revolut, bank, ChatGPT, goverment apps etc.
- Custom-modified boot, dtbo, kernel images, and source code on every release.
- Not working Pixelify files (use a LSPosed module for unlimited GPhotos backup).

Tested devices with Lineage:

- Realme 10 Pro​
  - SoC: sm6375, Snapdragon 695
  - codename: luigi
  - IDs:
    - RMX3660,
    - RMX3661,
    - RMX3663.
  - On v2 newest release based on KernelSU Next `v1.0.8` tag.

- Realme 9 Pro​
  - SoC: sm6375, Snapdragon 695
  - codename: oscar
  - IDs:
    - RMX3471,
    - RMX3472.
  - Confirmed by user on v1 in release based on KernelSU Next `Next` feature branch, when you are using v2 dedicated boot/dtbo to oscar series give us feedback if it is working on [post in XDA](https://xdaforums.com/t/kernel-unofficial-ksun-next-susfs-realme-10-pro-lineageos-22-2-with-spoofing-realme-ui-6-0-stable-5-4-292-qgki-frpunlocking-15-0.4745580/).

Possible devices which can work with kernel and/or boot images (v2)

- Realme 9 5G
  - SoC: sm6375, Snapdragon 695
  - codename: oscar
  - IDs:
    - RMX3474.
  - Needs testers, please write [post in XDA](https://xdaforums.com/t/kernel-unofficial-ksun-next-susfs-realme-10-pro-lineageos-22-2-with-spoofing-realme-ui-6-0-stable-5-4-292-qgki-frpunlocking-15-0.4745580/) if it is working in any way.     
 
- Realme Q5
  - SoC: sm6375, Snapdragon 695
  - codename: oscar
    - IDs: RMX3478.
  - Needs testers, please also write [post in XDA](https://xdaforums.com/t/kernel-unofficial-ksun-next-susfs-realme-10-pro-lineageos-22-2-with-spoofing-realme-ui-6-0-stable-5-4-292-qgki-frpunlocking-15-0.4745580/) if it is working in any way.     

## Installation Steps for luigi

Tested on 10 Pro:

- [lineage-22.2-20250614-nightly-luigi-signed.zip](https://mirrorbits.lineageos.org/full/luigi/20250614/lineage-22.2-20250614-nightly-luigi-signed.zip) 
- [lineage-22.2-20250621-nightly-luigi-signed.zip](https://mirrorbits.lineageos.org/full/luigi/20250621/lineage-22.2-20250621-nightly-luigi-signed.zip)
- [lineage-22.2-20250628-nightly-luigi-signed.zip](https://mirrorbits.lineageos.org/full/luigi/20250628/lineage-22.2-20250628-nightly-luigi-signed.zip)

If you don't have [LineageOS recovery](https://mirrorbits.lineageos.org/full/luigi/20250614/vendor_boot.img), flash it by:

```
fastboot flash vendor_boot vendor_boot.img
fastboot reboot recovery
```

After flashing LineageOS and/or MindTheGApps, boot into LOS recovery fastboot (preffered) or factory fastboot and flash [latest boot and dtbo images](https://github.com/frpunlocking-com/android_kernel_realme_sm6375/releases) by:

```
fastboot flash boot_a boot.img
fastboot flash dtbo_a dtbo.img
fastboot flash boot_b boot.img 
fastboot flash dtbo_b dtbo.img
fastboot reboot
```

After device boots, install [Kernel SU Next Manager v1.0.8 (Latest Nightly)](https://nightly.link/KernelSU-Next/KernelSU-Next/workflows/build-manager-ci/next/Manager.zip).

Confirmed safe for dirty flash on 2025‑06‑21 build, no data loss observed.

Works seamlessly with MindTheGapps in [recovery](https://mirrorbits.lineageos.org/full/luigi/20250614/vendor_boot.img) (via Fastboot boot partition reflash).

## Kernel Highlights

- Built on Linux 5.4.292-qgki from LineageOS - includes upstream Android GKI compliance patches.
- KernelSU Next - latest version providing root access.
- SuSFS v1.5.5 - Android dynamic rootfs support.

## Enhancements & Fixes

- Seamless GKI‑based kernel integration for the real Realme 10 Pro device built from scratch.
- No bootloops or data errors in testing on real device as of 2025‑07‑02.
- Spoofing RMX3661 factory Android 15 Realme UI 6.0 fingerprint.

## Known Issues

No issues have been reported so far, but if any problems arise, please report them in the official thread on XDA or create a GitHub issue with a detailed description of the situation and attach screenshots or videos from the detectors.

## Data Insights for Tech Enthusiasts

The development of this kernel modification was primarily driven by Google's ongoing attempts to block rooted devices via Play Integrity API checks - an action that we, as developers and researchers, strongly oppose. Root access is essential for thorough security research, and its restriction undermines transparency and the right to repair. This custom kernel was carefully crafted to bypass these limitations, integrating KernelSU and SuSFS into an older 5.4 LineageOS kernel.

These kernel modifications are part of an academic project related to my master's thesis on the security analysis of consumer electronics at the military university. Modifying a legacy Chinese-modified Realme 10 Pro kernel was quite a challenge - imagine trying to assemble IKEA furniture without any instructions, missing half the screws, and using pieces meant for a completely different set. Yes, it was precisely that entertaining.

| LOC Metric v1                 | Lines of Code (LOC) |
|----------------------------|--------------------:|
| Total (A + R + C)          | ~25.2k              |
| Added (A)                  | ~13.4k              |
| Removed (R)                | ~5.1k               |
| Changed (C)                | ~6.7k               |
| Unique LOC (`*.rej` files) | ~2.3k               |

**Note:** `.orig` and `.rej` files are intentionally preserved within the repository as references. They document the manual interventions required when automatic patching failed - particularly valuable for other developers wrestling with similarly aged Chinese kernels (such as those based on QGKI) on Realme and Oppo devices.

## Credits & Resources

- KernelSU & KernelSU Next.
- SuSFS, susfs4ksu, and Wild Kernels.
- Big thanks to the Realme 10 Pro device maintainers and devs on LineageOS, testers, and the MindTheGapps maintainers and devs.

```

#include <std_disclaimer.h>
/*
* Your warranty is... Still valid??
*
* I am not responsible if you brick your device,
* dead SD card, installed viruses, burned battery
* and thermonuclear war, or you getting fired
* because the alarm app failed. Please do
* some research if you have any concerns
* about features included in this software
* before flashing it! You are choosing to
* make these strong modifications on your
* device, and if you point the finger at me
* for messing up your device,
* I will laugh at you.
* LICENSE.md
* Our modifications are GPLv2 licensed.
*/

```

# How do I submit patches to Android Common Kernels

1. BEST: Make all of your changes to upstream Linux. If appropriate, backport to the stable releases.
   These patches will be merged automatically in the corresponding common kernels. If the patch is already
   in upstream Linux, post a backport of the patch that conforms to the patch requirements below.

2. LESS GOOD: Develop your patches out-of-tree (from an upstream Linux point-of-view). Unless these are
   fixing an Android-specific bug, these are very unlikely to be accepted unless they have been
   coordinated with kernel-team@android.com. If you want to proceed, post a patch that conforms to the
   patch requirements below.

# Common Kernel patch requirements

- All patches must conform to the Linux kernel coding standards and pass `script/checkpatch.pl`
- Patches shall not break gki_defconfig or allmodconfig builds for arm, arm64, x86, x86_64 architectures
(see  https://source.android.com/setup/build/building-kernels)
- If the patch is not merged from an upstream branch, the subject must be tagged with the type of patch:
`UPSTREAM:`, `BACKPORT:`, `FROMGIT:`, `FROMLIST:`, or `ANDROID:`.
- All patches must have a `Change-Id:` tag (see https://gerrit-review.googlesource.com/Documentation/user-changeid.html)
- If an Android bug has been assigned, there must be a `Bug:` tag.
- All patches must have a `Signed-off-by:` tag by the author and the submitter

Additional requirements are listed below based on patch type

## Requirements for backports from mainline Linux: `UPSTREAM:`, `BACKPORT:`

- If the patch is a cherry-pick from Linux mainline with no changes at all
    - tag the patch subject with `UPSTREAM:`.
    - add upstream commit information with a `(cherry-picked from ...)` line
    - Example:
        - if the upstream commit message is
```
        important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>
```
        - then Joe Smith would upload the patch for the common kernel as
```
        UPSTREAM: important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>

        Bug: 135791357
        Change-Id: I4caaaa566ea080fa148c5e768bb1a0b6f7201c01
        (cherry-picked from c31e73121f4c1ec41143423ac6ce3ce6dafdcec1)
        Signed-off-by: Joe Smith <joe.smith@foo.org>
```

- If the patch requires any changes from the upstream version, tag the patch with `BACKPORT:`
instead of `UPSTREAM:`.
    - use the same tags as `UPSTREAM:`
    - add comments about the changes under the `(cherry-picked from ...)` line
    - Example:
```
        BACKPORT: important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>

        Bug: 135791357
        Change-Id: I4caaaa566ea080fa148c5e768bb1a0b6f7201c01
        (cherry-picked from c31e73121f4c1ec41143423ac6ce3ce6dafdcec1)
        [ Resolved minor conflict in drivers/foo/bar.c ]
        Signed-off-by: Joe Smith <joe.smith@foo.org>
```

## Requirements for other backports: `FROMGIT:`, `FROMLIST:`,

- If the patch has been merged into an upstream maintainer tree, but has not yet
been merged into Linux mainline
    - tag the patch subject with `FROMGIT:`
    - add info on where the patch came from as `(cherry picked from commit <sha1> <repo> <branch>)`. This
must be a stable maintainer branch (not rebased, so don't use `linux-next` for example).
    - if changes were required, use `BACKPORT: FROMGIT:`
    - Example:
        - if the commit message in the maintainer tree is
```
        important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>
```
        - then Joe Smith would upload the patch for the common kernel as
```
        FROMGIT: important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>

        Bug: 135791357
        (cherry picked from commit 878a2fd9de10b03d11d2f622250285c7e63deace
         https://git.kernel.org/pub/scm/linux/kernel/git/foo/bar.git test-branch)
        Change-Id: I4caaaa566ea080fa148c5e768bb1a0b6f7201c01
        Signed-off-by: Joe Smith <joe.smith@foo.org>
```


- If the patch has been submitted to LKML, but not accepted into any maintainer tree
    - tag the patch subject with `FROMLIST:`
    - add a `Link:` tag with a link to the submittal on lore.kernel.org
    - if changes were required, use `BACKPORT: FROMLIST:`
    - Example:
```
        FROMLIST: important patch from upstream

        This is the detailed description of the important patch

        Signed-off-by: Fred Jones <fred.jones@foo.org>

        Bug: 135791357
        Link: https://lore.kernel.org/lkml/20190619171517.GA17557@someone.com/
        Change-Id: I4caaaa566ea080fa148c5e768bb1a0b6f7201c01
        Signed-off-by: Joe Smith <joe.smith@foo.org>
```

## Requirements for Android-specific patches: `ANDROID:`

- If the patch is fixing a bug to Android-specific code
    - tag the patch subject with `ANDROID:`
    - add a `Fixes:` tag that cites the patch with the bug
    - Example:
```
        ANDROID: fix android-specific bug in foobar.c

        This is the detailed description of the important fix

        Fixes: 1234abcd2468 ("foobar: add cool feature")
        Change-Id: I4caaaa566ea080fa148c5e768bb1a0b6f7201c01
        Signed-off-by: Joe Smith <joe.smith@foo.org>
```

- If the patch is a new feature
    - tag the patch subject with `ANDROID:`
    - add a `Bug:` tag with the Android bug (required for android-specific features)

# Vibrator driver for HHG device
## How to merge the driver into kernel source tree

 1. Copy \${this_project}/drivers/hid/hid-aksys.c into \${your_kernel_root}/drivers/hid/

 2. Compare and merge \${this_project}/drivers/hid/hid-ids.h into \${your_kernel_root}/drivers/hid/hid-ids.h :
 Add the following code before the last line of this file

    ```c
		#define USB_VENDER_ID_QUALCOMM  0x0a12
		#define USB_VENDER_ID_TEMP_HHG_AKSY 0x1234
		#define USB_PRODUCT_ID_AKSYS_HHG  0x1000
    ```

 3. Merge \${this_project}/drivers/hid/Kconfig into \${your_kernel_root}/drivers/hid/Kconfig :
Add the following code before the last line of this file

		config HID_AKSYS_QRD
    		tristate "AKSys gamepad USB adapter support"
    		depends on HID
    		---help---
    		Support for AKSys gamepad USB adapter

    	config AKSYS_QRD_FF
    		bool "AKSys gamepad USB adapter force feedback support"
    		depends on HID_AKSYS_QRD
    		select INPUT_FF_MEMLESS
    		---help---
    		Say Y here if you have a AKSys gamepad USB adapter and want to
    		enable force feedback support for it.
    		
 4. Merge \${this_project}/drivers/hid/Makefile into \${your_kernel_root}/drivers/hid/Makefile :
 Add the following code at the end of this file

		obj-$(CONFIG_HID_AKSYS_QRD)	+= hid-aksys.o
		
 5. Modify your kernel's default build configuration file. Add the following two lines:

        CONFIG_HID_AKSYS_QRD=m
        CONFIG_AKSYS_QRD_FF=y
