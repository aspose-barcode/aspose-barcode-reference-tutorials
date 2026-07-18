---
category: general
date: 2026-07-18
description: Buat kode batang PDF417 dengan cepat. Pelajari cara mengatur mode terhubung
  dan cara menghasilkan kode batang PDF417 dengan Aspose.BarCode dalam tutorial langkah
  demi langkah yang jelas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: id
lastmod: 2026-07-18
og_description: Hasilkan kode batang PDF417 secara instan. Tutorial ini menunjukkan
  cara mengatur mode terhubung dan cara menghasilkan kode batang PDF417 menggunakan
  Aspose.BarCode, lengkap dengan kode yang dapat dijalankan.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Buat Kode Bar PDF417 di C# – Panduan Lengkap Langkah demi Langkah
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Menghasilkan Kode Barcode PDF417 di C# – Panduan Pemrograman Lengkap
url: /id/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan Barcode PDF417 di C# – Panduan Pemrograman Lengkap

Pernah membutuhkan untuk **generate PDF417 barcode** dalam aplikasi .NET tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian. Baik Anda sedang membuat printer boarding‑pass, pemindai gudang, atau hanya bereksperimen dengan barcode 2‑D, membuat PDF417 berjalan lebih mudah daripada yang Anda kira.

Dalam panduan ini kami akan menjelaskan langkah‑langkah tepat untuk **generate PDF417 barcode** menggunakan Aspose.BarCode, menunjukkan **how to set linked mode**, dan membahas **how to generate PDF417 barcode** dengan parameter khusus—semua dalam satu contoh siap salin‑tempel.

## Apa yang Akan Anda Pelajari

- Paket NuGet minimal yang Anda butuhkan.
- Cara menginisialisasi generator PDF417 dengan teks Anda sendiri.
- **How to set linked mode** sehingga barcode dapat melilit ke beberapa baris.
- Penyesuaian tambahan seperti ukuran modul dan jumlah kolom.
- Cara menyimpan hasil sebagai PNG, JPEG, atau format lain yang didukung.
- Jebakan umum dan tips pemecahan masalah cepat.

### Prasyarat

- .NET 6.0 atau lebih baru (kode ini juga berfungsi pada .NET Framework 4.7+).
- Pengetahuan dasar C#.
- Visual Studio 2022 (atau IDE apa pun yang Anda sukai).
- Versi percobaan Aspose.BarCode gratis atau salinan berlisensi.

> **Pro tip:** Jika Anda berada di mesin baru, jalankan `dotnet add package Aspose.BarCode` dari terminal di dalam folder proyek Anda. Perintah ini akan mengunduh semua yang Anda perlukan.

---

## Langkah 1: Instal Aspose.BarCode dan Tambahkan Namespace

Langkah pertama—mari bawa pustaka ke dalam proyek.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Kemudian, di bagian atas file C# Anda, sertakan namespace yang diperlukan:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Mengapa ini penting:** Tanpa namespace `Aspose.BarCode.Generation` Anda tidak akan memiliki akses ke `BarcodeGenerator`, dan namespace `System.Drawing.Imaging` memberikan enum `ImageFormat` untuk menyimpan file.

---

## Langkah 2: Inisialisasi Generator Barcode PDF417

Sekarang kita membuat instance generator dan memberi teks yang ingin kita enkode. Ini adalah inti dari **how to generate PDF417 barcode**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Penjelasan:** `EncodeTypes.Pdf417` memberi tahu Aspose bahwa kita menggunakan simbol PDF417. Argumen kedua, `"Aspose"`, adalah data yang akan muncul saat barcode dipindai.

---

## Langkah 3: Tentukan Ukuran Modul (X‑Dimension)

Ukuran modul mengontrol seberapa besar setiap kotak kecil (atau “piksel”) pada barcode muncul. Nilai yang lebih kecil menghasilkan barcode yang lebih rapat; nilai yang lebih besar membuatnya lebih mudah dibaca pada printer beresolusi rendah.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Rentang tipikal:** 1–4 piksel bekerja untuk kebanyakan layar. Jika Anda mencetak pada printer label DPI tinggi, naikkan ke 3 atau 4.

---

## Langkah 4: Konfigurasikan Kolom dan Aktifkan Linked Mode

Di sinilah kami menjawab **how to set linked mode**. Linked mode memungkinkan barcode PDF417 terbagi menjadi beberapa baris, yang berguna ketika Anda memiliki ruang horizontal terbatas.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Mengapa linked mode?** Bayangkan Anda perlu barcode agar muat di dalam elemen UI yang sempit. Dengan `IsLinked = true`, pustaka secara otomatis memecah simbol menjadi baris sambil mempertahankan kemampuan pemindaian.

> **Kasus tepi:** Jika Anda mengatur `Columns` terlalu rendah sekaligus mengaktifkan linked mode, Aspose dapat meningkatkan jumlah baris secara dramatis, yang dapat meluapkan kanvas gambar kecil. Perhatikan dimensi akhir gambar.

---

## Langkah 5: Simpan Gambar Barcode

Akhirnya, tulis barcode ke sebuah file. Anda dapat memilih PNG, JPEG, BMP, atau bahkan PDF. PNG bersifat loss‑less, menjadikannya ideal untuk pemrosesan lebih lanjut.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Hasil:** Anda akan melihat barcode PDF417 yang tajam dengan tiga kolom, ukuran modul 2 piksel, dan baris terhubung jika data melebihi lebar satu baris.

---

## Contoh Lengkap yang Berfungsi

Berikut adalah program lengkap yang siap dijalankan. Salin‑tempel ke dalam proyek konsol baru (`dotnet new console`) dan tekan **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Output yang Diharapkan

Menjalankan program mencetak baris konfirmasi, dan folder kini berisi `Pdf417Linked.png`. Membuka PNG menampilkan barcode PDF417 tiga kolom yang mungkin meluas ke dua baris (berkat linked mode). Memindainya dengan aplikasi smartphone menampilkan teks **“Aspose”**.

---

## Pertanyaan Umum & Pemecahan Masalah

### 1. *Bagaimana jika barcode terlihat buram?*  
Biasanya ini masalah DPI. Tingkatkan `XDimension.Pixels` atau simpan gambar dengan resolusi lebih tinggi menggunakan `generator.Save(..., BarCodeImageFormat.Png, 300)` dimana `300` adalah DPI.

### 2. *Apakah saya dapat mengenkode string yang lebih panjang?*  
Ya—PDF417 dapat menampung hingga ~1.850 karakter. Jika Anda melebihi kapasitas jumlah kolom yang dipilih, pustaka secara otomatis menambahkan baris. Sesuaikan `Columns` atau aktifkan `IsLinked` untuk menjaga barcode tetap kompak.

### 3. *Apakah saya memerlukan lisensi untuk produksi?*  
Aspose.BarCode berfungsi dalam mode evaluasi, tetapi barcode yang dihasilkan akan memiliki watermark kecil. Beli lisensi untuk menghilangkannya dan membuka fitur lanjutan seperti penyesuaian tingkat koreksi kesalahan.

### 4. *Bagaimana cara generate PDF417 barcode dalam format lain?*  
Cukup ubah argumen kedua pada `Save`. Untuk JPEG gunakan `BarCodeImageFormat.Jpeg`; untuk PDF gunakan `BarCodeImageFormat.Pdf`.

---

## Memperluas Contoh

Sekarang Anda tahu **how to generate PDF417 barcode** dan **how to set linked mode**, Anda mungkin ingin menjelajahi:

- **Error correction level** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **Adding a border** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **Custom colors** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **Embedding the barcode in a PDF report** – combine Aspose.PDF with Aspose.BarCode.

Setiap penyesuaian ini mengikuti pola yang sama: temukan properti yang tepat di bawah `generator.Parameters.Barcode.Pdf417` (atau objek `Barcode` umum) dan tetapkan nilainya.

## Kesimpulan

Kami telah membahas semua yang Anda perlukan untuk **generate PDF417 barcode** di C#, mulai dari menginstal Aspose.BarCode hingga mengonfigurasi linked mode dan menyimpan gambar. Dengan mengikuti langkah‑langkah di atas, Anda akan memiliki generator barcode siap produksi yang dapat dimasukkan ke dalam solusi .NET apa pun.

Ingat, poin pentingnya adalah:

1. Inisialisasi dengan `EncodeTypes.Pdf417`.
2. Sesuaikan `XDimension` untuk kejelasan visual.
3. Atur `Columns` dan aktifkan `IsLinked` untuk mengontrol tata letak (**how to set linked mode**).
4. Simpan dalam format yang diinginkan.

Silakan bereksperimen dengan parameter tambahan, dan jangan ragu untuk membagikan hasil Anda atau mengajukan pertanyaan di komentar. Selamat coding, semoga barcode Anda selalu dapat dipindai pada percobaan pertama!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – Compact PDF417 dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara Menghasilkan Barcode PDF417 – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Cara Menghasilkan Gambar Barcode di Java dengan Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}