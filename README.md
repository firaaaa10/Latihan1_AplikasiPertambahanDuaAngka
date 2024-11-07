# Latihan1_AplikasiPertambahanDuaAngka
 Siti Safira - 2210010336

# Deskripsi Program
• Pengguna memasukkan dua angka

• Saat tombol Tambah diklik akan menampilkan hasil pertambahan

• Saat tombol Hapus diklik akan menghapus nilai di TextField dan
mengarahkan fokus ke TextField angka pertama

# Komponen GUI: JFrame, JPanel, JLabel, JTextField, JButton
- JLabel untuk memberi label pada input angka pertama, angka kedua, dan hasil.
- JTextField untuk memasukkan angka pertama, angka kedua dan menampilkan hasil.
- JButton dengan label "Tambah" untuk melakukan operasi pertambahan.
- JButton dengan label "Hapus" untuk mengosongkan input.
- JButton dengan label "Keluar" untuk menutup aplikasi.

# Logika Program
Penambahan dua angka, validasi input numerik

# Events
-ActionListener untuk tombol Tambah, Hapus, dan Keluar
A.Tambah
 ```
   private void btnTambahActionPerformed(java.awt.event.ActionEvent evt) {                                          
   try {
    int angka1 = Integer.parseInt(InputAngkaPertama.getText());
    int angka2 = Integer.parseInt(InputAngkaKedua.getText());
    int hasil = angka1 + angka2;
    txtHasil.setText(String.valueOf(hasil)); // Menampilkan hasil di jTextFieldHasil
} catch (NumberFormatException e) {
    JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
}

    }                    
```
B.Hapus
 ```
private void btnHapusActionPerformed(java.awt.event.ActionEvent evt) {                                         
    InputAngkaPertama.setText("");
    InputAngkaKedua.setText("");
    txtHasil.setText(""); // Menghapus hasil di jTextFieldHasil
    InputAngkaPertama.requestFocus(); // Mengarahkan fokus kembali ke jTextField1
    }         
```
C.Keluar
```
private void btnKeluarActionPerformed(java.awt.event.ActionEvent evt) {                                          
    System.exit(0);
    }
```
# Variasi
A.KeyAdapter pada JTextField untuk membatasi input hanya angka
```
    private void InputAngkaPertamaKeyTyped(java.awt.event.KeyEvent evt) {                                           
    char c = evt.getKeyChar();
    if (!Character.isDigit(c) && c != KeyEvent.VK_BACK_SPACE && c != KeyEvent.VK_DELETE) {
        evt.consume();
        JOptionPane.showMessageDialog(this, "Masukkan hanya angka!", "Error", JOptionPane.ERROR_MESSAGE);
}

    }
private void InputAngkaKeduaKeyTyped(java.awt.event.KeyEvent evt) {                                         
    char c = evt.getKeyChar();
    if (!Character.isDigit(c) && c != KeyEvent.VK_BACK_SPACE && c != KeyEvent.VK_DELETE) {
        evt.consume();
        JOptionPane.showMessageDialog(this, "Masukkan hanya angka!", "Error", JOptionPane.ERROR_MESSAGE);
}

    }   
```
B.Gunakan JOptionPane untuk menampilkan error input
```
} catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(this, "Input harus berupa angka!", "Error", JOptionPane.ERROR_MESSAGE);
    }
```
C.Implementasikan FocusListener untuk membersihkan JTextField
saat mendapatkan fokus.
   ```
   private void InputAngkaPertamaFocusGained(java.awt.event.FocusEvent evt) {                                              
    InputAngkaPertama.setText("");
    InputAngkaKedua.setText("");
    
    }
```    

# Hasil Tampilan
https://github.com/firaaaa10/Latihan1_AplikasiPertambahanDuaAngka/blob/main/Cuplikan%20layar%202024-11-04%20095949.png
## Indikator Penilaian:

| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    20    |
|  2  | Logika Program   |    20    |
|  3  | Kesesuaian UI    |    15    |
|  4  | Constructor      |    15    |
|  5  | Memenuhi Variasi |    30    |
|     | *TOTAL*        | *100* |

## Pembuat

Nama  : Siti Safira
NPM   : 2210010336
