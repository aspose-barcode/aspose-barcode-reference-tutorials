---
category: general
date: 2026-11-27
description: Buat kode QR di Python menggunakan Aspose.Barcode dan pelajari cara menyimpan
  gambar kode batang ke disk dengan cepat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: id
lastmod: 2026-11-27
og_description: Buat kode QR di Python dengan Aspose.Barcode dan langsung simpan gambar
  kode batang. Ikuti contoh lengkap untuk membuat, menyesuaikan, dan menyimpan kode
  QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Buat barcode QR dan simpan gambar dengan Python – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Buat kode QR dan simpan gambar dengan Python
url: /id/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat QR barcode dan simpan gambar dengan Python

Jika Anda perlu **generate QR barcode** dalam aplikasi Python, panduan ini menunjukkan cara melakukannya menggunakan library Aspose.Barcode. Anda juga akan belajar cara yang benar untuk **save barcode image** ke folder lokal, mengambil detail versi library, dan menangani segmen codetext yang diperluas.

Membuat QR code adalah kebutuhan umum untuk sistem tiket, pembayaran seluler, dan pelacakan produk. Pada akhir tutorial ini Anda akan memiliki skrip siap‑jalan yang menghasilkan file gambar QR barcode dan mencetak informasi versi untuk keperluan debugging atau kepatuhan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terpasang.
* Paket `aspose-barcode`. Instal dengan `pip install aspose-barcode`.
* Izin menulis ke direktori tempat gambar barcode akan disimpan.

Tidak ada layanan eksternal tambahan yang diperlukan; seluruh proses berjalan secara lokal.

## Langkah 1: Bangun extended codetext dengan `ExtCodetextBuilder`

Extended codetext memungkinkan Anda mencampur teks biasa dan segmen ECI (Extended Channel Interpretation) dalam satu QR code. Ini berguna ketika Anda perlu menyematkan karakter dari set karakter yang berbeda, seperti tanda Euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Mengapa langkah ini penting:**  
`ExtCodetextBuilder` menyusun string akhir yang akan diproses oleh encoder QR. Tanpa membangun extended codetext, barcode hanya akan berisi karakter ASCII biasa dan tidak dapat merepresentasikan simbol khusus locale.

## Langkah 2: Ambil string extended codetext yang digabungkan

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Outputnya terlihat seperti:

```
Extended codetext: ABC123[ECI3]€123
```

Penanda `[ECI3]` dalam tanda kurung memberi tahu encoder QR untuk beralih ke set karakter yang ditentukan untuk karakter berikutnya.

## Langkah 3: Hasilkan QR barcode menggunakan extended codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Penjelasan:**  
`BarcodeGenerator` menerima dua argumen: tipe barcode (`QR`) dan data yang akan dienkode (`extended_codetext`). Generator menyiapkan semua struktur internal yang diperlukan untuk rendering.

## Langkah 4: Simpan gambar barcode yang dihasilkan

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Mengapa Anda harus menggunakan pendekatan ini:**  
Memanggil `save` secara langsung menulis gambar ke disk menggunakan format yang disimpulkan dari ekstensi file. Metode ini mendukung PNG, JPEG, BMP, dan TIFF, memberi Anda fleksibilitas untuk berbagai konsumen downstream.

### Memverifikasi gambar yang disimpan

Buka file `output/qr_extended.png` dengan penampil gambar apa pun. Anda harus melihat QR code yang, ketika dipindai, mengembalikan string `ABC123€123`. Sebagian besar pemindai QR seluler modern menangani segmen ECI secara otomatis.

## Langkah 5: Query informasi versi Aspose.BarCode (opsional tetapi berguna)

Mengetahui versi tepat library Aspose.BarCode membantu ketika Anda perlu melaporkan bug atau memverifikasi kompatibilitas.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Output tipikal:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Skrip lengkap – salin, tempel, dan jalankan

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Menjalankan skrip menghasilkan gambar QR code dan mencetak baik extended codetext maupun detail versi ke konsol.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian yang disarankan |
|-----------|------------------------|
| **Set karakter yang berbeda** | Ubah identifier ECI yang diberikan ke `add_eci_codetext`. Untuk UTF‑8 gunakan `5`. |
| **Koreksi error yang lebih tinggi** | Set `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` sebelum memanggil `save`. |
| **Ukuran gambar khusus** | Gunakan `barcode.parameters.image_width` dan `barcode.parameters.image_height` untuk mengontrol dimensi piksel. |
| **Output non‑PNG** | Ubah ekstensi file di `output_path` menjadi `.jpg` atau `.bmp`. Library secara otomatis memilih encoder yang tepat. |

## Tips profesional

* **Buat folder output** secara programatik jika mungkin belum ada:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validasi QR code** setelah pembuatan dengan membacanya kembali menggunakan `aspose.barcode.BarcodeReader`. Ini memastikan data yang dikodekan sesuai harapan, terutama saat menggunakan segmen ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Tips performa** – gunakan kembali satu instance `BarcodeGenerator` jika Anda perlu menghasilkan banyak QR code dalam loop. Reset properti `code_text` alih‑alih membuat objek baru setiap iterasi.

## Kesimpulan

Anda kini tahu cara **generate QR barcode** di Python dengan Aspose.Barcode, membangun extended codetext yang mencampur segmen plain dan ECI, serta dengan benar **save barcode image** ke disk. Skrip ini juga menunjukkan cara mengambil informasi versi library untuk pemecahan masalah.

Langkah selanjutnya yang dapat Anda jelajahi meliputi:

* Menambahkan overlay logo atau warna khusus ke QR code.
* Menyematkan QR barcode langsung ke PDF menggunakan Aspose.PDF.
* Mengotomatiskan generasi batch untuk dataset besar.

Silakan bereksperimen dengan payload data yang berbeda, level koreksi error, dan format gambar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Cara membuat barcode Code 128 dan menyimpan gambar barcode dengan Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Cara membuat barcode DataMatrix di Python dengan Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}