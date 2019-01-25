## Operating System
* Do not install any AntiVirus product, if you like to use an AV then Windows Defender is good enough as proven in 'independent' AV tests. 
* Use only a good NAT Firewall and Sandboxie, sandbox untrusted or unknown stuff. Sandboxie has no performance drops unless you use it 'cracked' or load huge apps into it.
* Change Core Parking (only in XP, 7 and 8) - Windows 10 controls it automatically already.




### Windows 7 vs. Windows 10

Gaming on Windows 10 is not nessary better or worst, it's depending on several factors such as game development API, Engine itselt, if the game was 'designed' and 'optimized' for Windows 10/7, the driver and driver profiles and many more things. 

[![](http://img.youtube.com/vi/RkHFYKDOo74/0.jpg)](http://www.youtube.com/watch?v=RkHFYKDOo74 "Windows 7 Vs. Windows 10 Game Performance (right-click and open it in a new Browser tab)")

Application(s) impact
---------------

Some applications and their drivers from external devices like [a mouse can cause serious FPS drops](https://old.reddit.com/r/Doom/comments/8a1m9s/psa_deactivate_the_new_razer_chroma_option_in/).


### Fix Memory Issue before with Build 1607 (Anniversary Update)

* Download [EmptyStandbyList](https://wj32.org/wp/software/empty-standby-list/) and put it under e.g. C:\ (ensure you don't move this file)
* Right click > Properties and select 'Run as Admin' under compatibility.
* Open your Task Scheduler > Create Task (on the far right).
* General Tab (give it a name, doesn't matter which one!). Under security options > Change user or group > Advanced > Find Now > go down and choose SYSTEM (important to make it run silently in the background). Tick 'Run with highest privileges' and 'Hidden' at the bottom. You can find an example [here](https://stackoverflow.com/questions/6568736/how-do-i-set-a-windows-scheduled-task-to-run-in-the-background).
* Click Triggers Tab > New > On a schedule > One Time. Tick repeat task every 5 minutes (possibly excessive but it causes no issues). Also choose 'for the duration of: indefinitely'
* Actions tab > Start A program > Point to the EmptyStandbyList.exe file.
* The Standby memory is automatically cleared every 5 mins.


Task Scheduler
---------------

List of Windows tasks to disable (privacy & performance related):

* \Microsoft\Windows\Application Experience > AitAgent, ProgramDataUpdater
* \Microsoft\Windows\Autochk > Proxy
* \Microsoft\Windows\Customer Experience Improvement Program> Consolidator, KernelCeipTask, UsbCeip
* \Microsoft\Windows\DiskDiagnostic > Microsoft-Windows-DiskDiagnosticDataCollector
* \Microsoft\Windows\Maintenance > WinSAT
* \Microsoft\cSystemRestore > SR
* \Microsoft\Windows\WindowsBackup > ConfigNotification
* \Microsoft\Windows Defender > MP Scheduled Scan
* \Library\Microsoft\Windows\WindowsColorSystem\Calibration Loader (disable it if you use your own Display Color Profile)
* \Microsoft\\Microsoft\CDPUserSvc (see [here](https://account.microsoft.com/privacy/activity-history))



##### **The following workaround is specifically for Windows 1703 >= 1803**:


Some games might have random stutter because Windows tries to free some resources (more or less good) which might causes game stutters. A more detailed explanation can be found to the issue over [here](https://forums.guru3d.com/threads/fix-game-stutter-on-win-10-1703-1803.420251/page-12#post-5590635). Possible workarounds in form from batch files or small utilities can be found [here](https://forums.guru3d.com/threads/fix-game-stutter-on-win-10-1703-1803.420251/).

### Power Management

* Set power setting to maximum performance if you graphic card driver has an 'maximum performance' settings enable it, this will ensure that the GPU uses it's full potential. 


### GameDVR + GameBarPresenceWriter

```bash
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\System\GameConfigStore]
"GameDVR_Enabled"=dword:00000000
"GameDVR_FSEBehavior"=dword:00000002
"GameDVR_FSEBehaviorMode"=dword:00000002
"GameDVR_HonorUserFSEBehaviorMode"=dword:00000000
"GameDVR_DXGIHonorFSEWindowsCompatible"=dword:00000000
"GameDVR_EFSEFeatureFlags"=dword:00000000
"Win32_AutoGameModeDefaultProfile"=hex:02,00,01,00,00,00,c4,20,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00
"Win32_GameModeRelatedProcesses"=hex:01,00,01,00,01,00,c0,00,c6,02,50,54,c7,02,\
  70,00,61,00,6e,00,65,00,6c,00,2e,00,65,00,78,00,65,00,00,00,8c,00,4e,8d,e1,\
  74,b8,ed,d2,02,18,4c,c7,02,1e,00,00,00,b8,ed,d2,02,1e,00,00,00,0f,00,00,00,\
  30,e7,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00

; Disable GameBarPresenceWriter.exe (needs same like PowerShell removal higher rights) - Do not use it!
;[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsRuntime\ActivatableClassId\Windows.Gaming.GameBar.PresenceServer.Internal.PresenceWriter]
;"ActivationType"=dword:00000001
;"CLSID"="{cbfd414c-5037-3c98-a85e-a5e7ca509cfc}"
;"Server"="Windows.Gaming.GameBar.Internal.PresenceWriterServer"
; "TrustLevel"=dword:00000000
```