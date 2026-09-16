---
category: general
date: 2026-07-30
description: Buat kode batang Databar Stacked Omnidirectional di Python. Ikuti panduan
  langkah demi langkah ini untuk mengatur rasio aspek, XDimension, dan mengekspor
  PNG menggunakan generator kode batang Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: id
lastmod: 2026-07-30
og_description: Buat kode batang Databar Stacked Omnidirectional di Python. Tutorial
  ini menunjukkan cara mengatur XDimension, menyesuaikan rasio aspek DataBar, dan
  menyimpan sebagai PNG dengan BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Buat Barcode Databar Tumpuk Omnidireksional – Tutorial Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Buat Barcode Databar Stacked Omnidirectional dengan Python
url: /id/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Databar Stacked Omnidirectional Barcode di Python

Pernah membutuhkan untuk **membuat databar stacked omnidirectional** barcode di Python tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian—banyak pengembang mengalami kebuntuan saat pertama kali menggunakan kelas `BarcodeGenerator`. Kabar baiknya, seluruh proses cukup sederhana setelah Anda memahami properti kunci.

Dalam panduan ini kami akan membahas contoh lengkap yang dapat dijalankan yang menggunakan **python barcode generator** untuk mengatur XDimension, menyesuaikan rasio aspek DataBar, dan akhirnya mengekspor dua file PNG. Pada akhir panduan Anda akan memiliki pemahaman yang kuat tentang cara menghasilkan simbol stacked omnidirectional berkualitas tinggi untuk proyek inventaris atau logistik apa pun.

## Apa yang Akan Anda Pelajari

- Cara menginstansiasi generator **databar stacked omnidirectional** dengan payload GTIN‑14.  
- Mengapa **ukuran pixel XDimension** penting untuk keandalan pemindaian.  
- Dampak **rasio aspek DataBar** pada lebar baris vs. tinggi.  
- Cara menyimpan hasil sebagai file **BarCodeImageFormat PNG**.  
- Tips untuk menggunakan kembali objek generator yang sama untuk menghasilkan beberapa varian tanpa beban memori tambahan.

### Prasyarat

- Python 3.8+ (perpustakaan yang kami gunakan adalah pure‑Python, tidak memerlukan wheel yang dikompilasi).  
- Paket `barcode-generator` (pasang via `pip install barcode-generator`).  
- Folder yang dapat Anda tulis – skrip akan menaruh dua gambar PNG di sana.

Jika Anda nyaman dengan impor Python dasar dan kode berorientasi objek, Anda siap memulai.

## Membuat Databar Stacked Omnidirectional Barcode – Ikhtisar Langkah

Di bawah ini kami membagi alur kerja menjadi enam langkah kecil. Setiap langkah adalah potongan kode mandiri yang dapat Anda salin‑tempel ke REPL atau file skrip. Jangan ragu bereksperimen—mengubah rasio aspek atau XDimension akan langsung memberikan gaya visual yang berbeda.

---

## Langkah 1: Buat Generator Databar Stacked Omnidirectional

Hal pertama yang kami lakukan adalah **membuat databar stacked omnidirectional** instance generator, dengan memberikan enum `EncodeTypes` yang sesuai dan string data.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Mengapa ini penting:** Flag `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu perpustakaan untuk menghasilkan simbol stacked omnidirectional, yang merupakan satu‑satunya varian DataBar yang dapat mengenkode hingga 14 digit sekaligus tetap dapat dibaca dari sudut mana pun.

---

## Konfigurasikan Ukuran Pixel XDimension

Ukuran pixel **XDimension** mengontrol modul terkecil (garis hitam paling tipis). Nilai `2` pixel bekerja baik untuk kebanyakan skenario tampilan layar.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Tip pro:** Jika Anda berencana mencetak barcode dengan DPI tinggi, naikkan nilai ini menjadi 3 atau 4 untuk menghindari tepi yang blur.

---

## Sesuaikan Rasio Aspek DataBar (15)

Rasio aspek **DataBar** menentukan seberapa lebar setiap baris dibandingkan dengan tingginya. Rasio aspek `15` menghasilkan baris yang lebih lebar, yang disukai banyak pemindai untuk penangkapan gerakan cepat.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Mengapa 15?** Spesifikasi resmi GS1 merekomendasikan rasio antara 10 dan 20 untuk simbol stacked omnidirectional. Kami memilih `15` sebagai nilai default yang seimbang.

---

## Ekspor Barcode sebagai PNG Menggunakan BarCodeImageFormat

Setelah generator dikonfigurasi, kami menyimpan gambar. Enum `BarCodeImageFormat.Png` memastikan output lossless, sempurna untuk pemrosesan selanjutnya.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Apa yang akan Anda lihat:** Buka PNG yang dihasilkan; Anda akan melihat barcode yang bersih, kontras tinggi dengan baris yang relatif lebar.

---

## Ubah Rasio Aspek DataBar menjadi 30

Kadang Anda membutuhkan baris yang lebih tinggi daripada lebih lebar—mungkin untuk menyesuaikan label sempit. Mengubah **rasio aspek DataBar** menjadi `30` membuat setiap baris menjadi lebih tinggi.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Kasus tepi:** Rasio yang sangat tinggi (mis., >40) dapat menyebabkan barcode melebihi tinggi label standar, jadi uji pada printer nyata sebelum memutuskan.

---

## Ekspor Barcode Lagi dengan Rasio Aspek Baru

Akhirnya, kami menggunakan kembali objek `barcode_generator` yang sama untuk menulis PNG kedua. Tidak perlu membuat ulang generator—cukup ubah properti dan panggil `Save` lagi.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Hasil:** Sekarang Anda memiliki dua file PNG—satu dengan baris lebar (`AR15`) dan satu lagi dengan baris tinggi (`AR30`). Bandingkan keduanya berdampingan untuk memutuskan mana yang paling cocok untuk pengaturan pemindai Anda.

---

## Contoh Kerja Lengkap

Menggabungkan semuanya, berikut skrip lengkap yang dapat Anda jalankan langsung. Ganti `YOUR_DIRECTORY` dengan jalur absolut di mesin Anda.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Output yang diharapkan** (di konsol Anda):

```
✅ Two PNG files created – AR15 and AR30
```

Dan dua file gambar muncul di folder target, siap untuk pengujian pemindaian.

---

## Kesimpulan

Kami baru saja **membuat databar stacked omnidirectional** barcode di Python, menyesuaikan **ukuran pixel XDimension**, bereksperimen dengan dua pengaturan **rasio aspek DataBar** yang berbeda, dan mengekspor hasilnya sebagai file **BarCodeImageFormat PNG**. Seluruh alur kerja muat dalam beberapa baris kode, namun memberi Anda kontrol penuh atas karakteristik visual yang paling penting bagi pemindai.

Apa selanjutnya? Coba ganti payload ke GTIN lain, bermain dengan warna dengan mengonversi PNG ke gambar berbasis palet, atau buat laporan PDF yang menyematkan kedua PNG berdampingan. Kelas `BarcodeGenerator` cukup fleksibel untuk menangani semua skenario tersebut, jadi silakan bereksperimen.

Ada pertanyaan tentang kasus penggunaan tertentu atau menemukan error? Tinggalkan komentar di bawah, dan saya akan dengan senang hati membantu. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat dan membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Hasilkan gambar barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}