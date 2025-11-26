# geo_catatan

Nama : Ahmad Bachtiar Raflyansyah  
NIM  : 362458302141  
Prodi: Teknologi Rekayasa Perangkat Lunak  
Tugas: Geo

Project Flutter untuk menyimpan dan menandai lokasi pada peta dengan fitur kustomisasi marker, penghapusan data, dan penyimpanan lokal.

## Fitur utama
- Kustomisasi Marker: ikon & warna berbeda berdasarkan jenis catatan (Toko / Rumah / Kantor).
- Hapus Data: dialog konfirmasi untuk menghapus marker/catatan.
- Simpan Data (opsional): persistensi menggunakan SharedPreferences atau Hive agar data tidak hilang saat aplikasi ditutup.

## Penjelasan fitur dan potongan kode

### 1) Kustomisasi Marker
Penjelasan: Digunakan untuk membedakan marker pada peta dengan cara menetapkan ikon dan warna yang unik, yang ditentukan oleh jenis catatan yang disimpan (seperti 'Toko', 'Kantor', atau 'Rumah'). Proses kustomisasi ini dikendalikan oleh dua fungsi helper: `_getIconForType` yang memilih simbol (IconData) yang sesuai, dan `_getColorForType` yang menentukan skema warna. Kedua nilai ini kemudian diterapkan pada setiap objek `Marker` saat data `_savedNotes` diproses. Hal ini memastikan bahwa ikon dan warna marker selalu sinkron dengan properti jenis data, sehingga meningkatkan kemudahan pengguna dalam mengidentifikasi dan membedakan kategori lokasi di peta secara visual.

Contoh kode ;
<img width="1108" height="862" alt="Geo1" src="https://github.com/user-attachments/assets/be3e06d0-e328-43b7-b010-67b675d676c6" />


### 2) Hapus Data
Penjelasan: Fungsi `_showDeleteDialog` merupakan mekanisme konfirmasi dan eksekusi penghapusan marker. Fungsi ini menampilkan dialog untuk mendapatkan persetujuan pengguna, dan jika dikonfirmasi, ia akan menghapus objek catatan dari data (`_savedNotes.remove(note)`) dan memperbarui penyimpanan (`_saveNotes()`), memastikan marker tersebut hilang secara permanen dari peta dan aplikasi.

Contoh kode ;
<img width="1766" height="824" alt="deltegeo" src="https://github.com/user-attachments/assets/491bf06b-2505-433f-8172-476bb575017e" />


### 3) Simpan Data (SharedPreferences)
Penjelasan: Fungsi `_saveNotes()` melakukan serialisasi data catatan menjadi JSON String untuk disimpan ke disk, sementara `_loadNotes()` menangani deserialisasi (memuat dan mengembalikan data) saat aplikasi dimulai melalui `initState()`, yang secara bersatu menjamin data marker tersimpan dan dimuat kembali secara otomatis tanpa hilang.

Contoh kode :
<img width="1394" height="1052" alt="saved Loads" src="https://github.com/user-attachments/assets/5358d667-0f38-4eb7-ba68-e3f13002e4b8" />


## HASILNYA (contoh tampilan);

- tampilan awal
![WhatsApp Image 2025-11-26 at 15 54 03](https://github.com/user-attachments/assets/e928bfe3-dad7-4978-9520-f1b50a98be2b)

- menambahkan catatan
  ![WhatsApp Image 2025-11-26 at 15 54 03 (1)](https://github.com/user-attachments/assets/fa44783a-85bb-4885-b2c1-a2ae87641060)
  
- tampilan catatan yang telah dibuat  
  ![WhatsApp Image 2025-11-26 at 15 54 03 (2)](https://github.com/user-attachments/assets/91941ea1-c16e-4492-bcf8-7940119dba03)

- Hapus catatan
  ![WhatsApp Image 2025-11-26 at 15 54 04](https://github.com/user-attachments/assets/226d8548-1fba-4d49-9276-0229a7b2d211)

  
- setelah di hapus catatannya
  ![WhatsApp Image 2025-11-26 at 15 54 04 (1)](https://github.com/user-attachments/assets/4fd1460c-d135-4a4d-ac34-2995929b722e)

  


