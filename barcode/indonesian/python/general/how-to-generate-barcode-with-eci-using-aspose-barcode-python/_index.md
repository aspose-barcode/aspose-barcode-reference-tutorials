---
category: general
date: 2026-08-19
description: Cara menghasilkan barcode dengan ECI menggunakan Aspose.Barcode untuk
  Python. Pelajari cara menambahkan data ECI, mencampur teks biasa, dan menyimpan
  gambar dalam satu panduan yang jelas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: id
lastmod: 2026-08-19
og_description: Cara menghasilkan barcode dengan ECI menggunakan Aspose.Barcode untuk
  Python. Ikuti tutorial ini untuk mempelajari cara menambahkan data ECI, menyesuaikan
  tampilan, dan menyimpan hasilnya.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Cara menghasilkan barcode dengan ECI menggunakan Aspose.Barcode Python –
  langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Cara menghasilkan barcode dengan ECI menggunakan Aspose.Barcode Python
url: /id/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode dengan ECI menggunakan Aspose.Barcode Python

Jika Anda perlu mengetahui **cara menghasilkan barcode** yang berisi karakter biasa dan data yang dienkode dengan ECI, panduan ini menunjukkan proses lengkapnya. Anda akan melihat secara tepat **cara menambahkan eci** pada bagian, menyesuaikan ukuran, dan menulis gambar ke disk dengan satu skrip yang dapat dijalankan.

Tutorial ini mencakup:

* Mengambil versi pustaka Aspose.Barcode (opsional tetapi berguna untuk debugging).  
* Membuat string codetext ekstended yang mencampur karakter biasa dan karakter yang dienkode ECI.  
* Membuat generator barcode untuk simbol yang mendukung codetext ekstended.  
* Menyesuaikan dimensi barcode dan menyimpan file PNG akhir.

Tidak diperlukan dokumentasi eksternal; salin kode, jalankan, dan Anda akan mendapatkan gambar barcode yang mencakup karakter Cina yang dienkode dengan ECI 26 (UTF‑8).

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* Python 3.8 atau lebih baru terpasang.  
* Paket `aspose-barcode` terpasang (`pip install aspose-barcode`).  
* Izin menulis ke folder tempat Anda berencana menyimpan file PNG.

Jika Anda menggunakan lingkungan virtual, aktifkan terlebih dahulu untuk menjaga ketergantungan terisolasi.

## Langkah 1: Verifikasi versi Aspose.Barcode (opsional)

Mengetahui versi pustaka yang tepat membantu ketika Anda perlu melaporkan bug atau membandingkan fitur antar rilis.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Mengapa ini penting*: Output versi mengonfirmasi bahwa runtime cocok dengan dokumentasi yang Anda ikuti. Versi yang berbeda mungkin mendukung nilai ECI yang berbeda, sehingga ini merupakan pemeriksaan cepat.

## Langkah 2: Bangun codetext ekstended dengan bagian biasa dan ECI‑encoded

Aspose.Barcode menyediakan `ExtCodetextBuilder` untuk menggabungkan data biasa dan segmen yang dienkode ECI. Pada contoh ini kami mencampur string numerik dengan karakter Cina.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Penjelasan*:  
* `add_plain_codetext` menyisipkan data yang dianggap simbol barcode sebagai karakter biasa.  
* `add_eci_codetext` memberi tahu generator untuk menambahkan indikator ECI (di sini **26**, yang berhubungan dengan UTF‑8) sebelum teks yang diberikan. Ini adalah cara **menambahkan eci** ke barcode.

Anda dapat memanggil `add_eci_codetext` beberapa kali untuk menyematkan beberapa blok bahasa yang berbeda. Builder secara otomatis menangani urutan escape yang diperlukan.

## Langkah 3: Pilih simbol yang mendukung codetext ekstended

Tidak semua jenis barcode dapat menyimpan segmen ECI. Code 128, QR, dan Data Matrix adalah pilihan umum. Contoh ini menggunakan Code 128 karena didukung secara luas dan bekerja baik untuk data alfanumerik campuran.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Mengapa Code 128?*: Ia menerima seluruh rentang ASCII dan urutan escape ECI yang dihasilkan oleh builder, menjadikannya ideal untuk skenario “cara menghasilkan barcode” yang mencampur teks biasa dan teks yang dienkode.

## Langkah 4: Sesuaikan tampilan barcode

Anda dapat mengontrol ukuran, tinggi, margin, dan banyak aspek visual lainnya melalui objek `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tip*: Jika Anda berencana mencetak barcode, tingkatkan `x_dimension` dan `bar_height` secara proporsional untuk menjaga keterbacaan pada DPI target.

## Langkah 5: Simpan gambar barcode

Akhirnya, tulis gambar yang dihasilkan ke sebuah file. Aspose.Barcode mendukung PNG, JPEG, BMP, dan banyak format lainnya.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Pastikan folder `output` ada atau buat dengan `os.makedirs("output", exist_ok=True)` sebelum memanggil `save`.

### Hasil yang diharapkan

Saat Anda membuka `extended_codetext.png`, Anda akan melihat barcode Code 128 yang mengkodekan string numerik `1234567890` diikuti oleh karakter Cina “特殊字符”. Memindai barcode dengan pemindai modern yang menghormati ECI akan mengembalikan string campuran asli.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode yang dihasilkan dengan contoh cara menghasilkan barcode"}

## Pertanyaan umum dan kasus tepi

### Bagaimana jika saya membutuhkan set karakter yang berbeda?

Pilih nilai ECI yang sesuai dari tabel ISO/IEC 18004. Misalnya, ECI 27 mewakili ISO‑8859‑1 (Latin‑1). Ganti pengenal numerik dalam `add_eci_codetext` sesuai.

### Bisakah saya menyematkan lebih dari satu blok ECI?

Ya. Panggil `add_eci_codetext` beberapa kali. Builder menyisipkan kode switch ECI yang diperlukan di antara blok, mempertahankan urutan yang Anda tambahkan.

### Apakah generator mendukung kode QR dengan ECI?

Tentu saja. Ganti `barcode.Symbology.CODE_128` dengan `barcode.Symbology.QR` dan sesuaikan parameter khusus QR (mis., tingkat koreksi kesalahan) melalui `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Bagaimana menangani string data yang sangat panjang?

Untuk barcode linear seperti Code 128, panjang maksimum sekitar 80 karakter saat menggunakan codetext ekstended. Jika Anda melebihi itu, pertimbangkan beralih ke simbol dua‑dimensi seperti QR atau Data Matrix, yang dapat menyimpan ribuan karakter.

## Skrip lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke file bernama `generate_extended_barcode.py` dan jalankan langsung.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Menghasilkan Gambar Barcode dengan Kustomisasi Ruang Tambahan menggunakan Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cara Menghasilkan Gambar Barcode dalam Java dengan Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Cara menghasilkan barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}