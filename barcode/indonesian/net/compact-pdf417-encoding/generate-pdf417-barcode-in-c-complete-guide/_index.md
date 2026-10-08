---
category: general
date: 2026-09-18
description: Pelajari cara membuat gambar barcode PDF417 di C# dengan cepat dan mengatur
  kolom untuk barcode yang kompak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Pelajari cara membuat gambar barcode PDF417 di C# dengan cepat dan
  mengatur kolom untuk barcode yang kompak. Aspose.BarCode memudahkan prosesnya.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Buat gambar barcode PDF417 – panduan langkah demi langkah C#
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Cara membuat gambar barcode PDF417 di C# – panduan lengkap
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode PDF417 di C# – panduan lengkap

Jika Anda perlu **membuat gambar barcode PDF417** dalam aplikasi .NET, Anda berada di tempat yang tepat. Baik Anda mencetak tag boarding‑pass, mengkodekan data inventaris, atau membangun sistem tiket seluler, PDF417 menyediakan barcode dua‑dimensi berkapasitas tinggi. Panduan ini menunjukkan cara menghasilkan gambar dengan Aspose.BarCode dan cara mengatur kolom sehingga barcode tetap sekecil mungkin.

## Jawaban Cepat
- **Library mana yang membuat barcode PDF417?** Aspose.BarCode untuk .NET.
- **Berapa baris kode yang diperlukan?** Sekitar 10 baris dalam aplikasi console.
- **Apakah saya dapat mengontrol lebar barcode?** Ya, dengan mengatur properti `Columns`.
- **Format gambar apa yang direkomendasikan?** PNG untuk kualitas loss‑less.
- **Apakah .NET 6 didukung?** Sepenuhnya – perpustakaan bekerja dengan .NET 6, .NET 7, dan versi selanjutnya.

## Apa itu gambar barcode PDF417?
Gambar barcode PDF417 adalah matriks dua‑dimensi yang menyimpan hingga 1 700 karakter per baris, menggunakan baris dan kolom untuk mengemas data secara padat. Aspose.BarCode merender matriks ini ke dalam format gambar standar seperti PNG, JPEG, atau BMP. Gambar ini dapat disimpan dalam berbagai format dan cocok untuk pencetakan pada label, tiket, atau layar seluler.

## Mengapa mengatur kolom untuk gambar barcode PDF417 yang kompak?
Mengatur kolom memungkinkan Anda memperkecil lebar barcode, yang penting untuk label sempit atau elemen UI dengan ruang terbatas. Aspose.BarCode mendukung 1‑30 kolom, dan memilih jumlah yang lebih rendah mengurangi lebar gambar secara keseluruhan hingga 40 % sambil mempertahankan integritas data. Penyesuaian ini membantu menempatkan barcode pada tag kecil tanpa mengorbankan keterbacaan.

## Cara membuat gambar barcode PDF417 di C#?
Muat pustaka `Aspose.BarCode`, konfigurasikan `BarcodeGenerator` dengan `EncodeTypes.Pdf417`, atur `Columns` dan `Truncate`, lalu simpan hasilnya sebagai PNG. Seluruh proses memerlukan dua pemanggilan metode dan menghasilkan file gambar siap pakai. Anda juga dapat menyesuaikan dimensi, warna, dan menambahkan teks yang dapat dibaca manusia untuk memenuhi kebutuhan aplikasi Anda.

### Prasyarat
- .NET 6+ SDK (atau yang lebih baru)
- Visual Studio 2022 atau editor C# apa pun
- Paket NuGet `Aspose.BarCode`

### Implementasi Langkah‑per‑Langkah

## Langkah 1: Instal paket NuGet Aspose.BarCode
`Aspose.BarCode` adalah pustaka .NET untuk menghasilkan dan membaca berbagai simbologi barcode.

```bash
dotnet add package Aspose.BarCode
```

Baris tunggal itu mengimpor semua tipe yang Anda perlukan, termasuk `BarcodeGenerator`, `EncodeTypes`, dan enum `BarCodeImageFormat`.

> **Pro tip:** Jika Anda menargetkan .NET Framework alih-alih .NET 6, gunakan perintah PowerShell klasik `Install-Package Aspose.BarCode` di dalam Package Manager Console.

## Langkah 2: Buat aplikasi console minimal
`BarcodeGenerator` membuat gambar barcode berdasarkan pengaturan yang ditentukan. `EncodeTypes` mengenumerasi simbologi barcode yang didukung. `BarCodeImageFormat` mengenumerasi format gambar.

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
- `EncodeTypes.Pdf417` memberi tahu pustaka bahwa kami menginginkan barcode PDF417, bukan QR atau Code128.  
- `XDimension.Pixels` mengontrol resolusi setiap modul hitam atau putih yang sangat kecil.  
- Blok **cara mengatur kolom** secara langsung memengaruhi bentuk **gambar barcode PDF417**.  
- `Truncate = true` menghapus baris kosong yang tidak diperlukan, memberikan tampilan “kompak” yang disukai banyak pemindai.

## Langkah 3: Selami lebih dalam – memahami kolom dan pemotongan

### Cara mengatur kolom
PDF417 menyusun data dalam matriks *baris* × *kolom*. Pustaka secara default menggunakan 5 kolom, yang cocok untuk kebanyakan kasus. Namun, Anda mungkin memerlukan barcode yang lebih sempit untuk menyesuaikan label atau yang lebih lebar untuk meningkatkan keandalan pemindaian. Properti:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

menerima nilai dari **1** hingga **30** (batas tepatnya tergantung pada panjang data). Berikut lembar cheat cepat:

| Kolom | Lebar perkiraan (mm) | Kapan digunakan |
|-------|----------------------|-----------------|
| 1‑3   | Sangat sempit        | Label kecil, ruang terbatas |
| 4‑6   | Standar              | Kebanyakan struk, tiket |
| 7‑10  | Lebih lebar          | Data berkapasitas tinggi, keterbacaan lebih baik |

### Truncate (mode kompak)
Mengatur `Truncate = true` memberi tahu encoder untuk memotong baris kosong yang tidak diperlukan di bagian bawah. Hasilnya adalah **gambar barcode PDF417 yang kompak** yang menempati area sekecil mungkin sambil tetap berisi semua data. Jika Anda pernah mendapatkan kesalahan “barcode terlalu besar untuk label”, aktifkan flag ini.

## Langkah 4: Jalankan aplikasi dan verifikasi output
Compile and execute:

```bash
dotnet run
```

Anda harus melihat pesan console yang mengonfirmasi lokasi penyimpanan. Buka folder tersebut dan buka `CompactPdf417.png`. Gambar akan terlihat seperti ini:

![Gambar barcode PDF417 yang dihasilkan](./CompactPdf417.png "Gambar barcode PDF417 yang dihasilkan – PNG kompak yang dibuat oleh Aspose.BarCode")

[Generated PDF417 barcode image](./CompactPdf417.png "Generated PDF417 barcode image – compact PNG created by Aspose.BarCode")

*Teks alt gambar:* **Gambar barcode PDF417 yang dihasilkan** – file PNG kompak yang dihasilkan oleh kode tutorial.

Jika pemindai Anda dapat membacanya, selamat—Anda telah berhasil **menghasilkan barcode PDF417** dan menguasai **cara mengatur kolom** untuk **gambar barcode PDF417** yang rapi.

## Langkah 5: Kesalahan umum & cara memperbaikinya

| Gejala | Penyebab kemungkinan | Perbaikan cepat |
|--------|----------------------|-----------------|
| Barcode tampak buram | `XDimension.Pixels` terlalu rendah (mis., 1) | Naikkan ke 2‑3 piksel untuk gambar yang lebih jelas. |
| Pemindai tidak dapat membaca | Terlalu banyak kolom untuk data yang diberikan | Kurangi `Columns` atau aktifkan `Truncate`. |
| Format file salah | Disimpan dengan `BarCodeImageFormat.Jpeg` secara tidak sengaja | Gunakan `BarCodeImageFormat.Png` untuk hasil lossless. |
| Pengecualian `ArgumentOutOfRangeException` | Jumlah kolom melebihi rentang yang diizinkan | Pertahankan kolom antara 1‑30 dan pastikan data cocok. |

## Langkah 6: Melangkah lebih jauh – menyesuaikan warna dan menambahkan teks

Jika Anda ingin membuat barcode sesuai dengan palet merek, Anda dapat menyesuaikan warna latar depan dan latar belakang:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Atau menambahkan teks yang dapat dibaca manusia di bawah barcode:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Penambahan ini bersifat opsional, tetapi mereka menunjukkan betapa fleksibelnya alur kerja **menghasilkan barcode PDF417**.

## Kesimpulan
Kami telah melalui contoh lengkap end‑to‑end yang **menghasilkan barcode PDF417** menggunakan Aspose.BarCode, menjelaskan **cara mengatur kolom** untuk mengontrol dimensi barcode, dan menyimpan hasilnya sebagai **gambar barcode PDF417** yang tajam dalam format PNG. Kode ini mandiri, bekerja dengan .NET 6+, dan dapat dimasukkan ke dalam proyek apa pun dengan sedikit usaha.

Apa selanjutnya? Coba mengkodekan payload yang lebih besar (mis., string JSON), bereksperimen dengan format gambar yang berbeda, atau mengintegrasikan generator ke dalam API web yang menyajikan barcode sesuai permintaan. Tidak ada batasan, dan Anda kini memiliki fondasi yang kuat untuk dibangun.

Selamat coding, dan semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang harus Anda pelajari selanjutnya?
Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Gambar Barcode di Java dengan Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Menghasilkan Barcode Java – Atur Resolusi Gambar dengan Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan PNG yang dihasilkan di halaman web tanpa konversi tambahan?**  
A: Ya, PNG didukung secara native oleh semua browser modern, sehingga Anda dapat menyematkan file langsung dengan tag `<img>`.

**Q: Berapa banyak karakter yang dapat ditampung barcode PDF417?**  
A: Hingga 1 700 karakter per baris dan hingga 30 baris, memberikan maksimum teoretis sekitar 51 000 karakter, meskipun batas praktis tergantung pada kemampuan pemindai.

**Q: Apakah Aspose.BarCode memerlukan lisensi untuk pengembangan?**  
A: Lisensi evaluasi gratis tersedia untuk pengujian; lisensi komersial diperlukan untuk penyebaran produksi.

**Q: Apakah memungkinkan menghasilkan barcode PDF417 dalam layanan latar belakang?**  
A: Tentu saja. Pustaka ini thread‑safe untuk operasi baca‑saja, sehingga Anda dapat menghasilkan barcode di ASP.NET Core atau layanan Windows tanpa interaksi UI.

**Q: Format gambar apa selain PNG yang didukung?**  
A: BMP, JPEG, GIF, TIFF, dan SVG semuanya didukung melalui enumerasi `BarCodeImageFormat`.

---

**Terakhir diperbarui:** 2026-09-18  
**Diuji dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  






```bash
dotnet add package Aspose.BarCode
```

## Tutorial Terkait

- [Buat Barcode Pdf417 dengan Panduan Lengkap Aspose](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Cara Menghasilkan Gambar Barcode Pdf417 di C dengan Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Buat Barcode Pdf417 di C Panduan Langkah demi Langkah](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}