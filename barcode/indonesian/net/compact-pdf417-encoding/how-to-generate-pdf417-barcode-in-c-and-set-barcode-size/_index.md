---
category: general
date: 2026-08-22
description: Pelajari cara menghasilkan barcode PDF417 di C# dengan Aspose.BarCode,
  mengatur ukuran barcode, menyesuaikan kolom, dan mengaktifkan mode kompak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: id
lastmod: 2026-08-22
og_description: Hasilkan kode batang PDF417 dalam C# dengan Aspose.BarCode. Panduan
  ini menunjukkan cara mengatur ukuran kode batang, mengontrol kolom, dan mengaktifkan
  mode kompak untuk gambar yang lebih kecil.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Buat kode batang PDF417 di C# – atur ukuran, kolom, dan mode kompak
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Cara menghasilkan barcode PDF417 di C# dan mengatur ukuran barcode
url: /id/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghasilkan barcode PDF417 di C# dan mengatur ukuran barcode

Jika Anda perlu **menghasilkan barcode PDF417** dalam aplikasi .NET, panduan ini akan membawa Anda melalui proses lengkap. Anda akan melihat secara tepat **cara menghasilkan PDF417** dengan Aspose.BarCode, menyesuaikan **ukuran barcode**, dan menghasilkan PNG kompak yang dapat disematkan dalam laporan atau aplikasi seluler.

Membuat barcode tidak memerlukan editor grafis terpisah. Pada akhir tutorial ini Anda akan memiliki metode C# yang berfungsi penuh yang menghasilkan gambar PDF417 dengan dimensi tepat yang Anda butuhkan, siap untuk diproses lebih lanjut.

## Apa yang akan Anda pelajari

* Menginstal dan mereferensikan pustaka Aspose.BarCode.  
* Membuat generator barcode PDF417 dan menentukan teks yang akan dienkode.  
* **Mengatur ukuran barcode** dengan mengonfigurasi X‑dimension dan jumlah kolom.  
* Mengaktifkan mode kompak (truncated) untuk memperkecil simbol.  
* Menyimpan hasil sebagai file PNG.  
* Memecahkan masalah umum seperti kode yang tidak terbaca dan gambar yang terlalu besar.

### Prasyarat

* .NET 6.0 atau yang lebih baru (API juga berfungsi dengan .NET Framework 4.6+).  
* Familiaritas dasar dengan C# dan Visual Studio (atau IDE C# apa pun).  
* Lisensi Aspose.BarCode yang valid (evaluasi gratis dapat digunakan untuk pengujian).

> **Pro tip:** Jika Anda berencana menghasilkan banyak barcode dalam sebuah loop, gunakan kembali satu instance `BarcodeGenerator` dan hanya ubah properti `CodeText`. Ini mengurangi alokasi memori.

## Menghasilkan barcode PDF417 dengan Aspose.BarCode

Langkah pertama adalah menginstansiasi `BarcodeGenerator` untuk simbolologi PDF417. Objek ini merupakan titik masuk untuk semua operasi barcode.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Mengapa ini penting*: `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan standar PDF417, yang mendukung volume data besar dan koreksi kesalahan. Konstruktor juga menerima data yang ingin Anda enkode, menghilangkan kebutuhan penetapan `CodeText` terpisah nanti.

## Mengatur ukuran barcode dan jumlah kolom

Simbol PDF417 terdiri dari baris dan kolom modul persegi panjang kecil. Mengontrol lebar modul (X‑dimension) dan jumlah kolom memungkinkan Anda menyesuaikan dimensi keseluruhan dengan presisi.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Penjelasan*:  
* **X‑dimension** (`Pixels`) menentukan seberapa lebar setiap modul. Nilai yang lebih kecil menghasilkan barcode yang lebih rapat, sementara nilai yang lebih besar meningkatkan keterbacaan pada pemindai beresolusi rendah.  
* **Columns** mengontrol tata letak horizontal. Kolom yang lebih sedikit membuat barcode lebih tinggi; kolom yang lebih banyak membuatnya lebih lebar. Sesuaikan kedua pengaturan ini bersama‑sama untuk mencapai **ukuran barcode** yang tepat yang Anda butuhkan.

## Mengaktifkan mode kompak untuk barcode yang lebih kecil

PDF417 memiliki mode “compact” (atau truncated) yang menghapus padding yang tidak diperlukan dan mengurangi jejak keseluruhan. Ini sangat berguna ketika Anda memiliki ruang layar yang terbatas.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Mengapa mengaktifkan pemotongan?*  
Ketika `Truncate` bernilai `true`, generator menghilangkan pola berhenti dan beberapa kode koreksi‑kesalahan yang tidak diperlukan untuk kebanyakan skenario pemindaian. Gambar yang dihasilkan kira‑kira 15‑20 % lebih kecil tanpa mengorbankan integritas data untuk penggunaan umum.

## Menyimpan barcode sebagai gambar PNG

Setelah mengonfigurasi ukuran dan mode, tulis barcode ke disk. PNG bersifat lossless, memastikan tepi modul tetap tajam.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

File `CompactPdf417.png` akan berisi simbol PDF417 yang jelas dan sesuai dengan dimensi yang Anda tetapkan pada langkah‑langkah sebelumnya.

### Output yang diharapkan

Membuka PNG yang disimpan seharusnya menampilkan barcode PDF417 berorientasi vertikal yang terdiri dari tiga kolom, masing‑masing modul berukuran 2 px, dengan total ukuran kira‑kira **120 × 240 px** (lebar × tinggi). Memindai gambar dengan pembaca PDF417 standar mengembalikan teks asli “Sample text for PDF417”.

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab yang mungkin | Solusi |
|--------|-----------------------|--------|
| Barcode tidak terbaca | X‑dimension terlalu kecil untuk pemindai | Tingkatkan `XDimension.Pixels` menjadi 3 atau 4 |
| Gambar terlalu lebar untuk UI | Terlalu banyak kolom yang diatur | Kurangi `Pdf417.Columns` atau aktifkan `Truncate` |
| Exception `ArgumentOutOfRangeException` | Jumlah kolom negatif atau nol | Pastikan `Columns` adalah bilangan bulat positif (minimum 1) |
| File PNG kosong | Jalur output tidak ada atau tidak memiliki izin menulis | Verifikasi direktori ada dan aplikasi memiliki hak menulis |

> **Pro tip:** Gunakan `barcodeGenerator.ValidateParameters()` sebelum memanggil `Save()` untuk menangkap kesalahan konfigurasi lebih awal.

## Contoh lengkap yang dapat dijalankan

Berikut adalah program konsol mandiri yang menggabungkan semua langkah di atas. Salin ke proyek C# baru, pulihkan paket NuGet Aspose.BarCode, dan jalankan untuk melihat hasilnya.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Menjalankan program** menghasilkan `CompactPdf417.png` di direktori kerja executable. Pindai gambar dengan aplikasi seluler (misalnya “Barcode Scanner”) untuk memverifikasi bahwa teks yang dienkode cocok dengan string sumber.

## Langkah selanjutnya dan topik terkait

* **Meningkatkan level koreksi kesalahan** – sesuaikan `Pdf417.ErrorLevel` untuk lingkungan dengan pemindaian yang berisik.  
* **Mengubah orientasi** – setel `Pdf417.Rotate` ke `RotationAngle.Rotate90` jika Anda membutuhkan tata letak horizontal.  
* **Menyematkan barcode dalam PDF** – gabungkan Aspose.PDF dengan Aspose.BarCode untuk menempatkan gambar langsung ke dalam dokumen.  
* **Menghasilkan barcode 2‑D lainnya** – kelas `BarcodeGenerator` yang sama mendukung DataMatrix, QR, dan Aztec; cukup ganti `EncodeTypes.Pdf417` dengan simbolologi yang diinginkan.

Dengan menguasai teknik **menghasilkan barcode PDF417**, Anda dapat mengotomatiskan tiket, pelabelan inventaris, dan transmisi data aman di berbagai aplikasi .NET.

## Kesimpulan

Anda kini tahu cara **menghasilkan barcode PDF417** di C#, secara tepat **mengatur ukuran barcode**, mengonfigurasi kolom, mengaktifkan mode kompak, dan menyimpan hasil sebagai PNG. Terapkan pengaturan ini untuk menyesuaikan dengan batasan UI atau kebutuhan pemindaian apa pun, dan perluas pendekatan ke format barcode lain bila diperlukan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang berhubungan erat dan membangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}