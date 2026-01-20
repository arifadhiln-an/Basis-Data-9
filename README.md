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

## 🧪 Praktikum Menggunakan OpenRefine (Praktik Langsung + Kode)

Pada bagian ini, praktikum dilakukan menggunakan contoh data sederhana agar mudah dipahami.

---

### 1. Contoh Dataset (sample-file.csv)

Berikut contoh isi file `sample-file.csv` yang digunakan dalam praktikum:

```csv
id,name_of_person
1,alex castillo
2,Alex Castillo 
3,Alexander
4,alex castillooooooo
5,  alex castillo
```

Masalah pada data di atas:

* Perbedaan huruf besar/kecil
* Spasi di awal dan akhir teks
* Penulisan nama tidak konsisten

---

### 2. Loading File dan Membuat Project

1. Buka **OpenRefine**
2. Klik **Create Project**
3. Pilih file `sample-file.csv`
4. Klik **Next** → **Create Project**

Data akan muncul dalam bentuk tabel.

---

### 3. Examining Data (Text Facet)

* Klik panah pada kolom `name_of_person`
* Pilih **Facet → Text Facet**

Fungsi ini menampilkan seluruh variasi nilai pada kolom tersebut.

---

### 4. Removing Whitespace (Praktik)

Langkah manual:

* Klik panah kolom `name_of_person`
* **Edit Cells → Common Transformations → Trim leading and trailing whitespace**

Alternatif menggunakan **GREL**:

```grel
value.trim()
```

Hasil: spasi di awal dan akhir teks akan dihapus.

---

### 5. Changing Case ke Title Case

Langkah manual:

* **Edit Cells → Common Transformations → To Titlecase**

Menggunakan GREL:

```grel
toTitlecase(value)
```

Contoh hasil:

* `alex castillo` → `Alex Castillo`

---

### 6. Cleaning dengan Cluster and Edit

1. Pada Text Facet, klik **Cluster**
2. Pilih algoritma (misalnya *key collision*)
3. Centang kolom **Merge?**
4. Isi nilai benar pada kolom **New Cell Value**, contoh:

```
Alex Castillo
```

5. Klik **Merge Selected & Recluster**

Semua variasi nama akan digabung menjadi satu.

---

### 7. Cleaning Individual Entries (Edit Manual)

Jika masih ada data tidak sesuai:

* Klik **Edit** pada nilai di Text Facet
* Ubah langsung menjadi nilai yang benar

---

### 8. Hasil Data Setelah Cleaning

Contoh hasil akhir data:

```csv
id,name_of_person
1,Alex Castillo
2,Alex Castillo
3,Alex Castillo
4,Alex Castillo
5,Alex Castillo
```

---

### 9. Exporting Cleaned Data

1. Klik **Export**
2. Pilih **Comma Separated Value (CSV)**

File hasil export siap digunakan untuk analisis lanjutan atau disimpan ke database.

---

## ✅ Kesimpulan

Melalui praktikum ini, kita belajar bahwa data mentah sering kali tidak rapi dan tidak konsisten. OpenRefine membantu proses *data cleaning* menjadi lebih cepat, sistematis, dan akurat sebelum data digunakan dalam analisis atau sistem basis data.

---

## 👨‍🏫 Referensi

Materi diambil dari Modul **Basis Data Part 9 – Using OpenRefine**

---

**Terima Kasih** 🙏
