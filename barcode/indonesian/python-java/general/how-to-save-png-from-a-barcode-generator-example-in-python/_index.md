---
category: general
date: 2026-10-18
description: Pelajari cara menyimpan PNG menggunakan contoh generator kode batang.
  Sesuaikan rasio aspek, hasilkan DataBar, dan ekspor gambar kode batang langkah demi
  langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save png
- barcode generator example
- how to adjust aspect ratio
- how to generate databar
- export barcode image
language: id
lastmod: 2026-10-18
og_description: Cara menyimpan PNG menggunakan contoh generator kode batang. Ikuti
  panduan ini untuk menyesuaikan rasio aspek, menghasilkan DataBar, dan mengekspor
  gambar kode batang.
og_image_alt: Screenshot showing a saved PNG barcode generated with how to save PNG
  tutorial
og_title: Cara menyimpan PNG dari contoh generator barcode – Panduan Python
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to save PNG using a barcode generator example. Adjust aspect
    ratio, generate DataBar, and export barcode image step‑by‑step.
  headline: How to save PNG from a barcode generator example in Python
  type: TechArticle
tags:
- barcode
- PNG
- DataBar
title: Cara menyimpan PNG dari contoh generator barcode di Python
url: /id/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menyimpan PNG dari contoh generator barcode di Python

Jika Anda perlu **cara menyimpan PNG** dari contoh generator barcode, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan belajar menghasilkan DataBar Omni‑directional bertumpuk, menyesuaikan rasio aspeknya, dan mengekspor gambar barcode sebagai file PNG.

Kode ini menggunakan pustaka Aspose.BarCode untuk Python, yang menyediakan API yang mudah digunakan untuk membuat hampir semua jenis barcode. Pada akhir tutorial Anda akan memiliki file PNG siap pakai yang dapat Anda sematkan dalam laporan, faktur, atau aplikasi seluler.

## Prasyarat

* Python 3.8 atau yang lebih baru terinstal.
* Paket `aspose-barcode` (`pip install aspose-barcode`).
* Izin menulis ke direktori tempat Anda berencana menyimpan file PNG.

Prasyarat ini minimal, memungkinkan Anda fokus pada **contoh generator barcode** itu sendiri.

## Langkah 1: Buat generator barcode untuk DataBar Omni‑directional bertumpuk

Membuat generator adalah bagian pertama dari **cara menghasilkan databar**. Konstanta `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu pustaka simbol apa yang akan digunakan.

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Initialize the generator with the DataBar type and the data to encode
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

*Mengapa ini penting*: Objek `BarcodeGenerator` menyimpan semua pengaturan (ukuran, warna, margin) yang memengaruhi gambar akhir. Memulai dengan instance yang bersih memastikan tidak ada konfigurasi yang tersisa dari eksekusi sebelumnya.

## Langkah 2: Cara menyesuaikan rasio aspek untuk kontrol visual yang lebih halus

Rasio aspek mengontrol proporsi tinggi‑ke‑lebar bar. Nilai yang lebih tinggi membuat bar menjadi lebih tinggi, yang dapat meningkatkan keandalan pemindaian pada printer beresolusi rendah.

```python
# Adjust the X‑dimension (module width) to 2 pixels for finer detail
barcode_generator.parameters.barcode.x_dimension.pixels = 2

# Set the DataBar aspect ratio to 15
barcode_generator.parameters.barcode.databar.aspect_ratio = 15
```

Perhatikan penggunaan frasa **cara menyesuaikan rasio aspek** dalam komentar – ini adalah pengaturan tepat yang Anda butuhkan ketika proporsi default terlihat terlalu dipadatkan atau terlalu meregang.

## Langkah 3: Ekspor gambar barcode sebagai PNG – inti dari cara menyimpan PNG

Menyimpan gambar adalah bagian akhir dari alur kerja **ekspor gambar barcode**. Metode `save` menulis barcode yang dirender ke sistem file dalam format yang Anda tentukan.

```python
# Choose the output path (replace YOUR_DIRECTORY with a real folder)
output_path = "YOUR_DIRECTORY/DatabarStackedAR15.png"

# Save the generated barcode as a PNG image
barcode_generator.save(output_path, BarCodeImageFormat.Png)
```

Setelah baris ini dijalankan, `DatabarStackedAR15.png` akan berisi barcode yang tajam dan kontras tinggi, siap untuk dicetak atau ditampilkan secara digital.

### Output yang diharapkan

* File bernama `DatabarStackedAR15.png` yang terletak di direktori yang Anda tentukan.
* PNG menampilkan DataBar Omni‑directional bertumpuk dengan lebar modul 2 piksel dan rasio aspek 15.
* Anda dapat membuka file dengan penampil gambar apa pun untuk memverifikasi bahwa barcode telah dirender dengan benar.

## Langkah 4: Verifikasi PNG yang dihasilkan secara programatis (opsional)

Jika Anda ingin memastikan bahwa file telah dibuat tanpa membuka secara manual, Anda dapat menambahkan pemeriksaan cepat:

```python
import os

if os.path.isfile(output_path):
    print(f"✅ PNG successfully saved at: {output_path}")
else:
    print("❌ PNG was not created – check permissions and paths.")
```

Potongan kode ini menunjukkan cara sederhana untuk validasi **cara menyimpan PNG** dalam rangkaian tes otomatis.

## Kesalahan umum dan tips profesional

| Masalah | Mengapa terjadi | Cara menghindarinya |
|-------|----------------|-----------------|
| **FileNotFoundError** ketika direktori tidak ada | `save` tidak membuat folder yang hilang | Buat direktori terlebih dahulu: `os.makedirs("YOUR_DIRECTORY", exist_ok=True)` |
| **Barcode terlalu kecil untuk dipindai** | Dimensi X diatur ke 1 piksel atau rasio aspek terlalu rendah | Gunakan setidaknya 2 piksel untuk `x_dimension` dan rasio aspek 10 – 15 untuk DataBar bertumpuk |
| **Encoding tidak tepat** | Menggunakan konstanta `EncodeTypes` yang salah | Periksa kembali bahwa Anda menggunakan `EncodeTypes.DatabarStackedOmniDirectional` untuk simbol ini |

## Contoh lengkap yang dapat dijalankan

Menggabungkan semuanya, berikut adalah skrip mandiri yang dapat Anda salin, tempel, dan jalankan:

```python
import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# -------------------------------------------------
# Configuration
# -------------------------------------------------
output_dir = "generated_barcodes"
output_file = "DatabarStackedAR15.png"
output_path = os.path.join(output_dir, output_file)

# Ensure the output directory exists
os.makedirs(output_dir, exist_ok=True)

# -------------------------------------------------
# 1. Create the generator (how to generate databar)
# -------------------------------------------------
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# -------------------------------------------------
# 2. Adjust visual parameters (how to adjust aspect ratio)
# -------------------------------------------------
barcode_generator.parameters.barcode.x_dimension.pixels = 2          # finer module width
barcode_generator.parameters.barcode.databar.aspect_ratio = 15     # taller bars

# -------------------------------------------------
# 3. Export the image (how to save PNG & export barcode image)
# -------------------------------------------------
barcode_generator.save(output_path, BarCodeImageFormat.Png)

# -------------------------------------------------
# 4. Verify the result
# -------------------------------------------------
if os.path.isfile(output_path):
    print(f"✅ PNG successfully saved at: {output_path}")
else:
    print("❌ PNG was not created – investigate the error above.")
```

Jalankan skrip, lalu buka `generated_barcodes/DatabarStackedAR15.png` untuk melihat hasilnya.

## Kesimpulan

Anda kini tahu **cara menyimpan PNG** dari contoh generator barcode, cara **menyesuaikan rasio aspek**, cara **menghasilkan simbol DataBar**, dan cara **mengekspor gambar barcode** secara andal dan dapat diulang. Pengetahuan ini memungkinkan Anda menyematkan barcode langsung ke dalam alur laporan otomatis, aplikasi seluler, atau sistem apa pun yang membutuhkan pengenal yang dapat dibaca mesin.

**Langkah selanjutnya**:  

* Bereksperimen dengan tipe barcode lain (`EncodeTypes.QR`, `EncodeTypes.Code128`) untuk memperluas repertoar **contoh generator barcode** Anda.  
* Ubah format gambar ke JPEG atau BMP dengan mengganti `BarCodeImageFormat.Png` dengan nilai enum lain.  
* Integrasikan skrip ke dalam layanan web yang mengembalikan byte PNG sesuai permintaan, memungkinkan pembuatan barcode waktu nyata untuk platform e‑commerce.

Selamat coding, dan nikmati fleksibilitas pembuatan barcode secara programatik!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menyimpan gambar barcode dengan Barcode Generator C# – panduan langkah demi langkah](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)
- [Cara membuat PNG barcode dengan rasio aspek khusus di C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)
- [Cara menghasilkan barcode dengan ukuran khusus dan menyimpan gambar di C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}