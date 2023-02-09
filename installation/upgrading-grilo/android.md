---
description: Upgrading GRILO on Android!
---

# 📱 Android

The only way to upgrade GRILO in Android is to unpack the updated kernel files manually. This method also works for bleeding-edge builds, though you have to use unzip instead. To upgrade, follow these steps:

1. Log in to the Ubuntu proot
   * `proot-distro login ubuntu`
2. Install `wget` to download the latest release from [this page](https://github.com/Aptivi/GRILO/releases).
   * `apt install wget`
   * `wget https://github.com/Aptivi/GRILO/releases/download/vx.x.x/vx.x.x-Core.rar`
3. Install `unrar` (from multiverse) to extract the files
   * `apt install unrar`
   * `unrar vx.x.x-Core.rar`
4. Execute `dotnet GRILO.Bootloader.dll`
