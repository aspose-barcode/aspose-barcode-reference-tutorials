---
category: general
date: 2026-11-27
description: Pelajari cara membuat barcode dengan teks dan menghasilkan barcode planet
  di Python—panduan langkah demi langkah untuk output PNG beresolusi tinggi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: id
lastmod: 2026-11-27
og_description: Buat barcode dengan teks dan hasilkan barcode planet di Python. Ikuti
  panduan lengkap ini untuk menghasilkan PNG beresolusi tinggi.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Buat barcode dengan teks di Python – hasilkan barcode Planet dengan mudah
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Cara membuat barcode dengan teks menggunakan format Planet di Python
url: /id/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode dengan teks menggunakan format Planet di Python

Jika Anda perlu **membuat barcode dengan teks** untuk sistem pengiriman, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat contoh singkat end‑to‑end yang menghasilkan barcode Planet, menyesuaikan resolusi, dan menyimpan hasilnya sebagai gambar PNG.

Membuat barcode adalah kebutuhan umum untuk logistik, inventaris, dan aplikasi tiket. Dalam panduan ini Anda akan belajar tidak hanya **cara menghasilkan file barcode**, tetapi juga mengapa setiap langkah konfigurasi penting dan bagaimana menghindari jebakan umum.

## Apa yang akan Anda pelajari

* Menyiapkan generator barcode Planet dengan teks khusus.
* Menyesuaikan dimensi X untuk meningkatkan ketajaman gambar.
* Menyimpan barcode sebagai file PNG yang dapat dicetak atau ditampilkan di web.
* Memperluas contoh ke tipe barcode lain atau format output lainnya.

**Prasyarat**

* Python 3.8 atau lebih baru.
* Paket `aspose-barcode` (atau perpustakaan kompatibel lain yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`).
* Familiaritas dasar dengan scripting Python.

Anda dapat menginstal paket yang diperlukan dengan:

```bash
pip install aspose-barcode
```

---

## Langkah 1: Buat barcode dengan teks – inisialisasi generator

Hal pertama yang harus Anda lakukan adalah membuat instance `BarcodeGenerator` yang mengetahui simbol apa yang akan digunakan dan teks apa yang akan dienkode. Untuk barcode Planet, nilai enum `EncodeTypes.Planet` memberi tahu perpustakaan untuk mengikuti spesifikasi USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Mengapa ini penting:**  
Objek `BarcodeGenerator` menyatukan semua pengaturan untuk barcode. Menyediakan teks pada saat konstruksi menjamin bahwa nilai yang dienkode tidak dapat diubah selama proses selanjutnya, sehingga menghilangkan ketidaksesuaian yang tidak disengaja.

---

## Langkah 2: Sesuaikan pengaturan – cara menghasilkan barcode dengan resolusi lebih tinggi

Barcode beresolusi rendah dapat terlihat buram ketika dicetak pada printer label. Dimensi X (lebar modul) mengontrol ukuran setiap bar individu. Menetapkannya ke 4 piksel menghasilkan gambar tajam, beresolusi tinggi yang cocok untuk kebanyakan printer modern.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Penjelasan:**  
* `gen.parameters.barcode.x_dimension.pixels` secara langsung memetakan lebar fisik satu modul.  
* Nilai **4** berarti setiap bar berukuran empat piksel, yang kira‑kira setara dengan 0.127 mm pada 300 dpi—dalam rentang yang direkomendasikan untuk barcode USPS Planet.  

**Tips pro:** Jika Anda memerlukan DPI yang berbeda, hitung lebar pikselnya secara sesuai (misalnya, 2 piksel untuk 150 dpi, 8 piksel untuk 600 dpi).

---

## Langkah 3: Simpan gambar – hasilkan barcode planet sebagai PNG

Setelah generator dikonfigurasi, Anda dapat merender barcode ke file gambar. PNG bersifat loss‑less, memastikan pola modul yang tepat tetap terjaga.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Hasil:**  
Menjalankan skrip akan membuat file bernama `PostalPlanetBarHeightNone.png` yang berisi barcode Planet yang mengenkode string “123456”. Dimensi gambar akan kira‑kira 200 × 100 piksel, tergantung pada dimensi X yang Anda pilih.

---

## Opsional: Verifikasi barcode secara visual

Anda dapat dengan cepat membuka PNG yang dihasilkan menggunakan penampil gambar apa saja untuk memastikan barcode terlihat tajam dan teks yang dapat dibaca manusia muncul di bawah pola.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Jika gambar tampak kabur, tinjau kembali **Langkah 2** dan tingkatkan dimensi X hingga bar terlihat jelas.

---

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **Panjang teks berbeda** | Barcode Planet mendukung hingga 12 karakter numerik. Jika Anda melebihi batas ini, library akan mengeluarkan pengecualian. |
| **Format output alternatif** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp` untuk kasus penggunaan lain. |
| **Warna latar depan/latar belakang khusus** | Gunakan `gen.parameters.barcode.barcode_color = Color.Blue` dan `gen.parameters.barcode.back_color = Color.White`. |
| **Tanpa teks yang dapat dibaca manusia** | Setel `gen.parameters.barcode.hide_code_text = True` untuk menghasilkan barcode tanpa keterangan di bagian bawah. |
| **Pembuatan batch** | Lakukan loop pada daftar string, buat `BarcodeGenerator` baru untuk masing‑masing, dan simpan ke file dengan nama unik. |

Variasi‑variasi ini memungkinkan Anda **menghasilkan file barcode planet** yang sesuai dengan berbagai kebutuhan bisnis.

---

## Skrip lengkap – siap dijalankan

Berikut adalah skrip lengkap yang berdiri sendiri, dapat Anda salin, tempel, dan jalankan. Skrip ini mencakup semua impor, penanganan error, dan komentar.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Penjelasan skrip**

* Fungsi `create_planet_barcode` membungkus tiga langkah inti, menjadikan kode dapat digunakan kembali.
* Validasi input memastikan Anda mengikuti spesifikasi Planet (hanya numerik, maksimal 12 digit).
* Fungsi secara otomatis membuat folder output, sehingga Anda tidak perlu mengelola direktori secara manual.
* Setelah pembuatan, skrip membuka gambar menggunakan Pillow (`PIL`) untuk verifikasi langsung.

---

## Kesimpulan

Anda kini tahu cara **membuat barcode dengan teks** dan **menghasilkan file barcode planet** di Python. Panduan ini mencakup inisialisasi, penyesuaian resolusi, dan output file, serta kustomisasi opsional dan kasus tepi umum.  

Dari sini Anda dapat:

* Mengganti `EncodeTypes.Planet` dengan simbol lain (misalnya `EncodeTypes.Code128`) untuk menggunakan pola yang sama.
* Mengintegrasikan fungsi ke dalam layanan web yang mengembalikan gambar barcode sesuai permintaan.
* Bereksperimen dengan pemrosesan batch untuk menghasilkan ribuan barcode bagi pengiriman massal.

Silakan sesuaikan skrip dengan kebutuhan proyek Anda dan bagikan hasilnya di kolom komentar. Selamat coding!


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}