---
description: Installing GRILO on Windows!
---

# 🖥 Windows

There are separate versions of GRILO: the version which runs .NET Framework 4.8 bootable applications and versions that run from .NET 6.0 to .NET 8.0.

Before performing the installation, your Windows system must meet the following requirements:

| System     | Framework                                                                                                                                                                                                     | Terminal                                                  |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Windows 7+ | [.NET 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0), [.NET 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0), or [.NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) | [ConEmu](https://conemu.github.io/) or Windows 10 cmd.exe |

We advice you to use the terminal emulation software capable of displaying the VT sequences on systems older than Windows 10. GRILO is currently not color-heavy, but will be in the future.

## Installation

To install GRILO to your Windows system, follow these steps:

1. Ensure that you have all the required software installed
2. Download the latest core ZIP file from this page
3. Unpack the ZIP archive to any folder of your choice
4. Open your favorite terminal emulator, like ConEmu, and change the working directory to a folder containing the GRILO executable.
   * .NET Framework 4.8 version of GRILO is located at `net48`
   * .NET 6.0 version of GRILO is located at `net6.0`
   * .NET 7.0 version of GRILO is located at `net7.0`
   * .NET 8.0 version of GRILO is located at `net8.0`
5. Execute `GRILO.Bootloader.exe` to start the bootloader
