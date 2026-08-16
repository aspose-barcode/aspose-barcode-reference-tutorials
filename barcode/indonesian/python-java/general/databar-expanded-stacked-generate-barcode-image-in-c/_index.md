---
category: general
date: 2026-08-15
description: Databar memperluas pembuatan barcode bertumpuk di C#. Pelajari cara menghasilkan
  gambar barcode, mengatur kolom dan baris untuk tata letak DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: id
lastmod: 2026-08-15
og_description: Databar memperluas pembuatan barcode bertumpuk di C#. Ikuti panduan
  langkah demi langkah ini untuk menghasilkan gambar barcode, mengatur kolom, dan
  mengatur baris secara efisien.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – menghasilkan gambar barcode dalam C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: buat gambar kode batang di C#'
url: /id/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: menghasilkan gambar barcode dalam C#

Jika Anda perlu menghasilkan gambar barcode **databar expanded stacked** dalam C#, panduan ini menunjukkan secara tepat **cara menghasilkan barcode** dengan tata letak kolom dan baris yang dapat disesuaikan. Anda akan melihat cara mengatur kolom, cara mengatur baris, dan cara menyimpan gambar yang dihasilkan tanpa meninggalkan IDE.

Tutorial ini mencakup:

* Membuat generator barcode untuk simbol **databar expanded stacked**.  
* Mengonfigurasi tata letak 4‑kolom dan 3‑baris.  
* Menyimpan setiap konfigurasi sebagai file PNG.  
* Tips untuk menangani kasus tepi seperti jumlah kolom yang tidak valid.

Tidak diperlukan dokumentasi eksternal; contoh lengkap yang dapat dijalankan disertakan.

![Contoh barcode databar expanded stacked](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="barcode databar expanded stacked yang dihasilkan dengan C#" }

## Langkah-langkah menghasilkan barcode databar expanded stacked

### 1. Instal library Aspose.BarCode

Kode ini menggunakan library **Aspose.BarCode for .NET**, yang menyediakan kelas `BarcodeGenerator`. Instal paket NuGet dengan perintah berikut:

```bash
dotnet add package Aspose.BarCode
```

Setelah paket terinstal, tambahkan namespace yang diperlukan di bagian atas file Anda:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Buat generator barcode untuk **databar expanded stacked**

Generator adalah titik masuk untuk semua operasi barcode. Anda harus menentukan simbol (`EncodeTypes.DatabarExpandedStacked`) dan teks yang akan dienkode.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Mengapa ini penting:* Enum `EncodeTypes` memberi tahu library format barcode apa yang harus dihasilkan. Menggunakan **databar expanded stacked** memastikan gambar yang dihasilkan mengikuti spesifikasi GS1 DataBar untuk tata letak stacked.

### 3. Cara mengatur kolom untuk DataBar

Properti `Columns` mengontrol berapa banyak modul vertikal yang muncul dalam barcode stacked. Nilai yang valid adalah 2, 3, atau 4. Mengatur kolom memengaruhi lebar barcode dan jumlah data yang dapat disimpannya.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** Jika Anda mencoba menetapkan nilai di luar rentang yang diizinkan, library akan melempar `ArgumentException`. Selalu validasi input saat menampilkan pilihan kolom kepada pengguna.

### 4. Simpan gambar barcode 4‑kolom

Menyimpan gambar menghasilkan file yang dapat Anda sematkan dalam laporan, faktur, atau aplikasi seluler. Metode `Save` menerima jalur file dan format gambar.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Setelah file ditulis, Anda dapat membukanya dengan penampil gambar apa pun untuk memastikan pola **databar expanded stacked** muncul dengan benar.

### 5. Cara mengatur baris untuk DataBar

Baris menambahkan dimensi kedua ke tata letak stacked, memungkinkan lebih banyak data dienkode tanpa memperlebar barcode. Properti `Rows` defaultnya 1; Anda dapat meningkatkannya hingga 3 untuk varian expanded stacked.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Mengapa baris penting:** Menambah baris mengurangi lebar keseluruhan sambil mempertahankan kapasitas data, yang berguna untuk label sempit atau ruang layar seluler.

### 6. Simpan gambar barcode 3‑baris

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG—satu dengan tata letak 4‑kolom dan satu lagi dengan tata letak 3‑baris—keduanya menggunakan simbol **databar expanded stacked**.

### 7. Contoh lengkap C# untuk menghasilkan gambar barcode

Menggabungkan semua langkah menghasilkan program mandiri yang dapat Anda salin ke aplikasi konsol:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Output yang diharapkan**

Running the program prints:

```
4‑column barcode saved.
3‑row barcode saved.
```

dan membuat dua file PNG di `YOUR_DIRECTORY`. Buka file-file tersebut untuk memverifikasi bahwa setiap gambar menampilkan barcode **databar expanded stacked** yang valid.

## Kesalahan umum dan tips praktis

* **Keberadaan direktori** – `Save` tidak membuat folder yang hilang. Pastikan `YOUR_DIRECTORY` ada atau gunakan `Directory.CreateDirectory` sebelum menyimpan.
* **Batas kolom** – Nilai selain 2, 3, atau 4 memicu pengecualian. Lindungi dari kesalahan input pengguna dengan pemeriksaan rentang sederhana:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Batas baris** – Varian expanded stacked mendukung hingga 3 baris. Menetapkan `Rows` ke 0 atau nilai lebih dari 3 juga akan memicu pengecualian.
* **Format gambar** – `BarCodeImageFormat.Png` memberikan kualitas lossless, yang ideal untuk pencetakan. Gunakan `Jpeg` hanya ketika ukuran file menjadi perhatian utama.

## Langkah Selanjutnya

Sekarang Anda tahu **cara menghasilkan barcode** dengan konfigurasi kolom dan baris yang dapat disesuaikan, Anda dapat:

* Mengintegrasikan generator ke dalam web API untuk menyajikan gambar barcode sesuai permintaan.  
* Menggabungkan barcode dengan pustaka pembuatan PDF untuk menyematkannya dalam faktur.  
* Bereksperimen dengan varian DataBar lainnya (`DatabarExpanded`, `DatabarLimited`) menggunakan objek `Parameters.Barcode.DataBar` yang sama.

Untuk kustomisasi lebih mendalam—seperti mengubah warna bar, menambahkan teks yang dapat dibaca manusia, atau menerapkan overlay QR‑code—lihat dokumentasi Aspose.BarCode pada properti `BarcodeGenerator`.

---

Dengan mengikuti panduan ini Anda telah menguasai alur kerja **databar expanded stacked**, mempelajari **cara mengatur kolom**, **cara mengatur baris**, dan menghasilkan dua gambar barcode yang berbeda siap untuk penggunaan produksi. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}