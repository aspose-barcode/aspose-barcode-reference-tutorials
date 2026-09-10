---
category: general
date: 2026-09-10
description: Buat barcode PDF417 di C# dengan cepat. Pelajari cara mengaktifkan mode
  kompak, mengatur kolom, dan menghasilkan PNG dengan BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: id
lastmod: 2026-09-10
og_description: Buat kode batang PDF417 di C# dengan mengaktifkan mode kompak, mengatur
  kolom, dan menyimpan sebagai PNG. Ikuti panduan langkah demi langkah lengkap.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Buat barcode PDF417 di C# – tutorial mode kompak
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara membuat barcode PDF417 di C# dengan mode kompak
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat PDF417 barcode di C# dengan mode kompak

Jika Anda perlu **membuat PDF417 barcode** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan melihat cara **mengaktifkan mode kompak**, mengatur jumlah kolom, dan menyimpan hasilnya sebagai gambar PNG menggunakan pustaka BarcodeGenerator C#.

Membuat barcode adalah kebutuhan umum untuk pelacakan inventaris, sistem tiket, dan aplikasi pemindaian seluler. Pada akhir tutorial ini Anda akan memiliki contoh yang berdiri sendiri dan dapat dijalankan yang menghasilkan barcode PDF417 kompak siap untuk penggunaan produksi.

## Prasyarat

* .NET 6.0 atau yang lebih baru terinstal (kode juga berfungsi dengan .NET Framework 4.7+)
* Versi terbaru dari pustaka **BarcodeGenerator** (misalnya, Aspose.BarCode for .NET)
* IDE atau editor seperti Visual Studio 2022 atau VS Code
* Izin menulis ke folder tempat PNG akan disimpan

Tidak ada paket NuGet tambahan yang diperlukan selain pustaka barcode itu sendiri.

## Langkah 1: Buat generator barcode PDF417

Langkah pertama adalah menginstansiasi objek `BarcodeGenerator` dengan enum `EncodeTypes.Pdf417` dan teks yang ingin Anda enkode. Objek ini mengendalikan seluruh proses pembuatan.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Mengapa ini penting*: Nilai `EncodeTypes.Pdf417` memberi tahu pustaka untuk menggunakan simbol PDF417, sementara argumen kedua menyediakan payload. Anda dapat mengganti `"Compact mode"` dengan string alfanumerik apa pun yang perlu dienkode.

## Langkah 2: Atur dimensi X (lebar modul)

Dimensi X mengontrol lebar setiap kotak kecil (modul) dalam barcode. Nilai yang lebih kecil menghasilkan gambar yang lebih rapat, yang berguna ketika ruang terbatas.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nilai `2` piksel merupakan keseimbangan yang baik antara keterbacaan dan kekompakan untuk kebanyakan pemindai berbasis layar.

## Langkah 3: Tentukan jumlah kolom

PDF417 dapat menyusun data dalam grid baris dan kolom. Mengatur jumlah kolom mengubah rasio aspek barcode.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Mengatur **cara mengatur kolom** ke `3` menghasilkan barcode pendek dan lebar yang cocok pada label. Anda dapat bereksperimen dengan nilai antara `1` hingga `30` tergantung pada jumlah data dan pemindai target.

## Langkah 4: Aktifkan mode kompak

Mode kompak menghapus baris padding yang tidak diperlukan, membuat barcode lebih kecil tanpa kehilangan integritas data. Ini adalah langkah kunci untuk **PDF417 kompak**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Ketika `Truncate` bernilai `true`, pustaka secara otomatis menghitung jumlah baris minimal yang diperlukan untuk menyimpan data, itulah mengapa gambar akhir terlihat “rapat”.

## Langkah 5: Simpan barcode yang dihasilkan sebagai gambar PNG

Akhirnya, tulis barcode ke sebuah file. PNG mempertahankan tepi yang tajam diperlukan untuk pemindaian yang dapat diandalkan.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang dapat ditulis oleh aplikasi Anda. Setelah dijalankan, Anda akan menemukan file `CompactPdf417.png` yang berisi barcode.

### Kode sumber lengkap

Menggabungkan semua langkah memberikan Anda satu program siap‑jalankan:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Menjalankan program ini menghasilkan `CompactPdf417.png` di folder yang sama dengan executable. Buka gambar dengan penampil apa pun; Anda harus melihat barcode PDF417 yang padat dan kontras tinggi siap untuk dipindai.

## Cara mengaktifkan mode kompak dalam skenario lain

* **Batch generation** – Saat membuat banyak barcode, atur `Truncate` sekali pada generator dan gunakan kembali untuk setiap payload baru.
* **Different image formats** – Metode `Save` yang sama bekerja dengan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp` jika Anda memerlukan tipe file yang berbeda.
* **Dynamic column count** – Jika panjang string yang dienkode bervariasi, hitung jumlah kolom optimal berdasarkan panjang string dan resolusi pemindai.

## Cara mengatur kolom untuk kasus penggunaan tertentu

* **Label printing** – Gunakan jumlah kolom rendah (mis., `2`‑`5`) agar barcode cukup pendek untuk muat pada label sempit.
* **Mobile scanning** – Jumlah kolom lebih tinggi (`10`‑`15`) menghasilkan barcode yang lebih tinggi dan lebih mudah difokuskan oleh kamera ponsel.
* **Error‑correction trade‑off** – Lebih banyak kolom mengurangi jumlah baris, yang dapat memengaruhi koreksi kesalahan bawaan barcode. Uji dengan pemindai target Anda untuk menemukan titik optimal.

## Kesalahan umum dan tips profesional

| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| Barcode tidak dapat dibaca | Dimensi X terlalu rendah (mis., `1` piksel) | Tingkatkan `XDimension.Pixels` menjadi setidaknya `2` |
| Gambar terlalu besar | Kolom diatur terlalu tinggi untuk payload pendek | Kurangi `Pdf417.Columns` atau aktifkan `Truncate` |
| File PNG kosong | Folder output tidak ada atau tidak memiliki izin menulis | Pastikan direktori ada dan proses memiliki hak menulis |
| Pemindai melaporkan “data corrupted” | Truncate dinonaktifkan saat menggunakan banyak kolom | Aktifkan `Truncate` atau turunkan jumlah kolom |

## Memverifikasi hasil

Anda dapat memverifikasi barcode dengan aplikasi pemindai PDF417 apa pun (banyak aplikasi gratis Android/iOS tersedia). Buka `CompactPdf417.png` di aplikasi dan pastikan teks yang didekode cocok dengan payload asli (“Compact mode”). Jika teks berbeda, periksa kembali flag `Truncate` dan pengaturan kolom.

## Langkah selanjutnya

* **Integrate with ASP.NET Core** – Kembalikan PNG langsung dari aksi controller alih-alih menyimpannya ke disk.
* **Add human‑readable text** – Gunakan `barcodeGenerator.Parameters.Barcode.CodeTextParameters` untuk menampilkan string yang dienkode di bawah barcode.
* **Explore other symbologies** – Kelas `BarcodeGenerator` yang sama mendukung QR, Code128, DataMatrix, dan lainnya. Ganti `EncodeTypes` untuk mencobanya.

---

### Kesimpulan

Anda kini tahu cara **membuat barcode PDF417** di C# sambil **mengaktifkan mode kompak**, mengontrol **cara mengatur kolom**, dan menggunakan API **barcode generator C#** untuk **menghasilkan barcode** yang memenuhi batas ukuran dunia nyata. Terapkan langkah‑langkah ini pada proyek .NET apa pun yang membutuhkan barcode kompak dan ber‑densitas tinggi, serta perluas pola ini ke format barcode lain sesuai kebutuhan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Barcode PDF417 di C# – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Cara Mengatur Tingkat Kesalahan pada Barcode PDF417 – Panduan Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}