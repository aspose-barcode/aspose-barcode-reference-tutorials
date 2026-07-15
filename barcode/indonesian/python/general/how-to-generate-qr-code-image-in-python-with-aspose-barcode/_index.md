---
category: general
date: 2026-07-15
description: Cara menghasilkan gambar QR code di Python menggunakan Aspose.Barcode.
  Pelajari langkah demi langkah pembuatan QR code dengan codetext yang diperluas,
  enkoding ECI, dan dukungan Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: id
lastmod: 2026-07-15
og_description: Cara menghasilkan gambar kode QR di Python dengan Aspose.Barcode.
  Panduan ini memandu Anda melalui pembuatan kode QR menggunakan codetext yang diperluas,
  enkoding ECI, dan karakter Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Cara Menghasilkan Gambar Kode QR di Python – Tutorial Lengkap Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Cara Membuat Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap
url: /id/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menghasilkan Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap

Pernah bertanya-tanya **cara menghasilkan gambar QR code** di Python tanpa harus mencari puluhan pustaka? Anda tidak sendirian. Banyak pengembang membutuhkan cara yang andal untuk menyematkan teks multibahasa—misalnya Rusia, Arab, atau emoji—di dalam QR code, dan pustaka bawaan seringkali tidak memadai.

Berikut faktanya: Aspose.Barcode untuk Python membuat proses ini terasa sangat mudah. Dalam tutorial ini kami akan membimbing Anda melalui langkah‑langkah tepat, mulai dari menginstal paket hingga membuat string extended codetext yang menggabungkan ASCII biasa dengan Unicode yang dienkode ECI. Pada akhir tutorial Anda akan memiliki gambar QR code siap pakai yang tersimpan di disk.

## Apa yang Dibahas dalam Panduan Ini

- Menginstal **Aspose.Barcode** untuk Python (kompatibel dengan Python 3.8+)
- Membuat **extended codetext** yang menggabungkan segmen plain dan Unicode
- Menggunakan **ECI encoding** untuk menampilkan karakter Rusia dengan benar
- Mengonfigurasi `BarcodeGenerator` untuk menghasilkan QR code
- Menyimpan gambar output dalam format PNG
- Tips, jebakan umum, dan ide langkah selanjutnya (seperti menambahkan logo atau menyesuaikan error correction)

Tidak diperlukan pengalaman sebelumnya dengan Aspose; cukup dengan setup Python dasar dan rasa ingin tahu tentang QR code.

---

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **Python 3.8 atau lebih baru** terpasang di mesin Anda.  
2. **Virtual environment** (opsional namun disarankan) untuk menjaga ketergantungan tetap rapi.  
3. Akses **pip** untuk menginstal paket `aspose-barcode`.  
4. Izin menulis ke folder tempat PNG yang dihasilkan akan disimpan.

Jika ada yang belum familiar, berhentilah sejenak dan siapkan dulu—setelah semuanya siap, sisanya sangat mudah.

---

## Langkah 1: Instal Aspose.Barcode untuk Python

Rintangan pertama adalah mendapatkan pustaka tersebut. Aspose mendistribusikan paketnya di PyPI, jadi satu perintah `pip` sudah cukup:

```bash
pip install aspose-barcode
```

> **Pro tip:** Jika Anda berada di dalam virtual environment, Anda akan menjaga site‑packages global tetap bersih. Jika muncul error izin, tambahkan `--user` atau jalankan perintah dengan `sudo` (meskipun biasanya tidak diperlukan pada setup modern).

Setelah instalasi selesai, Anda dapat memverifikasinya dengan:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Jika versi tercetak tanpa keluhan, Anda siap melanjutkan.

---

## Langkah 2: Buat Instance **Extended Codetext Builder**

Aspose.Barcode menyediakan kelas `ExtCodetextBuilder` untuk menyusun payload QR yang kompleks. Anggaplah ini sebagai editor teks kecil yang tahu cara menambahkan karakter kontrol yang tepat untuk setiap segmen.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Mengapa menggunakan builder? Menggabungkan byte mentah secara langsung rawan kesalahan; builder menjamin pergantian ECI (Extended Channel Interpretation) yang benar, sehingga pemindai QR Anda dapat mendekode setiap bahasa dengan tepat.

---

## Langkah 3: Mulai dari Awal (Opsional tapi Bersih)

Jika Anda pernah menggunakan kembali instance builder yang sama, memanggil `clear()` akan menghapus data sebelumnya. Ini berfungsi sebagai jaring pengaman yang mencegah segmen lama masuk ke QR berikutnya.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Anda dapat melewatkan baris ini pada kali pertama menjalankan skrip, tetapi menyimpannya membuat kode menjadi idempotent—berguna ketika logika ini dibungkus dalam fungsi yang dipanggil berulang kali.

---

## Langkah 4: Tambahkan Segmen Plain (Tidak Dienkode)

Sebagian besar QR code dimulai dengan string ASCII sederhana—mungkin sebuah identifier atau URL. Metode `add_plain_codetext` menambahkan tepat itu, tanpa penanda ECI.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

Dalam contoh ini kami memakai `"HelloWorld"` sebagai placeholder. Ganti dengan apa pun yang Anda butuhkan—mungkin SKU produk atau pesan singkat.

---

## Langkah 5: Tambahkan Segmen **ECI‑Encoded** (UTF‑8 = 26)

Sekarang bagian multibahasa. Nilai ECI **26** mengacu pada UTF‑8, standar de‑facto untuk Unicode. Dengan memberikan `26` bersama frasa Rusia, kami memberi tahu pemindai QR untuk beralih ke UTF‑8 sebelum membaca karakter berikutnya.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Anda dapat mengganti `26` dengan nilai ECI lain (misalnya `27` untuk ISO‑8859‑1) jika memerlukan enkoding berbeda. Builder secara otomatis menyisipkan karakter kontrol yang tepat.

---

## Langkah 6: Dapatkan Extended Codetext yang Digabungkan

Setelah semua segmen ditambahkan, ambil string akhir yang akan dikonsumsi oleh generator QR. String ini berisi urutan kontrol tak terlihat, tetapi Anda tetap dapat mencetaknya untuk debugging.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Output di konsol akan terlihat berantakan (karena byte kontrol tertanam), hal ini normal. Yang penting, builder telah menyatukan bagian plain dan Unicode dengan benar.

---

## Langkah 7: Konfigurasikan Barcode Generator

Sekarang kami menyerahkan extended codetext ke `BarcodeGenerator` milik Aspose. Atur symbology menjadi `QR` dan berikan string gabungan ke `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Anda dapat menyesuaikan properti tambahan di sini—seperti `resolution`, `error_correction_level`, atau `foreground_color`. Opsi‑opsi tersebut dibahas di dokumentasi Aspose, tetapi untuk gambar dasar nilai default sudah cukup baik.

---

## Langkah 8: Simpan Gambar QR Code yang Dihasilkan

Akhirnya, tulis QR code ke disk. Metode `save` menerima path file dan format opsional; PNG adalah pilihan aman.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Buka `qr_extended.png` dengan penampil gambar apa pun. Memindainya menggunakan smartphone harus menampilkan dua pesan terpisah: “HelloWorld” dan “Привет”. Kebanyakan pembaca QR modern secara otomatis menangani pergantian ECI.

---

## Contoh Lengkap yang Berfungsi

Berikut skrip lengkap yang dapat Anda salin‑tempel dan jalankan:

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Output yang diharapkan** (konsol):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Buka `qr_extended.png` → pindai → Anda akan melihat “HelloWorld” diikuti oleh “Привет”.

---

## Pertanyaan Umum & Kasus Edge

### 1. *Bagaimana jika saya membutuhkan lebih dari dua segmen?*  
Cukup panggil `add_plain_codetext` atau `add_eci_codetext` sebanyak yang Anda perlukan. Builder menjaga urutan yang benar, sehingga QR code akan berisi setiap segmen sesuai urutan penambahan.

### 2. *Apakah saya bisa menyematkan emoji?*  
Ya—emoji hanyalah karakter Unicode. Gunakan ECI UTF‑8 (nilai 26) dan berikan string emoji, misalnya `builder.add_eci_codetext(26, "🚀")`. QR akan menampilkan emoji roket pada pemindai yang mendukungnya.

### 3. *Bagaimana jika QR menjadi terlalu padat?*  
QR code memiliki batas versi. Jika Anda melampaui kapasitas data, Aspose secara otomatis akan meningkatkan versi ke ukuran berikutnya, namun gambar mungkin menjadi lebih besar. Untuk mengontrol ukuran, Anda dapat menurunkan level error correction:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Apakah saya harus khawatir tentang set karakter selain UTF‑8?*  
Hanya jika Anda memiliki sistem legacy yang memerlukan enkoding khusus (misalnya ISO‑8859‑1). Dalam kasus tersebut, ganti `26` dengan nilai ECI yang sesuai (lihat tabel ECI Aspose). Untuk kebanyakan aplikasi modern, UTF‑8 adalah pilihan paling aman.

### 5. *Bagaimana cara menambahkan logo di tengah?*  
Aspose.Barcode mendukung `barcode.generator.QRCodeParameters.logo_image`. Muat gambar dengan Pillow (`from PIL import Image`) dan tetapkan:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

Logo akan ditumpangkan sambil tetap menjaga kemampuan pemindaian (Aspose secara otomatis menyesuaikan quiet zone).

---

## Pro Tips untuk Penggunaan di Produksi

- **Cache builder** jika Anda menghasilkan QR yang sama berulang kali; ini menghindari pembuatan ulang string extended setiap kali.
- **Validasi output** dengan unit test yang mendekode QR (misalnya menggunakan `zxing` atau `pyzbar`) untuk memastikan pergantian ECI Anda tepat.
- **Gunakan nama file deterministik** (misalnya sertakan hash dari payload) agar tidak menimpa gambar yang sudah ada.
- **Perhatikan lisensi**: Aspose.Barcode adalah perangkat lunak komersial. Evaluasi gratis cukup untuk pengembangan, tetapi lisensi diperlukan untuk deployment produksi.

---

## Langkah Selanjutnya & Topik Terkait

Sekarang Anda sudah tahu **cara menghasilkan QR code**


## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}