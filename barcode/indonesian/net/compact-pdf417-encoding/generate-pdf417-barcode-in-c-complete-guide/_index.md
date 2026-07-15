---
category: general
date: 2026-07-15
description: Hasilkan kode batang PDF417 dengan cepat dan pelajari cara mengatur kolom
  untuk gambar kode batang PDF417 yang kompak di C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set columns
- pdf417 barcode image
- Aspose.BarCode PDF417
- C# barcode generation
- compact PDF417
language: id
lastmod: 2026-07-15
og_description: Hasilkan kode batang PDF417 dengan Aspose.BarCode dan pelajari cara
  mengatur kolom untuk membuat gambar kode batang PDF417 yang kompak.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Menghasilkan Barcode PDF417 di C# – Panduan Langkah demi Langkah
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly and learn how to set columns for a
    compact PDF417 barcode image in C#.
  headline: Generate PDF417 Barcode in C# – Complete Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Menghasilkan Kode Bar PDF417 di C# – Panduan Lengkap
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan Barcode PDF417 di C# – Panduan Lengkap

Pernah perlu **menghasilkan barcode PDF417** dalam proyek .NET tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian. Dalam banyak aplikasi perusahaan—seperti pencetak boarding‑pass, label inventaris, atau tiket seluler—PDF417 adalah pahlawan yang memuat banyak data dalam jejak visual yang kecil.

Intinya: pustaka Aspose.BarCode membuat seluruh proses hampir tanpa rasa sakit, dan Anda bahkan dapat mengontrol **cara mengatur kolom** sehingga barcode menjadi sekecil mungkin. Pada akhir tutorial ini Anda akan memiliki gambar PNG **barcode PDF417** yang siap pakai dan dapat ditempatkan ke UI mana pun, email, atau pekerjaan cetak.

## Apa yang Akan Anda Dapatkan

- Aplikasi konsol C# yang berfungsi penuh untuk membuat barcode PDF417.  
- Pemahaman jelas tentang *X‑Dimension* (ukuran modul) dan mengapa itu penting.  
- Instruksi langkah‑demi‑langkah tentang **cara mengatur kolom** untuk barcode yang lebih rapat.  
- File `PNG` yang disimpan yang dapat Anda buka langsung untuk memverifikasi hasilnya.  
- Tips memecahkan masalah umum (mis., barcode tidak terbaca, format gambar salah).

> **Prasyarat** – .NET 6+ SDK, Visual Studio 2022 (atau editor pilihan Anda), dan referensi NuGet ke `Aspose.BarCode`. Tidak ada yang lain.

---

## Langkah 1: Instal Paket NuGet Aspose.BarCode

Sebelum kita dapat *menghasilkan barcode PDF417*, pustaka harus ada di proyek.

```bash
dotnet add package Aspose.BarCode
```

Baris tunggal itu menarik semua tipe yang Anda perlukan, termasuk `BarcodeGenerator`, `EncodeTypes`, dan enum `BarCodeImageFormat`.

> **Tips pro:** Jika Anda menargetkan .NET Framework alih‑alih .NET 6, gunakan perintah PowerShell klasik `Install-Package Aspose.BarCode` di dalam Package Manager Console.

---

## Langkah 2: Buat Aplikasi Konsol Minimal

Mari susun program kecil yang hanya menghasilkan barcode. Buka folder baru, jalankan `dotnet new console`, lalu ganti `Program.cs` yang dihasilkan secara otomatis dengan kode di bawah ini.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Mengapa ini penting:**  
- `EncodeTypes.Pdf417` memberi tahu pustaka bahwa kita menginginkan barcode PDF417, bukan QR atau Code128.  
- `XDimension.Pixels` mengontrol resolusi setiap modul hitam atau putih yang sangat kecil.  
- Blok **cara mengatur kolom** secara langsung memengaruhi bentuk **gambar barcode PDF417**.  
- `Truncate = true` menghilangkan baris kosong yang tidak diperlukan, memberi Anda tampilan “kompak” yang disukai banyak pemindai.

---

## Langkah 3: Selami Lebih Dalam – Memahami Kolom dan Truncation

### Cara Mengatur Kolom

PDF417 menyusun data dalam matriks *baris* × *kolom*. Pustaka secara default menggunakan 5 kolom, yang cocok untuk kebanyakan kasus. Namun, Anda mungkin memerlukan barcode yang lebih sempit untuk menyesuaikan label atau yang lebih lebar untuk meningkatkan keandalan pemindaian. Properti:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

menerima nilai dari **1** hingga **30** (batas pasti tergantung pada panjang data). Berikut cheat sheet singkat:

| Kolom | Lebar Perkiraan (mm) | Kapan Digunakan |
|------|----------------------|-----------------|
| 1‑3  | Sangat sempit        | Label kecil, ruang terbatas |
| 4‑6  | Standar              | Sebagian besar struk, tiket |
| 7‑10 | Lebih lebar          | Data kepadatan tinggi, keterbacaan lebih baik |

### Truncate (Mode Kompak)

Menetapkan `Truncate = true` memberi tahu encoder untuk memotong baris kosong yang tidak diperlukan di bagian bawah. Hasilnya adalah **gambar barcode PDF417 kompak** yang menempati area sekecil mungkin sambil tetap berisi semua data. Jika Anda pernah mendapatkan error “barcode terlalu besar untuk label”, alihkan flag ini.

---

## Langkah 4: Jalankan Aplikasi dan Verifikasi Output

Kompilasi dan eksekusi:

```bash
dotnet run
```

Anda akan melihat pesan konsol yang mengonfirmasi lokasi penyimpanan. Buka folder tersebut dan buka `CompactPdf417.png`. Gambarnya akan terlihat seperti ini:

![Generated PDF417 barcode image](./CompactPdf417.png "Generated PDF417 barcode image – compact PNG created by Aspose.BarCode")

*Teks alt gambar:* **Generated PDF417 barcode image** – file PNG kompak yang dihasilkan oleh kode tutorial.

Jika pemindai Anda dapat membacanya, selamat—Anda telah berhasil **menghasilkan barcode PDF417** dan menguasai **cara mengatur kolom** untuk **gambar barcode PDF417** yang rapi.

---

## Langkah 5: Masalah Umum & Cara Memperbaikinya

| Gejala | Penyebab Kemungkinan | Perbaikan Cepat |
|--------|----------------------|-----------------|
| Barcode terlihat buram | `XDimension.Pixels` terlalu rendah (mis., 1) | Tingkatkan menjadi 2‑3 piksel untuk gambar yang lebih jelas. |
| Pemindai tidak dapat membaca | Terlalu banyak kolom untuk data yang diberikan | Kurangi `Columns` atau aktifkan `Truncate`. |
| Format file salah | Disimpan dengan `BarCodeImageFormat.Jpeg` secara tidak sengaja | Gunakan `BarCodeImageFormat.Png` untuk hasil lossless. |
| Exception `ArgumentOutOfRangeException` | Jumlah kolom melebihi rentang yang diizinkan | Pertahankan kolom antara 1‑30 dan pastikan data cocok. |

---

## Langkah 6: Lebih Lanjut – Menyesuaikan Warna dan Menambahkan Teks

Jika Anda ingin barcode cocok dengan palet merek, Anda dapat menyesuaikan warna latar depan dan latar belakang:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Atau menambahkan teks yang dapat dibaca manusia di bawah barcode:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Penambahan ini bersifat opsional, tetapi menunjukkan seberapa fleksibel alur kerja **menghasilkan barcode PDF417** dapat menjadi.

---

## Kesimpulan

Kami telah menelusuri contoh lengkap end‑to‑end yang **menghasilkan barcode PDF417** menggunakan Aspose.BarCode, menjelaskan **cara mengatur kolom** untuk mengontrol dimensi barcode, dan menyimpan hasilnya sebagai gambar **barcode PDF417** yang tajam dalam format PNG. Kode ini berdiri sendiri, bekerja dengan .NET 6+, dan dapat disisipkan ke proyek apa pun dengan sedikit usaha.

Apa selanjutnya? Cobalah mengkodekan payload yang lebih besar (mis., payload JSON), bereksperimen dengan format gambar lain, atau integrasikan generator ke dalam API web yang menyajikan barcode sesuai permintaan. Langit adalah batasnya, dan Anda kini memiliki fondasi yang kuat untuk membangunnya.

Selamat coding, dan semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}