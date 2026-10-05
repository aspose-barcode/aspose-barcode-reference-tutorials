---
category: general
date: 2026-08-22
description: Pelajari cara membuat barcode PDF417 di C# dengan generator barcode,
  mengatur tata letak, dan menyimpan PNG. Termasuk kode lengkap serta tips untuk proyek
  generator barcode C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- barcode generator C#
- how to save PNG
- how to generate PDF417
language: id
lastmod: 2026-08-22
og_description: Buat kode batang PDF417 di C# menggunakan generator kode batang, sesuaikan
  tata letak, dan pelajari cara menyimpan PNG. Ikuti tutorial langkah demi langkah
  ini.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Buat kode batang PDF417 di C# – panduan lengkap untuk menghasilkan dan menyimpan
  PNG
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create PDF417 barcode in C# with a barcode generator,
    set layout, and save PNG. Includes full code and tips for barcode generator C#
    projects.
  headline: How to create PDF417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cara membuat barcode PDF417 di C# dan menyimpannya sebagai PNG
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 di C# dan menyimpannya sebagai PNG

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi C#, tutorial ini menunjukkan langkah‑langkah yang tepat. Anda akan melihat bagaimana library generator barcode C# dapat mengubah string apa pun menjadi gambar PDF417 yang dapat dipindai dan cara menyimpan file PNG tanpa alat tambahan.

Membuat barcode umum dalam bidang logistik, tiket, dan manajemen dokumen. Pada akhir panduan ini Anda akan memiliki program konsol yang dapat dijalankan dan menghasilkan file PNG bernama `Pdf417Layout.png` di folder yang Anda pilih.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- .NET 6.0 SDK atau yang lebih baru terpasang (kode ini juga berfungsi dengan .NET Framework 4.7+).
- Visual Studio 2022 atau editor apa pun yang dapat membangun proyek C#.
- Paket NuGet **Aspose.BarCode for .NET** (atau library generator barcode C# yang kompatibel).  
  Pasang dengan:

```bash
dotnet add package Aspose.BarCode
```

Tidak diperlukan library pemrosesan gambar tambahan karena generator dapat menulis PNG secara langsung.

## Langkah 1: Siapkan proyek konsol baru

Buat proyek konsol baru agar contoh tetap mandiri.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Folder `Pdf417Demo` kini berisi file `Program.cs` tempat kita akan menulis kode barcode.

## Langkah 2: Impor namespace barcode

Buka `Program.cs` dan tambahkan arahan `using` yang diperlukan di bagian atas:

```csharp
using Aspose.BarCode.Generation;
```

Namespace ini memberi Anda akses ke `BarcodeGenerator`, `EncodeTypes`, dan enum format gambar yang diperlukan untuk **cara menyimpan PNG**.

## Langkah 3: Buat generator barcode PDF417

Inti dari **cara menghasilkan PDF417** adalah kelas `BarcodeGenerator`. Berikan tipe enkode `EncodeTypes.Pdf417` dan teks yang ingin Anda enkode.

```csharp
// Step 3: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

`generator` kini menyimpan semua pengaturan untuk barcode. Tata letak default berfungsi, tetapi kita akan menyesuaikannya pada langkah berikutnya.

## Langkah 4: Tentukan tata letak barcode (kolom dan baris)

PDF417 memungkinkan Anda mengontrol jumlah kolom (2‑30) dan baris (1‑90). Menyesuaikan nilai‑nilai ini dapat meningkatkan keterbacaan untuk pemindai tertentu.

```csharp
// Step 4a: Set the number of columns (2‑30 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Step 4b: Set the number of rows (1‑90 allowed)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

> **Pro tip:** Jika Anda tidak menyertakan pengaturan ini, library akan memilih nilai optimal secara otomatis. Namun, menetapkan kolom dan baris memberikan dimensi gambar yang dapat diprediksi, yang berguna saat Anda menyematkan PNG ke dalam PDF atau tata letak UI.

## Langkah 5: Simpan barcode yang dihasilkan sebagai gambar PNG

Sekarang jawab **cara menyimpan PNG** dengan memanggil `Save`. Metode ini menerima jalur target dan enum format gambar.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Layout.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
```

File `Pdf417Layout.png` akan muncul di folder `bin/Debug/net6.0` proyek setelah Anda menjalankan program.

## Contoh lengkap yang dapat dijalankan

Berikut adalah file `Program.cs` lengkap. Salin ke dalam proyek yang dibuat pada **Langkah 1** dan jalankan `dotnet run`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 2️⃣ Define the barcode layout – set columns (2‑30) and rows (1‑90)
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // 9 rows

            // 3️⃣ Choose the output path and save as PNG
            string outputPath = Path.Combine(
                Environment.CurrentDirectory,
                "Pdf417Layout.png");

            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created and saved as PNG at:");
            Console.WriteLine(outputPath);
        }
    }
}
```

### Output yang diharapkan

Saat Anda menjalankan program, konsol akan mencetak jalur absolut ke file PNG, dan file tersebut berisi barcode PDF417 yang jelas dan mirip dengan gambar di bawah ini.

![contoh pembuatan barcode PDF417](image-placeholder.png "Barcode PDF417 disimpan sebagai PNG")

Anda dapat memindai PNG dengan pemindai yang kompatibel PDF417 apa pun (aplikasi seluler, pembaca perangkat keras) untuk memverifikasi bahwa teks yang dienkode adalah `"Sample"`.

## Menangani kasus tepi dan jebakan umum

| Situasi | Hal yang perlu diperhatikan | Solusi yang disarankan |
|-----------|-------------------|-----------------|
| **Nilai kolom/baris tidak valid** | Nilai di luar rentang 2‑30 (kolom) atau 1‑90 (baris) menyebabkan `ArgumentException`. | Validasi input pengguna sebelum menetapkan, atau biarkan library memilih nilai default. |
| **String input besar** | PDF417 dapat mengenkode hingga 1.850 karakter, tetapi string yang sangat panjang meningkatkan jumlah baris secara dramatis. | Bagi data menjadi beberapa barcode atau gunakan tingkat koreksi kesalahan yang lebih tinggi jika diperlukan. |
| **Izin sistem file** | Menyimpan ke folder read‑only akan memunculkan `UnauthorizedAccessException`. | Tulis ke `Environment.CurrentDirectory` atau jalur yang dapat ditulisi pengguna, dan tangani pengecualian dengan try/catch. |
| **Paket NuGet tidak ada** | Kompilasi gagal dengan “type or namespace name could not be found”. | Pastikan `Aspose.BarCode` terpasang (`dotnet add package Aspose.BarCode`). |

## Memperluas contoh

Setelah Anda mengetahui **cara membuat barcode PDF417** dan **cara menyimpan PNG**, Anda dapat menjelajahi topik terkait berikut:

- **Barcode generator C#**: Ubah `EncodeTypes` menjadi `Code128`, `QR`, atau simbol lainnya.
- **Warna kustom**: Gunakan `generator.Parameters.Barcode.ForegroundColor` dan `BackgroundColor` untuk menyesuaikan dengan identitas merek.
- **Menyematkan ke PDF**: Gabungkan PNG dengan library PDF (misalnya iText7) untuk membuat dokumen yang dapat dicetak.
- **Data dinamis**: Ambil teks dari basis data atau input pengguna untuk menghasilkan barcode secara otomatis.

## Kesimpulan

Anda kini memiliki solusi lengkap dan siap produksi untuk **membuat barcode PDF417** di C# dan menyimpan hasilnya sebagai file PNG. Tutorial ini mencakup setiap langkah mulai dari penyiapan proyek hingga penyesuaian tata letak, serta menyoroti cara menghindari kesalahan umum saat menggunakan library generator barcode C#.  

Silakan bereksperimen dengan pengaturan kolom/baris, warna, atau bahkan format barcode lainnya. Jika Anda menemui masalah, tinjau kembali bagian **cara menghasilkan PDF417** atau jelajahi dokumentasi library untuk fitur lanjutan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Barcode PDF417 – Pengkodean PDF417 Kompak](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Membuat Zona Tenang Barcode untuk ITF-14 Menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}