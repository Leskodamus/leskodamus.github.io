---
title: "Support"
draft: false
---

Feel free to support with any of the options listed below.

{{< line_break >}}

### Bitcoin - BTC

{{< rawHTML >}}
<pre tabindex="0">
<code id="btc-address">3AB8UgwqNGhHHM1omxMZQzQmbhSspy6j9k</code>
</pre>
<button onclick="copyValue('btc-address')">Copy BTC</button>
{{< /rawHTML >}}

### Monereo - XMR
{{< rawHTML >}}
<pre tabindex="0">
<code id="xmr-address">4APRmZPfPMKj2qyxTJBN3pDzVni9e9ZsSWwFpucXyekLbnA3tU3znY5ALt8XMZ4rkcaMHbYzqDHNr3YcApVVHp8aT5wsdCv</code>
</pre>
<button onclick="copyValue('xmr-address')">Copy XMR</button>
{{< /rawHTML >}}

<!-- JS for copying to clipboard -->
{{< rawHTML >}}
<script>
function copyValue(name) {
    var copyText = document.getElementById(name);
    var value = copyText.textContent
    navigator.clipboard.writeText(value);
    alert("Copied to clipboard: " + value);
}
</script>
{{< /rawHTML >}}
