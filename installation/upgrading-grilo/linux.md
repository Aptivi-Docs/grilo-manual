---
description: How to upgrade GRILO on Linux!
---

# 🐧 Linux

To upgrade GRILO in your Linux system, replace the current GRILO executable with the latest version.

1. Ensure that you have all the required software installed
2. Download the latest core RAR file from this page
3. Unpack the RAR archive to any folder of your choice
4. Open your favorite terminal emulator, like ConEmu, and change the working directory to a folder containing the GRILO executable.
   * .NET Framework 4.8 version of GRILO is located at `net48`
   * .NET 6.0 version of GRILO is located at `net6.0`
5. Execute `mono GRILO.Bootloader.exe` for .NET Framework or `dotnet GRILO.Bootloader.exe` for .NET 6.0 to start the bootloader
