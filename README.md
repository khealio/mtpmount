# mtpmount
Mounts Media Transfer Protocol (MTP) devices as (removable) drives on Windows for access via command line.

[![License](https://img.shields.io/badge/license-WTFPL-brightgreen?style=plastic)](https://github.com/hst125fan/mtpmount/blob/master/license.md)

Project is built using Visual Studio 2017. An Installation of Dokan is required for this program to run (https://dokan-dev.github.io/).

Usage only from command line. Once mtpmount executable is in a %PATH% directory, these commands should do it:

- ```mtpmount list available```: This shows you the connected MTP devices/storages.
- ```mtpmount mount #x```: Mount a storage media as drive. x is an Index received from previous command.
- ```mtpmount unmount #x```: Unmount it again once you are done.

In addition to that, you can also mount a storage by its name:
- ```mtpmount mount devicename storagename (driveletter)```.
Also, the letter of the virtual drive can be set as shown in the example. This makes things easier when used in a script.


# Binaries
CURRENTLY UNAVAILABLE - See the [original repo](https://github.com/hst125fan/mtpmount/releases) for old releases that require [Dokan 1.5](https://github.com/dokan-dev/dokany/releases/tag/v1.5.1.1000) to run.
You may build Dokan 2-requiring binaries from this repo, the main branch of which has not yet been updated from the parent repo. All current updates are done in the 2025-updates branch, which is in-progress, potentially buggy code.

# Build it yourself
1. Install Dokan (see above). You will need the "full" package (including development content), the MSI installers have these components opted out by default.
2. Install Visual Studio 2017 (if you don't have that already). Community works fine.
3. Check out repository.
4. Open mtp-2-drive.sln in Visual Studio.
5. Build target "mtpmount" in desired configuration (Debug/Release/x86/x64)

# Testing
mtp-2-drive.sln also contains a "tests" target, which contains some integration tests for the most important features/use cases. The tests will automatically run on build. If you need to debug them, you can do so by starting tests_dbg with attached debugger (F5).
