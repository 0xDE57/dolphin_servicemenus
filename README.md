# dolphin_servicemenus
Right-Click Utilities for KDE Dolphin service menus. These files add new actions to the right-click menu's for Dolphin file explorer. These commands simply pass the file or folder as an argument to common utilities to solve various common tasks.

See Docs: https://develop.kde.org/docs/apps/dolphin/service-menus/


## How to install:
 1. Place the `.desktop` extensions you want into: `/usr/share/kio/servicemenus/`
 2. May need to make file executable: `chmod +x <menu>.desktop`
 3. Ensure the dependency for each command used is installed for your distro (eg: `pacman -S imagemagic` on arch)
 4. Changes should show immediately. If not; restart dolphin.
 
## Service Menus:
 * `convertImage.desktop`
    * action: Convert Image to JPEG (new file)
    * action: Convert Image to PNG (new file)
    * dependency: **imagemagic**
 * `convertVideo.desktop`
    * action: Convert to GIF (new file)
    * action: Convert to MVK (new file)
    * action: Convert to MOV (new file)
    * action: Convert to MP4 (new file)
    * dependency: **ffmpeg**
* `exifTool.deskstop`
    * action: View Exif Data (opens terminal)
        * Note: Terminal launch expects konsole as default. You may have to replace the command for your prefered terminal.
    * action: Remove Exif Data (overwrites existing file)
    * dependency: **ExifTool**
    * Note: ExifTool supports many filetypes: https://exiftool.org/exiftool_pod.html
 * `checksum.deskstop`
    * action: md5sum (terminal)
    * action: sha1sum (terminal)
    * action: sha256sum (terminal)
    * dependency: **md5sum sha1sum sha256sum**
        * likely already installed by many distros
 
## Tips:
You can add your own entries to extend or customize the arguments passed to the utilities.

To view output from the terminal without the terminal automatically closing, we can pass `--noclose`:
`konsole --noclose -e <command>`

More service menus can be found:
* https://store.kde.org/browse?cat=102&ord=latest
