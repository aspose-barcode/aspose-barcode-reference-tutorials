---
category: general
date: 2026-08-12
description: Buat databar omnidirectional dengan Python dan pelajari cara membuat
  gambar barcode Python menggunakan Aspose.BarCode. Ikuti panduan langkah demi langkah
  untuk solusi lengkap.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: id
lastmod: 2026-08-12
og_description: Buat databar omnidirectional dengan Python dan hasilkan gambar barcode
  dalam hitungan menit. Tutorial ini menampilkan contoh lengkap yang dapat dijalankan.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Buat databar omnidirectional – panduan lengkap Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Buat gambar databar dan kode batang omni arah dengan Python
url: /id/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Omni-directional Databar dan Gambar Barcode di Python

Jika Anda perlu **membuat omni directional databar** dalam proyek Python, panduan ini menunjukkan cara melakukannya serta cara **membuat barcode image python** menggunakan pustaka Aspose.BarCode. Anda akan mendapatkan skrip siap‑jalankan yang menghasilkan dua file PNG dengan rasio aspek yang berbeda.

Membuat DataBar yang mengikuti spesifikasi Omni‑directional merupakan kebutuhan umum untuk aplikasi ritel dan logistik. Tutorial ini mencakup instalasi, konfigurasi X‑dimension, penyesuaian rasio aspek, dan penyimpanan gambar akhir. Tidak ada layanan eksternal yang diperlukan; semuanya berjalan secara lokal.

## Apa yang Anda butuhkan

Sebelum memulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terpasang di mesin Anda.  
* Akses ke terminal atau command prompt.  
* Izin menulis ke folder tempat gambar barcode akan disimpan.  

Satu‑satunya ketergantungan pihak ketiga adalah **Aspose.BarCode for Python via .NET**, yang mendukung tipe Omni‑directional DataBar secara langsung.

## Langkah 1: Instal Aspose.BarCode untuk Python

Aspose.BarCode menyediakan kelas `BarcodeGenerator` yang digunakan dalam contoh kode. Instal paket dengan `pip`:

```bash
pip install aspose-barcode
```

Paket ini menyertakan binding runtime .NET yang diperlukan, sehingga Anda tidak perlu menginstal .NET SDK secara terpisah.

## Langkah 2: Impor pustaka dan buat generator

Baris pertama skrip membuat generator untuk Omni‑directional DataBar bertumpuk. Nilai GTIN‑14 `(01)12345678901231` digunakan sebagai data contoh.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Mengapa langkah ini penting*: Konstanta `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` memberi tahu pustaka untuk mengkodekan nilai sebagai Omni‑directional DataBar, yang merupakan format yang dibutuhkan oleh banyak pemindai point‑of‑sale.

## Langkah 3: Atur X‑dimension (lebar modul)

X‑dimension menentukan lebar modul bar terkecil. Nilai `2` piksel menghasilkan barcode yang jelas dan dapat dibaca tanpa ukuran file yang berlebihan.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Mengapa langkah ini penting*: Menyesuaikan X‑dimension memungkinkan Anda menyeimbangkan keterbacaan dan dimensi gambar. X‑dimension yang terlalu kecil dapat menghasilkan kualitas buruk pada printer beresolusi rendah.

## Langkah 4: Konfigurasikan rasio aspek dan simpan gambar pertama

Rasio aspek memengaruhi tinggi keseluruhan DataBar relatif terhadap lebarnya. Rasio aspek `15` menciptakan gaya visual yang kompak.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Tip Pro**: Gunakan `pathlib.Path` untuk membangun jalur output, yang secara otomatis membuat direktori yang belum ada.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Langkah 5: Ubah rasio aspek untuk gaya visual kedua dan simpan gambar lain

Mengubah rasio aspek menjadi `30` menghasilkan barcode yang lebih tinggi yang mungkin diperlukan oleh perangkat keras pemindai tertentu.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Mengapa langkah ini penting*: Retailer dan perangkat pemindai memiliki batasan ukuran yang berbeda. Menyediakan kedua rasio aspek dalam satu skrip memungkinkan Anda menghasilkan gaya yang tepat tanpa menduplikasi kode.

## Skrip lengkap – buat omni directional databar dan gambar barcode python

Berikut adalah contoh lengkap yang dapat dijalankan dan menggabungkan semua langkah sebelumnya. Simpan sebagai `generate_databar.py` dan jalankan dengan `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Output yang diharapkan

Menjalankan skrip akan membuat file berikut:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Kedua gambar menampilkan Omni‑directional DataBar yang valid dan dapat dipindai oleh peralatan ritel standar.

![contoh membuat omni directional databar gambar barcode di Python](example_databar.png "membuat omni directional databar gambar barcode python")

*Gambar di atas adalah placeholder yang menggambarkan dua file PNG yang disimpan.*

## Menangani masalah umum

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode belum diinstal atau diinstal di lingkungan yang berbeda. | Aktifkan lingkungan virtual yang tepat dan jalankan `pip install aspose-barcode`. |
| `PermissionError` saat menyimpan | Skrip tidak memiliki izin menulis ke folder target. | Pilih direktori yang Anda miliki atau jalankan skrip dengan hak istimewa yang sesuai. |
| Barcode tidak dapat dipindai | X‑dimension terlalu rendah atau rasio aspek tidak kompatibel dengan pemindai. | Tingkatkan `x_dimension.pixels` menjadi 3 atau 4, dan coba nilai `aspect_ratio` lain (mis., 20, 25). |
| Runtime .NET tidak ada | Aspose.BarCode bergantung pada runtime .NET di Windows/Linux. | Instal runtime .NET terbaru dari situs Microsoft; dokumentasi paket menyediakan panduan khusus platform. |

## Memperluas contoh

Anda dapat menyesuaikan skrip untuk menghasilkan varian DataBar lain (mis., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Ganti konstanta `EncodeTypes` sesuai kebutuhan:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Jika Anda perlu menyematkan barcode ke dalam PDF, Aspose.PDF for Python dapat mengimpor file PNG secara langsung atau Anda dapat menggunakan metode `save` dengan `BarCodeImageFormat.Pdf`.

## Kesimpulan

Tutorial ini menunjukkan cara **membuat omni directional databar** dan cara **membuat barcode image python** menggunakan Aspose.BarCode. Sekarang Anda memiliki skrip lengkap dan dapat direproduksi yang menghasilkan dua file PNG dengan rasio aspek berbeda, menangani jebakan umum, dan dapat diperluas ke format barcode lainnya.

Selanjutnya, jelajahi pembuatan QR code, menambahkan barcode ke faktur PDF, atau mengotomatisasi pemrosesan batch untuk katalog produk besar. Semua topik tersebut dibangun di atas pola `BarcodeGenerator` yang sama seperti yang ditunjukkan di sini. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}