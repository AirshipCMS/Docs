## Auto Install Instructions
Click the above button to start the CLI installation on your Win64 machine. 

(You will get a warning that this installer is not signed with a digital signature. This is expected behavior. If you prefer, you may follow the manual install instructions below instead.)

## Manual Install Instructions
1. Download https://install.airshipcms.io/Win64/2.3.1/airship.exe
2. Download https://install.airshipcms.io/Win64/2.3.1/airship-server.exe
3. Create a new folder `C:\AirshipLauncher`.
   [include screenshots of the new folder]
4. Move `airship.exe` and `airship-server.exe` into the `C:\AirshipLauncher\` folder.
   [include gif of moving the files over from downloads to destination folder]
5. Open up Environment Variable System Settings.
   [include step by step instructions for opening environment variable system settings]
   [include gif demonstrating how to open the settings panel]
6. Select `PATH` and click the `Edit` button.
   [include gif showing where PATH is and the edit button is]
7. Add a new entry to this list of PATH variables, select the `C:\AirshipLauncher` folder.
   [include gif demonstrating how to add this new env]
8. Close all the Settings windows.
9. Open a CLI, either CMD.exe or PowerShell.exe to test.
10. In the CLI, run `airship version` and `airship help`.
