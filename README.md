# mtpmount
Mounts Media Transfer Protocol (MTP) devices as removable drives on Windows for access via command line. Essentially, this lets you treat your phone/camera/etc as a USB drive, allowing you to run commands such as ```robocopy``` on your device. Note that functionality may be restricted by device functionality (e.g. some cameras may not allow write access at all).

[![License](https://img.shields.io/badge/license-WTFPL-brightgreen?style=plastic)](https://github.com/hst125fan/mtpmount/blob/master/license.md)
[![Build status](https://ci.appveyor.com/api/projects/status/84yloiixlecablel?svg=true)](https://ci.appveyor.com/project/khealio/mtpmount)

Project is built using Visual Studio 2022. An installation of [Dokan](https://dokan-dev.github.io/) is required for this program to run. The current version was built with Dokan v2.3.0.1000. Older versions **will not work at all.** Newer versions will be tested once they receive stable releases.

Once mtpmount executable is in a %PATH% directory, these are the basic commands:

- ```mtpmount list available``` - This shows you connected MTP devices.
- ```mtpmount mount <device name> <storage name> <drive letter>``` - Mount storage media as a drive. The drive letter is up to you, as long as it is available.
- ```mtpmount unmount <drive letter>``` - Unmount the drive once you are done. This is the same as ejecting a USB drive, and should be done for safety. The device can then be unplugged.

These commands (and others) can also be shown by running mtpmount with no arguments. There is a built-in help function that can provide more information on individual commands.

# Installation
Download the latest release from the Releases tab (x86 or x64 depending on your OS and architecture). Place the executable somewhere accessible, or add it to your system's %PATH% if you feel so inclined. Run the executable in the terminal (or simply run ```mtpmount``` if the executable is in %PATH%).

# Build it yourself
1. Install Dokan (see above). You will need the "full" package (including development content).
    - The MSI installer will have these available; make sure "The entire feature will be installed" is selected for each feature.
2. Install Visual Studio 2022 (if it isn't already installed). Community works fine.
3. Clone this repo.
4. Open mtp-2-drive.sln from the cloned repo in Visual Studio.
5. Build in desired configuration (Debug/Release/x86/x64).

## Testing
mtp-2-drive.sln also contains a "tests" target, which contains some integration tests for the most important features/use cases. The tests will automatically run on build. If you need to debug them, you can do so by starting tests_dbg with attached debugger (F5).

## Issues
If you run into any issues with mtpmount, whether in usage or in building/working on the project, please check the issues to see if a similar issue has already been opened. Feel free to like or add new information to a similar issue if one already exists. If no issue exists, please create an issue and I'll take a look! (Feel free to try your hand at a fix and submit a PR if you feel so inclined).

## Disclaimer
This program mounts your device's storage in an unconventional manner for the purposes of accessing said device as a standard storage device instead of as an MTP device. **I am not responsible for any loss of data that occurs related to or directly resulting from usage of this program.** I have tested mtpmount to the best of my ability and with the equipment that I have, and I will never release software that I do not believe to be safe and functional. That said, data loss may still occur. **If you ever lose data as a result of using this program,** please submit an issue with exactly what happened so I can do my best to make sure it doesn't happen again.
