---
category: general
date: 2026-10-05
description: Pelajari cara membuat barcode PDF417 di C# dan menghasilkan PNG barcode
  dengan kode langkah demi langkah serta tips praktik terbaik.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: id
lastmod: 2026-10-05
og_description: Buat kode batang PDF417 di C# dan hasilkan PNG kode batang secara
  instan. Ikuti tutorial lengkap ini untuk solusi siap produksi.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Buat kode batang PDF417 di C# – panduan lengkap untuk menghasilkan PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Cara membuat barcode PDF417 dan menyimpannya sebagai PNG di C#
url: /id/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode PDF417 dan menyimpannya sebagai PNG di C#

Jika Anda perlu **membuat barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan secara tepat cara melakukannya. Anda akan mendapatkan potongan kode C# siap pakai yang menghasilkan file **barcode PNG** berkualitas tinggi, dan Anda akan memahami setiap pengaturan yang memengaruhi output.

Membuat barcode adalah kebutuhan umum untuk sistem tiket, pelacakan inventaris, dan pengkodean dokumen yang aman. Pada akhir tutorial ini Anda dapat menjawab pertanyaan “**bagaimana cara menghasilkan PDF417**” dengan contoh lengkap yang dapat dijalankan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Lingkungan pengembangan seperti Visual Studio 2022 atau VS Code  
* Paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang mendukung PDF417)  

Anda dapat menambahkan paket dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Kode di bawah ini menggunakan Aspose API karena menyediakan kontrol granular atas parameter PDF417 dan mendukung ekspor PNG secara langsung.

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru dan impor namespace yang diperlukan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace `Aspose.BarCode.Generation` berisi kelas `BarcodeGenerator`, yang merupakan titik masuk untuk **membuat gambar barcode PDF417**.

## Langkah 2: Buat barcode PDF417 dengan teks yang diinginkan

Instansiasi generator dengan enum `EncodeTypes.Pdf417` dan data yang ingin Anda enkode. Contoh ini menggunakan string yang berisi karakter khusus untuk mendemonstrasikan penanganan Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Generator kini menyimpan objek barcode yang dapat Anda konfigurasikan sebelum dirender.

## Langkah 3: Konfigurasikan parameter visual

Penyetelan halus pada barcode meningkatkan keterbacaan dan mengurangi ukuran gambar. Pengaturan yang paling sering disesuaikan adalah **X‑dimension**, **columns**, dan **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** mengontrol lebar setiap modul; nilai `2` piksel menghasilkan barcode yang kompak namun tetap terbaca.  
* **Columns** menentukan berapa banyak kolom data yang digunakan kode. Lebih sedikit kolom membuat barcode lebih sempit tetapi lebih tinggi.  
* **Truncate** mengaktifkan mode “compact” yang didefinisikan oleh spesifikasi PDF417, yang menghapus baris padding yang tidak diperlukan.

Anda dapat bereksperimen dengan `Rows` dan `ErrorCorrectionLevel` jika kasus penggunaan Anda memerlukan ketahanan yang lebih tinggi terhadap kerusakan.

## Langkah 4: Simpan barcode sebagai gambar PNG

Akhirnya, ekspor barcode ke file PNG. PNG mempertahankan tepi tajam dan mendukung transparansi, menjadikannya ideal untuk skenario web dan cetak.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Menjalankan program akan membuat `CompactPdf417.png` di direktori yang ditentukan. Gambar tersebut terlihat seperti ini:

![Barcode PDF417 kompak yang dibuat dengan C#](compact-pdf417.png "Contoh barcode PDF417 kompak yang dibuat dengan C#")

*Teks alt di atas berisi kata kunci utama, memenuhi persyaratan SEO dan aksesibilitas.*

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian, berikut adalah program mandiri yang dapat Anda salin, tempel, dan jalankan:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Output yang diharapkan

Saat Anda membuka `CompactPdf417.png`, Anda akan melihat barcode vertikal dengan kepadatan tinggi yang mengenkode string *Åspóse.Barcóde©*. Memindai gambar dengan pembaca PDF417 apa pun akan mengembalikan teks asli.

## Mengapa pengaturan ini penting

* **X‑dimension** memengaruhi baik ukuran fisik maupun kecepatan pemindaian. Modul yang lebih kecil meningkatkan kepadatan data tetapi mungkin memerlukan pemindai beresolusi tinggi.  
* **Columns** memengaruhi rasio aspek. Untuk struk mobile, jumlah kolom yang rendah menjaga barcode cukup sempit untuk muat pada kertas tipis.  
* **Truncate** mengurangi jumlah baris, menghemat tinta dan ruang tanpa mengorbankan integritas data, karena PDF417 sudah menyertakan kode koreksi kesalahan.

Memahami parameter ini memungkinkan Anda menyesuaikan barcode dengan batasan media target—apakah itu printer label, halaman web, atau aplikasi seluler.

## Variasi umum dan kasus tepi

### Membuat format gambar lain

Jika Anda lebih suka JPEG atau BMP, ubah enum `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG mengompresi gambar tetapi dapat memperkenalkan artefak yang memengaruhi pemindaian pada ukuran kecil.

### Menyesuaikan koreksi kesalahan

Untuk lingkungan keras (misalnya tanda luar ruangan), tingkatkan level koreksi kesalahan:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Level yang lebih tinggi menambah redundansi, membuat barcode lebih besar tetapi lebih tahan banting.

### Menyandikan data biner

PDF417 dapat mengenkode muatan biner. Berikan `byte[]` alih-alih string:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Perpustakaan secara otomatis beralih ke mode biner.

### Menangani string yang sangat panjang

Ketika data melebihi kapasitas default, generator secara otomatis membuat baris tambahan. Anda dapat membatasi jumlah baris untuk menghindari gambar yang terlalu besar:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Jika konten masih tidak muat, pertimbangkan membaginya ke beberapa barcode.

## Tips profesional

* **Cache generator** jika Anda perlu membuat banyak barcode dengan pengaturan yang sama. Menggunakan kembali objek menghindari alokasi ulang sumber daya internal.  
* **Set `Resolution`** pada `ImageOptions` jika Anda memerlukan DPI tertentu untuk pencetakan:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validasi output** secara programatis dengan `BarCodeReader` untuk memastikan PNG yang dihasilkan dapat didekode sebelum dikirim ke pengguna.

## Kesimpulan

Anda kini tahu cara **membuat barcode PDF417** di C# dan **menghasilkan file barcode PNG** dengan kontrol penuh atas ukuran, kolom, dan mode kompak. Contoh lengkap menunjukkan pendekatan standar, menjelaskan mengapa setiap pengaturan penting, serta mencakup variasi seperti koreksi kesalahan, format alternatif, dan data biner. Gunakan tips di atas untuk menyesuaikan solusi dengan alur kerja spesifik Anda, baik Anda membangun sistem tiket, generator label logistik, atau pengkode dokumen aman.

---

**Langkah selanjutnya**

* Jelajahi simbol 2D lainnya (DataMatrix, QR) menggunakan kelas `BarcodeGenerator` yang sama.  
* Integrasikan pembuatan barcode ke dalam API ASP.NET Core untuk menyajikan PNG sesuai permintaan.  
* Gabungkan gambar barcode dengan perpustakaan pembuatan PDF untuk menyematkannya langsung ke dalam laporan.

Selamat mengoding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang berhubungan erat dan membangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat barcode pdf417 di C# – panduan langkah‑per‑langkah](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara menghasilkan barcode micro pdf417 di C# – panduan langkah‑per‑langkah](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Cara membuat barcode PDF417 di C# dengan mode kompak](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}