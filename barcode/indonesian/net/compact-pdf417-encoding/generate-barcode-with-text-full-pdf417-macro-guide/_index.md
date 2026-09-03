---
category: general
date: 2026-07-18
description: Hasilkan kode batang dengan teks menggunakan Aspose.BarCode untuk .NET.
  Pelajari cara menghasilkan kode batang PDF417, mengatur opsi makro, dan mengekspor
  gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: id
lastmod: 2026-07-18
og_description: Buat barcode dengan teks di C# dengan cepat. Tutorial langkah demi
  langkah ini menunjukkan cara menghasilkan barcode PDF417, mengonfigurasi pengaturan
  makro, dan menyimpan sebagai PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Buat kode batang dengan teks – Pembuatan Macro PDF417 Master
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Buat kode batang dengan teks – Panduan Lengkap PDF417 Macro
url: /id/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode dengan teks – Panduan Lengkap Macro PDF417

Pernah bertanya‑tanya **bagaimana cara menghasilkan PDF417** barcode yang juga menyematkan teks khusus? Dalam tutorial ini Anda akan melihat secara tepat bagaimana **menghasilkan barcode dengan teks** menggunakan Aspose.BarCode untuk .NET, dan kami akan membahas setiap pengaturan yang Anda perlukan untuk simbol Macro PDF417. Tanpa basa‑basi, hanya contoh lengkap yang dapat dijalankan yang dapat Anda masukkan ke dalam proyek Anda hari ini.

Kami akan membahas:

* Paket NuGet yang diperlukan dan direktif `using`.  
* Cara membuat generator barcode yang mendukung karakter Unicode.  
* Menetapkan ukuran modul, jumlah kolom, dan ID khusus macro.  
* Menyimpan hasil sebagai file PNG dan memverifikasi output.  

Pada akhir tutorial Anda akan memiliki gambar PNG siap pakai dari barcode Macro PDF417 yang dapat Anda sematkan dalam faktur, tiket, atau dokumen apa pun yang memerlukan segmen yang dapat dibaca mesin.

---

## Prasyarat

Sebelum kita melanjutkan, pastikan Anda memiliki:

| Persyaratan | Alasan |
|-------------|--------|
| **.NET 6.0** atau lebih baru | Aspose.BarCode mendukung .NET Standard 2.0+, jadi .NET 6 memberi Anda runtime terbaru. |
| **Visual Studio 2022** (atau IDE C# apa pun) | Untuk memudahkan penyuntingan dan debugging. |
| **Aspose.BarCode for .NET** paket NuGet | Perpustakaan yang benar‑benarnya membuat barcode. Instal dengan `dotnet add package Aspose.BarCode`. |
| **Izin menulis** ke folder output | Metode `Save` perlu menulis file PNG. |

Jika ada yang belum Anda kenal, berhentilah sejenak dan selesaikan dulu—kalau tidak kode akan melempar pengecualian yang jelas.

---

## Langkah 1 – Instal dan impor pustaka

Pertama, tambahkan paket NuGet ke proyek Anda:

```bash
dotnet add package Aspose.BarCode
```

Kemudian, bawa namespace yang diperlukan ke dalam ruang lingkup:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Pro tip:** Jika Anda menggunakan Visual Studio, klik kanan proyek → *Manage NuGet Packages* → cari *Aspose.BarCode* dan instal versi stabil terbaru.

---

## Langkah 2 – Buat generator barcode dengan teks khusus Anda

Tugas *utama* adalah **menghasilkan barcode dengan teks** yang berisi karakter khusus seperti “Å” dan “©”. Konstruktor mengambil tipe enkode dan string data mentah:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Mengapa ini penting: `EncodeTypes.MacroPdf417` memberi tahu Aspose bahwa kita menginginkan versi macro, yang memungkinkan kita membagi pesan besar menjadi beberapa simbol. String teks dapat berupa urutan UTF‑8 apa pun; Aspose menangani konversinya secara internal.

---

## Langkah 3 – Sesuaikan tampilan dasar (ukuran modul)

“Modul” pada barcode adalah kotak hitam‑atau‑putih terkecil. Menetapkan ukuran pikselnya mengontrol dimensi gambar secara keseluruhan tanpa mengubah kepadatan data:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jika Anda memerlukan gambar yang lebih besar untuk pencetakan, naikkan nilai ini menjadi 4 atau 6. Ingat bahwa modul yang lebih besar akan meningkatkan ukuran file PNG akhir.

---

## Langkah 4 – Konfigurasikan opsi khusus Macro PDF417

Macro PDF417 menambahkan dua pengenal yang memungkinkan pemindai menyatukan beberapa simbol. Anda biasanya akan mengatur:

| Properti | Fungsinya |
|----------|-----------|
| `Columns` | Jumlah kolom data per simbol (mempengaruhi lebar). |
| `MacroPdf417FileID` | ID unik untuk seluruh file macro (harus ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Indeks segmen saat ini (0‑254). |

Berikut kodenya:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Catatan kasus tepi:** `MacroPdf417FileID` harus sama untuk setiap segmen dalam file logis yang sama. Jika Anda menghasilkan beberapa segmen, gunakan kembali ID yang sama atau Anda akan mendapatkan simbol yang tidak terkait dan tidak dapat digabungkan.

---

## Langkah 5 – Simpan barcode sebagai gambar PNG

Sekarang semua sudah dikonfigurasi, tulis gambar ke disk:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Metode `Save` secara otomatis membuat PNG, menangani DPI dan kedalaman warna untuk Anda. Setelah dijalankan, buka file untuk melihat sesuatu seperti ini:

![Contoh barcode dengan teks](/images/barcode-example.png){.center alt="Contoh barcode dengan teks"}

Jika Anda tidak melihat barcode, periksa kembali bahwa folder tersebut ada dan aplikasi Anda memiliki izin menulis.

---

## Contoh Lengkap yang Siap Dijalankan

Salin seluruh potongan kode di bawah ini ke aplikasi konsol baru (`dotnet new console`) dan jalankan. Itu akan menghasilkan PNG di folder `C:\Barcodes` (buat foldernya terlebih dahulu).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Output yang diharapkan** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

Dan PNG akan menampilkan simbol Macro PDF417 yang kompak berisi teks “Åspóse.Barcóde©”.

---

## Pertanyaan Umum & Jebakan

| Pertanyaan | Jawaban |
|------------|---------|
| *Bisakah saya menggunakan format gambar lain?* | Tentu saja—ganti `BarCodeImageFormat.Png` dengan `Jpeg`, `Bmp`, atau `Gif`. PNG bersifat lossless, itulah mengapa kami menjadikannya default. |
| *Bagaimana jika saya membutuhkan lebih dari satu segmen?* | Buat `BarcodeGenerator` baru untuk setiap segmen, pertahankan `MacroPdf417FileID` sama, dan tingkatkan `MacroPdf417SegmentID` (0‑254). |
| *Teks saya berisi emoji—apakah mereka akan berfungsi?* | Aspose.BarCode mendukung UTF‑8, jadi sebagian besar emoji dapat diproses. Pastikan pemindai target dapat mendekodenya; banyak pemindai industri hanya menangani data alfanumerik. |
| *Barcode terlalu lebar untuk label saya.* | Kurangi `Columns` atau tingkatkan ukuran modul. Lebih sedikit kolom menghasilkan simbol yang lebih sempit, tetapi mungkin memerlukan printer dengan DPI lebih tinggi. |
| *Apakah saya memerlukan lisensi?* | Lisensi evaluasi gratis dapat dipakai untuk pengujian, tetapi akan menambahkan watermark kecil. Untuk produksi, beli lisensi untuk menghilangkan watermark dan membuka semua fitur. |

---

## Langkah Selanjutnya

Sekarang Anda tahu **bagaimana cara menghasilkan PDF417** barcode dengan teks khusus, Anda mungkin ingin:

* **Mendekode** barcode dalam aplikasi seluler menggunakan `BarCodeReader` Aspose.BarCode.  
* **Menggabungkan** beberapa segmen macro menjadi satu dokumen PDF untuk pencetakan massal.  
* **Menjelajahi simbol lain** (QR, DataMatrix) dengan pola parameter serupa.  
* **Menyesuaikan tingkat koreksi kesalahan** melalui `Pdf417.ErrorCorrectionLevel` untuk lingkungan yang lebih keras.

Setiap topik ini dibangun di atas konsep inti yang baru saja Anda pelajari, sehingga transisinya akan terasa mulus.

---

## Kesimpulan

Kami telah menelusuri solusi lengkap dari ujung ke ujung yang memungkinkan Anda **menghasilkan barcode dengan teks** dan, secara khusus, **bagaimana cara menghasilkan macro PDF417** menggunakan Aspose.BarCode untuk .NET. Dengan mengatur dimensi X, jumlah kolom, dan ID macro, Anda memperoleh kontrol penuh atas ukuran, tata letak, dan penanganan multi‑segmen. PNG yang dihasilkan dapat dicetak, disematkan dalam PDF, atau dikirim ke pemindai tanpa konversi lebih lanjut.

Cobalah, sesuaikan parameternya, dan biarkan barcode bekerja untuk kebutuhan bisnis Anda. Jika Anda menemui kendala, dokumentasi Aspose dan forum komunitas adalah sumber daya lanjutan yang sangat baik. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut membahas topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}