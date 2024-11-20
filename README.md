function inputBarangMasuk() {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Data Barang");
  const ui = SpreadsheetApp.getUi();
  
  if (!sheet) {
    ui.alert('Sheet "Data Barang" tidak ditemukan. Pastikan sheet dengan nama tersebut ada.');
    return;
  }
  
  const response = ui.prompt("Barang Masuk", "Masukkan nama barang, jumlah masuk (dipisahkan koma), banyak barang dipisahkan dengan titik koma (;):", ui.ButtonSet.OK_CANCEL);
  if (response.getSelectedButton() === ui.Button.OK) {
    const items = response.getResponseText().split(';').map(item => item.trim());
    
    // Proses setiap barang dalam input
    for (let i = 0; i < items.length; i++) {
      const [namaBarang, jumlahMasuk] = items[i].split(',').map(item => item.trim());
      
      // Validasi input
      if (!namaBarang || isNaN(jumlahMasuk)) {
        ui.alert('Input tidak valid! Pastikan format: nama barang, jumlah');
        return;
      }
      
      // Memperbarui stok barang
      updateStok(sheet, namaBarang, parseInt(jumlahMasuk), true);
    }
  }
}

function updateStok(sheet, namaBarang, jumlah, isMasuk) {
  const data = sheet.getDataRange().getValues();
  let ditemukan = false;

  for (let i = 1; i < data.length; i++) {
    if (data[i][0] === namaBarang) {
      ditemukan = true;
      let stokSaatIni = data[i][1] || 0;
      if (isMasuk) {
        stokSaatIni += jumlah;
      } else {
        stokSaatIni -= jumlah;
      }
      sheet.getRange(i + 1, 2).setValue(stokSaatIni);
      break;
    }
  }

  if (!ditemukan) {
    sheet.appendRow([namaBarang, jumlah]);
  }
}
