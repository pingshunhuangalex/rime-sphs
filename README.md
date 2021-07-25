# Rime XKJD

My user configs backup for [Rime XKJD](https://xkinput.gitee.io/)

Wanna give Rime XKJD a go? Check out my own version of [Rime XKJD Documentation](https://pingshunhuangalex.gitbook.io/rime-xkjd/)!

## Install

- Download the latest [Rime for Windows](https://github.com/rime/weasel/releases/latest)

- Install Rime in the default directory

- Download the latest Rime XKJD ([GitHub](https://github.com/xkinput/Rime_JD) | [Gitee](https://gitee.com/xkinput/Rime_JD))

- Install Rime XKJD in the default directory (the same directory as Rime), but unzip the installation tools in `D:\Rime XKJD`

- Right-click the input method icon at the bottom-right of the screen and hit `Quit`

- Replace all default configs in `C:\Users\%USERNAME%\AppData\Roaming\Rime` with the user configs in this repo (including the hidden git folder, so all future modifications can be managed by git)

- Copy the theme preview file (`color_scheme_sphs.png`) from `C:\Users\%USERNAME%\AppData\Roaming\Rime\preview` to `C:\Program Files (x86)\Rime\weasel-<latest version>\data\preview`

- After an OS restart, activate the input method (add Rime in `Start -> Settings -> Time & Language -> Language (Chinese)` if it's not added automatically during the installation)

- Right-click the input method icon at the bottom-right of the screen and hit `Redeploy`

## Update

- Update Rime: right-click the input method icon at the bottom-right of the screen and hit `Check for updates`

- [All your user configs will be lost after the Rime XKJD update] Backup the entire user configs folder including git configs (`C:\Users\%USERNAME%\AppData\Roaming\Rime`)

- Update Rime XKJD: go to the installation tools folder and run the update script (`D:\Rime XKJD\Rime_JD\Tools\SystemTools\WindowsTools\update.bat`), or just re-intialise everything using the start script (`D:\Rime XKJD\start.bat`)

- Right-click the input method icon at the bottom-right of the screen and hit `Quit`, so the Rime service is shut down before restoring your customisation

- Duplicate the entire user configs folder without git configs (`C:\Users\%USERNAME%\AppData\Roaming\Rime`) so changes from the official repo can be isolated

- Revert the entire user configs folder including git configs (`C:\Users\%USERNAME%\AppData\Roaming\Rime`) to restore all the customisation

- Merge the duplicated folder with changes from the official repo into the user config folder (so you can see what's been changed after the update)

- Review all changes carefully to ensure all conflicts are resolved between your customisaion and changes from the official repo

- Restart your OS to bring back the Rime service

- Right-click the input method icon at the bottom-right of the screen and hit `Redeploy`

- Right-click the input method icon at the bottom-right of the screen and hit `Sync user data`

## Uninstall

- Uninstall Rime using the Windows `Programs and Features`, followed by an OS restart

- Delete the folder in `C:\Program Files (x86)\Rime`

- Delete the installation tools in `D:\Rime XKJD`

- Delete the user configs in `C:\Users\%USERNAME%\AppData\Roaming\Rime`

- Clean the registry and any residue if needed
