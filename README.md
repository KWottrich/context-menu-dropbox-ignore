### Context Menu entries for Dropbox ignore
These registry entries add Context Menu (i.e. right click) options to Dropbox files and folders in Windows File Explorer to ignore (or un-ignore) files and folders.

![image](https://user-images.githubusercontent.com/3628457/172520857-97fce272-90c2-46b3-a481-978c050dbc47.png)

### Compatibility
* Windows 11
* Windows 10
* Windows 7 (should work, but **has not been tested**)

### Installation
Download and run [`InstallContextMenuEntries.reg`](Regedit/InstallContextMenuEntries.reg) and merge the entries into your registry. *I strongly encourage you to examine the contents of the file with a text editor BEFORE merging the entries, as you should do with any script you find on the internet!*

### Uninstallation
Download and run [`UninstallContextMenuEntries.reg`](Regedit/UninstallContextMenuEntries.reg) and merge the entries into your registry.

### Usage
To have Dropbox ignore a file or folder, right-click it and choose `Ignore from Dropbox`. To stop ignoring a file or folder, right-click it and choose `Un-Ignore from Dropbox`. These context menu entries will only be present within your Dropbox folder.

If you ignore a folder, Dropbox will also ignore all files and subfolders within that folder.

### Known Limitations
- Requires Dropbox to be installed at `C:\Program Files (x86)\Dropbox` for the icons to properly show in the Context Menu. If Dropbox is installed somewhere else, the context menu entries will still work, they will just have placeholder images instead of the Dropbox icon.
- A momentary powershell window popup will sometimes occur while the script is running to ignore/un-ignore a file or folder.
- Because the context menu only shows for folders that include "\Dropbox" in the path, the context menu entries will also show if you right click a file or folder within the Dropbox installation directory (or within any other folder named "Dropbox"). Ignoring or un-ignoring files or folders in the installation directory will not do anything, as Dropbox only observes the Dropbox folder for changes, not its installed location.
- I have not figured out a good way to only show the "Un-Ignore" entry if the file or folder is currently being ignored, and vice versa. If anyone has an idea of how to do this, please feel free to submit a PR!
