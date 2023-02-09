---
description: What loads your operating system?
---

# 💿 What is the Bootloader?

A bootloader is a first computer program that is run after the Basic Input/Output System (BIOS) or the Unified Extensible Firmware Interface (UEFI) phase. It's the computer program that is responsible for booting an operating system.

There are two stages for the bootloader: the first-stage boot loader and the second-stage boot loader. The first-stage boot loader resides in the boot sector, usually found in the first few bytes of your hard drive. However, the second-stage bootloaders are typically stored on the hard drive and are usually loaded by the first-stage ones.

Second-stage bootloaders can be configured to give the user multiple booting choices, which is what major bootloaders, like Windows Boot Manager and GRUB, do.

GRILO simulates the second-stage bootloader. To learn more what is GRILO, click on the link below.

{% content-ref url="what-is-grilo.md" %}
[what-is-grilo.md](what-is-grilo.md)
{% endcontent-ref %}
