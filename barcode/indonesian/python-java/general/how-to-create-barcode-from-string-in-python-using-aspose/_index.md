---
category: general
date: 2026-10-15
description: Buat kode batang dari string dengan Aspose.Barcode untuk Python. Pelajari
  cara menghasilkan kode batang, mengatur dimensi, dan menyimpannya sebagai PNG dalam
  hitungan menit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: id
lastmod: 2026-10-15
og_description: Buat kode batang dari string dengan Aspose.Barcode untuk Python. Tutorial
  ini menunjukkan langkah demi langkah cara menghasilkan kode batang pos dan menyimpannya
  sebagai PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Buat barcode dari string di Python – Panduan Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Cara membuat barcode dari string di Python menggunakan Aspose
url: /id/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode dari string di Python menggunakan Aspose

Jika Anda perlu **membuat barcode dari string** dengan cepat, Aspose.Barcode untuk Python mempermudah prosesnya. Pada panduan ini Anda akan melihat secara tepat **cara menghasilkan gambar barcode**, mengatur dimensi X, dan menyimpan hasilnya sebagai file PNG—semua hanya dengan beberapa baris kode.

Anda juga akan mendapatkan contoh **generator barcode lengkap** yang dapat Anda salin‑tempel ke proyek Anda sendiri. Tidak diperlukan skrip eksternal atau konfigurasi yang rumit, dan tutorial ini bekerja dengan rilis Aspose.Barcode 23.10 terbaru.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Python 3.8+ terpasang di mesin Anda  
- Lisensi aktif Aspose.Barcode untuk Python (versi percobaan gratis dapat digunakan untuk evaluasi)  
- `pip install aspose-barcode` dijalankan di lingkungan virtual Anda  

Item‑item ini memastikan kode dapat berjalan tanpa error impor.

## Membuat barcode dari string dengan Aspose.Barcode (Python)

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan symbology yang diinginkan—dalam kasus ini barcode pos **Planet**—dan string yang ingin Anda enkode.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Mengapa ini penting:**  
`EncodeTypes.Planet` memberi tahu Aspose untuk menggunakan symbology Planet, yang dirancang untuk penyortiran surat di banyak negara. Argumen kedua (`"123456"`) adalah string mentah yang akan dienkode menjadi barcode. Mengubah nilai ini memungkinkan Anda **membuat barcode dari string** untuk kode pos atau nomor pelacakan apa pun yang Anda perlukan.

## Cara menghasilkan barcode dengan dimensi khusus

Lebar modul barcode pos (dimensi X) sering harus sesuai dengan spesifikasi pencetakan. Aspose memungkinkan Anda mengatur lebar dalam piksel sambil secara otomatis menghitung tinggi.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Mengapa Anda mungkin menyesuaikannya:**  
Dimensi X yang lebih besar membuat bar menjadi lebih tebal, yang dapat meningkatkan keandalan pemindaian pada printer beresolusi rendah. Sebaliknya, nilai yang lebih kecil mengurangi ukuran gambar untuk penggunaan web. Baris ini menunjukkan **cara menghasilkan barcode** yang memenuhi persyaratan ukuran yang tepat.

## Menyimpan gambar barcode

Setelah mengonfigurasi generator, Anda cukup memanggil `save`. Metode ini menerima jalur output dan format gambar yang diinginkan.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Apa yang Anda dapatkan:**  
Sebuah file PNG bernama `PostalPlanetAuto.png` yang berisi barcode Planet yang mengenkode `"123456"`. Anda dapat membuka file tersebut dengan penampil gambar apa pun untuk memverifikasi hasilnya.

![Screenshot barcode pos yang dihasilkan dan disimpan sebagai PNG](barcode_example.png){.align-center alt="Screenshot barcode pos yang dihasilkan dan disimpan sebagai PNG"}

## Contoh lengkap generator barcode

Berikut adalah skrip lengkap yang siap dijalankan, mencakup semua langkah di atas. Salin ke file bernama `generate_postal_barcode.py` dan jalankan dengan `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Output yang diharapkan

Menjalankan skrip menghasilkan:

```
Barcode saved to PostalPlanetAuto.png
```

…dan membuat file `PostalPlanetAuto.png` yang tampak seperti ini:

![Barcode Planet yang dihasilkan](barcode_example.png){.align-center alt="Barcode Planet yang dihasilkan dan disimpan sebagai PNG"}

## Variasi umum dan kasus tepi

| Situasi | Apa yang diubah | Mengapa |
|-----------|----------------|-----|
| **Symbology berbeda** (misalnya, Code128) | Ganti `EncodeTypes.Planet` dengan `EncodeTypes.Code128` | Memungkinkan Anda **menghasilkan barcode** untuk label inventaris, bukan hanya kode pos. |
| **String data lebih panjang** | Pastikan symbology yang dipilih mendukung panjang tersebut; untuk Planet harus tetap 6 digit. | Mencegah `ValueError` saat runtime. |
| **Resolusi lebih tinggi** | Tingkatkan `x_dimension.pixels` menjadi 6 atau 8. | Menghasilkan bar yang lebih tebal untuk pencetakan DPI tinggi. |
| **Format gambar lain** | Gunakan `BarCodeImageFormat.JPEG` atau `BarCodeImageFormat.GIF`. | Berguna bila PNG tidak cocok untuk alur kerja Anda. |
| **Menjalankan di layanan web** | Ganti pemanggilan `save` berbasis sistem file dengan aliran `BytesIO` dan kembalikan byte‑nya. | Memungkinkan pembuatan barcode secara langsung di Flask atau Django. |

**Tips pro:** Selalu validasi string input sebelum memanggil `BarcodeGenerator`. Data tidak valid (panjang salah, karakter non‑numeric untuk Planet) akan memicu pengecualian dan menghentikan aplikasi Anda.

## Cara menghasilkan barcode di endpoint Flask (langkah selanjutnya opsional)

Jika Anda ingin mengekspos **contoh generator barcode** sebagai API REST, Anda dapat membungkus fungsi `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Cuplikan ini menunjukkan cara **menghasilkan barcode** secara dinamis tanpa menulis ke disk, yang sangat berguna untuk micro‑service.

## Kesimpulan

Sekarang Anda tahu cara **membuat barcode dari string** di Python menggunakan Aspose.Barcode, cara **menghasilkan barcode** dengan dimensi khusus, dan cara **menyimpan** hasilnya sebagai file PNG. Contoh **generator barcode lengkap** mencakup validasi input, penanganan kesalahan, dan fungsi yang dapat dipakai ulang untuk diintegrasikan ke aplikasi yang lebih besar.

Selanjutnya, jelajahi symbology lain (`EncodeTypes.Code128`, `EncodeTypes.QR`) atau sematkan generator ini dalam kerangka kerja web seperti Flask atau Django. Kedua langkah tersebut akan memperdalam pemahaman Anda tentang pustaka **aspose barcode python** dan memperluas cara Anda **menghasilkan barcode pos** untuk proyek dunia nyata.


## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}