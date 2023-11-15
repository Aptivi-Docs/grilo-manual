---
description: Upgrading GRILO on Windows!
---

# 🖥 Windows

To upgrade GRILO in your Windows system, replace the current GRILO executable with the latest version.

1. Ensure that you have all the required software installed
2. Download the latest core ZIP file from this page
3. Unpack the ZIP archive to any folder of your choice
4. Open your favorite terminal emulator, like ConEmu, and change the working directory to a folder containing the GRILO executable.
   * .NET Framework 4.8 version of GRILO is located at `net48`
   * .NET 6.0 version of GRILO is located at `net6.0`
   * .NET 7.0 version of GRILO is located at `net7.0`
   * .NET 8.0 version of GRILO is located at `net8.0`
5. Execute `mono GRILO.Bootloader.exe` for .NET Framework or `dotnet GRILO.Bootloader.exe` for .NET 6.0, 7.0, or 8.0 to start the bootloader
