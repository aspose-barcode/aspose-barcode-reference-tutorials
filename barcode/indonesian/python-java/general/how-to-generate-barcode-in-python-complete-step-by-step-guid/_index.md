---
category: general
date: 2026-08-12
description: Cara menghasilkan barcode dengan cepat menggunakan Python. Pelajari cara
  membuat barcode dari data dan mengekspor gambar barcode dengan satu pustaka.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: id
lastmod: 2026-08-12
og_description: Cara menghasilkan barcode di Python dengan Aspose.BarCode. Ikuti panduan
  ini untuk membuat barcode dari data dan mengekspor gambar barcode sebagai PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Cara menghasilkan barcode di Python – panduan cepat dan andal
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Cara menghasilkan barcode di Python – panduan lengkap langkah demi langkah
url: /id/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode di Python – panduan lengkap langkah demi langkah

Jika Anda perlu **cara menghasilkan barcode** dalam aplikasi Python, tutorial ini menunjukkan kode tepat yang Anda butuhkan. Anda akan belajar **membuat barcode dari data**, menyesuaikan tampilannya, dan **mengekspor gambar barcode** sebagai file PNG—semua dalam kurang dari sepuluh baris kode.

Membuat barcode mungkin terasa seperti hal terpisah dari logika bisnis Anda yang lain, tetapi dengan satu pustaka Anda dapat menjaga proses tetap sejalan dengan basis kode yang ada. Pada bagian-bagian berikut Anda akan melihat contoh lengkap yang dapat dijalankan, memahami mengapa setiap baris penting, dan menemukan variasi umum seperti mengubah lebar modul atau menggambar barcode hanya berupa outline.

## Cara menghasilkan barcode dengan pustaka Aspose.BarCode

Pustaka Aspose.BarCode untuk Python (via .NET) menyediakan API yang sederhana untuk banyak simbol, termasuk barcode Planet yang digunakan dalam panduan ini. Sebelum memulai, pastikan Anda telah menginstal paketnya:

```bash
pip install aspose-barcode
```

> **Tip pro:** Gunakan lingkungan virtual untuk menghindari konflik versi dengan proyek lain.

### 1. Impor kelas yang diperlukan

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Impor ini memberi Anda akses ke kelas generator, enumerasi tipe barcode, dan enum format gambar yang digunakan saat menyimpan hasil.

### 2. Buat barcode dari data

Langkah pertama adalah **membuat barcode dari data**. Konstruktor `BarcodeGenerator` menerima simbol dan string mentah yang ingin Anda enkode.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Nilai `EncodeTypes.Planet` memilih barcode Planet, sementara `"123456"` adalah payload yang akan muncul dalam gambar akhir.

### 3. Sesuaikan dimensi X (lebar modul)

Dimensi X mengontrol lebar setiap modul barcode (garis tipis). Mengaturnya menjadi 4 pixel menghasilkan gambar yang jelas dan dapat dibaca tanpa membuat file terlalu besar.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Mengapa ini penting:** Dimensi X yang lebih besar meningkatkan keandalan pemindaian pada printer beresolusi rendah, sementara nilai yang lebih kecil mengurangi ukuran file untuk penggunaan web.

### 4. Ekspor gambar barcode (gaya terisi)

Sekarang Anda dapat **mengekspor gambar barcode** menggunakan metode `save`. Contoh ini menyimpan file PNG, tetapi Anda dapat memilih JPEG, BMP, atau TIFF dengan mengubah enum `BarCodeImageFormat`.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

File `PlanetFilled.png` berisi barcode Planet yang sepenuhnya terisi, siap untuk dicetak atau disisipkan dalam PDF.

### 5. Buat generator kedua untuk barcode hanya outline

Jika Anda memerlukan versi outline (batang kosong), Anda harus membuat generator baru karena flag `filled_bars` tidak dapat diubah setelah gambar disimpan.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Terapkan pengaturan dimensi X yang sama

Ketika Anda membuat generator kedua, Anda harus mengulangi semua pengaturan visual yang ingin Anda pertahankan konsistensinya.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Nonaktifkan batang terisi untuk barcode outline

Mengatur `filled_bars` menjadi `False` memberi tahu renderer untuk menggambar hanya outline setiap modul, menghasilkan gambar yang lebih ringan yang dapat berguna untuk keperluan desain.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Ekspor gambar barcode outline

Akhirnya, **ekspor gambar barcode** lagi, kali ini menyimpan versi outline.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Sekarang Anda memiliki dua file PNG: satu dengan batang solid (`PlanetFilled.png`) dan satu lagi hanya dengan outline (`PlanetEmpty.png`).

## Ekspor gambar barcode dalam format lain (opsional)

Metode `save` mendukung beberapa format. Untuk mengekspor sebagai JPEG dengan kualitas 90 %:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Jika Anda memerlukan latar belakang transparan untuk penggunaan web, pilih PNG dengan saluran alfa:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Variasi umum dan kasus tepi

| Skenario | Perubahan yang diperlukan | Potongan kode |
|----------|---------------------------|--------------|
| **Simbol berbeda** (misalnya, QR) | Gunakan nilai `EncodeTypes` yang berbeda | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Warna latar depan khusus** | Setel `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Resolusi lebih tinggi** | Tingkatkan DPI melalui `image_width` dan `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **String data besar** | Pastikan panjang data sesuai dengan spesifikasi simbol | Validate length before creating the generator |

> **Waspadai:** Memberikan data yang melebihi panjang maksimum untuk simbol yang dipilih akan memunculkan pengecualian runtime. Selalu validasi panjang string atau tangkap `ArgumentException`.

## Contoh lengkap yang dapat dijalankan

Berikut adalah skrip lengkap yang dapat Anda salin‑tempel ke dalam file bernama `generate_planet_barcode.py`. Sesuaikan `YOUR_DIRECTORY` ke folder yang ada di mesin Anda.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

Menjalankan skrip ini menghasilkan dua file PNG di direktori yang ditentukan. Verifikasi output dengan membuka gambar di penampil gambar apa pun; keduanya harus menampilkan barcode Planet yang mengenkode string `123456`.

## Kesimpulan

Sekarang Anda tahu **cara menghasilkan barcode** di Python menggunakan Aspose.BarCode, cara **membuat barcode dari data**, dan cara **mengekspor gambar barcode** dalam gaya terisi maupun outline. Pola yang sama berlaku untuk simbol lain, format gambar, dan kustomisasi visual, memberikan Anda fondasi fleksibel untuk fitur apa pun yang terkait barcode dalam aplikasi Anda.

### Langkah selanjutnya

* Jelajahi simbol lain seperti QR, Code‑128, atau DataMatrix dengan mengganti `EncodeTypes.Planet` dengan nilai yang diinginkan.  
* Integrasikan file PNG yang dihasilkan ke dalam laporan PDF menggunakan pustaka seperti `ReportLab` atau `PyPDF2`.  
* Bereksperimen dengan nilai dimensi X dinamis untuk menyesuaikan ukuran barcode berdasarkan resolusi layar atau DPI printer.

Selamat coding, dan silakan sesuaikan contoh ini agar cocok dengan kebutuhan proyek Anda!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Gambar Barcode di Java dengan Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Cara Menghasilkan Barcode Java – Panduan Konfigurasi Lengkap](/barcode/english/java/barcode-configuration/)
- [Cara membuat gambar barcode code128 di Java dengan Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}