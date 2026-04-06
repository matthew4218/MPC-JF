# MPC-JF - MPC-HC - MPC-BE launcher for Jellyfin Web

## Installation Steps

### 0. Download MPC-JF.zip
Download **latest for Jellyfin 10.11.+** : [MPC-JF.zip](https://github.com/Damocles-fr/MPC-JF/releases/)

### 1. Place Required Files
- Extract and move the MPC-JF folder to :
  ```
  C:\ProgramData\
  ```
- You should end up with: `C:\ProgramData\MPC-JF\` (with all files inside).

### 2 : If you don't use ***MPC-BE*** and his default path :
- Edit the file `MPC-JF.ps1` and **replace the path in the last line** with ***your own*** MPC.exe paths
- E.g. for MPC-BE default path : ``` & "C:\Program Files\MPC-BE\mpc-be64.exe" "`"$path`""/fullscreen ```

### 3. Install ViolentMonkey and my scripts
- In your browser, install ViolentMonkey extension :
https://addons.mozilla.org/fr/firefox/addon/violentmonkey/
###### Alternatively you can use TamperMonkey or any userscript extension

### 4. Install MPC-JF.js userscript
- Install the .js userscript, one click link : [MPC-JF.js](https://github.com/Damocles-fr/MPC-JF/main/MPC-JF.js)
- If your Jellyfin Server is not set the default adress ``` http://localhost:8096/ ```
	Edit `MPC-JF.js` to replace ``` http://localhost:8096/ ``` with your Jellyfin web URL, for exemple :
  ```
  // @match        http://192.168.1.10:8096/*
  ```
#### Don't forget the * at the end.
##### To find the installed `MPC-JF.js` Browser settings → Extensions → **Violentmonkey** → Options
##### → Go to **Installed Scripts** > ***`</>`***

###### MPC-JF.js can be put in Jellyfin JavaScript Injector plugin instead, but every play buttons in Jellyfin Web won't work anywhere else without MPC-JF.

### 5. Enable PowerShell Scripts Execution to allow MPC-JF.ps1
- In Windows 11, go to, Settings → Developers → PowerShell → Allow unsigned scripts
- Or if you can't find it :
	- Search for `PowerShell` in the Start menu, right-click it, and select **Run as Administrator**.
	- Type the following command and press Enter:
     ```
     Set-ExecutionPolicy RemoteSigned
     ```
- Or
     ```
     Set-ExecutionPolicy RemoteSigned -Force
     ```
### 6. Apply MPC-JF Registry Settings
- Run `MPC-JF.reg` and confirm changes.
- You may need to re-run `MPC-JF.reg` after major MPC Updates.

### 7. Done !
- You can test if it works already. If not, see Workaround below.

### Optionnal :  Hide the Powerscript window at MPC-JF launch
- `Install-MPC-JF-HiddenProtocol.ps1` must be in your default MPC-JF folder.
- It **require VBScript** installed (may not be installed by default on all Windows 11 installation)
- Run the file `Install-MPC-JF-HiddenProtocol.ps1` (Right click and ***Run with PowerShell***)

### Optional : Adjust Full-Screen Settings
- Edit "MPC-JF.ps1" located in ``` C:\ProgramData\MPC-JF ```
- At the end of the script, remove or add ```/fullscreen```

---

### Workaround : If MPC starts but fail to launch the media
- Your NAS/network drives must be mount with a letter like D:\ E:\ ... in Windows.
- Edit "MPC-JF.ps1" located in ``` C:\ProgramData\MPC-JF ```
  	- At the end of the file, just below : ``` # YOUR NAS CONFIG, IF NEEDED, ADD YOUR OWN WORKAROUND JUST BELOW ```
  	- Add this line : ``` $path = $path -replace "\\share\\SHAREFOLDER\\", "D:" ```
  	- In this, change ``` "\\share\\SHAREFOLDER\\" ```
  	  It should be the part of the path that appear in your NAS (and maybe your library path in JF), but not in the Windows explorer path of your movies. 
  	- Add double backslash ``` \\ ``` instead of single backslash ``` \ ``` in your own path, they are essential
  	- Replace "D:" with the drive letter of your NAS or drive in Windows.
  	- For exemple ``` $path = $path -replace "\\share\\MEDIA\\", "D:" ```
	That works for everything located in my NAS mounted as the D: drive in Windows, so D:\FILMS, D:\SERIES etc.
	``` "\\share\\\MEDIA\\" ``` depends of your NAS/drives configuration (see your NAS and Jellyfin library path to identify your issue)
  	- If you have other drives, do the same for them by adding lines below.
  	- No need to do add lines for every library folder, just one line for each different drive should be enough.

---

#### Files in C:\ProgramData\MPC-JF
- ``` MPC-JF.ps1 ``` : Do not delete. Main Script.
- ``` MPC-JF.reg ``` : Do not delete. You may need to run it again if the script don't run anymore
- ``` Install-MPC-JF-HiddenProtocol.ps1 ``` : One time run to hide the Powershell window at MPC launch. You may need to run it again if the script don't run hidden anymore
- ``` MPC-JF.js ``` : backup file of the main browser script, it's in ViolentMonkey in your browser

---

#### TIPS
- Sometimes if it stop working, because of idk, **MPC-JF updates** or some specific settings change, just **re-run** `MPC-JF.reg` .
- If MPC takes time to launch, it's because your HDD is in standby, the script is waiting for your HDD to respond. I have made a tiny watcher that wake up HDDs at JF Home screen for faster first play here : 
[jellyfin-nas-hdd-spinup](https://github.com/Damocles-fr/jellyfin-nas-hdd-spinup)
- To uninstall `Install-MPC-JF-HiddenProtocol.ps1` : run in Powershell :
     ```
     Remove-Item -Recurse -Force "HKCU:\Software\Classes\MPC-JF" -ErrorAction SilentlyContinue
     Remove-Item -Recurse -Force (Join-Path $env:LOCALAPPDATA "MPC-JF") -ErrorAction SilentlyContinue
     ```
- The .js userscript can be put in Jellyfin JavaScript Injector plugin instead, but every play buttons in Jellyfin Web won't work anywhere else without the .ps1 and MPC-JF.
- If you use the Firefox extension ``` Dark Reader ``` , it breaks Jellyfin pictures loading in browsers, desactivate it only for jellyfin : Go into Dark Reader settings while you have the Jellyfin page open (firefox menu bar), click to uncheck Jellyfin URL.

---

#### Need Help?
- Don't hesitate to open an [issue](https://github.com/Damocles-fr/MPC-JF/issues)
- **DM me** https://forum.jellyfin.org/u-damocles
- GitHub https://github.com/Damocles-fr/
