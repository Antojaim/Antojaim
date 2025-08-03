<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Prediksi Togel Lengkap</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #141e30, #243b55);
      color: #fff;
      margin: 0;
      padding: 20px;
    }
    h2 {
      color: #00ffd5;
    }
    .container {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 20px;
    }
    .card {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid #00ffd5;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 0 15px rgba(0, 255, 213, 0.2);
      transition: transform 0.3s;
    }
    .card:hover {
      transform: scale(1.02);
    }
    button {
      background: #00ffd5;
      color: #000;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 10px;
    }
    pre {
      white-space: pre-wrap;
      word-wrap: break-word;
      background-color: rgba(0, 0, 0, 0.3);
      padding: 10px;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <h1>🔮 Prediksi Togel Hari Ini</h1>
  <div class="container" id="prediksi-container"></div>

  <script>
    const pasarans = [
      "CHELSEA 21",
      "TOTO MACAU PAGI",
      "TOTOMACAU SIANG",
      "TOTOMACAU SORE",
      "TOTOMACAU MALAM-I",
      "TOTOMACAU MALAM-II",
      "TOTOMACAU MALAM-III",
      "TOTOMACAU 5D SORE",
      "TOTOMACAU 5D MALAM",
      "KENTUCKYMID",
	  "FLORIDA MIDDAY","HUAHIN 0100","NEW YORK MIDDAY","BANGKOK 0130","CAROLINA DAY",
      "SYDNEY","BRUNEI 02","OREGON03","OREGON06","CALIFORNIA","FLORIDAEVE","OREGON09","BANGKOK 0930",
      "SINGAPORE","NEWYORKEVE","KENTUCKYEVE","CAROLINAEVE","TOTOCAMBODIA","CHELSEA 11","OREGON12",	
      "HONGKONG","BULLSEYE","POIPET12","JAKARTA 1400","BRUNEI 14","CHELSEA 15","TOTO MALI 1530",
      "JAKARTA POOLS","POIPET15","HUAHIN 1630","MAGNUM4D","CHELSEA 19","POIPET19","PCSO",
      "BRUNEI","TOTO MALI 2030","HUAHIN 2100","NEVADA","BRUNEI 21","POIPET22","TOTO MALI 2330",
      "KIM TOTO","JAKARTA 2330",
      "POIPET",
      "HUAHIN",
      "TOTOMALI",
      "HOKIDRAW",
      "KING KONG4D-I",
      "KING KONG4D-II"
    ];

    function generatePrediksi(pasaran) {
      const hari = new Date().toLocaleDateString("id-ID", { weekday: "long", day: "2-digit", month: "long", year: "numeric" });
      const bbfs = Array.from({ length: 7 }, () => Math.floor(Math.random() * 10)).join("");
      const angkaMain = Array.from({ length: 5 }, () => Math.floor(Math.random() * 10)).join("");

      const angka5D = () => Array.from({ length: 4 }, () => Math.floor(10000 + Math.random() * 89999)).join(" ");
      const angka4D = () => Array.from({ length: 4 }, () => Math.floor(1000 + Math.random() * 8999)).join(" ");
      const angka3D = () => Array.from({ length: 4 }, () => Math.floor(100 + Math.random() * 899)).join(" ");
      const angka2D = () => Array.from({ length: 9 }, () => Math.floor(10 + Math.random() * 89)).join(" ");
      const colokBebas = () => `${Math.floor(Math.random() * 10)}/${Math.floor(Math.random() * 10)}`;
      const colokBebas2D = () => Array.from({ length: 3 }, () => Math.floor(10 + Math.random() * 89)).join(" / ");
      const cadangan2D = () => Array.from({ length: 3 }, () => Math.floor(10 + Math.random() * 89)).join(" / ");
      const shioList = ["TIKUS","KERBAU","MACAN","KELINCI","NAGA","ULAR","KUDA","KAMBING","MONYET","AYAM","ANJING","BABI"];
      const shio = Array.from({ length: 3 }, () => shioList[Math.floor(Math.random() * shioList.length)]).join(" / ");

      const is5D = pasaran.includes("5D");

      return `PREDIKSI ${pasaran.toUpperCase()}\nHari Ini ${hari}\nBBFS ${bbfs}\nANGKA MAIN ${angkaMain}\n${is5D ? `PREDIKSI 5D ${angka5D()}\n` : ''}PREDIKSI 4D ${angka4D()}\nPREDIKSI 3D ${angka3D()}\nPREDIKSI 2D (BB) ${angka2D()}\nCOLOK BEBAS ${colokBebas()}\nCOLOK BEBAS 2D ${colokBebas2D()}\n2D (CADANGAN) ${cadangan2D()}\nSHIO ${shio}\nSelalu Utamakan Prediksi Sendiri ya bosku`;
    }

    const container = document.getElementById("prediksi-container");
    pasarans.forEach(pasaran => {
      const card = document.createElement("div");
      card.className = "card";
      const title = document.createElement("h2");
      title.textContent = pasaran;
      const result = document.createElement("pre");
      result.textContent = "Klik tombol untuk generate prediksi...";
      const button = document.createElement("button");
      button.textContent = "🎲 GENERATE PREDIKSI";
      button.onclick = () => {
        result.textContent = generatePrediksi(pasaran);
      };
      card.appendChild(title);
      card.appendChild(result);
      card.appendChild(button);
      container.appendChild(card);
    });
  </script>
</body>
</html>
