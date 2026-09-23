---
category: general
date: 2026-09-23
description: Pelajari cara menghasilkan barcode Code 128 dan menyimpan gambar barcode
  menggunakan Aspose.BarCode di Python – panduan langkah demi langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: id
lastmod: 2026-09-23
og_description: Hasilkan kode batang Code 128 dan simpan gambar kode batang dengan
  Aspose.BarCode di Python. Ikuti contoh lengkap ini untuk membuat, menyesuaikan,
  dan mengekspor kode batang sebagai file PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Buat barcode Code 128 dan simpan gambar barcode – Panduan Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Cara menghasilkan barcode Code 128 dan menyimpan gambar barcode dengan Aspose.BarCode
url: /id/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode Code 128 dan menyimpan gambar barcode dengan Aspose.BarCode

Jika Anda perlu **menghasilkan barcode Code 128** dan **menyimpan gambar barcode** dalam proyek Python, tutorial ini menunjukkan langkah‑langkah tepatnya. Dengan menggunakan `ExtCodetextBuilder` dari Aspose.BarCode, Anda dapat menyematkan teks biasa dan segmen Unicode dalam satu payload, kemudian merender hasilnya sebagai file PNG.

Anda akan melihat skrip lengkap yang dapat dijalankan, penjelasan setiap baris, dan tips untuk jebakan umum seperti menangani enkoding ECI atau memilih folder output yang tepat. Tidak diperlukan dokumentasi eksternal—cukup salin, tempel, dan jalankan.

## Prasyarat

* Python 3.8+ terinstal.
* Paket `aspose.barcode` (pasang dengan `pip install aspose-barcode`).
* Izin menulis ke direktori tempat PNG akan disimpan.

Kode ini bekerja dengan semua simbolologi yang didukung oleh Aspose.BarCode, tetapi contoh ini berfokus pada **Code 128** karena secara efisien mengkodekan data alfanumerik dan mendukung set karakter yang diperluas.

## Langkah 1: Impor kelas yang diperlukan

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Mengapa langkah ini?* Mengimpor kelas memberi Anda akses ke builder untuk extended codetext, writer yang membuat gambar, dan version helper yang dapat berguna untuk men‑debug pembaruan pustaka.

## Langkah 2: Bangun extended codetext

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` memungkinkan Anda mencampur data ASCII biasa dan Unicode dalam satu payload barcode. Byte ECI (Extended Channel Interpretation) `0x03` memberi tahu pemindai bahwa byte berikutnya dienkode UTF‑8, yang penting untuk bahasa seperti Rusia, Cina, atau Arab.

## Langkah 3: Konfigurasikan barcode writer untuk Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Menetapkan `encode_type` ke `CODE_128` memberi instruksi kepada writer untuk merender **barcode Code 128**. Properti `code_text` menerima string extended yang dibangun pada langkah sebelumnya.

## Langkah 4: Simpan gambar barcode sebagai PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Metode `save` menulis barcode ke sebuah file. Menggunakan `BarCodeImageFormat.PNG` memastikan kompresi loss‑less dan kompatibilitas luas dengan aplikasi web dan seluler.

## Langkah 5 (opsional): Verifikasi versi pustaka Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Mengetahui versi pustaka yang tepat membantu saat Anda perlu melaporkan bug atau membandingkan perilaku antar rilis.

## Output yang Diharapkan

Menjalankan skrip menghasilkan output konsol yang mirip dengan:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

PNG yang dihasilkan (`extended_codetext.png`) terlihat seperti ini:

![Barcode Code 128 yang dihasilkan oleh Python disimpan sebagai gambar PNG](images/code128_extended.png)

*Gambar ini menunjukkan barcode Code 128 yang mengkodekan baik string ASCII `ABC123` maupun kata Rusia “Пример”.*

## Pertanyaan umum dan penanganan kasus tepi

| Question | Answer |
|----------|--------|
| **Apakah saya dapat menggunakan simbolologi yang berbeda?** | Ya. Ganti `BarCodeEncodeMode.CODE_128` dengan mode lain yang didukung seperti `QR`, `EAN_13`, atau `PDF_417`. |
| **Bagaimana jika teks Unicode saya berisi emoji?** | Emoji juga merupakan karakter UTF‑8, sehingga pemanggilan `add_eci_codetext` yang sama berfungsi. Pastikan pemindai target mendukung ECI yang Anda gunakan. |
| **Bagaimana cara mengubah ukuran gambar?** | Setel `writer.x_dimension` dan `writer.bar_height` sebelum memanggil `save`. |
| **Folder apa yang harus saya gunakan untuk `output_path`?** | Folder apa pun yang dapat ditulisi oleh proses Python. Gunakan `os.makedirs` dengan `exist_ok=True` untuk membuatnya secara otomatis. |

## Tips Pro

* **Hindari meng‑hard‑code jalur.** Gunakan `os.path.join` dan `Path` dari modul `pathlib` untuk kompatibilitas lintas‑platform.
* **Validasi barcode.** Setelah menyimpan, Anda dapat membaca kembali gambar dengan `barcode.BarCodeReader` untuk memastikan bahwa teks yang dikodekan cocok dengan `extended_codetext`.
* **Tips performa.** Jika Anda menghasilkan banyak barcode dalam sebuah loop, gunakan kembali satu instance `BarCodeWriter` dan hanya perbarui `code_text` setiap iterasi.

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode Code 128** dengan data ASCII dan Unicode campuran serta **menyimpan gambar barcode** sebagai PNG menggunakan Aspose.BarCode di Python. Skrip lengkap mencakup pembuatan extended codetext, konfigurasi writer, mengekspor gambar, dan memeriksa versi pustaka.

Dari sini Anda dapat menjelajahi:

* Menambahkan warna latar depan/latar belakang (`writer.back_color`, `writer.fore_color`).
* Menyematkan barcode dalam PDF dengan `Aspose.PDF`.
* Menggunakan kelas `BarCodeReader` untuk mendekode gambar yang disimpan dan memverifikasi konten secara otomatis.

Selamat coding, dan silakan bereksperimen dengan simbolologi lain serta format gambar!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Menghasilkan Barcode Code128 dengan Aspose.Barcode Python – Panduan Lengkap](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Cara menghasilkan barcode di Python – panduan langkah demi langkah lengkap](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Cara Menghasilkan Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}