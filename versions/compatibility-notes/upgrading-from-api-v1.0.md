---
description: Do you want to upgrade from API v1.0?
---

# 🔼 Upgrading from API v1.0

When you're trying to upgrade to a version of GRILO that provides the next version of API, like GRILO 1.0.0 (API 2.0), you'll have to follow these steps to ensure that you'll get a smooth upgrade process.

## Binary compatibility

In order to upgrade your boot styles and GRILO to 1.0.0 or higher, you'll have to first follow the two changes described below, then you'll have to change the boot styles as follows:

### Configuration changes

None of the APIs are affected, but we decided to change the mechanism of the configuration so that it uses the serialization and deserialization techniques instead of the standard LINQ parser.

Unfortunately, you'll have to edit your configuration file manually. Luckily, it's a very simple change; just remove the "GRILO" property heading and footer, so that it would become like this:

*   Before

    <pre class="language-json"><code class="lang-json">{
    <strong>  "GRILO": {
    </strong>    "Boot style": "Default",
        "Diagnostic messages": false,
        "Print diagnostic messages to console": false,
        "Additional bootable folders": []
    <strong>  }
    </strong>}
    </code></pre>
*   After

    ```json
    {
      "Boot style": "Default",
      "Diagnostic messages": false,
      "Print diagnostic messages to console": false,
      "Additional bootable folders": []
    }
    ```

{% hint style="info" %}
You can now easily access configuration using the `Instance` property found in `Config`.
{% endhint %}

### Loading changes

Since GRILO 1.1.0, we've made a substantial effort to fix dependency loading so that different applications that need different versions of one library (for example, Nitrocid KS and GRILO both need Terminaux) can resolve their dependencies appropriately.

Unfortunately, this means that you'll have to move all your .NET 4.8 bootable apps to a different directory, which the page linked below will explain this in depth:

{% content-ref url="../../power-users/boot-apps.md" %}
[boot-apps.md](../../power-users/boot-apps.md)
{% endcontent-ref %}

## Breaking changes

We've made breaking changes between API v1.0 and API v2.0 in which you'll have to follow to ensure smooth transition of your boot styles:

### From 1.0.0 to 1.2.0

Between 1.0.0 and 1.2.0, we've made breaking changes that may affect your boot styles:

#### Moved classes around

{% code title="" lineNumbers="true" %}
```csharp
// GRILO.Bootloader.BootApps to GRILO.Bootloader.Boot.Apps
public class BootAppInfo
public static class BootManager

// GRILO.Bootloader.Diagnostics to GRILO.Bootloader.Boot.Diagnostics
public enum DiagnosticsLevel
public static class DiagnosticsWriter

// GRILO.Bootloader.BootStyle to GRILO.Bootloader.Boot.Style
public interface IBootStyle
public abstract class BaseBootStyle : IBootStyle
public static class BootStyleManager

// GRILO.Bootloader.Configuration.Instance to GRILO.Bootloader.Common.Configuration.Instance
public class ConfigInstance

// GRILO.Bootloader.Configuration to GRILO.Bootloader.Common.Configuration
public static class Config

// GRILO.Bootloader to GRILO.Bootloader.Common.Configuration
public static class GRILOPaths -> ConfigPaths

// GRILO.Bootloader to GRILO.Bootloader.Common
public class GRILOException : Exception -> BootloaderException
```
{% endcode %}

We needed to organize the bootloader classes more efficiently to ensure easy maintenance, so we've decided to move classes around, including those that are internal and not documented here, to achieve better organization.

This makes sure that we've organized these classes in a better way.

{% hint style="info" %}
Your boot styles need to update the references as shown in the above code block.
{% endhint %}

#### Used screen feature

{% code title="IBootStyle.cs" lineNumbers="true" %}
```csharp
void Render();
void RenderHighlight(int chosenBootEntry);
void RenderModalDialog(string content);
void RenderBootingMessage(string chosenBootName);
void RenderBootFailedMessage(string content);
void RenderSelectTimeout(int timeout);
void ClearSelectTimeout();
```
{% endcode %}

Starting from 1.2.0, GRILO uses the screen feature for flexibility. This means that these functions have been changed to return a string of a terminal sequence representing each part of the boot style.

{% hint style="info" %}
You must use a string builder to be able to easily build your sequences for rendering. Beware that you must adhere to the Terminaux guidelines as demonstrated here:

[Console Screen](https://app.gitbook.com/s/G0KrE9Uk2AiblqjWtpAo/usage/console-tools/console-screen "mention")
{% endhint %}
