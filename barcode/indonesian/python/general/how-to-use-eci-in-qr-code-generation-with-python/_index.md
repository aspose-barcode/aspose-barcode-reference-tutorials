---
category: general
date: 2026-11-20
description: Pelajari cara menggunakan ECI, menghasilkan QR dari teks, membersihkan
  builder, dan menyimpan gambar QR menggunakan pustaka barcode Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: id
lastmod: 2026-11-20
og_description: Cara menggunakan ECI untuk menghasilkan QR dari teks, membersihkan
  pembuat QR, dan menyimpan gambar QR – panduan lengkap langkah demi langkah.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Cara menggunakan ECI dalam pembuatan kode QR dengan Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Cara menggunakan ECI dalam pembuatan kode QR dengan Python
url: /id/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan ECI dalam pembuatan kode QR dengan Python

Jika Anda perlu **cara menggunakan eci** saat membuat kode QR, panduan ini menunjukkan langkah‑langkah yang tepat. Anda akan melihat cara menghasilkan QR dari teks, membersihkan builder, dan akhirnya menyimpan gambar QR—semua dengan beberapa baris Python.

Kode QR yang berisi data multibahasa sering memerlukan segmen Extended Channel Interpretation (ECI) agar pemindai tahu set karakter mana yang harus diterapkan. Tutorial ini memandu Anda membangun codetext yang diperluas, membersihkan builder saat menggunakannya kembali, dan menyimpan hasilnya sebagai file PNG.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Python 3.8+ terpasang.
- Paket Aspose.BarCode untuk Python via .NET (atau perpustakaan `barcode` kompatibel yang menyediakan `ExtCodetextBuilder` dan `BarcodeGenerator`).
- Familiaritas dasar dengan konsep kode QR.

Pasang perpustakaan dengan pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Gunakan lingkungan virtual untuk menghindari konflik versi.

## Langkah 1: Impor kelas yang diperlukan

Kelas utama yang akan Anda gunakan adalah `ExtCodetextBuilder` untuk membangun codetext yang diperluas dan `BarcodeGenerator` untuk merender kode QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Impor ini memberi Anda akses ke metode builder (`add_plain_codetext`, `add_eci_codetext`, dll.) serta fungsi `set_code_text`, `set_symbology`, dan `save` pada generator.

## Langkah 2: Buat dan konfigurasikan ExtCodetextBuilder

Membuat instance builder baru adalah contoh konkret pertama **cara menggunakan eci**. Anda juga dapat membersihkan builder nanti jika perlu menggunakannya kembali.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Memanggil `clear()` memastikan builder memulai dengan keadaan bersih, yang penting saat menghasilkan beberapa kode QR dalam sebuah loop.

## Langkah 3: Tambahkan codetext biasa (non‑ECI)

Teks biasa tidak memerlukan segmen ECI. Gunakan `add_plain_codetext` untuk string yang kompatibel dengan ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Builder kini menyimpan segmen biasa `"HelloWorld"`.

## Langkah 4: Tambahkan segmen yang dienkode dengan ECI

Berikut inti **cara menggunakan eci**: Anda menentukan nilai ECI (26 untuk UTF‑8) dan menyediakan string Unicode yang ingin dienkode. Ini memungkinkan kode QR membawa bahasa Rusia, Mandarin, atau bahasa lain yang tidak tercakup dalam set default ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Mengapa ini penting:** Tanpa indikator ECI, pemindai akan menginterpretasikan byte menggunakan set karakter default dan menampilkan karakter yang kacau untuk teks non‑ASCII.

## Langkah 5: Ambil string codetext yang diperluas yang digabungkan

Setelah menambahkan semua segmen yang diperlukan, ambil string akhir yang akan diberikan ke generator QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Nilai yang dicetak terlihat kira‑kira seperti:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Format tepatnya tergantung pada perpustakaan, tetapi bagian pentingnya adalah penanda ECI (`[ECI26]`) yang mendahului payload UTF‑8.

## Langkah 6: Hasilkan kode QR menggunakan teks yang digabungkan

Sekarang Anda dapat **generate QR from text** dengan memberikan codetext yang diperluas ke `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Saat Anda membuka `qr_extended.png`, sebuah kode QR muncul yang mengenkode baik string bahasa Inggris biasa maupun salam dalam bahasa Rusia. Memindainya dengan pemindai QR modern akan menampilkan “HelloWorld” dan “Привет” dengan benar.

### Mengapa Anda harus memanggil `clear()` sebelum menggunakan kembali builder

Jika Anda menghasilkan beberapa kode QR dalam sebuah loop, melupakan pemanggilan `clear()` akan menggabungkan segmen lama dengan yang baru, menghasilkan kode yang tidak valid. Berikut pola singkatnya:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Cuplikan ini menggambarkan **cara membersihkan builder** dan **cara menghasilkan QR dari teks** secara berulang.

## Kasus tepi dan jebakan umum

| Situasi | Hal yang perlu diperhatikan | Cara menanganinya |
|-----------|-------------------|---------------|
| **Nilai ECI tidak didukung** | Perpustakaan melempar `InvalidArgumentException`. | Gunakan hanya nilai ECI yang tercantum dalam spesifikasi (misalnya 26 untuk UTF‑8, 20 untuk Shift‑JIS). |
| **Teks gabungan sangat panjang** | Versi QR mungkin melebihi kapasitas maksimum. | Tingkatkan versi QR secara otomatis (`qr_generator.set_qr_version(QRVersion.AUTO)`) atau bagi data ke beberapa kode QR. |
| **Kesalahan izin sistem file** | `save` gagal dengan `IOError`. | Pastikan direktori target ada dan proses memiliki izin menulis. |
| **Set karakter ditampilkan tidak tepat** | Pemindai menampilkan karakter kacau. | Verifikasi nilai ECI yang benar sesuai dengan enkoding string yang sebenarnya. |

## Contoh lengkap yang dapat dijalankan

Berikut adalah skrip mandiri yang dapat Anda salin, tempel, dan jalankan. Skrip ini mencakup semua impor, penanganan error, dan komentar untuk kejelasan.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Menjalankan skrip ini menghasilkan `output/qr_extended.png`, sebuah kode QR yang mengenkode dengan benar teks bahasa Inggris dan Rusia.

## Kesimpulan

Anda kini tahu **cara menggunakan eci** saat membangun kode QR, cara **membersihkan builder QR** sebelum digunakan kembali, cara **generate QR from text**, dan langkah tepat untuk **save QR image** dengan Python. Dengan mengikuti pola di atas, Anda dapat menyematkan string Unicode apa pun ke dalam kode QR sambil menjaga keadaan builder tetap dapat diprediksi.

### Apa selanjutnya?

- Jelajahi nilai ECI lain untuk bahasa seperti Mandarin (ECI 20) atau ISO‑8859‑5.
- Sesuaikan level koreksi error (`qr_generator.set_error_correction_level`) untuk meningkatkan keandalan pemindaian.
- Gabungkan beberapa segmen ECI dalam satu QR untuk pesan campuran bahasa.

Selamat coding, dan selamat membuat kode QR multibahasa!

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}