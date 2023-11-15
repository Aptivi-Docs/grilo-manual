---
description: Upgrading GRILO on Android!
---

# 📱 Android

The only way to upgrade GRILO in Android is to unpack the updated files manually. This method also works for bleeding-edge builds. To upgrade, follow these steps:

1. Log in to the Ubuntu proot
   * `proot-distro login ubuntu`
2. Install `wget` to download the latest release from [this page](https://github.com/Aptivi/GRILO/releases).
   * `apt install wget`
   * `wget https://github.com/Aptivi/GRILO/releases/download/vx.x.x/x.x.x-bin.zip`
3. Install `unzip` to extract the files
   * `apt install unzip`
   * `unzip x.x.x-bin.zip`
4. Execute `dotnet GRILO.Bootloader.dll`
