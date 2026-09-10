---
category: general
date: 2026-07-27
description: Panduan barcode databar expanded stacked – pelajari cara menghasilkan
  barcode, mengatur dimensi, membuat barcode databar, dan mengonfigurasi ukuran barcode
  dalam beberapa langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to generate barcode
- how to set dimensions
- create databar barcode
- configure barcode size
language: id
lastmod: 2026-07-27
og_description: Tutorial barcode bertumpuk yang diperluas databar menunjukkan cara
  menghasilkan barcode, mengatur dimensi, dan mengonfigurasi ukuran barcode dengan
  contoh kode yang jelas.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  and row settings
og_title: databar expanded stacked barcode – tutorial cepat C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  headline: databar expanded stacked barcode guide – how to generate and size it in
    C#
  type: TechArticle
- description: databar expanded stacked barcode guide – learn how to generate barcode,
    set dimensions, create databar barcode, and configure barcode size in a few steps.
  name: databar expanded stacked barcode guide – how to generate and size it in C#
  steps:
  - name: Why we re‑instantiate the generator
    text: You might wonder why we create a new `BarcodeGenerator` before setting rows.
      The **columns** and **rows** properties belong to the same `DataBar` object,
      but they each have a default that the other side respects. By starting with
      a fresh instance we guarantee that the column setting doesn’t inadvert
  - name: What does “column” mean for a **databar expanded stacked** symbol?
    text: '- **Columns** split the stacked barcode horizontally. More columns mean
      the symbol becomes wider, which can be useful when you have limited vertical
      space. - **Rows** stack the columns vertically. Adding rows makes the barcode
      taller, helpful for narrow label widths.'
  - name: When should you adjust these dimensions?
    text: '| Scenario | Recommended tweak | |----------|-------------------| | Thin
      label printer (e.g., receipt printers) | Reduce columns, increase rows. | |
      Wide shelf label (e.g., price tags) | Increase columns, keep rows low. | | High‑resolution
      print (e.g., packaging) | Use default layout but boost DPI v'
  - name: 1️⃣ *What if my data string exceeds the maximum length?*
    text: The **databar expanded stacked** format can encode up to 74 numeric characters
      or 41 alphanumeric characters. If you exceed that, the generator throws a `BarcodeException`.
      Trim or hash the data, or switch to a different barcode type (e.g., `Pdf417`).
  - name: 2️⃣ *Can I output SVG instead of PNG?*
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg`.
      SVG is vector‑based and scales without loss—great for web apps.
  - name: 3️⃣ *Do I need to worry about background color?*
    text: 'By default the background is white. To make it transparent, set:'
  - name: 4️⃣ *Is there a way to add a caption beneath the barcode?*
    text: Yes. Use `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;`
      and then combine the barcode with a `Graphics` object to draw text. That’s a
      bit more involved, but the Aspose API provides a `BarcodeGenerator.Save` overload
      that accepts a `Stream`—you can post‑process the image a
  type: HowTo
tags:
- barcode
- databar
- csharp
title: Panduan barcode Databar Expanded Stacked – cara menghasilkan dan mengatur ukurannya
  di C#
url: /id/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar expanded stacked barcode – Tutorial Lengkap C#

Pernah bertanya-tanya bagaimana cara menghasilkan **databar expanded stacked** barcode tanpa harus menyelami dokumentasi API yang tak berujung? Anda tidak sendirian. Baik Anda sedang membangun sistem checkout ritel maupun printer label logistik, menguasai tipe barcode ini dapat menghemat berjam-jam percobaan‑dan‑kesalahan.

Dalam panduan ini kami akan membahas seluruh proses: mulai dari menginstal pustaka, membuat barcode, hingga **cara mengatur dimensi** untuk kolom dan baris, dan akhirnya **mengonfigurasi ukuran barcode** sesuai kebutuhan pencetakan Anda. Pada akhir tutorial Anda akan memiliki proyek C# siap‑jalankan yang menghasilkan dua gambar PNG—satu dengan kolom khusus, lainnya dengan baris khusus.

---

## Apa yang Akan Anda Pelajari

- **Cara menghasilkan gambar barcode** menggunakan pustaka Aspose.BarCode untuk .NET.  
- Perbedaan antara **kolom** dan **baris** dalam simbol **databar expanded stacked**.  
- Langkah praktis untuk **membuat barcode databar** dengan tata letak tertentu.  
- Tips tentang **mengonfigurasi ukuran barcode**, DPI, dan format gambar.  
- Penanganan kasus tepi ketika string data terlalu panjang atau ketika Anda memerlukan latar belakang transparan.

Tidak diperlukan pengalaman sebelumnya dengan Aspose; cukup dengan pengaturan C# dasar dan rasa ingin tahu tentang barcode.

## Prasyarat

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6.0 SDK or later | Menyediakan fitur bahasa terbaru serta kinerja runtime yang optimal. |
| Visual Studio 2022 (or VS Code) | Memudahkan pengelolaan paket NuGet dan menjalankan contoh. |
| Internet access to download the **Aspose.BarCode** NuGet package | Pustaka ini berisi kelas `BarcodeGenerator` yang akan kami gunakan. |
| A folder you can write to (e.g., `C:\Barcodes\`) | Tempat penyimpanan file PNG. |

Jika Anda belum memiliki salah satu dari ini, dapatkan segera—jika tidak, Anda akan menemui error “missing reference” nanti dan itu akan membuang waktu.

## Langkah 1: Instal Aspose.BarCode via NuGet

Buka folder proyek Anda di terminal dan jalankan:

```bash
dotnet new console -n DatabarDemo
cd DatabarDemo
dotnet add package Aspose.BarCode
```

> **Pro tip:** Versi komunitas gratis sudah cukup untuk kebanyakan skenario pengembangan, tetapi jika Anda memerlukan dukungan komersial, dapatkan lisensi dari Aspose dan panggil `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` di awal `Main`.

Paket `Aspose.BarCode` menyertakan semua yang Anda perlukan untuk **cara menghasilkan barcode** dalam bentuk gambar, termasuk nilai enum `EncodeTypes.DatabarExpandedStacked`.

## Langkah 2: Tulis Kode Inti – Buat Barcode Generator

Buat file bernama `Program.cs` (atau ganti yang default) dan tempelkan kode berikut. Blok ini menunjukkan langkah **membuat barcode databar** dan juga menyiapkan kita untuk **mengonfigurasi ukuran barcode** nanti.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to your own path
            string outputFolder = @"C:\Barcodes\";

            // -----------------------------------------------------------------
            // 1️⃣  Create a barcode generator for Databar Expanded Stacked
            // -----------------------------------------------------------------
            // The second argument is the data you want to encode.
            // For Databar Expanded Stacked the string can be fairly long.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 2️⃣  Set a custom column count (default rows are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;   // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarCols4.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3️⃣  Re‑initialize the generator for the same data
            // -----------------------------------------------------------------
            // This demonstrates that column and row settings are independent.
            generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // -----------------------------------------------------------------
            // 4️⃣  Set a custom row count (default columns are used)
            // -----------------------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;      // ← how to set dimensions
            generator.Save($"{outputFolder}DatabarRows3.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 5️⃣  Optional: tweak overall image size and resolution
            // -----------------------------------------------------------------
            // If you need a larger barcode for printing, adjust the X/Y DPI.
            generator.Parameters.Image.XResolution = 300; // DPI
            generator.Parameters.Image.YResolution = 300;
            generator.Parameters.Image.Width = 400;       // pixels
            generator.Parameters.Image.Height = 200;      // pixels
            generator.Save($"{outputFolder}DatabarLarge.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully!");
        }
    }
}
```

### Mengapa kami membuat ulang generator

Anda mungkin bertanya-tanya mengapa kami membuat `BarcodeGenerator` baru sebelum mengatur baris. Properti **kolom** dan **baris** milik objek `DataBar` yang sama, namun masing‑masing memiliki nilai default yang dihormati oleh sisi lainnya. Dengan memulai dari instance baru, kami memastikan pengaturan kolom tidak secara tidak sengaja memengaruhi jumlah baris, yang merupakan jebakan umum saat **mengonfigurasi ukuran barcode**.

## Langkah 3: Jalankan Proyek dan Verifikasi Output

Dari terminal, jalankan:

```bash
dotnet run
```

Jika semuanya terhubung dengan benar, Anda akan melihat:

```
Barcodes generated successfully!
```

Buka `C:\Barcodes\` (atau folder apa pun yang Anda pilih). Anda akan menemukan tiga file PNG:

| File | Apa yang ditampilkan |
|------|----------------------|
| `DatabarCols4.png` | Barcode **databar expanded stacked** dengan **4 kolom** (baris default). |
| `DatabarRows3.png` | Data yang sama, tetapi kini dengan **3 baris** (kolom default). |
| `DatabarLarge.png` | Versi yang lebih besar dimana kami **mengonfigurasi ukuran barcode** melalui DPI dan dimensi piksel. |

Buka salah satu di penampil gambar—ya, barcode tersebut terlihat persis seperti yang Anda temukan di rak toko, hanya dengan tata letak khusus.

## Langkah 4: Penjelasan Mendalam – Memahami Kolom vs. Baris

### Apa arti “kolom” untuk simbol **databar expanded stacked**?

- **Kolom** membagi barcode bertumpuk secara horizontal. Lebih banyak kolom membuat simbol menjadi lebih lebar, yang berguna ketika ruang vertikal terbatas.  
- **Baris** menumpuk kolom secara vertikal. Menambah baris membuat barcode lebih tinggi, membantu untuk lebar label yang sempit.

Kedua properti menerima nilai antara 2 hingga 8 (tergantung panjang data). Jika Anda mencoba mengatur nilai di luar rentang ini, Aspose akan melempar `ArgumentException`. Itulah mengapa kami menggunakan angka yang wajar (4 kolom, 3 baris) dalam demo.

### Kapan Anda harus menyesuaikan dimensi ini?

| Skenario | Penyesuaian yang disarankan |
|----------|-----------------------------|
| Printer label tipis (misalnya printer struk) | Kurangi kolom, tingkatkan baris. |
| Label rak lebar (misalnya tag harga) | Tingkatkan kolom, pertahankan baris rendah. |
| Cetakan resolusi tinggi (misalnya kemasan) | Gunakan tata letak default tetapi tingkatkan DPI via `XResolution`/`YResolution`. |

## Langkah 5: Lanjutan – Menyetel Ukuran Barcode

Jika Anda memerlukan **mengonfigurasi ukuran barcode** lebih besar dari default 200 × 100 px, Anda memiliki dua cara:

1. **Resolusi gambar (DPI)** – DPI yang lebih tinggi menghasilkan detail lebih banyak, penting untuk pemindai yang memerlukan tepi yang tajam.  
2. **Dimensi piksel eksplisit** – Menimpa ukuran yang dihitung otomatis dengan `Parameters.Image.Width` dan `Height`.

Berikut cuplikan cepat yang memaksa gambar 600 × 300 px pada 600 DPI:

```csharp
generator.Parameters.Image.XResolution = 600;
generator.Parameters.Image.YResolution = 600;
generator.Parameters.Image.Width = 600;   // pixels
generator.Parameters.Image.Height = 300;  // pixels
generator.Save($"{outputFolder}DatabarHighRes.png", BarCodeImageFormat.Png);
```

> **Perhatian:** Menetapkan lebar/tinggi yang terlalu kecil untuk jumlah kolom/baris yang dipilih akan memotong barcode, menyebabkan kegagalan pemindaian. Selalu uji dengan pemindai nyata setelah mengubah dimensi.

## Pertanyaan Umum & Kasus Tepi

### 1️⃣ *Bagaimana jika string data saya melebihi panjang maksimum?*  

Format **databar expanded stacked** dapat mengkodekan hingga 74 karakter numerik atau 41 karakter alfanumerik. Jika Anda melebihi itu, generator akan melempar `BarcodeException`. Potong atau hash data, atau beralih ke tipe barcode lain (misalnya `Pdf417`).

### 2️⃣ *Bisakah saya menghasilkan SVG alih-alih PNG?*  

Tentu saja. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`. SVG berbasis vektor dan dapat diskalakan tanpa kehilangan kualitas—bagus untuk aplikasi web.

### 3️⃣ *Apakah saya perlu khawatir tentang warna latar belakang?*  

Secara default latar belakang berwarna putih. Untuk membuatnya transparan, atur:

```csharp
generator.Parameters.Image.BackgroundColor = System.Drawing.Color.Transparent;
```

### 4️⃣ *Apakah ada cara menambahkan keterangan di bawah barcode?*  

Ya. Gunakan `generator.Parameters.Barcode.BarcodeImageFormat = BarCodeImageFormat.Png;` lalu gabungkan barcode dengan objek `Graphics` untuk menggambar teks. Itu sedikit lebih rumit, tetapi API Aspose menyediakan overload `BarcodeGenerator.Save` yang menerima `Stream`—Anda dapat memproses gambar setelahnya.

## Ringkasan Langkah‑per‑Langkah (Referensi Cepat)

| Langkah | Aksi | Potongan kode |
|------|--------|--------------|
| 1️⃣ | Instal Aspose.BarCode | `dotnet add package Aspose.BarCode` |
| 2️⃣ | Buat generator untuk **databar expanded stacked** | `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "your`

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Hasilkan gambar barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Cara Menghasilkan Barcode Java – Panduan Konfigurasi Lengkap](/barcode/english/java/barcode-configuration/)
- [Buat Barcode dengan Aspose - Atur Dimensi X & Y di Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}