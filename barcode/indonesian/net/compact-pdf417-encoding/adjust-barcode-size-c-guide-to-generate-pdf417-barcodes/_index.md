---
category: general
date: 2026-07-24
description: Sesuaikan ukuran barcode dengan mudah menggunakan C# dan temukan cara
  menghasilkan barcode PDF417 menggunakan Aspose.BarCode untuk gambar yang tajam dan
  dapat diskalakan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode size
- how to generate pdf417
- Aspose.BarCode MicroPdf417
- C# barcode generation
- barcode image resolution
language: id
lastmod: 2026-07-24
og_description: Sesuaikan ukuran barcode dengan contoh C# sederhana dan pelajari cara
  menghasilkan barcode PDF417 menggunakan Aspose.BarCode. Ikuti panduan langkah demi
  langkah untuk hasil yang sempurna.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with adjusted size in
  C#
og_title: Sesuaikan Ukuran Kode Batang – Panduan C# untuk Menghasilkan Kode Batang
  PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: adjust barcode size easily with C# and discover how to generate PDF417
    barcodes using Aspose.BarCode for crisp, scalable images.
  headline: adjust barcode size – C# guide to generate PDF417 barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- PDF417
title: Sesuaikan ukuran barcode – Panduan C# untuk menghasilkan barcode PDF417
url: /id/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# sesuaikan ukuran barcode – Tutorial C# Lengkap untuk Menghasilkan Barcode PDF417

Pernah mencoba **menyesuaikan ukuran barcode** dan berakhir dengan gambar yang buram atau tidak dapat dibaca? Anda tidak sendirian. Dalam banyak proyek—baik itu sistem tiket, printer label gudang, atau aplikasi seluler—mendapatkan dimensi yang tepat untuk barcode PDF417 dapat menentukan keberhasilan pengalaman pengguna.

Berita baiknya? Dengan beberapa baris C# dan pustaka Aspose.BarCode, Anda dapat **menyesuaikan ukuran barcode** secara tepat dan juga belajar **cara menghasilkan PDF417** barcode yang tajam di layar mana pun. Di bawah ini Anda akan menemukan contoh lengkap yang dapat dijalankan, serta penjelasan mengapa setiap pengaturan penting.

## Prasyarat — Apa yang Anda Butuhkan

Sebelum kita mulai, pastikan Anda memiliki:

| Persyaratan | Mengapa penting |
|-------------|----------------|
| .NET 6.0 atau lebih baru (atau .NET Framework 4.7+) | Aspose.BarCode mendukung keduanya, tetapi runtime yang lebih baru memberikan kinerja yang lebih baik. |
| Visual Studio 2022 (atau IDE lain yang Anda sukai) | IDE yang baik membantu Anda melihat kesalahan kompilasi secara instan. |
| Paket NuGet `Aspose.BarCode` (versi terbaru) | Ini adalah mesin yang sebenarnya membuat barcode MicroPdf417. |
| Izin menulis ke folder tempat PNG akan disimpan | Metode `Save` akan melempar pengecualian jika tidak dapat menulis file. |

Anda dapat menginstal paket tersebut dari konsol NuGet:

```powershell
Install-Package Aspose.BarCode
```

Itu saja—tidak ada DLL tambahan, tidak ada dependensi native. Setelah paket terpasang, Anda siap untuk **menyesuaikan ukuran barcode** dan mulai menghasilkan gambar PDF417.

## Langkah 1: Buat Generator MicroPdf417 (cara menghasilkan pdf417)

Hal pertama yang Anda lakukan ketika ingin **cara menghasilkan pdf417** adalah menginstansiasi `BarcodeGenerator`. Konstruktornya menerima dua argumen: tipe barcode dan teks yang ingin dienkode. Dalam kasus ini kita menggunakan `EncodeTypes.MicroPdf417`, yang merupakan varian kompak dari PDF417 klasik.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and sample text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,               // Barcode type
    "Åspóse.Barcóde©");                    // Text to encode (Unicode supported)
```

> **Tip profesional:** Teks dapat berisi karakter Unicode apa pun, tetapi ingat kapasitas data maksimum MicroPdf417—sekitar 150 karakter. Melebihi batas tersebut akan otomatis beralih ke PDF417 ukuran penuh, yang mengubah dimensi.

## Langkah 2: Sesuaikan X‑Dimension (cara menyesuaikan ukuran barcode)

**X‑dimension** menentukan lebar satu modul (garis hitam atau putih terkecil). Secara default Aspose menggunakan 3 piksel, yang sering terlalu kasar untuk cetakan resolusi tinggi. Mengaturnya menjadi `2` piksel memberikan grid yang lebih halus tanpa mengorbankan keterbacaan.

```csharp
// Step 2: Set module width to 2 pixels for a tighter, sharper barcode
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Mengapa ini penting? X‑dimension yang lebih kecil menghasilkan DPI yang lebih tinggi ketika Anda mengekspor gambar, yang berarti tepi yang lebih tajam di layar atau printer. Sebaliknya, jika Anda membutuhkan barcode yang lebih besar untuk pemindai yang jauh, naikkan nilai menjadi `4` atau `5`.

## Langkah 3: Pilih Jumlah Kolom (cara menghasilkan pdf417)

MicroPdf417 memungkinkan Anda mengontrol tata letak melalui properti `Columns`. Lebih banyak kolom berarti barcode yang lebih lebar tetapi lebih pendek; lebih sedikit kolom membuatnya lebih tinggi dan lebih sempit. Untuk kebanyakan printer label, tata letak **4‑kolom** memberikan keseimbangan yang baik.

```csharp
// Step 3: Define a 4‑column layout to keep the barcode compact
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

Jika Anda penasaran **cara menghasilkan pdf417** dengan bentuk khusus, cukup ubah angka ini. Pustaka secara otomatis menghitung ulang jumlah baris agar sesuai dengan data, sehingga Anda tidak perlu menghitung baris secara manual.

## Langkah 4: Simpan Barcode sebagai PNG (cara menghasilkan pdf417)

Akhirnya, kita menulis gambar ke disk. PNG bersifat lossless, sehingga mempertahankan pola piksel yang baru saja Anda atur dengan cermat.

```csharp
using Aspose.BarCode;

// Step 4: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to: {outputPath}");
```

Saat Anda membuka `MicroPdf417.png`, Anda akan melihat barcode beresolusi tinggi yang bersih, sesuai dengan X‑dimension 2 piksel dan tata letak 4‑kolom yang Anda konfigurasikan. Sebagian besar pemindai modern akan membacanya secara instan, bahkan dari tangkapan layar.

![sesuaikan ukuran barcode – contoh barcode MicroPdf417](MicroPdf417.png "sesuaikan ukuran barcode – contoh barcode MicroPdf417")

*Deskripsi gambar (alt text):* **sesuaikan ukuran barcode – contoh barcode MicroPdf417 yang dihasilkan dengan C#**.

## Contoh Lengkap yang Berfungsi (Semua Langkah Digabung)

Berikut adalah program lengkap yang dapat Anda salin‑tempel ke proyek Console App baru. Program ini mencakup direktif `using`, penanganan kesalahan, dan komentar yang menjelaskan setiap baris.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the generator with MicroPdf417 and Unicode text
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417,
                    "Åspóse.Barcóde©");

                // 2️⃣ Adjust the X‑dimension for finer resolution (2 px)
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Set columns to 4 for a compact layout
                generator.Parameters.Barcode.Pdf417.Columns = 4;

                // 4️⃣ Choose where to save the PNG image
                string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
                string filePath = Path.Combine(desktop, "MicroPdf417.png");

                // 5️⃣ Save the image
                generator.Save(filePath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode generated and saved to: {filePath}");
            }
            catch (Exception ex)
            {
                // In production code you’d log this instead of writing to console
                Console.WriteLine($"❌ An error occurred: {ex.Message}");
            }
        }
    }
}
```

### Output yang Diharapkan

Menjalankan program akan mencetak sesuatu seperti:

```
✅ Barcode generated and saved to: C:\Users\YourName\Desktop\MicroPdf417.png
```

Membuka PNG akan menampilkan barcode MicroPdf417 yang tajam dengan dimensi tepat yang Anda tentukan. Pindai dengan pembaca PDF417 apa pun (aplikasi seluler, pemindai Zebra, dll.) dan Anda akan mendapatkan kembali string asli `"Åspóse.Barcóde©"`.

## Pertanyaan Umum & Kasus Tepi

| Pertanyaan | Jawaban |
|------------|---------|
| **Bagaimana jika saya membutuhkan gambar yang lebih besar?** | Tingkatkan `XDimension.Pixels` (misalnya menjadi `4`) atau ekspor sebagai format resolusi tinggi seperti `BarCodeImageFormat.Tiff`. |
| **Bisakah saya menghasilkan PDF417 ukuran penuh alih-alih MicroPdf417?** | Tentu—ganti saja `EncodeTypes.MicroPdf417` dengan `EncodeTypes.Pdf417`. Properti `Columns` dan `XDimension` tetap berlaku. |
| **Apakah dukungan Unicode dapat diandalkan?** | Ya. Aspose.BarCode mengkodekan karakter Unicode menggunakan UTF‑8 secara internal, tetapi ingat batas kapasitas data MicroPdf417. |
| **Bagaimana jika folder target tidak ada?** | Metode `Save` akan melempar `DirectoryNotFoundException`. Bungkus pemanggilan dalam blok `try/catch` (seperti yang ditunjukkan) atau buat folder dengan `Directory.CreateDirectory`. |
| **Apakah saya harus mengatur tinggi barcode secara manual?** | Tidak. Tinggi dihitung secara otomatis berdasarkan jumlah baris yang diperlukan untuk data dan jumlah kolom. |

## Tips untuk Barcode yang Sempurna

- **Tip profesional:** Saat mencetak pada label termal, atur DPI printer ke 300 dpi dan pertahankan `XDimension.Pixels` pada `2`. Ini menghasilkan lebar modul fisik sekitar ≈0,17 mm, yang disukai kebanyakan pemindai.
- **Waspadai:** Mengompresi PNG secara berlebihan (menggunakan pengaturan kualitas rendah) dapat membuat tepi menjadi buram, meniadakan tujuan X‑dimension yang halus.
- **Kesalahan umum:** Lupa menambahkan `using Aspose.BarCode;` akan menyebabkan kesalahan kompilasi pada enum `BarCodeImageFormat`.

## Langkah Selanjutnya — Melebihi Dasar

Sekarang Anda sudah tahu **menyesuaikan ukuran barcode** dan **cara menghasilkan PDF417**, Anda mungkin ingin menjelajahi:

- Menambahkan **warna** pada barcode (`generator.Parameters.Barcode.Color = Color.Blue;`).
- Menyematkan barcode langsung ke PDF menggunakan `Aspose.Pdf`.
- Menghasilkan **beberapa barcode** dalam operasi batch untuk pencetakan label massal.
- Menggunakan pengaturan **level koreksi kesalahan** untuk meningkatkan keandalan pemindaian di lingkungan yang berisik.

Setiap topik ini dibangun di atas konsep inti yang dibahas di sini, dan pola yang sama—buat generator, sesuaikan parameter, simpan—berlaku di seluruh situasi.

---

### TL;DR

Anda baru saja mempelajari cara **menyesuaikan ukuran barcode** di C# dengan mengatur X‑dimension dan jumlah kolom, serta memahami **cara menghasilkan PDF417** (khususnya MicroPdf417) barcode dengan Aspose.BarCode. Contoh lengkap yang dapat dijalankan di atas menghasilkan gambar PNG yang tajam siap untuk alur kerja selanjutnya. Silakan bereksperimen dengan parameter, ganti ke PDF417 ukuran penuh, atau integrasikan kode ke aplikasi yang lebih besar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cara Menghasilkan Barcode – Konfigurasi Code 39 dengan Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}