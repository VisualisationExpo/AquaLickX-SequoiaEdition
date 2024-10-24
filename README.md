### AquaLickX for Sequoia 15.0.1

# THIS IS THE LAST VERSION OF THIS THEME USING THIS METHOD OF THEMING
# 15.0.1 IS THE END STATION FOR AQUALICKX AS I'M MOVING ON TO A DIFFERENT EASIER AND SAFER MACOS THEMING OPTION.
# THE WAY OF MAKING THEMES LIKE THIS TAKES TOO MUCH OF A TOLL ON ME AND IT'S NOT SUSTAINABLE.


## NOTE:This theme is strickly for macOS Sequoia 15.0.1

## I see some errors when not having Reduce transparency active. I'm not fixing those.

## I would advice that you do use Reduce transparency. That way you also have a themed menu bar.
> In System Settings go to Accessibility - then Display - then activate Reduce transparency

# AquaLickX for macOS Sequoia 15.0.1
**A macOS Sequoia 15.0.1 theme that has some Aqua elements in it**

**PREVIEW** - subject to change
![LightModeAquaLickXPreview@2x.png](https://github.com/VisualisationExpo/AquaLickX-SONOMA145Edition/blob/main/LightModeAquaLickXPreview@2x.png?raw=true)

**DARK MODE PREVIEW**
![DarkModeAquaLickXPreview@2x](https://github.com/VisualisationExpo/AquaLickX-SONOMA145Edition/blob/main/DarkModeAquaLickXPreview@2x.png?raw=true)
---

### **GETTING READY**

----

> text edited and snagged from jslegendre [https://github.com/jslegendre/ThemeEngine]()

Note for Big Sur, Monterey and Ventura users:
If you want to edit system .car files it is no longer enough to remount the boot volume as read/write.
You will need to follow the steps below:

1. Disable SIP and authenticated-root:
In recovery mode, open Terminal and enter

`csrutil disable`

`csrutil authenticated-root disable`

Then reboot into macOS.

2. Identify the System Volume Disk Device Name
Run the mount command in Terminal to identify the devices of your system volume snapshot. Look for the device mounted at “/“, which identifies the system volume disk.  In the following example, this disk is `/dev/disk4s5s1`.
```
/dev/disk4s5s1 on / (apfs, sealed, local, read-only, journaled)
devfs on /dev (devfs, local, nobrowse)
/dev/disk4s4 on /System/Volumes/VM (apfs, local, noexec, journaled, noatime, nobrowse)
/dev/disk4s2 on /System/Volumes/Preboot (apfs, local, journaled, nobrowse)
/dev/disk4s1 on /System/Volumes/Data (apfs, local, journaled, nobrowse)
```
To get the actual name of the system volume disk, remove the final “sX” from the device. In the preceding example, the name of the system volume disk is `/dev/disk4s5`.

3. Mount a Live Version of the System Volume
Run the mount command in Terminal to mount the system volume disk to a temporary location. When running the mount command, always include the nobrowse mount option to prevent Spotlight from indexing the volume.

`mkdir /Users/<YOUR USER NAME>/livemount`

`sudo mount -o nobrowse -t apfs  /dev/disk4s5 /Users/<YOUR USER NAME>/livemount`

---

## Getting the AquaLickX theme copied over for use. Continue using the already open Terminal window

4. `cd ~/Downloads/AquaLickX-main/`
5. `sudo cp Aqua.car ~/livemount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/`
6. `sudo cp VibrantLight.car ~/livemount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/`
7. `sudo cp DarkAqua.car ~/livemount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/`
8. `sudo cp VibrantDark.car ~/livemount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/`
9. Bless your livemount directory with `sudo bless --mount /Users/<YOUR USER NAME>/livemount --bootefi --create-snapshot`

If you're on an Apple Silicon Mac then issue this `bless` command instead

`sudo bless --mount "$HOME/livemount/System/Library/CoreServices/" --setBoot --create-snapshot`


Reboot your Mac using the regular reboot mechanisms immediately after issuing the `bless` command described above.

**the command below will reboot your Mac then and there, so be careful unless you're certain that you have all your work saved in other applications** 

type `sudo reboot` in the existing Terminal window

---

### **TO DO:**
NOTHING - BECAUSE IT'S THE END OF THE LINE.

