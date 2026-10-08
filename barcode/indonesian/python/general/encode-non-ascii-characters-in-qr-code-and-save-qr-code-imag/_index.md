---
category: general
date: 2026-09-10
description: Enkode karakter non‑ASCII dalam kode QR dan simpan gambar kode QR dengan
  pembuat Python sederhana. Ikuti panduan langkah demi langkah menggunakan ExtCodetextBuilder
  dan BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: id
lastmod: 2026-09-10
og_description: Enkode karakter non-ASCII dalam kode QR dan simpan gambar kode QR
  menggunakan Python. Tutorial ini menunjukkan cara membuat teks kode yang diperluas,
  menghasilkan kode QR, dan menyimpan gambar.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Encode karakter non‑ASCII dalam kode QR dan simpan gambar kode QR – panduan
  Python langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Enkode karakter non-ASCII dalam kode QR dan simpan gambar kode QR
url: /id/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enkode karakter non ASCII dalam QR code dan simpan gambar QR code

Jika Anda perlu **menkode karakter non ASCII** dalam QR code, panduan ini menunjukkan secara tepat cara melakukannya dan kemudian **menyimpan gambar QR code** ke disk. Baik Anda menangani data bahasa Rusia, Cina, atau emoji, ExtCodetextBuilder memungkinkan Anda mencampur teks biasa dan segmen yang dienkode ECI tanpa harus mengutak‑atik byte secara manual.

Anda akan belajar cara membuat string codetext ekstended, menghasilkan QR code yang memahami string tersebut, dan akhirnya menulis gambar barcode ke sebuah file. Tutorial ini mengasumsikan pengetahuan dasar Python dan bahwa Anda telah menginstal SDK `barcode`.

## Prasyarat

Sebelum Anda mulai, pastikan Anda memiliki:

* Python 3.8+ terinstal.
* Paket Python `barcode` (atau SDK yang sesuai) yang menyediakan `ExtCodetextBuilder`, `CodetextEncodingType`, dan `BarcodeGenerator`.
* Izin menulis ke direktori tempat Anda ingin **menyimpan gambar QR code**.

Anda dapat menginstal SDK dengan pip (ganti `barcode-sdk` dengan nama paket yang sebenarnya):

```bash
pip install barcode-sdk
```

## Langkah 1: Buat pembuat extended codetext

Langkah pertama adalah menginstansiasi `ExtCodetextBuilder`. Objek ini mengumpulkan beberapa segmen teks dan menghasilkan satu string yang dapat dipahami oleh simbol QR code.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Mengapa ini penting*: QR code mendukung **extended codetext**, yang berarti Anda dapat menyematkan beberapa mode enkoding (plain, ECI, dll.) dalam satu barcode. Builder ini mengabstraksi format tingkat‑rendah yang diperlukan oleh spesifikasi QR.

## Langkah 2: Tambahkan segmen teks biasa

Teks biasa adalah mode default dan berfungsi untuk karakter ASCII. Menambahkannya terlebih dahulu memberikan fallback yang dapat dibaca bagi pemindai yang mengabaikan ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Jika Anda melewatkan langkah ini, QR code hanya akan berisi segmen ECI, yang mungkin tidak dapat didekode dengan benar oleh beberapa pembaca lama.

## Langkah 3: Tambahkan segmen yang dienkode ECI untuk karakter non‑ASCII

Untuk menyertakan karakter di luar rentang ASCII—seperti Cyrillic, Cina, atau emoji—Anda harus menentukan enkoding ECI (Extended Channel Interpretation). Di sini kami menggunakan UTF‑8 untuk kata Rusia “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Mengapa ini berhasil*: Spesifikasi QR mendefinisikan nilai ECI yang memberi tahu pemindai set karakter mana yang harus diterapkan. Tanpa penanda ECI, byte mentah akan diinterpretasikan sebagai ISO‑8859‑1, menghasilkan output yang kacau.

## Langkah 4: Dapatkan string extended codetext yang digabungkan

Setelah menambahkan semua segmen yang diinginkan, panggil `get_extended_codetext()` untuk memperoleh string akhir yang diharapkan oleh generator barcode.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Nilai yang dicetak terlihat seperti serangkaian karakter kontrol diikuti oleh teks sebenarnya, namun Anda tidak perlu mem‑parse‑nya secara manual.

## Langkah 5: Hasilkan QR code menggunakan extended codetext

Sekarang buat `BarcodeGenerator`, atur simbolologi ke QR (satu‑satunya simbolologi 2‑D umum yang mendukung extended codetext), dan berikan string yang telah digabungkan.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: Jika Anda mencoba proses yang sama dengan Code‑128 atau DataMatrix, SDK akan mengeluarkan pengecualian karena format tersebut tidak dapat menginterpretasikan penanda ECI.

## Langkah 6: Simpan gambar QR code

Akhirnya, tulis barcode ke file PNG. Di sinilah Anda **menyimpan gambar QR code** untuk penggunaan selanjutnya.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Pastikan folder `output` ada atau buat dengan `os.makedirs('output', exist_ok=True)` sebelum memanggil `save`.

### Contoh lengkap yang dapat dijalankan

Menggabungkan semua langkah memberikan Anda skrip mandiri yang dapat dijalankan langsung:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Output yang diharapkan** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Membuka `qr_extended.png` dengan pemindai QR apa pun akan menampilkan `HelloWorldПривет`. Pemindai yang memahami ECI akan menampilkan karakter Cyrillic dengan benar; yang lain hanya akan menampilkan bagian ASCII.

## Pertanyaan umum & kasus tepi

| Pertanyaan | Jawaban |
|------------|---------|
| *Apakah saya dapat menggunakan enkoding lain seperti Shift‑JIS?* | Ya. Ganti `CodetextEncodingType.UTF_8` dengan `CodetextEncodingType.SHIFT_JIS` dan berikan teks yang sesuai. |
| *Bagaimana jika data yang digabung melebihi kapasitas QR?* | QR code memiliki batas versi (hingga 177 × 177 modul). Jika builder mengeluarkan pengecualian ukuran, tingkatkan level koreksi kesalahan atau bagi data ke beberapa QR code. |
| *Apakah saya perlu mengatur versi QR tertentu?* | SDK secara otomatis memilih versi terkecil yang cocok dengan data. Anda dapat memaksa versi dengan `qr_generator.set_qr_version(10)` jika diperlukan. |
| *Apakah gambar akan transparan?* | Secara default SDK menulis PNG dengan latar belakang putih. Gunakan `qr_generator.set_background_color(Color.Transparent)` sebelum `save` jika Anda memerlukan transparansi. |

## Kesimpulan

Dalam tutorial ini Anda belajar cara **menkode karakter non ASCII** dalam QR code menggunakan `ExtCodetextBuilder` dan kemudian **menyimpan gambar QR code** dengan `BarcodeGenerator`. Proses ini melibatkan pembuatan string extended codetext, menambahkan segmen teks biasa dan segmen yang dienkode ECI, menghasilkan simbolologi QR, dan akhirnya menulis file gambar.

Dari sini Anda dapat mengeksplorasi:

* Menambahkan lebih banyak segmen ECI (bahasa berbeda atau emoji).
* Menyesuaikan level koreksi kesalahan QR untuk keandalan yang lebih tinggi.
* Menyematkan PNG yang dihasilkan ke dalam PDF atau halaman web.

Selamat coding, dan selamat menikmati membuat QR code multibahasa!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Menghasilkan Barcode Code128 dengan Aspose.Barcode Python – Panduan Lengkap](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [tampilkan nama produk menggunakan perpustakaan barcode Python – panduan langkah‑demi‑langkah](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}