---
category: general
date: 2026-08-09
description: Buat kode QR barcode di Python menggunakan Aspose.BarCode. Pelajari cara
  membangun codetext yang diperluas, menyesuaikan tampilan, dan menyimpan gambar—semua
  dalam satu tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: id
lastmod: 2026-08-09
og_description: Buat barcode QR di Python dengan Aspose.BarCode. Panduan ini menunjukkan
  cara membuat codetext yang diperluas, mengatur parameter visual, dan mengekspor
  gambar.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Buat kode QR dengan Aspose.BarCode di Python – contoh kode lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Buat kode batang QR dengan Aspose.BarCode di Python – panduan langkah demi
  langkah
url: /id/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat kode batang QR dengan Aspose.BarCode di Python – panduan langkah demi langkah

Jika Anda perlu **membuat kode batang QR** di Python, tutorial ini akan memandu Anda melalui seluruh proses menggunakan pustaka Aspose.BarCode. Baik Anda mengkodekan ID produk, teks multibahasa, atau data khusus, Anda akan melihat cara membangun codetext yang diperluas, menyesuaikan pengaturan visual, dan menyimpan gambar akhir dalam satu skrip yang dapat dijalankan.

Contoh ini juga menunjukkan cara menampilkan versi pustaka, yang membantu Anda memverifikasi bahwa Anda menjalankan rilis yang kompatibel. Pada akhir panduan ini Anda akan memiliki gambar kode batang QR siap pakai dan pemahaman yang jelas tentang setiap opsi konfigurasi.

## Prerequisites

Sebelum Anda memulai, pastikan Anda memiliki:

- Python 3.8+ terpasang.
- Paket `aspose-barcode` (pasang via `pip install aspose-barcode`).
- Familiaritas dasar dengan sintaks Python.
- Izin menulis ke direktori output tempat file PNG akan disimpan.

> **Pro tip:** Gunakan lingkungan virtual untuk menghindari konflik versi dengan proyek lain.

## Step 1: Verify the Aspose.BarCode library version

Menampilkan versi pustaka memastikan Anda menggunakan rilis yang mendukung codetext yang diperluas dan enkoding QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Mengapa ini penting:**  
Rilis lama mungkin tidak memiliki kelas `ExtCodetextBuilder` yang diperlukan untuk segmen campuran plain dan ECI. Memastikan versi mencegah kesalahan runtime nanti dalam alur kerja.

## Step 2: Build an extended codetext string

Codetext yang diperluas memungkinkan Anda menggabungkan data ASCII biasa dengan segmen Unicode (ECI), yang penting untuk kode QR multibahasa.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Mengapa ini penting:**  
Metode `add_plain_codetext` menyimpan data sebagai ASCII standar, sementara `add_eci_codetext` menambahkan awalan blok Unicode dengan penunjuk ECI yang sesuai. Pendekatan ini memastikan pemindai QR menginterpretasikan teks Jepang dengan benar, menghindari karakter yang rusak.

### Common variations

Variasi umum

- **Multiple ECI segments:** Panggil `add_eci_codetext` beberapa kali untuk mencampur beberapa bahasa.
- **Different ECI identifiers:** Gunakan `27` untuk ISO‑8859‑1, `28` untuk ISO‑8859‑2, dll., tergantung pada enkoding target Anda.

## Step 3: Generate the QR barcode using the extended codetext

Sekarang kita memiliki string yang diformat dengan benar, kita dapat membuat kode QR.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Mengapa ini penting:**  
`EncodeTypes.QR` memberi tahu Aspose.BarCode untuk menggunakan simbol QR. Mengirimkan `extended_codetext` secara langsung menghubungkan data campuran ke matriks QR, mempertahankan bagian plain dan Unicode.

## Step 4: Adjust visual appearance (optional but recommended)

Penyetelan halus parameter visual kode batang meningkatkan keandalan pemindaian dan menyesuaikan pedoman merek.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Mengapa ini penting:**  
- **`x_dimension`** mengontrol ukuran setiap modul QR; terlalu kecil dapat menyebabkan kesalahan pembacaan pada perangkat beresolusi rendah.
- **`border_width`** menambahkan zona tenang. Beberapa pemindai memerlukan setidaknya zona tenang 4‑modul; pustaka menambahkannya secara otomatis, tetapi Anda dapat meningkatkannya untuk keamanan ekstra.

### Edge case handling

Penanganan kasus tepi

- **Data ber‑densitas tinggi:** Jika data yang dienkode besar, Anda mungkin perlu meningkatkan `x_dimension` atau memilih tingkat koreksi kesalahan yang lebih tinggi (melalui `qr_generator.parameters.qr.error_correction_level`).
- **Latar belakang transparan:** Atur `qr_generator.parameters.barcode.bg_color = Color.Transparent` untuk PNG dengan saluran alfa.

## Step 5: Save the QR barcode image

Akhirnya, tulis gambar ke disk dalam format pilihan Anda.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Mengapa ini penting:**  
Menyimpan sebagai PNG mempertahankan kualitas lossless, yang ideal untuk kode QR yang memerlukan tepi tajam. Jika Anda memerlukan format lain untuk aplikasi web, cukup ubah enumerasi `BarCodeImageFormat`.

### Verifying the result

Memverifikasi hasil

Buka file yang disimpan di penampil gambar apa pun. Anda harus melihat kode QR yang, ketika dipindai, mengembalikan string gabungan:

```
ABC12345
こんにちは
```

Sebagian besar aplikasi pemindai QR modern menampilkan segmen plain terlebih dahulu dan kemudian menampilkan salam Jepang dengan benar.

---

## Full runnable script

Skrip lengkap yang dapat dijalankan

Salin seluruh blok di bawah ini ke dalam file bernama `create_qr_barcode.py` dan jalankan dengan `python create_qr_barcode.py`. Sesuaikan `YOUR_DIRECTORY` ke folder yang dapat ditulisi di mesin Anda.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Menjalankan skrip ini akan mencetak versi, codetext yang diperluas, dan konfirmasi bahwa file PNG telah dibuat.

---

## Conclusion

Kesimpulan

Anda sekarang tahu cara **membuat gambar kode batang QR** di Python menggunakan Aspose.BarCode. Tutorial ini mencakup:

1. Memverifikasi versi pustaka.
2. Membangun codetext yang diperluas dengan segmen plain dan ECI (Unicode).
3. Menghasilkan kode QR.
4. Menyesuaikan parameter visual seperti ukuran modul dan lebar batas.
5. Menyimpan gambar akhir dalam format PNG.

Dari sini Anda dapat menjelajahi:

- Mengubah tingkat koreksi kesalahan (`qr_generator.parameters.qr.error_correction_level`).
- Menambahkan logo atau gambar latar belakang (`qr_generator.parameters.qr.logo`).
- Mengekspor ke format lain seperti SVG untuk grafik web yang dapat diskalakan.
- Mengintegrasikan generator ke endpoint Flask atau Django untuk pembuatan QR secara langsung.

Bereksperimenlah dengan payload data dan pengaturan visual yang berbeda untuk menyesuaikan merek serta kebutuhan pemindaian aplikasi Anda. Selamat coding!

## What Should You Learn Next?

Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}