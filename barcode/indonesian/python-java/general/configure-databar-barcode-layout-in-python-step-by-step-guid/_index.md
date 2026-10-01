---
category: general
date: 2026-08-12
description: Konfigurasikan tata letak kode batang Databar di Python dengan cepat.
  Pelajari cara mengatur kolom, baris, dan menyimpan gambar dengan perpustakaan generator
  kode batang.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: id
lastmod: 2026-08-12
og_description: Konfigurasikan tata letak barcode Databar di Python untuk mengontrol
  kolom, baris, dan output gambar. Ikuti panduan ini untuk solusi siap dijalankan.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Konfigurasikan tata letak kode batang Databar di Python – tutorial lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Konfigurasikan tata letak kode batang Databar di Python – panduan langkah demi
  langkah
url: /id/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasikan tata letak barcode Databar di Python – panduan langkah demi langkah

Jika Anda perlu **mengonfigurasi tata letak barcode Databar di Python**, panduan ini akan membawa Anda melalui seluruh proses. Anda akan melihat cara mengatur jumlah kolom atau baris untuk barcode Databar Expanded Stacked dan cara menyimpan gambar yang dihasilkan dengan satu panggilan ke pustaka generator barcode.

Mengendalikan tata letak sangat penting ketika Anda menyematkan barcode pada kemasan sempit, struk, atau layar seluler. Pada bagian di bawah ini kami akan membahas impor yang diperlukan, dua opsi tata letak (kolom dan baris), serta praktik terbaik untuk menyimpan gambar PNG yang bersih.

## Apa yang Anda butuhkan

Sebelum memulai, pastikan Anda memiliki:

* Python 3.8 atau lebih baru
* `aspose.barcode` (atau paket generasi barcode yang kompatibel) terpasang  
  ```bash
  pip install aspose-barcode
  ```
* Izin menulis ke folder tempat file PNG akan disimpan

Tidak ada alat eksternal tambahan yang diperlukan—pustaka menangani rendering, skala, dan enkoding gambar secara internal.

## Cara mengonfigurasi tata letak barcode Databar di Python

Inti solusi adalah kelas `BarcodeGenerator`. Kelas ini menerima enum `EncodeTypes` yang mengidentifikasi simbolologi barcode—dalam kasus ini `EncodeTypes.DatabarExpandedStacked`. Setelah membuat generator, Anda dapat menyesuaikan tata letak dengan mengatur properti `columns` atau `rows` pada objek parameter `data_bar`.

### Langkah 1: Impor kelas yang diperlukan

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Impor ini memberi Anda akses ke generator, enumerasi untuk tipe Databar, dan konstanta format gambar PNG.

### Langkah 2: Buat generator barcode untuk Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Mengapa langkah ini?*  
`EncodeTypes.DatabarExpandedStacked` memberi tahu pustaka untuk menghasilkan simbolologi **Databar Expanded Stacked**, yang mendukung string numerik lebih panjang sambil tetap memiliki jejak kompak. Argumen kedua adalah data yang akan dienkode; dapat berupa string apa pun yang memenuhi spesifikasi Databar.

### Langkah 3: Atur jumlah kolom (tata letak horizontal)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**atur kolom barcode** adalah frasa kunci untuk operasi ini. Ketika Anda meningkatkan jumlah kolom, barcode menyebar secara horizontal, yang dapat berguna untuk label lebar. Pustaka secara otomatis menghitung ulang lebar modul untuk menjaga ukuran keseluruhan tetap konsisten.

#### Tips pro
Jumlah kolom maksimum untuk Databar Expanded Stacked adalah 8. Menetapkan nilai lebih tinggi dari batas akan dipotong ke maksimum, tetapi sebaiknya validasi masukan Anda terlebih dahulu.

### Langkah 4: Simpan gambar barcode dengan tata letak kolom

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**simpan gambar barcode** adalah tindakan yang menulis barcode yang dirender ke disk. PNG bersifat lossless, sehingga mempertahankan tepi tajam yang diperlukan untuk pemindaian yang dapat diandalkan.

### Langkah 5: Buat generator kedua untuk tipe barcode yang sama (tata letak baris)

Jika Anda lebih suka tumpukan vertikal, Anda bekerja dengan baris alih-alih kolom. Kode di bawah ini menggunakan kembali nilai yang sama tetapi membuat instance `BarcodeGenerator` baru untuk menghindari pencampuran pengaturan kolom dan baris.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Langkah 6: Atur jumlah baris (tata letak vertikal)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**atur baris barcode** menyusun modul barcode secara vertikal. Tata letak tiga baris mengurangi tinggi setiap tumpukan individu, menjadikan barcode cocok untuk struk sempit atau layar seluler.

#### Kasus khusus
Jika Anda menetapkan `rows` ke 1, pustaka menghasilkan Databar satu‑baris (setara dengan Databar standar). Nilai di bawah 1 diabaikan dan direset ke nilai default (1 baris).

### Langkah 7: Simpan gambar barcode dengan tata letak baris

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Sekali lagi, kami **simpan gambar barcode** menggunakan PNG agar output tetap tajam.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian memberikan Anda skrip mandiri yang dapat ditempatkan ke proyek Python mana pun.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Output yang diharapkan**

Menjalankan skrip akan membuat dua file PNG:

* `output/ExpandedCols4.png` – barcode yang diperluas ke empat kolom
* `output/ExpandedRows3.png` – barcode yang dipadatkan menjadi tiga baris

Kedua gambar dapat dibuka di penampil gambar apa pun atau diimpor langsung ke faktur PDF, templat label, atau halaman web.

## Pertanyaan umum dan pemecahan masalah

| Pertanyaan | Jawaban |
|----------|--------|
| *Bagaimana jika barcode terlihat buram?* | Tingkatkan resolusi gambar dengan mengatur `barcode_generator.parameters.image_width` dan `image_height` sebelum memanggil `save`. |
| *Apakah saya dapat menggunakan format gambar lain?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif` sesuai kebutuhan. |
| *Apakah ada batas panjang data?* | Databar Expanded Stacked mendukung hingga 74 karakter numerik. Melebihi batas akan memunculkan `ArgumentException`. |
| *Bagaimana cara mengubah warna latar depan?* | Gunakan `barcode_generator.parameters.barcode.color = Color.Blue` (impor `System.Drawing.Color`). |
| *Bisakah saya menggabungkan kolom dan baris?* | Tidak. API memperlakukan kolom dan baris sebagai mode tata letak yang saling eksklusif. Pilih satu per instance barcode. |

## Langkah selanjutnya

Sekarang Anda dapat **mengonfigurasi tata letak barcode Databar**, pertimbangkan untuk menjelajahi topik terkait berikut:

* **Tambahkan keterangan teks** – gunakan `barcode_generator.parameters.barcode.code_text` untuk menampilkan nilai yang dienkode di bawah gambar.
* **Sematkan barcode dalam PDF** – gabungkan PNG yang dihasilkan dengan `aspose.pdf` untuk membuat dokumen yang dapat dicetak.
* **Ukuran dinamis** – hitung jumlah kolom atau baris optimal berdasarkan dimensi label pada waktu berjalan.
* **Pemrosesan batch** – iterasi melalui CSV kode produk untuk menghasilkan perpustakaan gambar barcode secara otomatis.

Bereksperimenlah dengan nilai kolom dan baris yang berbeda untuk melihat bagaimana mereka memengaruhi keandalan pemindaian pada perangkat target Anda. Semakin banyak Anda menguji, semakin baik Anda memahami trade‑off antara ukuran barcode, keterbacaan, dan keterbatasan ruang.

---

*Selamat coding! Jika Anda menemukan tutorial ini berguna, bagikan kepada rekan tim atau tinggalkan komentar tentang tantangan tata letak yang Anda hadapi.*

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait dan membangun pada teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Buat gambar barcode DotCode – baris & kolom (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Buat gambar barcode c# – Konfigurasikan Baris & Kolom Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Penyesuaian Tinggi Barcode Databar Satu Dimensi](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}