---
description: How do you diagnose the bootloader?
---

# 🦠 Diagnostics

GRILO contains diagnostic tools that can be enabled with the `Diagnostic messages` variable found in the bootloader configuration. It basically saves all the debug information written with the `DiagnosticsWriter.WriteDiag()` function found in the `GRILO.Bootloader.Diagnostics` namespace.

The following diagnostics levels (`DiagnosticsLevel` enum) are usable:

* `Info`
  * Informational diagnostic messages
* `Warning`
  * Warning messages
* `Error`
  * Error messages, usually indicating that something is wrong

Any diagnostic information is written to the `BootloaderDebug.log` file with the following format:

```
[<level>] <content>
```

where:

* `level`
  * The first letter of the diagnostics level
* `content`
  * Any message to be written

If the printing to console option is enabled, you can also see the diagnostic messages being printed to the console **live**.
