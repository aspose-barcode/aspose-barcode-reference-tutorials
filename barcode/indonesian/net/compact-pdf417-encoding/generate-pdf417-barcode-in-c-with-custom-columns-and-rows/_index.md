---
category: general
date: 2026-10-21
description: Hasilkan barcode PDF417 dengan cepat di C#. Pelajari cara menghasilkan
  barcode PDF417 dengan tata letak khusus, kolom, baris, dan output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: id
lastmod: 2026-10-21
og_description: Buat barcode pdf417 di C#. Ikuti tutorial ini untuk mempelajari cara
  menghasilkan barcode pdf417 dengan kolom, baris, dan output PNG yang dapat disesuaikan.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Buat barcode pdf417 di C# – panduan lengkap langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Hasilkan barcode pdf417 di C# dengan kolom dan baris khusus
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode pdf417 di C# – panduan pemrograman lengkap

Jika Anda perlu **generate pdf417 barcode** dalam aplikasi .NET, panduan ini menunjukkan cara melakukannya dengan beberapa baris kode. Anda akan melihat contoh praktis yang mengonfigurasi jumlah kolom dan baris, lalu menyimpan hasilnya sebagai gambar PNG. Pendekatan yang sama berlaku untuk teks apa pun yang ingin Anda enkode, sehingga Anda dapat menyesuaikannya untuk faktur, tiket, atau kartu identitas.

Membuat **pdf417 barcode** sering terasa seperti tugas terpisah dari sisa basis kode Anda. Pada akhir tutorial ini Anda akan memahami mengapa parameter tata letak penting, cara mengontrol kualitas gambar, dan panggilan pustaka mana yang diperlukan untuk **generate pdf417 barcode** secara andal.

## Apa yang Anda butuhkan

* .NET 6.0 SDK atau yang lebih baru terpasang  
* IDE yang kompatibel dengan C# (Visual Studio, VS Code, Rider, dll.)  
* Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan barcode yang kompatibel)  

Anda dapat menambahkan pustaka dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Pustaka ini menyediakan kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 1: Buat instance generator barcode

Baris pertama membuat objek yang mengetahui cara **generate pdf417 barcode**. Anda harus menentukan tipe enkoding (`EncodeTypes.Pdf417`) dan teks yang ingin Anda enkode.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Mengapa langkah ini penting* – `BarcodeGenerator` mengenkapsulasi semua pengaturan untuk barcode. Menginstansiasinya dengan `EncodeTypes` yang tepat memberi tahu mesin untuk menggunakan simbol PDF417 alih-alih QR, Code128, atau format lainnya.

## Langkah 2: Konfigurasikan tata letak PDF417

PDF417 memungkinkan Anda mengontrol jumlah kolom dan baris, yang secara langsung memengaruhi ukuran dan kepadatan barcode. Menyesuaikan nilai-nilai ini adalah inti dari **how to generate pdf417 barcode** dengan tata letak khusus.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Mengapa Anda mungkin mengubah nilai-nilai ini* – Lebih banyak kolom mengurangi tinggi barcode, sementara lebih banyak baris meningkatkan lebar. Pilih nilai yang sesuai dengan perangkat pemindai target dan area cetak yang tersedia.

> **Pro tip:** Jika Anda mengabaikan baris, pustaka secara otomatis menghitung jumlah optimal berdasarkan panjang data. Menetapkan baris secara eksplisit berguna ketika Anda memerlukan ukuran gambar tetap untuk tata letak UI.

## Langkah 3: Pilih format gambar dan simpan file

Setelah mengonfigurasi tata letak, Anda dapat merender barcode menjadi gambar. Contoh di bawah menyimpan barcode sebagai file PNG, tetapi Anda juga dapat memilih JPEG, BMP, atau TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Saat kode dijalankan, `CustomLayout.png` akan berisi **pdf417 barcode** yang jelas dan sesuai dengan pengaturan kolom/baris yang Anda berikan.

### Output yang diharapkan

Membuka `CustomLayout.png` menampilkan barcode persegi panjang dengan empat kolom data dan sembilan baris. Memindai gambar dengan pembaca PDF417 apa pun mengembalikan teks asli **“Sample Text”**.

![Contoh barcode PDF417 yang dihasilkan](generated-pdf417.png){: .center-image alt="Barcode pdf417 yang dihasilkan disimpan sebagai file PNG"}

## Langkah 4: Contoh lengkap yang dapat dijalankan

Berikut ini adalah aplikasi konsol mandiri yang menyatukan semua bagian. Salin kode ke dalam proyek `.csproj` baru dan jalankan—tidak diperlukan file tambahan.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Menjalankan program mencetak baris konfirmasi dan membuat file PNG di dalam subfolder `output`. Gambar dapat disisipkan dalam laporan, dicetak pada label, atau dikirim ke perangkat seluler untuk dipindai.

## Variasi umum dan kasus tepi

| Skenario | Apa yang diubah | Mengapa penting |
|----------|----------------|----------------|
| **Enkode string panjang** | Tingkatkan `Rows` atau biarkan pustaka menghitung otomatis dengan menghilangkan penetapan `Rows` | PDF417 dapat menampung hingga 1.850 karakter; baris yang tidak cukup menyebabkan pemotongan |
| **Kualitas visual lebih tinggi** | Setel `generator.Parameters.ImageResolution` ke 600 DPI | Berguna untuk mencetak pada printer beresolusi tinggi |
| **Format gambar berbeda** | Ganti `BarCodeImageFormat.Png` dengan `Jpeg` atau `Tiff` | JPEG mengurangi ukuran file; TIFF mempertahankan data lossless untuk arsip |
| **Tambahkan zona tenang** | `generator.Parameters.Barcode.XDimension = 2;` (atau sesuaikan `Margins`) | Zona tenang meningkatkan keandalan pemindai di lingkungan berisik |
| **Teks dinamis dari input pengguna** | Ganti string yang di‑hard‑code dengan `Console.ReadLine()` | Memungkinkan pembuatan pada waktu berjalan berdasarkan data pengguna |

### Cara menghasilkan pdf417 barcode dalam API web

Jika Anda perlu mengekspos pembuatan barcode melalui endpoint ASP.NET Core, kembalikan gambar sebagai array byte:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Potongan kode ini menjawab **how to generate pdf417 barcode** secara langsung tanpa menulis ke disk, yang ideal untuk mikroservis atau backend seluler.

## Menguji barcode yang dihasilkan

Untuk memverifikasi bahwa barcode dibuat dengan benar:

1. Buka file PNG di penampil gambar apa pun.  
2. Gunakan aplikasi pemindai PDF417 gratis (mis., ZXing, PDF417 Decoder) untuk memindai gambar.  
3. Pastikan teks yang terdekripsi cocok dengan input asli.

Jika pemindai melaporkan kesalahan, periksa kembali nilai kolom/baris dan pastikan resolusi gambar cukup tinggi untuk perangkat Anda.

## Kesimpulan

Anda kini tahu cara **generate pdf417 barcode** di C# dengan kontrol penuh atas kolom, baris, dan format output. Contoh lengkap menunjukkan seluruh alur kerja—dari membuat `BarcodeGenerator` hingga menyimpan file PNG—sehingga Anda dapat mengintegrasikan pembuatan barcode ke dalam proyek .NET apa pun.

Selanjutnya, jelajahi topik terkait seperti optimasi **pdf417 barcode layout**, menyisipkan barcode dalam laporan PDF, atau mendekode barcode pada perangkat seluler. Menyesuaikan tingkat koreksi kesalahan dan bereksperimen dengan resolusi gambar yang berbeda akan membantu Anda menyempurnakan solusi untuk kasus penggunaan spesifik Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menghasilkan PDF417 barcode di C# – panduan langkah demi langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara Menyimpan Barcode di C# – Menghasilkan Barcode PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Cara Menghasilkan PDF417 Barcode – Panduan Pemrograman Lengkap](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}