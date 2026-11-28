---
category: general
date: 2026-11-27
description: Pelajari cara menyesuaikan tinggi bar kode dalam generator DataBar Omni‑Directional.
  Kode langkah demi langkah menunjukkan pengaturan tinggi menjadi 30 px dan 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: id
lastmod: 2026-11-27
og_description: Sesuaikan tinggi batang kode pada generator DataBar Omni‑Directional
  dengan Python. Ikuti panduan lengkap untuk mengatur tinggi, dimensi X, dan menyimpan
  gambar PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Sesuaikan tinggi batang kode pada generator DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Cara menyesuaikan tinggi bar kode batang di generator DataBar Omni‑Directional
url: /id/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menyesuaikan tinggi bar kode batang dalam generator DataBar Omni‑Directional

Jika Anda perlu **menyesuaikan tinggi bar kode batang** untuk kode batang DataBar Omni‑Directional, panduan ini menunjukkan secara tepat caranya. Anda akan melihat contoh Python lengkap yang dapat dijalankan yang mengubah tinggi bar dari 30 px menjadi 60 px sambil mempertahankan X‑dimension dan format gambar tetap konsisten.

Mengubah dimensi visual kode batang adalah kebutuhan umum ketika kode batang harus sesuai dengan ukuran label atau pedoman desain tertentu. Selain tinggi bar, Anda mungkin juga ingin menyesuaikan **X‑dimension** (ukuran modul) atau memilih **format gambar kode batang** yang berbeda seperti PNG atau JPEG.

Dalam tutorial ini Anda akan:

* Menginstal pustaka yang diperlukan (GroupDocs.Barcode untuk Python)
* Membuat generator kode batang DataBar Omni‑Directional
* Menetapkan ukuran modul dengan `XDimension`
* Menyesuaikan properti tinggi bar dua kali
* Menyimpan gambar yang dihasilkan dalam **BarCodeImageFormat** yang diinginkan

Tidak diperlukan pengalaman sebelumnya dengan API GroupDocs—hanya pengetahuan dasar Python.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terinstal
* Paket `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Izin menulis ke folder tempat file PNG akan disimpan

Jika Anda belum familiar dengan **DataBar Omni‑Directional barcode**, kode ini mengkodekan GTIN 14‑digit dan banyak digunakan di ritel untuk pemindaian dari orientasi apa pun.

## Langkah 1: Siapkan generator kode batang DataBar Omni‑Directional

Pertama, impor kelas yang diperlukan dan buat instance generator dengan data GTIN yang ingin Anda enkode.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Mengapa ini penting:* Konstanta `EncodeTypes.DatabarOmniDirectional` memberi tahu pustaka untuk menghasilkan simbolologi Omni‑Directional. String data mencakup AI `(01)` yang menandai nilai GTIN‑14.

## Langkah 2: Tentukan X‑dimension (ukuran modul)

X‑dimension mengontrol lebar bar paling sempit. Nilai umum untuk rendering di layar adalah **2 px per modul**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Menggunakan **set XDimension** yang konsisten memastikan kode batang skala dengan benar di berbagai printer dan pemindai.

## Langkah 3: Sesuaikan tinggi bar menjadi 30 px dan simpan gambar

Sekarang kita mengubah properti tinggi bar. Tinggi pertama yang akan kita gunakan adalah **30 px**, yang cocok untuk label kecil.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Konstanta `BarCodeImageFormat.Png` memilih **format gambar kode batang** PNG, yang mempertahankan kualitas lossless.

### Hasil yang Diharapkan

File `DatabarBarHeight30Pixels.png` berisi kode batang DataBar Omni‑Directional yang bar‑nya setinggi 30 px. Di bawah ini adalah pratinjau placeholder:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tip:** Jika Anda membuka PNG di editor gambar, Anda akan melihat tinggi bar yang tepat. Bar sempit berukuran 2 px lebar, seperti yang didefinisikan sebelumnya.

## Langkah 4: Ubah tinggi bar menjadi 60 px untuk kode batang yang lebih tinggi

Untuk aplikasi yang memerlukan jejak visual lebih besar—seperti label freight—Anda dapat meningkatkan tinggi bar menjadi **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Hanya properti `BarHeight` yang berubah; X‑dimension dan enkoding tetap sama, sehingga kode batang tetap dapat dipindai.

## Langkah 5: Simpan gambar kode batang yang diperbarui

Akhirnya, tulis kode batang yang lebih tinggi ke file PNG kedua.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Hasil yang Diharapkan

File `DatabarBarHeight60Pixels.png` menampilkan data yang sama, tetapi setiap bar kini setinggi 60 px. Perbedaan visual ditunjukkan di bawah ini:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Contoh lengkap yang dapat dijalankan

Menggabungkan semuanya, berikut adalah skrip lengkap yang dapat Anda salin‑tempel ke file bernama `adjust_barcode_height.py` dan jalankan langsung.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Jalankan skrip:

```bash
python adjust_barcode_height.py
```

Anda akan melihat dua file PNG di folder `output`, masing‑masing mencerminkan tinggi bar yang Anda tetapkan.

## Pertanyaan umum dan kasus tepi

| Question | Answer |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg`. JPEG bersifat lossy, jadi lebih baik gunakan PNG untuk pemindaian yang presisi. |
| **What if I need a bar height that isn’t a multiple of 10?** | Properti `BarHeight.Pixels` menerima nilai integer apa pun. Cukup tetapkan jumlah piksel yang diinginkan (misalnya `45`). |
| **Does changing the bar height affect the encoded data?** | Tidak. Hanya representasi visual yang berubah; string data yang mendasarinya tetap identik. |
| **How do I change the X‑dimension after saving the first image?** | Anda dapat memodifikasi `gen.parameters.barcode.x_dimension.pixels` kapan saja sebelum memanggil `save()`. Perubahan akan diterapkan pada gambar berikutnya. |
| **Is the generator thread‑safe?** | Instance `BarcodeGenerator` tidak dijamin thread‑safe. Buat instance terpisah per thread jika Anda menghasilkan kode batang secara bersamaan. |

## Kesimpulan

Anda kini tahu cara **menyesuaikan tinggi bar kode batang** dalam generator DataBar Omni‑Directional menggunakan Python. Tutorial ini mencakup pembuatan generator, penetapan **X‑dimension**, modifikasi properti **barcode bar height**, dan penyimpanan gambar dalam **format gambar kode batang** yang diinginkan.

Mulai sekarang Anda dapat bereksperimen dengan tinggi lain, ukuran modul yang berbeda, atau beralih ke format gambar alternatif seperti JPEG atau BMP. Anda juga dapat mengeksplorasi fitur tambahan **barcode generator python** seperti menambahkan teks yang dapat dibaca manusia atau mengubah skema warna.

Selamat coding, dan jaga kode batang Anda tetap tajam serta berukuran sempurna!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}