# Blog Praktikum Basis Data – Part 9

## Using OpenRefine untuk Data Cleaning

Repository ini berisi rangkuman materi **Basis Data Part 9** sekaligus praktik langsung (*practical*) penggunaan **OpenRefine** untuk membersihkan data (*data cleaning*). Seluruh isi blog ini disusun berdasarkan modul perkuliahan dan ditujukan sebagai dokumentasi pembelajaran.

---

## 📌 Tujuan Praktikum

* Memahami konsep *data cleaning*
* Mampu menggunakan OpenRefine
* Membersihkan data tidak konsisten (spasi, huruf besar-kecil, duplikasi nama)
* Mengekspor data yang sudah bersih

---

## 🧰 Tools yang Digunakan

* **OpenRefine**
* File dataset contoh: `sample-file.csv`

---

## 🧪 Praktikum Menggunakan OpenRefine

### 1. Loading File dan Membuat Project

1. Buka aplikasi **OpenRefine**
2. Klik **Create Project**
3. Pilih file `sample-file.csv`
4. Klik **Next** lalu **Create Project**

Setelah itu, data akan ditampilkan dalam bentuk tabel.

---

### 2. Examining Data (Pemeriksaan Data)

* Klik tanda panah pada kolom **Name of Person**
* Pilih **Facet → Text Facet**

Fitur ini menampilkan seluruh variasi data pada kolom nama. Pada tahap ini akan terlihat banyak data yang tidak konsisten, misalnya:

* Alex Castillo
* Alexander
* Alexander Castillo
* Alex Castillooooooo

Secara logika manusia, ini adalah orang yang sama, namun komputer menganggapnya berbeda.

---

### 3. Removing Whitespace (Menghapus Spasi Berlebih)

Masalah umum lainnya adalah spasi di awal atau akhir teks.

Langkah-langkah:

1. Klik panah pada kolom **Name of Person**
2. Pilih **Edit Cells**
3. Pilih **Common Transformations**
4. Klik **Trim leading and trailing whitespace**

Langkah ini akan menghapus spasi yang menyebabkan data dianggap berbeda.

---

### 4. Changing the Case (Mengubah Format Huruf)

Untuk menyeragamkan penulisan nama:

1. Klik panah pada kolom **Name of Person**
2. Pilih **Edit Cells**
3. Pilih **Common Transformations**
4. Klik **To Titlecase**

Contoh hasil:

* alex castillo → Alex Castillo

---

### 5. Cleaning dengan Cluster and Edit

Fitur **Cluster & Edit** digunakan untuk menggabungkan data yang mirip.

Langkah:

1. Pada Text Facet, klik **Cluster**
2. OpenRefine akan menampilkan beberapa grup data mirip
3. Centang kolom **Merge?**
4. Tentukan nama yang benar di kolom **New Cell Value**
5. Klik **Merge Selected & Recluster**

Semua variasi nama akan digabung menjadi satu nilai yang benar.

---

### 6. Algorithm Settings

OpenRefine menyediakan beberapa algoritma clustering (misalnya:

* key collision
* nearest neighbor)

Pengaturan algoritma ini membantu menemukan data yang mirip dengan tingkat akurasi berbeda.

---

### 7. Cleaning Individual Entries (Edit Manual)

Jika masih ada data yang tidak bisa digabung otomatis:

* Klik **Edit** pada nilai di Text Facet
* Ubah nama secara manual sesuai yang benar

---

### 8. Exporting Cleaned Data

Setelah data bersih:

1. Klik **Export** di bagian atas
2. Pilih **Comma Separated Value (CSV)**

File CSV hasil export siap digunakan untuk analisis data lanjutan atau diimpor ke database.

---

## ✅ Kesimpulan

Melalui praktikum ini, kita belajar bahwa data mentah sering kali tidak rapi dan tidak konsisten. OpenRefine membantu proses *data cleaning* menjadi lebih cepat, sistematis, dan akurat sebelum data digunakan dalam analisis atau sistem basis data.

---

## 👨‍🏫 Referensi

Materi diambil dari Modul **Basis Data Part 9 – Using OpenRefine**

---

**Terima Kasih** 🙏
