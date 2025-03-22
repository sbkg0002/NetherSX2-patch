<p align="center">
  <img width="312" height="312" src="/.github/assets/logo_light.png">
</p>

# NetherSX2-patch
These are Unofficial companion scripts for NetherSX2 to expand on the amazing work already done by Anon and EZOnTheEyes

They aim to do the following:
* Remove the unnecessary ad services bloat left in the apk
* Fix the RetroAchievements Notifications
* Expose more Global settings in the App Settings to the user
* Update the GameDB, Controller Support, and the Widescreen and No-Interlace Patches
* Add additional AetherSX2/NetherSX2 spesific fixes to the GameDB
* Resign the APK to Remove the Play Protect Warning

The Script can also be used to reupdate the GameDB, Controller Support, and Widescreen and No-Interlace Patches at a later date

## Prerequisites
Windows:
* Windows Vista or higher
* [The Java(TM) SE Development Kit](https://www.oracle.com/java/technologies/downloads/#jdk21-windows)

Linux:
* The OpenJDK package (this name my vary depending on your Linux Distro)
* Optional: The aapt, apksigner and xdelta3 packages (the script will attempt to use it's own binaries if these packages aren't installed)

macOS:

* Tested on macOS Sequoia but should work on any version with the requisite dependencies.
* A working `java` implementation. [Amazon Coretto](https://aws.amazon.com/corretto/) is bloat-free and recommended. Runtimes exist for Apple Silicon `aarch64` as well as Intel `x86_64`.
* [Android SDK Build-Tools](https://developer.android.com/about/versions/15/setup-sdk), specifically `aapt` and `apksigner` for your target-Android version. These can be downloaded using [Android Studio](https://developer.android.com/studio). `Tools > SDK Manager > SDK Tools > Android SDK Build-Tools`.
* [`xdelta`](https://github.com/jmacd/xdelta) installable via MacPorts or Homebrew.

Android:
* The [UniPatcher App](https://play.google.com/store/apps/details?id=org.emunix.unipatcher&hl=en_US&gl=US)
* A copy of the [AetherSX2 4248 apk](https://github.com/Trixarian/NetherSX2-patch/releases/download/0.0/15210-v1.5-4248.apk)
* One of the following:
  - [nethersx2.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2.xdelta) for the New Touchscreen Buttons
  - [nethersx2-oldui.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2-oldui.xdelta) for the Classic AetherSX2 Buttons

The rest comes prepackaged for your convenience

## Using these scripts
1. Run patch-apk.cmd (selecting Run Anyway when prompted) to patch your self-provided copy of the AetherSX2 4248 apk or to download a copy for you
2. Allow it to finish patching, building and signing your copy of NetherSX2
3. This will produce two copies of NetherSX2:
   - 15210-v1.8-4248-noads.apk - Comes with the Original GameDB
   - 15210-v1.8-4248-noads[patched].apk - Comes with the updated GameDB
4. Copy your prefered apk file to your phone and install it using your File Manager app (normally named Files or File Manager depending on your phone)

You can now rerun patch-apk.cmd with the above APK to update the GameDB, Controller Support, and the Widescreen and No-Interlace Patches at a later date without needing to repatch it each time
If you prefer the Older UI Design, drop the old-ui.xdelta file in the extras folder into the main folder (the one with patch-apk.cmd) to make the script revert NetherSX2 to the Older UI design

### Linux instructions

Run these commands:

```bash
chmod +x patch-apk.sh
# then run sh file
./patch-apk.sh
```

Credit: [TheKingFireS](https://github.com/TheKingFireS) + [BryanJacobs](https://github.com/BryanJacobs)

And there you go, you should now have an updated and bug fixed copy of NetherSX2 for your phone!

### macOS instructions

1. Update the `BUILD_TOOLS_VERSION` with the correct version of your `build-tools` install.

   > 💡 Your `build-tools` version can be found by listing: `/Users/${USER}/Library/Android/sdk/build-tools/`.

    ```bash
    export BUILD_TOOLS_VERSION="35.0.0" # The latest (at the time of writing) for Android 15.
    export BUILD_TOOLS_PATH="/Users/${USER}/Library/Android/sdk/build-tools/${BUILD_TOOLS_VERSION}"
    export PATH="${BUILD_TOOLS_PATH}:${PATH}"
    ```

2. Run `patch-apk.sh`:

    ```bash
    ./patch-apk.sh
    ```

    This will download `15210-v1.5-4248.apk`, patch, sign, and generate the following files:

    * `15210-v1.5-4248.apk`
    * `15210-v1.5-4248-noads.apk`
    * `15210-v1.5-4248-patched.apk`
    * `15210-v1.5-4248-patched.apk.idsig`

    These files can be copied to and sideloaded onto your Android device.

## Using Builder on Windows + Linux
1. Grab a copy of [NetherSX2-builder.zip](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/NetherSX2-builder.zip) file from this repository
2. Unzip the zip file by right clicking and selecting Extracting Here, and enter the now extracted builder folder
3. On Windows, run build-nethersx2.cmd to build your copy of the latest NetherSX2 in the PatchedAPK folder
4. On Linux, right click the build-nethersx2.sh file, click Properties and set it as executable, then double click on build-nethersx2.sh to run it
5. Alternatively if you're running it from the Linux terminal, use the following commands:
```bash
chmod +x build-nethersx2.sh
./build-nethersx2.sh
```
Now just copy the 15210-v1.5-4248-noads.apk in the PatchedAPK folder to your phone and install it using your File Manager app (normally named Files or File Manager depending on your phone)

## Using UniPatcher on Android
1. Install [UniPatcher](https://play.google.com/store/apps/details?id=org.emunix.unipatcher&hl=en_US&gl=US) from the Play Store, download the required [AetherSX2 4248 apk](https://github.com/Trixarian/NetherSX2-patch/releases/download/0.0/15210-v1.5-4248.apk) and prefered xdelta file
2. Start UniPatcher, tap the Patch file box and select the [nethersx2.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2.xdelta) or [nethersx2-oldui.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2-oldui.xdelta) file
3. Tap the Rom file box and select the 15210-v1.5-4248.apk file
4. Tap the Output file box and just tap save on the name it gives you (should be 15210-v1.5-4248 [patched].apk by default)
5. Tap the red save icon at the bottom right. A "Patching complete" message should popup if it worked

Now just install the 15210-v1.5-4248 [patched].apk file using your File Manager app (normally named Files or File Manager depending on your phone)

## Installing NetherSX2
One you've used one of the above methods to create your NetherSX2 apk, it's time to install it on your phone

1. Backup your files. The easiest method is to use the AetherSX2's built in Transfer Data function by using it's Export feature to move your files to an external folder. This will backup your bios files, memcards, save states, game settings, covers and texture packs
2. After backing up your files, you need to remove any previous copies of AetherSX2 or NetherSX2. Do this by Uninstalling the app normally. Be sure NOT to keep any files if prompted
3. With the Backup and Uninstalls done, all that remains is to navigate to where you put your NetherSX2 apk with your File Manager (named Files or File Manager depending on your phone) and tapping it to install it to your phone
4. Once installed, run the app and configure it normally. Once at the Game List screen, you can access the Transfer Data/Backup Data feature and Import the files you exported earlier by navigating to the folder you put all your backed up files. This should import your bios files, memcards, save states, game settings, covers and texture packs
5. Now spend some time redoing the Global App Settings and you should be ready to go

## Downloads
### Stable
* [NetherSX2-builder.zip](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/NetherSX2-builder.zip) - Alternate way to build the NetherSX2 APK for yourself with these fixes already pre-applied. It can be used with this script to update it's contents
* [NetherSX2-patch.zip](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/NetherSX2-patch.zip) - Copy of this script
* [nethersx2.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2.xdelta) - The xdelta patch that can be applied to the AetherSX2 4248 apk with any patching program that supports the format and comes with all the changes pre-applied. This allows the creation of NetherSX2 on systems other than Windows, including Android when using the UniPatcher application
* [nethersx2-oldui.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.8/nethersx2-oldui.xdelta) - Same as the above, but only using the classic AetherSX2 buttons
### Development Builds
* [NetherSX2-builder.zip](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.9-dev/NetherSX2-builder.zip) - Alternate way to build the NetherSX2 APK for yourself with these fixes already pre-applied. It can be used with this script to update it's contents
* [NetherSX2-patch.zip](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.9-dev/NetherSX2-patch.zip) - Copy of this script
* [nethersx2.xdelta](https://github.com/Trixarian/NetherSX2-patch/releases/download/1.9-dev/nethersx2.xdelta) - The xdelta patch that can be applied to the AetherSX2 4248 apk with any patching program that supports the format and comes with all the changes pre-applied. This allows the creation of NetherSX2 on systems other than Windows, including Android when using the UniPatcher application


NOTE: No APKs are provided due to licensing issues. You have to build it yourselves using the above methods

## Credits
* PCSX2: <https://github.com/PCSX2/pcsx2>
* EZOnTheEyes: <https://www.youtube.com/@EZOnTheEyes>
* Xdelta-GPL: <https://github.com/jmacd/xdelta-gpl>
* cmdcolor: <https://github.com/alecmev/cmdcolor>
* md5sums: <http://www.pc-tools.net/win32/md5sums>
* Android Keystore: <https://github.com/jorfao/pkStore>
* Alternate Keystore: <https://github.com/tytydraco/public-keystore>
* Android build-tools: <https://androidsdkmanager.azurewebsites.net/Buildtools>
