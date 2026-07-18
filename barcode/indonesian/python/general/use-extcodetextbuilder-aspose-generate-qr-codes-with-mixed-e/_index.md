---
category: general
date: 2026-07-18
description: Gunakan extcodetextbuilder Aspose untuk membuat kode QR yang menggabungkan
  teks ASCII biasa dan teks Rusia UTF‑8. Pelajari pembuatan kode QR Aspose.Barcode
  dengan Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: id
lastmod: 2026-07-18
og_description: Gunakan extcodetextbuilder Aspose yang memungkinkan Anda menggabungkan
  fragmen teks biasa dan yang terenkode UTF‑8 dalam QR Code. Ikuti panduan langkah
  demi langkah untuk Aspose.Barcode di Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: gunakan extcodetextbuilder aspose – Buat Kode QR dengan Teks ECI Campuran
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Gunakan ExtCodeTextBuilder Aspose: Hasilkan Kode QR dengan Teks ECI Campuran'
url: /id/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# gunakan extcodetextbuilder aspose – Bangun QR Code dengan Teks ECI Campuran

Pernah bertanya-tanya bagaimana cara **use extcodetextbuilder aspose** untuk menyematkan karakter bahasa Inggris biasa dan Cyrillic ke dalam satu QR Code? Anda tidak sendirian. Banyak pengembang mengalami kebuntuan ketika harus mencampur data ASCII dan non‑ASCII, terutama ketika pemindai target mengharapkan penanda ECI (Extended Channel Interpretation) yang tepat.  

Dalam tutorial ini kami akan menelusuri langkah‑langkah tepat untuk membuat QR Code yang memuat “HELLO123” **dan** kata Rusia “Привет”, semuanya dengan API Python Aspose.Barcode. Pada akhir tutorial Anda akan memiliki skrip siap‑jalankan, memahami mengapa setiap pemanggilan penting, dan mengetahui cara menyesuaikan proses untuk bahasa lain atau format data lainnya.

## Apa yang Akan Anda Pelajari

- Cara **initialize ExtCodetextBuilder** dan menambahkan fragmen biasa serta yang ter‑encode ECI.  
- Mengapa nilai **ECI encoding** `3` berkorespondensi dengan UTF‑8 dan bagaimana hal itu memengaruhi pemindaian.  
- Urutan tepat untuk menyiapkan **QR Code generator** dengan Aspose.Barcode.  
- Cara menyimpan gambar yang dihasilkan dan memverifikasi konten campuran.  

**Prerequisites** – Anda memerlukan Python 3.8+, paket `aspose-barcode` terpasang (`pip install aspose-barcode`), dan sebuah folder yang dapat Anda tulis gambar ke dalamnya. Tidak ada yang lain.

---

## gunakan extcodetextbuilder aspose untuk membangun codetext campuran

Hal pertama yang kita butuhkan adalah sebuah instance `ExtCodetextBuilder`. Anggaplah ini sebagai pola builder yang menggabungkan berbagai potongan teks sambil secara otomatis menyisipkan penanda ECI yang tepat di belakang layar.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Mengapa ini penting:**  
- `add_plain_codetext` mempertahankan data apa adanya, yang sempurna untuk angka atau huruf Inggris.  
- `add_eci_codetext` menyisipkan segmen ECI (`[ECI:3]`) sebelum string yang diberikan, memberi tahu pembaca yang sesuai bahwa byte berikutnya adalah UTF‑8. Tanpa ini, pemindai akan menginterpretasikan byte Cyrillic sebagai sampah.

> **Pro tip:** Jika Anda memerlukan set karakter yang berbeda, ubah nilai `eci_encoding` sesuai tabel ECI (mis., `26` untuk ISO‑8859‑1).  

---

## Inisialisasi Pembuatan QR Code dengan Aspose.Barcode

Sekarang kita memiliki `extended_codetext` yang diformat dengan benar, kita dapat menyerahkannya ke generator QR Code. Aspose.Barcode mengabstraksi pembuatan matriks QR tingkat rendah, memungkinkan Anda fokus pada data.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Apa yang terjadi di sini?**  
- `BarcodeGenerator()` membuat objek generator baru dengan pengaturan default (ukuran, resolusi, dll.).  
- `set_symbology` memberi tahu mesin bahwa kita menginginkan QR Code, bukan misalnya Code128.  

Jika Anda memerlukan tingkat koreksi kesalahan yang lebih tinggi, Anda dapat memanggil `qr_generator.parameters.barcode.qr_error_level = ...` sebelum menetapkan codetext.

---

## Tetapkan extended codetext ke generator QR

Dengan generator siap, langkah berikutnya cukup memberi masukan string campuran yang telah kita bangun sebelumnya.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Mengapa tidak menggunakan `set_codetext`?**  
`set_codetext` memperlakukan input sebagai teks biasa, menghapus semua penanda ECI. `set_extended_codetext` mempertahankan byte mentah, termasuk segmen ECI, memastikan pemindai melihat pergantian bahasa yang benar.

---

## Simpan gambar QR Code dan verifikasi hasilnya

Akhirnya, kita menulis QR Code ke disk. Aspose.Barcode mendukung PNG, JPEG, BMP, dan lainnya; PNG adalah pilihan aman karena mempertahankan data lossless.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Sekarang Anda seharusnya memiliki file PNG di lokasi yang ditentukan. Buka dengan aplikasi pemindai QR apa pun yang mendukung ECI (sebagian besar smartphone modern melakukannya). Pindai sekali – Anda akan melihat “HELLO123”. Pindai lagi (atau gunakan pemindai yang menampilkan data mentah) – Anda juga akan mendapatkan “Привет”. Kedua bagian muncul sebagai satu payload, persis seperti yang kami buat.

![contoh QR code extcodetextbuilder aspose menunjukkan teks ECI campuran](YOUR_DIRECTORY/qr_extended.png)

*Teks alt gambar: contoh QR code extcodetextbuilder aspose menunjukkan teks ECI campuran*

---

## Skrip Lengkap, Siap‑Jalankan

Menggabungkan semuanya, berikut program lengkap yang dapat Anda salin‑tempel ke dalam file bernama `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Jalankan dengan:

```bash
python qr_mixed_eci.py
```

Anda akan melihat pesan konsol yang mengonfirmasi lokasi penyimpanan, dan PNG akan muncul tepat di tempat yang Anda tentukan.

---

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika pemindai saya tidak mengenali bagian Cyrillic?
Pastikan aplikasi pemindai mengiklankan dukungan ECI. Perangkat keras lama mungkin mengabaikan segmen ECI dan memperlakukan byte sebagai ISO‑8859‑1, menghasilkan karakter yang rusak.

### Bisakah saya menambahkan lebih dari dua fragmen?
Tentu saja. Panggil `add_plain_codetext` atau `add_eci_codetext` sebanyak yang Anda perlukan. Builder akan menggabungkannya dalam urutan pemanggilan metode.

### Bagaimana cara mengubah ukuran QR Code atau warna latar depan?
Gunakan objek `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Apakah ada cara menyematkan data biner (mis., file kecil) bersama teks?
Ya. Gunakan `add_binary_codetext` dengan array byte, dan padukan dengan ECI yang sesuai jika biner tersebut mewakili set karakter tertentu. Builder akan menangani pergantian mode yang diperlukan.

---

## Kesimpulan

Anda kini tahu **cara menggunakan extcodetextbuilder aspose** untuk membuat QR Code yang secara mulus menggabungkan teks ASCII biasa dan teks Rusia yang ter‑encode UTF‑8. Dengan memanfaatkan `ExtCodetextBuilder`, menetapkan **ECI encoding** yang tepat, dan memberi hasilnya ke **generator QR Code Aspose.Barcode**, Anda mendapatkan satu gambar yang mematuhi standar dan berfungsi pada pemindai modern.  

Dari sini, coba ganti `eci_encoding=3` dengan pengenal bahasa lain, atau bereksperimen dengan fragmen plain tambahan untuk membangun payload multibahasa. Anda juga dapat menjelajahi opsi `BarCodeImageFormat` untuk menghasilkan SVG atau PDF jika memerlukan grafik vektor.  

Selamat coding, dan jangan ragu meninggalkan komentar jika mengalami kendala—umpan balik Anda membantu membuat panduan ini semakin baik!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}