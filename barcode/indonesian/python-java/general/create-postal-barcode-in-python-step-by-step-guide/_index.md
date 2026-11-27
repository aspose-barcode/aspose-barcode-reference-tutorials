---
category: general
date: 2026-11-27
description: Buat barcode pos dengan cepat menggunakan Python. Pelajari cara menghasilkan
  gambar barcode dari string menggunakan simbol RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- create barcode from string
- how to generate barcode image
language: id
lastmod: 2026-11-27
og_description: Buat kode batang pos di Python. Ikuti panduan ini untuk belajar cara
  menghasilkan gambar kode batang dari string dengan simbol RM4SCC.
og_image_alt: Screenshot showing a created postal barcode saved as a PNG file
og_title: Buat barcode pos di Python – tutorial coding lengkap
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create postal barcode quickly with Python. Learn how to generate a
    barcode image from a string using the RM4SCC symbology.
  headline: Create postal barcode in Python – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- Python
- RM4SCC
title: Buat kode batang pos di Python – panduan langkah demi langkah
url: /id/python-java/general/create-postal-barcode-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode pos dalam Python – panduan langkah demi langkah

Jika Anda perlu **membuat barcode pos** untuk aplikasi pengiriman, panduan ini menunjukkan secara tepat cara melakukannya dengan Python. Anda akan melihat contoh singkat yang dapat dijalankan yang mengubah string sederhana menjadi gambar PNG berkualitas tinggi menggunakan simbol RM4SCC.  

Membuat alur kerja **create barcode from string** berguna untuk verifikasi alamat, pencetakan label massal, dan integrasi dengan layanan pos. Langkah‑langkah di bawah mencakup semuanya mulai dari menginstal pustaka hingga menyesuaikan lebar bar untuk kinerja pemindai yang optimal.

## Apa yang dibahas dalam tutorial ini

* Menginstal paket `barcode` yang diperlukan (atau SDK resmi yang menyediakan `BarcodeGenerator`).
* Menginisialisasi generator untuk format RM4SCC dengan string data.
* Menyesuaikan dimensi X (lebar modul) untuk mengontrol ketebalan bar.
* Menyimpan hasil sebagai gambar PNG – format paling umum ketika Anda bertanya **how to generate barcode image** untuk web atau cetak.
* Tips menangani direktori yang hilang, format gambar alternatif, dan jebakan umum.

Pada akhir artikel Anda akan memiliki file PNG siap pakai bernama `PostalRM4SCCFilledBars.png` yang dapat disematkan dalam faktur, manifest pengiriman, atau alur kerja pos apa pun.

## Prasyarat

* Python 3.8+ terpasang di mesin Anda.  
* Akses ke terminal atau command prompt.  
* Familiaritas dasar dengan impor Python dan jalur file.  

Jika Anda sudah memiliki lingkungan virtual, aktifkan sebelum menginstal paket.

```bash
pip install python-barcode-sdk   # replace with the actual package name if different
```

> **Pro tip:** Pin versi (`python-barcode-sdk==1.4.2`) untuk menghindari perubahan yang dapat merusak di rilis mendatang.

## Langkah 1: Buat barcode pos dengan simbol RM4SCC

Langkah pertama adalah menginstansiasi `BarcodeGenerator` untuk format RM4SCC dan memberi data yang ingin Anda enkode.

```python
from barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialise the generator with the RM4SCC symbology
# "123456" is the example postal code; replace it with any alphanumeric string.
gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
```

**Mengapa ini penting:**  
`EncodeTypes.RM4SCC` memberi tahu SDK untuk menggunakan *Royal Mail 4‑State Code* (RM4SCC), yang merupakan standar untuk barcode pos di Inggris. Menyediakan data sebagai string biasa (`"123456"`) adalah cara paling sederhana untuk **create barcode from string** tanpa harus berurusan dengan tabel enkoding tingkat rendah.

## Langkah 2: Sesuaikan dimensi barcode untuk keterbacaan yang lebih baik

Pemindai biasanya mengharapkan lebar bar minimum. Menetapkan dimensi X ke 4 piksel memberi Anda bar yang lebih halus sambil tetap berada dalam rentang yang direkomendasikan.

```python
# Step 2 – set the module (X) dimension to 4 pixels
gen.Parameters.Barcode.XDimension.Pixels = 4
```

**Mengapa Anda mungkin mengubah ini:**  
Dimensi X yang lebih besar (mis., 6 px) menghasilkan bar yang lebih tebal, yang dapat berguna untuk printer beresolusi rendah. Sebaliknya, nilai yang lebih kecil membuat barcode lebih kompak—ideal untuk label dengan ruang terbatas.

## Langkah 3: Simpan barcode sebagai gambar PNG

Sekarang tulis barcode yang dihasilkan ke disk. PNG bersifat lossless, memastikan barcode tetap tajam untuk pembaca optik.

```python
# Step 3 – export the barcode to a PNG file
output_path = "YOUR_DIRECTORY/PostalRM4SCCFilledBars.png"
gen.Save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Mengapa PNG?**  
`BarCodeImageFormat.Png` mempertahankan data piksel secara tepat, yang penting ketika Anda menanyakan **how to generate barcode image** yang harus dibaca oleh pemindai berkecepatan tinggi. Jika Anda memerlukan format lain (JPEG, BMP, TIFF), ganti `Png` dengan nilai enum yang sesuai.

### Hasil yang diharapkan

Setelah menjalankan skrip, Anda akan melihat file serupa dengan gambar di bawah:

![Example of a created postal barcode saved as a PNG file](https://example.com/images/postal-rm4scc.png "Created postal barcode in PNG format")

Gambar tersebut berisi serangkaian bar empat‑state yang mewakili string `123456`. Memindai PNG dengan pembaca barcode mengembalikan data asli.

## Menangani kasus tepi umum

| Situasi | Apa yang harus dilakukan |
|-----------|------------|
| **Direktori tidak ada** | Gunakan `os.makedirs(os.path.dirname(output_path), exist_ok=True)` sebelum memanggil `gen.Save`. |
| **Karakter tidak valid dalam data** | RM4SCC hanya menerima digit (0‑9). Validasi input dengan `str.isdigit()` dan lempar error yang jelas jika gagal. |
| **Dibutuhkan format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Jpeg` (atau `Bmp`, `Tiff`) dan sesuaikan ekstensi file. |
| **Perlu resolusi lebih tinggi untuk cetak** | Tingkatkan `gen.Parameters.Barcode.XDimension.Pixels` dan opsional set `gen.Parameters.Image.Dpi = 300`. |

```python
import os

# Ensure output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# Optional: enforce numeric data for RM4SCC
data = "123456"
if not data.isdigit():
    raise ValueError("RM4SCC barcode data must contain only digits.")

# Continue with generator creation as shown earlier...
```

## Skrip lengkap untuk salin‑tempel cepat

Berikut adalah program lengkap yang siap dijalankan dan mencakup semua tips praktik terbaik yang dibahas.

```python
import os
from barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, out_path: str, x_dim: int = 4):
    """
    Generates an RM4SCC postal barcode from a string and saves it as PNG.

    Args:
        data: Numeric string to encode (e.g., "123456").
        out_path: Full file path where the PNG will be written.
        x_dim: Desired X‑dimension in pixels (default 4).
    """
    # Validate input for RM4SCC
    if not data.isdigit():
        raise ValueError("RM4SCC barcode data must contain only digits.")
    
    # Ensure the output directory exists
    os.makedirs(os.path.dirname(out_path), exist_ok=True)

    # Initialise generator
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)

    # Set module width
    gen.Parameters.Barcode.XDimension.Pixels = x_dim

    # Save as PNG
    gen.Save(out_path, BarCodeImageFormat.Png)
    print(f"Barcode saved to {out_path}")

if __name__ == "__main__":
    # Example usage
    create_postal_barcode(
        data="123456",
        out_path="output/PostalRM4SCCFilledBars.png",
        x_dim=4
    )
```

Menjalankan skrip ini menghasilkan file `PostalRM4SCCFilledBars.png` yang sama seperti yang ditunjukkan sebelumnya.

## Kesimpulan

Anda kini tahu cara **membuat barcode pos** dalam Python menggunakan simbol RM4SCC. Tutorial ini mencakup seluruh pipeline—dari **create barcode from string** hingga menyesuaikan dimensi dan akhirnya menjawab **how to generate barcode image** dalam format PNG.  

Langkah selanjutnya yang dapat Anda jelajahi meliputi:

* Menghasilkan barcode untuk kumpulan data massal (loop melalui baris CSV).  
* Beralih ke simbol lain seperti `EncodeTypes.Code128` atau `EncodeTypes.QR`.  
* Menyematkan PNG langsung ke faktur PDF dengan `reportlab`.  

Bereksperimenlah dengan nilai dimensi X dan format gambar yang berbeda untuk menyesuaikan dengan spesifikasi printer atau pemindai Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create postal barcode in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-in-python-with-aspose-barcode/)
- [How to create barcode from string in Python using Aspose](/barcode/english/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}