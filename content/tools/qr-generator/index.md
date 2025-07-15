---
title: "QR Generator"
draft: false
---

Simply generate a QR code from any text.

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
        colorDark: "#000000",
        colorLight: "#ffffff",
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

<style>
  #qrcode img {
      border: 10px solid #ffffff;
  }
</style>

<input type="text" id="qrInput" placeholder="Enter text ..."/>
<br/><br/>
<span style="display: flex; gap: 10px;">
<button onclick="generateQR()">Generate QR</button>
<button onclick="downloadQR()">Download</button>
</span>
<br/>
<div id="qrcode"></div>
<br/>

{{< /rawHTML >}}
