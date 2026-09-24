---
category: general
date: 2026-08-09
description: Buat kode batang PDF417 dalam C# dengan cepat. Pelajari cara menghasilkan
  PDF417 dengan mode kompak, kontrol kolom, dan output PNG menggunakan API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: id
lastmod: 2026-08-09
og_description: Hasilkan kode batang PDF417 di C# dengan contoh singkat. Panduan ini
  menunjukkan cara mengatur mode kompak, menentukan kolom, dan menyimpan hasilnya
  sebagai gambar PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Buat barcode PDF417 di C# – tutorial lengkap
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Menghasilkan barcode PDF417 di C# – panduan langkah demi langkah
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan barcode PDF417 di C# – panduan langkah demi langkah

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, tutorial ini menunjukkan secara tepat cara melakukannya. Anda akan melihat program lengkap yang dapat dijalankan yang membuat barcode PDF417 kompak, menyesuaikan ukurannya, dan menyimpan gambar sebagai file PNG.

Membuat barcode PDF417 adalah kebutuhan umum untuk tiket seluler, pelacakan inventaris, dan keamanan dokumen. Panduan ini mencakup opsi konfigurasi penting, menjelaskan mengapa setiap pengaturan penting, dan memberikan tips praktis untuk penggunaan di dunia nyata.

## Prasyarat

* .NET 6.0 SDK atau yang lebih baru terpasang  
* IDE C# seperti Visual Studio 2022 atau Visual Studio Code  
* Paket NuGet **Aspose.BarCode for .NET** (versi 23.10 atau lebih baru)  

Anda dapat menginstal paket dengan perintah CLI berikut:

```bash
dotnet add package Aspose.BarCode
```

Kode di bawah mengasumsikan paket sudah direferensikan dan Anda memiliki izin menulis ke direktori output.

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan tambahkan direktif `using` yang diperlukan. Namespace ini menyediakan kelas `BarcodeGenerator` dan enumerasi format gambar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Mengapa ini penting:** Mengimpor namespace yang tepat memastikan kompilator dapat menemukan tipe `BarcodeGenerator` dan enum `BarCodeImageFormat`. Kehilangan sebuah namespace akan menghasilkan error kompilasi, yang menghentikan proses pembuatan barcode.

## Langkah 2: Inisialisasi `BarcodeGenerator` dengan enkoding PDF417

Konstruktor `BarcodeGenerator` menerima dua argumen: simbol barcode (`EncodeTypes.Pdf417`) dan teks yang ingin Anda enkode. PDF417 mendukung berbagai karakter, termasuk simbol Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Penjelasan:**  
* `EncodeTypes.Pdf417` memberi tahu perpustakaan untuk menggunakan standar PDF417.  
* Teks contoh berisi karakter aksen dan simbol hak cipta untuk menunjukkan penanganan Unicode.  

Jika Anda hanya perlu mengenkode data numerik, Anda dapat memberikan string biasa seperti "1234567890".

## Langkah 3: Sesuaikan dimensi X untuk resolusi lebih halus

Dimensi X mengontrol lebar satu modul barcode (elemen hitam atau putih terkecil). Menetapkan nilai piksel yang lebih kecil menghasilkan gambar dengan resolusi lebih tinggi.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa menyesuaikannya?** Dimensi X default 3–4 piksel dapat menghasilkan barcode yang tampak kasar pada layar ber‑DPI tinggi. Menguranginya menjadi **2 piksel** menyeimbangkan keterbacaan dengan ukuran file, terutama ketika Anda kemudian mengaktifkan mode kompak.

## Langkah 4: Konfigurasikan jumlah kolom

PDF417 memungkinkan Anda menentukan berapa banyak kolom yang harus dimiliki barcode. Lebih sedikit kolom membuat barcode lebih sempit namun lebih tinggi, sementara lebih banyak kolom menghasilkan barcode yang lebih lebar dan lebih pendek.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Tip praktis:** Untuk tiket seluler yang harus muat dalam label sempit, jumlah kolom **3–5** bekerja dengan baik. Tingkatkan jumlahnya jika Anda memiliki banyak data dan menginginkan barcode yang lebih pendek.

## Langkah 5: Aktifkan mode kompak untuk memotong baris kosong

Mode kompak menghapus baris yang tidak diperlukan dari matriks barcode, mengurangi ukuran gambar secara keseluruhan tanpa kehilangan data yang dienkode.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Kapan menggunakannya:** Jika Anda menghasilkan barcode untuk penyimpanan atau transmisi jaringan, mode kompak dapat memperkecil file PNG hingga 30 %. Namun, beberapa pemindai lama mungkin tidak mendukung PDF417 yang dipotong; uji dengan perangkat keras target Anda.

## Langkah 6: Simpan barcode sebagai gambar PNG

Pilih jalur output dan panggil `Save`. Enumerasi `BarCodeImageFormat.Png` menghasilkan gambar lossless yang cocok untuk kebanyakan aplikasi.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Verifikasi hasil:** Buka file PNG di penampil gambar apa pun. Anda harus melihat barcode yang padat dan kontras tinggi yang cocok dengan teks contoh. Memindai gambar dengan pembaca PDF417 (mis., ZXing atau aplikasi smartphone) mengembalikan string asli "Åspóse.Barcóde©".

![Gambar barcode PDF417 yang dihasilkan disimpan sebagai PNG](compact-pdf417.png "Barcode PDF417 yang dihasilkan dalam C#")

*Gambar di atas menunjukkan output akhir dari kode tutorial.*

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian, berikut adalah program konsol lengkap yang dapat Anda salin, tempel, dan jalankan.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Output yang diharapkan

Menjalankan program mencetak:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

File `CompactPdf417.png` berisi barcode PDF417 kompak yang mengenkripsi string Unicode yang diberikan. Memindai gambar dengan pembaca PDF417 standar mengembalikan teks yang tepat.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian | Alasan |
|-----------|------------|--------|
| **Payload data lebih panjang** (mis., > 150 karakter) | Tingkatkan `generator.Parameters.Barcode.Pdf417.Columns` menjadi 6‑8 | Lebih banyak kolom mencegah barcode menjadi terlalu tinggi. |
| **Butuh latar belakang transparan** | Gunakan `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG transparan lebih mudah diintegrasikan ke dalam overlay UI. |
| **Menghasilkan JPEG untuk web** | Ubah format menjadi `BarCodeImageFormat.Jpeg` dan opsional atur `ImageQuality` | JPEG mengurangi ukuran file dengan mengorbankan kesetiaan lossless. |
| **Menangani input null atau kosong** | Lindungi input sebelum membuat generator: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Mencegah pengecualian runtime dan memastikan barcode yang bermakna. |

## Tips untuk penggunaan produksi

* **Penanganan pengecualian:** Bungkus logika pembuatan dalam blok `try/catch` untuk mencatat error seperti ruang disk tidak cukup atau parameter tidak valid.  
* **Kinerja:** Gunakan kembali satu instance `BarcodeGenerator` saat menghasilkan banyak barcode dengan pengaturan yang sama; hanya perbarui properti `CodeText` di antara penyimpanan.  
* **Keamanan:** Ketika teks yang dienkode berisi informasi sensitif, pertimbangkan untuk mengenkripsinya sebelum diberikan ke generator dan mendekripsinya setelah pemindaian.  

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode PDF417** di C# menggunakan pustaka Aspose.BarCode, mengonfigurasi mode kompak, mengontrol jumlah kolom, dan mengekspor hasilnya sebagai gambar PNG. Tutorial ini mencakup setiap langkah mulai dari penyiapan proyek hingga penanganan kasus tepi, memberikan Anda solusi siap pakai untuk aplikasi berbasis barcode.

Selanjutnya, jelajahi topik terkait seperti **membuat QR code di C#**, **pembuatan barcode batch**, dan **mengintegrasikan pemindaian barcode dengan aplikasi seluler**. Masing‑masing topik ini dibangun di atas dasar `BarcodeGenerator` yang sama yang baru saja Anda kuasai.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang dibangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Barcode PDF417 – Enkoding PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}