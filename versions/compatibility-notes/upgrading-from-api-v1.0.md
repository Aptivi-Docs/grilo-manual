---
description: Do you want to upgrade from API v1.0?
---

# 🔼 Upgrading from API v1.0

When you're trying to upgrade to a version of GRILO that provides the next version of API, like GRILO 1.0.0 (API 2.0), you'll have to follow these steps to ensure that you'll get a smooth upgrade process.

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
