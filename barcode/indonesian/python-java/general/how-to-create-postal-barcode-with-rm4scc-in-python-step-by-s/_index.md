---
category: general
date: 2026-11-27
description: Pelajari cara membuat kode batang pos di Python menggunakan format RM4SCC.
  Tutorial ini mencakup dimensi X, tinggi bar, dan penyimpanan gambar sebagai PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- RM4SCC barcode
- barcode X dimension
- barcode bar height
- save barcode as PNG
language: id
lastmod: 2026-11-27
og_description: Buat barcode pos di Python menggunakan RM4SCC. Sesuaikan dimensi X,
  tinggi bar, dan ekspor ke PNG dengan skrip lengkap yang dapat dijalankan.
og_image_alt: Screenshot of a generated RM4SCC postal barcode saved as a PNG file
og_title: Buat barcode pos di Python – contoh lengkap RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create postal barcode in Python using the RM4SCC format.
    This tutorial covers X dimension, bar height, and saving the image as PNG.
  headline: How to create postal barcode with RM4SCC in Python – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- Python
- Aspose
title: Cara membuat kode batang pos dengan RM4SCC di Python – panduan langkah demi
  langkah
url: /id/python-java/general/how-to-create-postal-barcode-with-rm4scc-in-python-step-by-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode pos dengan RM4SCC di Python – panduan langkah demi langkah

Jika Anda perlu **membuat barcode pos** untuk sistem pengiriman, panduan ini menunjukkan secara tepat cara menghasilkan barcode RM4SCC di Python. Anda akan melihat cara mengonfigurasi dimensi X, mengatur tinggi bar khusus, dan menyimpan hasilnya sebagai gambar PNG—semua dengan satu skrip yang berdiri sendiri.

Membuat **barcode pos** adalah kebutuhan umum untuk logistik, e‑commerce, dan solusi pengiriman massal. Kode di bawah ini menggunakan pustaka Aspose.BarCode untuk Python, yang mengimplementasikan simbolologi RM4SCC yang dibutuhkan oleh banyak layanan pos. Pada akhir tutorial ini Anda akan memiliki file PNG siap pakai yang dapat dicetak pada amplop atau ditempelkan pada paket.

## Prasyarat

* Python 3.8 atau yang lebih baru terinstal.
* Lisensi aktif Aspose.BarCode untuk Python (atau kunci evaluasi gratis).  
  Instal paket dengan `pip install aspose-barcode`.
* Izin menulis ke direktori tempat PNG akan disimpan.

Tidak diperlukan pustaka sistem tambahan; pustaka ini menangani semua pemrosesan gambar secara internal.

## Langkah 1: Impor kelas Aspose.BarCode dan buat generator

Tugas pertama adalah mengimpor kelas yang diperlukan dan menginstansiasi `BarcodeGenerator` untuk format RM4SCC. **Barcode RM4SCC** mengkodekan string numerik 6‑digit yang mewakili kode rute pos.

```python
# Step 1: Import and create a barcode generator for RM4SCC
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data "123456" is a sample postal routing number.
barcode_generator = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
```

**Mengapa ini penting:**  
`EncodeTypes.RM4SCC` memberi tahu pustaka untuk menerapkan aturan simbolologi tepat yang didefinisikan oleh Royal Mail 4‑State Customer Code. Menggunakan tipe yang benar memastikan barcode dapat dipindai oleh peralatan pos.

## Langkah 2: Konfigurasikan dimensi X (lebar modul)

**Dimensi X barcode** mengontrol lebar elemen bar terkecil. Menetapkannya ke 4 piksel menghasilkan barcode yang menyeimbangkan keterbacaan dan kekompakan untuk kebanyakan printer label.

```python
# Step 2: Set the X dimension (module width) to 4 pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

**Mengapa ini penting:**  
Dimensi X yang lebih kecil mengurangi lebar keseluruhan barcode, sementara nilai yang lebih besar meningkatkan toleransi terhadap ketidaksempurnaan pencetakan. Sesuaikan nilai ini berdasarkan DPI printer Anda dan ruang yang tersedia pada label.

## Langkah 3: Tentukan tinggi bar

**Tinggi bar barcode** menentukan seberapa tinggi setiap bar muncul. Tinggi 100 piksel memberikan kontras yang cukup untuk pemindai optik tanpa menghabiskan ruang label yang berlebihan.

```python
# Step 3: Set the bar height to 100 pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

**Mengapa ini penting:**  
Pemindai pos mengharapkan tinggi bar minimum untuk secara andal mendeteksi pola empat‑state. Jika Anda menurunkan tinggi terlalu banyak, pemindai mungkin melewatkan perbedaan halus antara bar dan spasi.

## Langkah 4: Simpan barcode sebagai gambar PNG

Akhirnya, **simpan barcode sebagai PNG** untuk mendapatkan gambar lossless yang cocok untuk pencetakan. PNG mempertahankan dimensi piksel tepat yang Anda konfigurasikan, yang penting untuk akurasi barcode.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

**Mengapa ini penting:**  
PNG didukung secara luas oleh perangkat lunak desain label dan printer. File dapat disisipkan langsung ke dalam PDF, dokumen Word, atau dicetak menggunakan alat pencetakan gambar standar.

### Output yang diharapkan

Menjalankan skrip menghasilkan file bernama `PostalRM4SCCBarHeight100Pixels.png`. Membuka gambar menampilkan barcode RM4SCC yang bersih dengan modul 4‑piksel dan tinggi bar 100‑piksel, siap untuk dimasukkan ke label pengiriman.

## Kode sumber lengkap – siap disalin dan dijalankan

Berikut adalah contoh lengkap yang dapat dijalankan yang menggabungkan semua langkah. Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif tempat Anda ingin menyimpan PNG.

```python
"""
Complete example: create postal barcode (RM4SCC) in Python,
configure X dimension and bar height, and save as PNG.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_postal_barcode(data: str,
                            x_dim_pixels: int = 4,
                            bar_height_pixels: int = 100,
                            output_file: str = "PostalRM4SCC.png") -> None:
    """
    Generates an RM4SCC postal barcode with custom dimensions.

    Args:
        data: Six‑digit numeric string for the postal routing code.
        x_dim_pixels: Width of the smallest bar element (default 4).
        bar_height_pixels: Height of the bars in pixels (default 100).
        output_file: Path where the PNG image will be saved.
    """
    # Create generator for RM4SCC
    generator = BarcodeGenerator(EncodeTypes.RM4SCC, data)

    # Apply custom dimensions
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels
    generator.parameters.barcode.bar_height.pixels = bar_height_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.Png)

    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage
    generate_postal_barcode(
        data="123456",
        x_dim_pixels=4,
        bar_height_pixels=100,
        output_file="YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Penjelasan fungsi:**

* `generate_postal_barcode` memisahkan logika pembuatan barcode, menjadikannya dapat digunakan kembali di berbagai proyek.
* Parameter default cocok dengan nilai yang ditunjukkan di bagian langkah demi langkah, tetapi Anda dapat memberikan angka berbeda untuk menyesuaikan dengan format label lain.
* Fungsi mencetak pesan konfirmasi, yang berguna untuk pemrosesan batch di mana Anda menghasilkan banyak barcode dalam sebuah loop.

## Variasi umum dan kasus tepi

| Situasi | Perubahan yang disarankan |
|-----------|--------------------|
| **Panjang nomor rute berbeda** | RM4SCC mengharapkan tepat 6 digit. Jika Anda menerima string yang lebih pendek, pad dengan nol di depan (`data.zfill(6)`). |
| **Printer resolusi tinggi** | Tingkatkan `x_dim_pixels` menjadi 6 atau 8 untuk menjaga lebar bar proporsional dengan DPI printer. |
| **Membutuhkan latar belakang transparan** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.PngTransparent` (jika didukung) atau set `generator.parameters.image.transparent_background = True`. |
| **Generasi batch** | Lakukan loop pada daftar nomor rute dan panggil `generate_postal_barcode` untuk masing‑masing, menyimpan hasil di folder khusus. |
| **Data non‑numerik** | RM4SCC tidak menerima karakter alfabetik. Validasi input sebelum memanggil generator untuk menghindari error runtime. |

## Tips profesional untuk pencetakan barcode pos yang handal

* **Validasi panjang data** sebelum membuat barcode; pengecualian akan dilempar jika string tidak berjumlah enam digit.
* **Uji barcode yang dicetak** dengan pemindai fisik sebelum diterapkan ke produksi. Variasi kecil pada kepadatan tinta printer dapat memengaruhi keterbacaan.
* **Pertahankan file PNG tidak terkompresi** (kompresi PNG default bersifat lossless). Mengompres ulang ke JPEG akan menambahkan artefak yang merusak barcode.
* **Gunakan direktori output yang konsisten** untuk mempermudah integrasi dengan alat desain label yang mengharapkan struktur folder tertentu.

## Kesimpulan

Anda kini tahu cara **membuat barcode pos** di Python menggunakan simbolologi RM4SCC, menyesuaikan **dimensi X barcode**, mengatur **tinggi bar barcode**, dan **menyimpan barcode sebagai PNG**. Skrip lengkap dapat diintegrasikan ke dalam alur kerja label pengiriman apa pun, dan fungsi modular memudahkan pembuatan ratusan barcode secara otomatis.

Selanjutnya, jelajahi topik terkait seperti **menghasilkan QR code untuk URL pelacakan**, **menyisipkan barcode dalam faktur PDF**, atau **menggunakan simbolologi pos lain seperti POSTNET**. Masing‑masing topik ini dibangun di atas prinsip yang sama yang ditunjukkan di sini: pilih tipe encode yang tepat, konfigurasikan parameter visual, dan ekspor gambar berkualitas tinggi.

Silakan bereksperimen dengan dimensi, warna, atau format file yang berbeda untuk menyesuaikan lingkungan pencetakan Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membuat barcode pos di Python dengan Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-in-python-with-aspose-barcode/)
- [Buat barcode PNG di Python – Panduan Lengkap](/barcode/english/python-java/general/create-barcode-png-in-python-complete-guide/)
- [Cara membuat barcode planet PNG dengan Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}