# mtpmount
Mounts Media Transfer Protocol (MTP) devices as (removable) drives on Windows for access via command line. Essentially, this lets you treat your phone/camera/etc as a USB drive, allowing you to run commands such as ```robocopy``` on your device. Note that functionality may be restricted by device functionality (e.g. some cameras may not allow write access at all, whether from mtpmount or simply through File Explorer).

[![License](https://img.shields.io/badge/license-WTFPL-brightgreen?style=plastic)](https://github.com/hst125fan/mtpmount/blob/master/license.md)

Project is built using Visual Studio 2022. An installation of [Dokan](https://dokan-dev.github.io/) is required for this program to run. The current version was built with Dokan v2.3.0.1000. Older versions **will not work at all.** Newer versions will be tested once they receive stable releases.

Usage only from command line. Once mtpmount executable is in a %PATH% directory, these commands should do it:

- ```mtpmount list available```: This shows you the connected MTP devices/storages.
- ```mtpmount mount #x```: Mount a storage media as drive. x is an Index received from previous command.
- ```mtpmount unmount #x```: Unmount it again once you are done.

In addition to that, you can also mount a storage by its name:
- ```mtpmount mount devicename storagename driveletter```.
Also, the letter of the virtual drive can be set as shown in the example. This makes things easier when used in a script.

Other commands are available in the program's built-in help functions.

# Binaries
Binaries are available in the Releases tab.

# Build it yourself
1. Install Dokan (see above). You will need the "full" package (including development content), the MSI installers have these components opted out by default.
2. Install Visual Studio 2022 (if you don't have that already). Community works fine.
3. Clone this repo.
4. Open mtp-2-drive.sln in Visual Studio.
5. Build target "mtpmount" in desired configuration (Debug/Release/x86/x64)

## Testing
mtp-2-drive.sln also contains a "tests" target, which contains some integration tests for the most important features/use cases. The tests will automatically run on build. If you need to debug them, you can do so by starting tests_dbg with attached debugger (F5).

## Issues
If you run into any issues with mtpmount, please check the issues to see if a similar issue has already been opened. Feel free to like or add new information to a similar issue if one already exists. If no issue exists, please create an issue.

## Disclaimer
This program mounts your device's storage in an unconventional manner for the purposes of accessing said device as a standard storage device instead of as an MTP device. **I am not responsible for any loss of data that occurs related to or directly resulting from usage of this program.** I have tested mtpmount to the best of my ability and with the equipment that I have, and I will never release software that I do not believe to be safe and functional. That said, data loss may still occur. **If you ever lose data as a result of using this program,** please submit an issue with exactly what happened so I can do my best to make sure it doesn't happen again.
