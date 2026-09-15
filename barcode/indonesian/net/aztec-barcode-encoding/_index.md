---
date: 2026-05-19
description: Pelajari cara membuat Aztec barcode menggunakan Aspose.BarCode untuk
  .NET, menyesuaikan aspect ratios, meng-encode bytes atau teks, dan master symbol
  modes.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Enkoding Aztec barcode
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cara membuat Aztec barcode dengan Aspose.BarCode untuk .NET
url: /id/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pengkodean Barcode Aztec

Apakah Anda siap menyelami dunia Pengkodean Barcode Aztec dan belajar cara **membuat barcode Aztec** dengan Aspose.BarCode untuk .NET? Perpustakaan ini memberi Anda kontrol penuh atas ukuran, koreksi kesalahan, dan representasi data, menjadikannya ideal untuk segala hal mulai dari tiket seluler hingga pelacakan inventaris.

## Jawaban Cepat
- **Perpustakaan apa yang mendukung barcode Aztec?** Aspose.BarCode for .NET  
- **Apakah saya dapat mengubah rasio aspek?** Ya, melalui properti `AspectRatio`  
- **Apakah pengkodean tingkat byte memungkinkan?** Tentu – gunakan metode `EncodeBytes`  
- **Level koreksi kesalahan apa yang tersedia?** Level 0 hingga 4 (lebih tinggi = lebih banyak redundansi)  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial menghapus batas evaluasi  

## Apa itu barcode Aztec?
Barcode Aztec adalah kode matriks dua dimensi yang dapat mengkodekan hingga 3.000 karakter numerik atau 2.300 karakter alfanumerik. Ia memiliki pola pencari pusat, memungkinkan pemindaian cepat bahkan ketika simbol dicetak dengan resolusi rendah. Karena pola berada di tengah, kode dapat dibaca dari arah mana pun, menjadikannya sangat dapat diandalkan untuk aplikasi seluler dan industri.

## Bagaimana cara menyesuaikan rasio aspek barcode Aztec?
`BarcodeGenerator` adalah kelas utama yang digunakan untuk membuat barcode di Aspose.BarCode. Atur properti `AspectRatio` pada objek `BarcodeGenerator` ke proporsi lebar‑ke‑tinggi yang diinginkan, kemudian hasilkan gambar. Menyesuaikan rasio aspek membantu menempatkan barcode dalam ruang UI atau tata label yang terbatas tanpa mengorbankan keandalan pemindaian, dan juga memungkinkan Anda menyesuaikan pedoman merek atau persyaratan printer tertentu.

### Langkah-langkah menyesuaikan rasio aspek
1. **Buat instance `BarcodeGenerator`** dengan `EncodeTypes.Aztec`.  
2. **Tetapkan data Anda** (teks, byte, atau string numerik).  
3. **Atur `AspectRatio`** – misalnya, `1.5` untuk bar yang lebih lebar.  
4. **Hasilkan gambar** menggunakan `Save` atau `GetBarCodeImage`.  

## Bagaimana cara mengkodekan byte mentah ke dalam barcode Aztec?
`EncodeBytes` adalah metode yang menerima array byte dan mengubahnya menjadi matriks Aztec. Berikan array byte ke metode `EncodeBytes` pada `BarcodeGenerator`. API secara otomatis mengubah data biner menjadi matriks Aztec yang kompak, mempertahankan setiap bit. Ini sempurna untuk menyematkan payload terenkripsi, pengidentifikasi biner, atau file terkompresi langsung ke dalam barcode.

### Langkah-langkah mengkodekan byte
1. **Siapkan array byte** (mis., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instansiasi `BarcodeGenerator`** dengan `EncodeTypes.Aztec`.  
3. **Panggil `EncodeBytes(data)`** untuk memuat konten biner.  
4. **Render barcode** dengan `Save` atau `GetBarCodeImage`.  

## Bagaimana cara mengkodekan teks ke dalam barcode Aztec?
`CodeText` adalah properti yang menyimpan data teks biasa yang akan dikodekan. Gunakan properti `CodeText` pada `BarcodeGenerator` untuk menyediakan data teks biasa. Perpustakaan secara otomatis memilih mode pengkodean optimal (numerik, alfanumerik, atau byte) dan menerapkan level koreksi kesalahan yang sesuai. Ini memudahkan penyematan URL, ID produk, atau string yang dapat dibaca apa pun.

### Langkah-langkah mengkodekan teks
1. **Buat generator** dengan `EncodeTypes.Aztec`.  
2. **Atur `CodeText`** ke string yang ingin Anda kodekan.  
3. **Opsional, sesuaikan `ErrorLevel`** untuk ketahanan yang lebih tinggi.  
4. **Hasilkan gambar** menggunakan `Save` atau `GetBarCodeImage`.  

## Bagaimana cara menghasilkan barcode Aztec dengan level koreksi kesalahan yang berbeda?
`ErrorLevel` adalah properti yang mengontrol jumlah data redundan yang ditambahkan ke barcode. Sesuaikan properti `ErrorLevel` (0‑4) sebelum merender. Level yang lebih tinggi meningkatkan jumlah data redundan, memungkinkan barcode dibaca bahkan ketika hingga 30 % simbol rusak. Ini penting untuk lingkungan keras seperti pelabelan industri atau tanda luar ruangan.

### Langkah-langkah mengatur koreksi kesalahan
1. **Instansiasi `BarcodeGenerator`** untuk Aztec.  
2. **Tetapkan data Anda** (teks atau byte).  
3. **Atur `ErrorLevel`** – mis., `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Render barcode** dengan format output pilihan Anda.  

## Apa saja Mode Simbol Aztec yang berbeda dan bagaimana cara menggunakannya?
`SymbolMode` adalah pengaturan yang menentukan ukuran matriks dan kapasitas data dari kode Aztec yang dihasilkan. Mode Simbol Aztec menentukan ukuran matriks dan kapasitas data. Perpustakaan menawarkan empat mode: **Auto**, **FullRange**, **Compact**, dan **Rune**.  

- **Auto** – generator memilih ukuran terkecil yang mungkin.  
- **FullRange** – memungkinkan ukuran matriks maksimum untuk kumpulan data yang sangat besar.  
- **Compact** – membuat simbol yang lebih kecil dan lebih padat, ideal untuk ruang terbatas.  
- **Rune** – mode khusus untuk mengkodekan rune Unicode.  

Pilih mode melalui `Generator.Parameters.Barcode.Aztec.SymbolMode`. Setiap mode menyeimbangkan ukuran, keterbacaan, dan kapasitas data, memungkinkan Anda menyesuaikan barcode dengan batasan aplikasi Anda.

## Tutorial Pengkodean Barcode Aztec
Berikut adalah panduan langkah‑demi‑langkah yang didedikasikan untuk menyelami lebih dalam setiap topik yang dibahas di atas. Klik tautan mana pun untuk menjelajahi contoh kode lengkap, prasyarat, dan tips praktik terbaik.

### [Sesuaikan Rasio Aspek Barcode Aztec](./aztec-aspect-ratio-customization/)
Pelajari cara menyesuaikan rasio aspek barcode Aztec menggunakan Aspose.BarCode untuk .NET. Buat barcode yang unik dan fleksibel untuk aplikasi .NET Anda.

### [Pengkodean Byte Aztec](./aztec-bytes-encoding/)
Pelajari cara melakukan Pengkodean Byte Aztec dengan Aspose.BarCode untuk .NET. Panduan langkah demi langkah, prasyarat, dan contoh kode disertakan.

### [Pengkodean Teks Kode Aztec](./aztec-code-text-encoding/)
Temukan kekuatan Pengkodean Teks Kode Aztec dengan Aspose.BarCode untuk .NET. Pelajari cara membuat dan mengenali kode Aztec dalam aplikasi .NET Anda.

### [Menghasilkan Barcode Aztec dengan Level Kesalahan](./aztec-error-level-example/)
Pelajari cara menghasilkan barcode Aztec dengan level kesalahan yang berbeda menggunakan Aspose.BarCode untuk .NET. Panduan komprehensif untuk pembuatan barcode.

### [Menguasai Mode Simbol Aztec](./aztec-symbol-mode-example/)
Jelajahi Mode Simbol Aztec di Aspose.BarCode untuk .NET dan pelajari cara menghasilkan barcode serbaguna dengan mudah. Dapatkan pengalaman langsung dengan mode Auto, FullRange, Compact, dan Rune dalam tutorial komprehensif ini.

## Pertanyaan yang Sering Diajukan

**Q: Versi .NET apa yang didukung oleh Aspose.BarCode untuk pengkodean Aztec?**  
A: Perpustakaan ini bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6, dan versi selanjutnya.

**Q: Bisakah saya membuat barcode Aztec resolusi tinggi untuk pencetakan?**  
A: Ya—atur properti `Resolution` (mis., 300 dpi) sebelum menyimpan gambar untuk mendapatkan kualitas siap cetak.

**Q: Seberapa besar payload data yang dapat ditampung barcode Aztec?**  
A: Hingga 3.000 karakter numerik atau 2.300 karakter alfanumerik, atau kira-kira 1.800 byte data mentah dalam mode Compact.

**Q: Apakah memungkinkan membaca barcode Aztec yang telah diputar?**  
A: Tentu—decoder Aspose.BarCode secara otomatis mendeteksi orientasi dan memperbaikinya selama operasi pembacaan.

**Q: Apakah saya memerlukan lisensi untuk pengembangan dan pengujian?**  
A: Lisensi evaluasi gratis tersedia untuk pengujian; lisensi komersial diperlukan untuk penerapan produksi.

---

**Terakhir Diperbarui:** 2026-05-19  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Pengkodean Byte Aztec menggunakan generator barcode .NET](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Cara membuat barcode Aztec dengan koreksi kesalahan di .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}