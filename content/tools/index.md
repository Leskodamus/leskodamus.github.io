---
title: "Tools"
draft: false
---

A collection of tools.

<hr/>

{{< line_break >}}

# QR Code Generator

<!-- JS -->
{{< rawHTML >}}

<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>

<script>
    let qr;

    function generateQR() {
      const container = document.getElementById("qrcode");
      container.innerHTML = "";
      const text = document.getElementById("qrInput").value.trim();
      if (!text) return;

      qr = new QRCode(container, {
        text: text,
        width: 256,
        height: 256,
        colorLight: "#000000",
        colorDark: "#ffffff",
        correctLevel: QRCode.CorrectLevel.H
      });
    }

    function downloadQR() {
      const img = document.querySelector("#qrcode img") || document.querySelector("#qrcode canvas");
      if (!img) return;

      const link = document.createElement("a");
      link.download = "qr.png";
      link.href = img.src || img.toDataURL("image/png");
      link.click();
    }
</script>

<input type="text" id="qrInput" placeholder="Enter text or "/>
<br/><br/>
<button onclick="generateQR()">Generate QR</button>
<br/>
<div id="qrcode"></div>
<br/>
<button onclick="downloadQR()">Download</button>

{{< /rawHTML >}}
