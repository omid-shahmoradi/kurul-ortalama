#   
<!DOCTYPE html>  
<html lang="tr">  
<head>  
  <meta charset="UTF-8">  
  <title>3. Dönem Kurul Ortalama Hesaplama</title>  
  <style>  
    body {  
      background:#050505;  
      color:#fff;  
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;  
      display:flex;  
      justify-content:center;  
      padding:20px;  
    }  
    .container {  
      max-width:500px;  
      width:100%;  
      background:#111;  
      padding:24px;  
      border-radius:18px;  
      box-shadow:0 0 20px rgba(0,0,0,0.4);  
    }  
    h1 { font-size:22px; text-align:center; margin-bottom:8px; }  
    h2 { font-size:14px; font-weight:400; color:#aaa; text-align:center; margin-top:0; }  
    .row {  
      display:flex;  
      align-items:center;  
      justify-content:space-between;  
      margin:12px 0;  
    }  
    .row label {  
      flex:1.4;  
      font-size:15px;  
      padding-right:10px;  
    }  
    .row input {  
      width:70px;  
      padding:6px 8px;  
      border-radius:8px;  
      border:none;  
      background:#000;  
      color:#fff;  
      text-align:center;  
      margin-right:6px;  
    }  
    .row span {  
      font-size:14px;  
      color:#ccc;  
    }  
    button {  
      width:100%;  
      margin-top:18px;  
      padding:10px;  
      border-radius:10px;  
      border:none;  
      background:#22c55e;  
      color:#000;  
      font-weight:600;  
      font-size:16px;  
    }  
    #sonuc {  
      margin-top:16px;  
      font-size:18px;  
      text-align:center;  
      font-weight:600;  
    }  
  </style>  
</head>  
<body>  
  <div class="container">  
    <h1>3. Dönem Kurul Ortalama Hesaplama</h1>  
    <h2>7 Kurul – AKTS Hesaplama</h2>  
  
    <div class="row">  
      <label>Neoplazi ve Hematopoetik Sistem</label>  
      <input type="number" class="not" data-akts="9" placeholder="Not">  
      <span>AKTS: 9</span>  
    </div>  
  
    <div class="row">  
      <label>Endokrin ve Beslenme</label>  
      <input type="number" class="not" data-akts="8" placeholder="Not">  
      <span>AKTS: 8</span>  
    </div>  
  
    <div class="row">  
      <label>Dolaşım ve Solunum Sistemi</label>  
      <input type="number" class="not" data-akts="9" placeholder="Not">  
      <span>AKTS: 9</span>  
    </div>  
  
    <div class="row">  
      <label>Gastrointestinal Sistem</label>  
      <input type="number" class="not" data-akts="8" placeholder="Not">  
      <span>AKTS: 8</span>  
    </div>  
  
    <div class="row">  
      <label>Ürogenital Sistem</label>  
      <input type="number" class="not" data-akts="8" placeholder="Not">  
      <span>AKTS: 8</span>  
    </div>  
  
    <div class="row">  
      <label>Nörolojik Bilimler ve Psikiyatri</label>  
      <input type="number" class="not" data-akts="9" placeholder="Not">  
      <span>AKTS: 9</span>  
    </div>  
  
    <div class="row">  
      <label>Kas–İskelet Sistemi</label>  
      <input type="number" class="not" data-akts="8" placeholder="Not">  
      <span>AKTS: 8</span>  
    </div>  
  
    <button onclick="hesapla()">Ortalamayı Hesapla</button>  
    <div id="sonuc"></div>  
  </div>  
  
  <script>  
    function hesapla() {  
      const inputs = document.querySelectorAll('.not');  
      let toplamNotXAkts = 0;  
      let toplamAkts = 0;  
  
      inputs.forEach(input => {  
        const not = parseFloat(input.value);  
        const akts = parseFloat(input.dataset.akts);  
  
        if (!isNaN(not)) {  
          toplamNotXAkts += not * akts;  
          toplamAkts += akts;  
        }  
      });  
  
      const sonucDiv = document.getElementById('sonuc');  
  
      if (toplamAkts === 0) {  
        sonucDiv.textContent = "Lütfen en az bir nota gir.";  
      } else {  
        const ort = toplamNotXAkts / toplamAkts;  
        sonucDiv.textContent = "Ağırlıklı Kurul Ortalaman: " + ort.toFixed(2);  
      }  
    }  
  </script>  
</body>  
</html>  
