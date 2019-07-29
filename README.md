# 2019-NeurIPS
anonymous supplementary material

## Complex information encryption
### Qualitative comparison 
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-uca5{text-decoration:underline;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
.tg .tg-uog8{text-decoration:underline;border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-0pky">Methods</th>
    <th class="tg-0pky">FID</th>
    <th class="tg-0pky">Encryption(LPIPS/MSE)</th>
    <th class="tg-0pky">MSE</th>
    <th class="tg-0lax">RMSE</th>
    <th class="tg-0lax">PSNR</th>
    <th class="tg-0lax">SSIM</th>
    <th class="tg-0lax">LPIPS</th>
  </tr>
  <tr>
    <td class="tg-0pky">CycleGAN</td>
    <td class="tg-0pky">189.5232</td>
    <td class="tg-0pky">0.5231/0.0912</td>
    <td class="tg-0pky">0.0096</td>
    <td class="tg-0lax">0.1269</td>
    <td class="tg-0lax">19.3523</td>
    <td class="tg-0lax">0.9754</td>
    <td class="tg-0lax">0.3128</td>
  </tr>
  <tr>
    <td class="tg-0pky">MUNIT</td>
    <td class="tg-0pky">225.1347</td>
    <td class="tg-0pky">0.6212/0.0723</td>
    <td class="tg-0pky">0.0097</td>
    <td class="tg-0lax">0.1272</td>
    <td class="tg-0lax">18.6742</td>
    <td class="tg-0lax">0.9637</td>
    <td class="tg-0lax">0.3312</td>
  </tr>
  <tr>
    <td class="tg-0pky">DRIT</td>
    <td class="tg-0pky">217.3423</td>
    <td class="tg-0pky">0.5124/0.0852</td>
    <td class="tg-0pky">0.0091</td>
    <td class="tg-0lax">0.1042</td>
    <td class="tg-0lax">19.0313</td>
    <td class="tg-0lax">0.9673</td>
    <td class="tg-0lax">0.3042</td>
  </tr>
  <tr>
    <td class="tg-0pky">Steganography</td>
    <td class="tg-0pky">212.5234</td>
    <td class="tg-0pky">0.5341/0.0634</td>
    <td class="tg-0pky">0.0089</td>
    <td class="tg-0lax">0.0975</td>
    <td class="tg-0lax">18.9933</td>
    <td class="tg-0lax">0.9698</td>
    <td class="tg-0lax">0.2871</td>
  </tr>
  <tr>
    <td class="tg-0pky">EncryptGAN</td>
    <td class="tg-uog8">155.1446</td>
    <td class="tg-uog8">0.7670/0.0967</td>
    <td class="tg-uog8">0.0084</td>
    <td class="tg-uca5">0.0901</td>
    <td class="tg-uca5">20.9072</td>
    <td class="tg-uca5">0.9710</td>
    <td class="tg-uca5">0.2631</td>
  </tr>
</table>


<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-uog8{text-decoration:underline;border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-0pky">Methods</th>
    <th class="tg-0pky">FID</th>
    <th class="tg-0pky">Encryption(LPIPS/MSE)</th>
    <th class="tg-0pky">MSE</th>
    <th class="tg-0pky">RMSE</th>
    <th class="tg-0pky">PSNR</th>
    <th class="tg-0pky">SSIM</th>
    <th class="tg-0pky">LPIPS</th>
  </tr>
  <tr>
    <td class="tg-0pky">CycleGAN</td>
    <td class="tg-0pky">165.6343</td>
    <td class="tg-0pky">0.4105/0.1024</td>
    <td class="tg-0pky">0.0115</td>
    <td class="tg-0pky">0.1209</td>
    <td class="tg-0pky">21.3641</td>
    <td class="tg-0pky">0.9246</td>
    <td class="tg-0pky">0.3173</td>
  </tr>
  <tr>
    <td class="tg-0pky">MUNIT</td>
    <td class="tg-0pky">221.6354</td>
    <td class="tg-0pky">0.3367/0.0824</td>
    <td class="tg-0pky">0.0124</td>
    <td class="tg-0pky">0.1222</td>
    <td class="tg-0pky">19.6723</td>
    <td class="tg-0pky">0.9423</td>
    <td class="tg-0pky">0.3418</td>
  </tr>
  <tr>
    <td class="tg-0pky">DRIT</td>
    <td class="tg-0pky">182.5341</td>
    <td class="tg-0pky">0.3135/0.0942</td>
    <td class="tg-0pky">0.0102</td>
    <td class="tg-0pky">0.1211</td>
    <td class="tg-0pky">19.2341</td>
    <td class="tg-0pky">0.9219</td>
    <td class="tg-0pky">0.3174</td>
  </tr>
  <tr>
    <td class="tg-0pky">Steganography</td>
    <td class="tg-0pky">198.2543</td>
    <td class="tg-0pky">0.3112/0.1013</td>
    <td class="tg-0pky">0.0128</td>
    <td class="tg-0pky">0.1226</td>
    <td class="tg-0pky">19.9832</td>
    <td class="tg-0pky">0.9473</td>
    <td class="tg-0pky">0.2941</td>
  </tr>
  <tr>
    <td class="tg-0pky">EncryptGAN</td>
    <td class="tg-uog8">140.7061</td>
    <td class="tg-uog8">0.4190/0.1214</td>
    <td class="tg-uog8">0.0068</td>
    <td class="tg-uog8">0.0808</td>
    <td class="tg-uog8">22.0137</td>
    <td class="tg-uog8">0.9475</td>
    <td class="tg-uog8">0.2854</td>
  </tr>
</table>