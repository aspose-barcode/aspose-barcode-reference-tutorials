---
category: general
date: 2026-10-15
description: Buat barcode dari string di Python menggunakan Aspose.BarCode, pelajari
  cara menghasilkan barcode Code 128 dan menyimpan barcode PNG hanya dalam beberapa
  baris.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: id
lastmod: 2026-10-15
og_description: Buat barcode dari string di Python untuk mengkodekan data ke dalam
  barcode Code 128 dan simpan sebagai file PNG dengan Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Buat barcode dari string di Python – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Buat kode batang dari string di Python dengan Aspose.BarCode
url: /id/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode dari string di Python dengan Aspose.BarCode

Jika Anda perlu **create barcode from string** di Python, panduan ini menunjukkan langkah-langkah tepat dengan Aspose.BarCode. Anda akan belajar cara **generate Code 128 barcode**, menyesuaikan tampilannya, dan **save barcode PNG** ke disk. Solusi ini bekerja pada platform apa pun yang mendukung Python 3.9+ dan hanya memerlukan beberapa baris kode.

Membuat barcode secara programatik menghilangkan kesalahan entri manual dan menyederhanakan alur kerja seperti pelacakan inventaris, tiket, dan pencetakan label. Pada akhir tutorial ini Anda akan dapat **encode data into barcode**, menyesuaikan dimensi, dan menyimpan gambar di mana pun Anda membutuhkannya.

## Prasyarat

- Python 3.9 atau yang lebih baru terinstal  
- Akses internet untuk mengunduh paket Aspose.BarCode  
- Izin menulis ke direktori tempat Anda akan menyimpan file PNG  

Jika Anda menggunakan lingkungan virtual (sangat disarankan), aktifkan sekarang.

## Instal paket Aspose.BarCode Python

Aspose menyediakan pustaka pure‑Python yang menangani semua simbol barcode umum, termasuk Code 128. Instal dengan pip:

```bash
pip install aspose-barcode
```

*Pro tip:* Pin versi (misalnya, `aspose-barcode==23.9`) untuk menghindari perubahan yang tidak terduga di produksi.

## Buat barcode dari string di Python

Langkah fungsional pertama adalah mengimpor kelas yang diperlukan dan membuat instance generator untuk simbol yang diinginkan. Contoh ini menggunakan **Code 128**, yang ideal untuk data alfanumerik.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Why this matters:** `EncodeTypes.CODE_128` memberi tahu pustaka standar barcode mana yang akan diterapkan, sementara argumen kedua (`"1234567890"`) adalah **string you want to encode into barcode**. Anda dapat menggantinya dengan string ASCII apa pun hingga 80 karakter untuk Code 128.

## Hasilkan Code 128 barcode

Setelah generator siap, Anda dapat menghasilkan gambar barcode di memori. Pustaka secara otomatis merender barcode berdasarkan data yang diberikan.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

Pada titik ini `barcode_image` adalah instance dari `System.Drawing.Image` (di Windows) atau objek gambar yang kompatibel di platform lain. Anda dapat menampilkannya langsung di GUI, menyematkannya dalam PDF, atau melanjutkan kustomisasi.

## Sesuaikan tampilan barcode

Penyetelan halus properti visual memastikan barcode dapat dipindai dengan andal di lingkungan spesifik Anda. Penyesuaian umum meliputi X‑dimension (lebar bar paling sempit) dan tinggi bar keseluruhan.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Why adjust these values?*  
- **X dimension** memengaruhi kepadatan barcode; nilai yang lebih kecil menghasilkan barcode yang lebih rapat yang cocok untuk label kecil.  
- **Bar height** memengaruhi keterbacaan; bar yang lebih tinggi lebih mudah dideteksi pemindai dari jarak jauh.

Anda juga dapat mengubah warna, menambahkan margin, atau menyematkan teks yang dapat dibaca manusia melalui objek `parameters`. Lihat dokumentasi Aspose.BarCode untuk daftar lengkap opsi.

## Cara menyimpan barcode sebagai PNG

Menyimpan gambar yang dihasilkan adalah langkah akhir dalam alur kerja **create barcode from string**. Pustaka mendukung beberapa format; PNG bersifat lossless dan didukung secara luas.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

Metode `save` menulis gambar ke sistem file menggunakan format yang Anda tentukan. Jika direktori target (`output/` dalam contoh ini) tidak ada, Python akan mengeluarkan `FileNotFoundError`. Buat direktori tersebut sebelumnya atau tangani pengecualian:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Expected result:** Setelah menjalankan skrip, `output/barcode.png` berisi barcode Code 128 yang jelas yang meng-encode `"1234567890"`. Membuka file tersebut di penampil gambar apa pun akan menampilkan barcode hitam‑di‑atas‑putih siap dipindai.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian, berikut adalah skrip mandiri yang dapat Anda salin, tempel, dan jalankan:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Jalankan skrip dengan `python create_barcode.py`. Jika semuanya terinstal dengan benar, Anda akan melihat:

```
Barcode saved to output/barcode.png
```

Buka file PNG dan verifikasi bahwa barcode cocok dengan string asli menggunakan aplikasi pemindai barcode apa pun.

## Pertanyaan umum dan kasus tepi

- **What if I need a different symbology?**  
  Ganti `EncodeTypes.CODE_128` dengan nilai enum lain seperti `EncodeTypes.QR`, `EncodeTypes.EAN_13`, atau `EncodeTypes.PDF_417`. Sisanya kode tetap sama.

- **Can I generate a barcode from non‑ASCII characters?**  
  Code 128 mendukung seluruh set ASCII 128 karakter. Untuk data Unicode, pertimbangkan menggunakan QR Code (`EncodeTypes.QR`) yang menangani UTF‑8 secara native.

- **How do I change the image format?**  
  Berikan anggota lain dari `BarCodeImageFormat` ke `save`, misalnya, `BarCodeImageFormat.JPEG` atau `BarCodeImageFormat.BMP`.

- **What if the output directory is read‑only?**  
  Bungkus pemanggilan `save` dalam blok try/except dan tangani `PermissionError` secara elegan, mungkin dengan meminta pengguna memilih jalur alternatif.

- **Performance tip:**  
  Menghasilkan ribuan barcode dalam loop dapat intensif CPU. Gunakan kembali satu instance `BarcodeGenerator` dan hanya perbarui `generator.parameters.barcode.code_text` di antara iterasi.

## Kesimpulan

Anda sekarang tahu cara **create barcode from string** di Python menggunakan Aspose.BarCode, **generate Code 128 barcode**, menyesuaikan ukurannya, dan **save barcode PNG** ke disk. Solusi end‑to‑end ini memungkinkan Anda **encode data into barcode** dengan cepat dan andal, memudahkan integrasi barcode ke dalam sistem inventaris, platform tiket, atau aplikasi apa pun yang memerlukan pengenal yang dapat dibaca mesin.

**Langkah selanjutnya**

- Jelajahi simbol lain (`generate code 128 barcode` alternatives) seperti QR atau DataMatrix.  
- Tambahkan logika penanganan error untuk membuat skrip lebih kuat untuk penggunaan produksi (`how to save barcode` failures).  
- Sematkan PNG yang dihasilkan ke dalam PDF atau laporan HTML (`generate barcode png` for web).  

Selamat coding, dan nikmati kesederhanaan pembuatan barcode secara programatik!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}