---
category: general
date: 2026-08-22
description: Pelajari cara menghasilkan kode batang DataMatrix di Python dan mengkodekan
  teks Rusia menggunakan Aspose.BarCode – panduan langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: id
lastmod: 2026-08-22
og_description: Buat kode batang DataMatrix di Python dan enkode teks Rusia dengan
  Aspose.BarCode. Ikuti contoh lengkapnya dan jalankan secara langsung.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Menghasilkan barcode DataMatrix di Python – tutorial lengkap Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Cara menghasilkan barcode DataMatrix di Python dengan Aspose.BarCode
url: /id/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan DataMatrix barcode di Python dengan Aspose.BarCode

Jika Anda perlu **menghasilkan DataMatrix barcode** di Python sambil **mengodekan teks Rusia**, panduan ini menunjukkan langkah‑langkah tepatnya. Anda akan melihat contoh lengkap yang dapat dijalankan yang membangun extended codetext, mengkonfigurasi barcode, dan menyimpan gambar dalam satu skrip.

Membuat barcode yang berisi karakter non‑ASCII sering menimbulkan pertanyaan tentang set karakter dan enkoding data. Dengan menggunakan `ExtCodetextBuilder` dari Aspose.BarCode, Anda dapat dengan aman menyematkan teks UTF‑8 seperti karakter Cyrillic di dalam simbol DataMatrix. Hasilnya dapat bekerja dengan pemindai apa pun yang mendukung standar DataMatrix.

Dalam tutorial ini Anda akan:

* Menginstal paket Aspose.BarCode yang diperlukan.
* Membuat extended codetext yang mencampur data biasa dan teks Rusia.
* **Menghasilkan DataMatrix barcode** dengan string yang diperluas.
* Menyesuaikan parameter barcode seperti ukuran modul.
* Menyimpan barcode sebagai file PNG.

Tidak diperlukan layanan eksternal; semuanya berjalan secara lokal di mesin Anda.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terinstal.
* Lisensi aktif Aspose.BarCode untuk Python (versi percobaan gratis dapat digunakan untuk pengembangan).
* Familiaritas dasar dengan scripting Python.

Anda dapat menginstal library Aspose.BarCode melalui pip:

```bash
pip install aspose-barcode
```

## Langkah 1: Membuat string extended codetext

Tugas pertama adalah membuat satu string yang berisi baik pengidentifikasi produk biasa maupun frasa Rusia. `ExtCodetextBuilder` memungkinkan Anda menggabungkan bagian‑bagian codetext yang berbeda sambil mempertahankan informasi enkodingnya.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Mengapa langkah ini penting** – Simbol DataMatrix menyimpan byte mentah. Ketika Anda perlu mencampur alfabet, Anda harus memberi tahu encoder set karakter mana yang berlaku untuk setiap segmen. Metode `add_eci_codetext` menyisipkan indikator ECI sebelum teks Rusia, memastikan pemindai menginterpretasikan byte sebagai UTF‑8. Tanpa ECI, karakter Cyrillic akan muncul sebagai data yang rusak.

## Langkah 2: Membuat generator barcode DataMatrix

Dengan extended codetext siap, buat instance `BarcodeGenerator` dengan menentukan tipe `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Mengapa DataMatrix?** – DataMatrix adalah barcode dua dimensi yang dapat menyimpan hingga 2.335 karakter alfanumerik atau 1.556 byte. Ini ideal untuk barang kecil, komponen industri, dan situasi di mana Anda perlu menyematkan teks multibahasa.

## Langkah 3: (Opsional) Mengonfigurasi parameter barcode

Aspose.BarCode menyediakan banyak parameter. Untuk sebagian besar kasus penggunaan, pengaturan default menghasilkan simbol yang dapat dibaca. Namun, Anda mungkin ingin mengontrol ukuran setiap modul (kotak terkecil dalam matriks) agar sesuai dengan kebutuhan pencetakan.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Parameter berguna lainnya termasuk tingkat koreksi kesalahan, margin, dan warna latar belakang. Sesuaikan hanya jika lingkungan pemindaian target Anda memerlukan toleransi tertentu.

## Langkah 4: Menyimpan gambar barcode

Akhirnya, tulis barcode ke sebuah file. Metode `save` mendukung PNG, JPEG, BMP, dan beberapa format vektor.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Saat Anda membuka `extended_codetext.png`, Anda akan melihat simbol DataMatrix yang tajam. Memindainya dengan pembaca DataMatrix standar mengembalikan dua bagian:

1. **ABC123** – pengidentifikasi biasa.
2. **Привет** – salam Rusia, terdekripsi dengan benar sebagai UTF‑8.

## Contoh lengkap yang dapat dijalankan

Berikut adalah skrip lengkap yang dapat Anda salin‑tempel ke dalam file bernama `generate_datamatrix.py`. Ganti `YOUR_DIRECTORY` dengan folder yang ada di sistem Anda.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Jalankan skrip dari baris perintah:

```bash
python generate_datamatrix.py
```

Anda harus melihat output konsol yang mirip dengan:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Memverifikasi hasil

Untuk memastikan bahwa barcode mengodekan frasa Rusia dengan benar:

1. Buka file PNG dengan penampil gambar.
2. Gunakan aplikasi pemindai DataMatrix apa pun (banyak aplikasi seluler mendukungnya) atau pemindai perangkat keras.
3. String yang terdekripsi harus menampilkan `ABC123Привет` (atau dua bagian terpisah tergantung pada UI pemindai).

Jika karakter Rusia muncul sebagai teks tidak terbaca, periksa kembali bahwa pemindai mendukung ECI UTF‑8. Sebagian besar pembaca modern melakukannya, tetapi perangkat lama mungkin memerlukan konfigurasi eksplisit.

## Kesalahan umum dan cara menghindarinya

| Issue | Cause | Fix |
|-------|-------|-----|
| Output Cyrillic yang terdistorsi | Indikator ECI tidak ada | Gunakan `add_eci_codetext` dengan `eci_encoding=3`. |
| Barcode terlalu kecil untuk printer | Ukuran modul default terlalu kecil untuk DPI rendah | Tingkatkan `x_dimension` (misalnya `3.0` atau `4.0`). |
| File tidak tersimpan | Path direktori tidak valid | Pastikan `YOUR_DIRECTORY` ada dan dapat ditulisi. |
| Pemindai tidak dapat membaca | Kepadatan data berlebih | Kurangi jumlah data yang dienkode atau tingkatkan level koreksi kesalahan (`generator.parameters.barcode.error_correction_level`). |

## Memperluas contoh

Anda dapat mengadaptasi pola ini untuk bahasa atau tipe data lain:

* **Menyandikan teks Jepang atau Arab** – ubah `eci_encoding` ke nilai yang sesuai (misalnya 5 untuk ISO‑8859‑5, 6 untuk ISO‑8859‑7).  
* **Menambahkan beberapa segmen ECI** – panggil `add_eci_codetext` beberapa kali, masing‑masing dengan enkodingnya sendiri.  
* **Membuat kode QR sebagai gantinya** – ganti `EncodeTypes.DATA_MATRIX` dengan `EncodeTypes.QR`.  

Semua langkah lain tetap sama karena `ExtCodetextBuilder` mengabstraksi penanganan byte tingkat rendah.

## Kesimpulan

Anda sekarang tahu cara **menghasilkan barcode DataMatrix** di Python dan **mengodekan teks Rusia** menggunakan fitur extended codetext dari Aspose.BarCode. Skrip lengkap menangani negosiasi set karakter, pembuatan barcode, dan output gambar dengan hanya beberapa baris kode.

Selanjutnya, jelajahi simbol barcode lain (PDF417, Aztec) atau integrasikan generator ke dalam layanan web yang mengembalikan gambar PNG sesuai permintaan. Prinsip yang sama—membangun extended codetext dan memilih `EncodeTypes` yang tepat—berlaku di seluruh rangkaian Aspose.BarCode.

Selamat coding, dan nikmati kekuatan pembuatan barcode multibahasa!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Menghasilkan barcode DataMatrix dalam mode ASCII dengan Aspose.BarCode untuk .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}