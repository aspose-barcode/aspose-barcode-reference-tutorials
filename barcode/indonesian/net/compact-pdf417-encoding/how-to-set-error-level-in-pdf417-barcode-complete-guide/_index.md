---
category: general
date: 2026-07-18
description: cara mengatur tingkat kesalahan pada kode batang PDF417 menggunakan Aspose.BarCode.
  Pelajari cara menghasilkan kode batang PDF417 dengan teks khusus dan menyesuaikan
  koreksi kesalahan dalam hitungan menit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: id
lastmod: 2026-07-18
og_description: Cara mengatur tingkat kesalahan pada kode batang PDF417 dengan cepat.
  Tutorial ini memandu Anda melalui pembuatan kode batang PDF417 dengan teks khusus
  dan berbagai tingkat koreksi kesalahan.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Langkah demi
  Langkah
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap
url: /id/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap

Pernah bertanya-tanya **bagaimana cara mengatur kesalahan** saat Anda menghasilkan barcode PDF417? Anda tidak sendirian—banyak pengembang mengalami masalah ini ketika mereka membutuhkan barcode yang lebih kuat untuk pemindaian di lingkungan yang keras. Kabar baiknya? Menyesuaikan tingkat koreksi kesalahan sangat mudah dengan Aspose.BarCode, dan Anda juga akan belajar **cara menghasilkan PDF417** dengan teks khusus Anda sendiri.

Dalam tutorial ini kami akan membahas setiap langkah, mulai dari membuat generator barcode dengan karakter khusus hingga menyimpan dua file PNG yang menampilkan tingkat koreksi kesalahan yang berbeda. Pada akhir tutorial Anda akan nyaman **menghasilkan barcode PDF417**, menyesuaikan X‑dimension, jumlah kolom, dan yang paling penting, **mengatur kesalahan** sesuai kebutuhan Anda.

## Prerequisites

- .NET 6.0 atau lebih baru (kode ini juga berfungsi dengan .NET Framework)
- Aspose.BarCode untuk .NET terpasang (`Install-Package Aspose.BarCode` via NuGet)
- Folder di disk tempat gambar dapat ditulis (ganti `YOUR_DIRECTORY/` dalam contoh)
- Pengetahuan dasar C#—jika Anda pernah menulis `Console.WriteLine`, Anda siap melanjutkan

> **Pro tip:** Jika Anda menargetkan pemindaian seluler, pilih tingkat kesalahan yang lebih tinggi (Level 5) untuk bertahan dari kotoran, goresan, atau kondisi cahaya rendah.

## Langkah 1: Buat Barcode Generator dengan Teks Kustom

Hal pertama yang Anda perlukan adalah instance `BarcodeGenerator` yang tahu harus menghasilkan **barcode PDF417** dan membawa teks tepat yang ingin Anda enkode. Perhatikan penggunaan karakter aksen dan simbol hak cipta—ini membuktikan generator dapat menangani Unicode secara langsung.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Mengapa ini penting:* Flag `EncodeTypes.Pdf417` memberi tahu Aspose bahwa Anda berurusan dengan barcode 2‑D berlapis, sementara argumen string menjadi payload data. Jika Anda melewatkan langkah ini, Anda akan mendapatkan barcode Code128 default alih-alih PDF417 berkapasitas tinggi yang Anda butuhkan.

## Langkah 2: Sesuaikan Parameter Visual

Barcode PDF417 bukan hanya data; ia juga pola visual. Menyesuaikan **X‑dimension** (lebar bar terkecil) dan jumlah **columns** memungkinkan Anda mengontrol ukuran fisik barcode dan keterbacaannya.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Mengapa ini penting:* X‑dimension yang lebih kecil menghasilkan gambar yang lebih kompak tetapi dapat menjadi tidak terbaca pada pemindai beresolusi rendah. Tiga kolom memberikan rasio aspek seimbang untuk kebanyakan ukuran label.

## Langkah 3: Atur Tingkat Koreksi Kesalahan ke 2 dan Simpan

Koreksi kesalahan adalah inti dari **bagaimana cara mengatur kesalahan** untuk PDF417. Enum `Pdf417ErrorLevel` berkisar dari `Level0` (tanpa data tambahan) hingga `Level5` (redundansi maksimum). Di sini kami mulai dengan **Level 2**, yang menambahkan sedikit ketahanan kesalahan tanpa memperbesar gambar terlalu banyak.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Setelah menjalankan potongan kode ini Anda akan menemukan `Pdf417ErrorLevel2.png` di folder Anda. Buka file tersebut, dan Anda akan melihat barcode tiga kolom yang bersih namun tetap mengandung redundansi yang cukup.

## Langkah 4: Tingkatkan Koreksi Kesalahan ke Level 5 dan Simpan Lagi

Kadang‑kadang Anda membutuhkan barcode yang dapat bertahan dari kerusakan lebih agresif—bayangkan lantai gudang di mana label sering tergores. Beralih ke **Level 5** memaksimalkan koreksi kesalahan dengan biaya gambar yang sedikit lebih besar.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG berdampingan: satu dengan koreksi kesalahan sedang, yang lainnya dengan tingkat maksimum. Bandingkan keduanya; versi Level 5 akan memiliki lebih banyak modul gelap, yang memang ditambahkan algoritma untuk melindungi data.

![contoh cara mengatur tingkat kesalahan pada barcode PDF417](image.png)

*Deskripsi gambar (teks alt): contoh cara mengatur tingkat kesalahan pada barcode PDF417 – menampilkan dua file PNG dengan tingkat koreksi kesalahan yang berbeda.*

## Output yang Diharapkan

| Nama file                     | Tingkat kesalahan | Dimensi perkiraan (px) |
|-------------------------------|-------------------|------------------------|
| `Pdf417ErrorLevel2.png`       | Level 2           | 150 × 80               |
| `Pdf417ErrorLevel5.png`       | Level 5           | 180 × 95               |

Kedua gambar mengenkode string **“Åspóse.Barcóde©”** dan dapat dipindai dengan pembaca PDF417 standar apa pun (misalnya, ZXing, Scandit). Gambar Level 5 dapat menahan kerusakan hingga ~30 %, sementara Level 2 menahan sekitar ~15 %.

## Pertanyaan Umum & Kasus Tepi

### Bagaimana jika teks saya mengandung baris baru?

PDF417 secara otomatis mengenkode karakter line‑feed (`\n`). Cukup sertakan dalam string:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Bisakah saya menggunakan format gambar yang berbeda?

Tentu saja. Ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Svg` tergantung alur kerja downstream Anda.

### Apakah mengubah X‑dimension memengaruhi koreksi kesalahan?

Secara tidak langsung, ya. X‑dimension yang lebih besar menghasilkan modul yang lebih besar, yang dapat meningkatkan keandalan pemindaian tetapi **tidak** mengubah tingkat koreksi kesalahan logis. Sesuaikan kedua parameter secara independen untuk hasil terbaik.

### Bagaimana cara menghasilkan barcode PDF417 dalam API web?

Bungkus kode yang sama dalam controller ASP.NET Core dan alirkan PNG kembali sebagai `FileResult`. Logika inti tetap tidak berubah, yang berarti **cara menghasilkan PDF417** tetap konsisten di lingkungan desktop dan web.

## Ringkasan

Kami telah membahas **bagaimana cara mengatur kesalahan** untuk barcode PDF417, mendemonstrasikan **cara menghasilkan PDF417** dengan teks Unicode kustom, dan menunjukkan cara menyesuaikan pengaturan visual seperti X‑dimension dan jumlah kolom. Dengan menukar `Pdf417ErrorLevel.Level2` dengan `Level5` Anda dapat mengendalikan kompromi antara ukuran gambar dan ketahanan.

## Langkah Selanjutnya

- Bereksperimen dengan **barcode dengan teks kustom** yang mencakup URL atau ID produk.
- Coba jumlah kolom yang berbeda (`generator.Parameters.Barcode.Pdf417.Columns = 5`) untuk melihat bagaimana bentuknya berubah.
- Gabungkan PDF417 dengan tipe barcode lain dalam dokumen yang sama untuk solusi pemindaian multi‑modal.
- Selami [dokumentasi resmi](https://docs.aspose.com/barcode/net/) Aspose untuk fitur lanjutan seperti macro PDF417 atau mode kompak.

Silakan tinggalkan komentar jika Anda mengalami kendala, atau bagikan hasil pemindaian Anda sendiri. Selamat berkarya dengan barcode!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Membuat Barcode Aztec dengan Koreksi Kesalahan di .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}