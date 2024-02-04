---
description: Setting your bootloader up.
---

# ⚙ Configuration

The bootloader can be configured in various ways, like the selection of the boot style. When GRILO starts for the first time, the application creates the following files and folders necessary for the configuration:

* `%LOCALAPPDATA%/GRILO` on Windows systems
* `$HOME/.config/GRILO` on Linux systems

The configuration files and folders within the directory are made by GRILO itself:

* `BootloaderConfig.json`
  * This file stores all the bootloader configuration options.
  * The type is a **file**
* `Styles`
  * Lists all the custom boot styles
  * The type is a **folder**
* `Bootables`
  * Stores all the folders that contain bootable applications inside
  * The type is a **folder**
* `BootloaderDebug.log`
  * Stores all the debugging messages that come from the bootloader
  * The type is a **file**

Let's start with the configuration file, as this page covers the general GRILO configuration.

## Configuration

Typical GRILO configuration files start with this:

```json
{
  "Boot style": "Default",
  "Diagnostic messages": false,
  "Additional bootable folders": [],
  "Timeout to boot to selection": 60,
  "Default boot entry selection": 0
}
```

The following configuration descriptions are listed below:

* `Boot style`
  * Stores the name of the boot style
  * The type of this variable is a **string**
* `Diagnostic messages`
  * Whether to enable storing the diagnostic messages to the `BootloaderDebug.log` file
  * The type of this variable is a **boolean**
* `Additional bootable folders`
  * An array of complete file paths to additional bootable folders for the scanner to use
  * The type of this variable is an **array** of **strings**
* `Timeout to boot to selection`
  * Timeout in seconds to boot to selection if no key is pressed
  * The type of this variable is an **integer**
* `Default boot entry selection`
  * Zero-based choice number for the default boot entry
  * The type of this variable is an **integer**

Each time GRILO starts up, it checks the settings file for any values and installs them to the bootloader, making it configurable.
