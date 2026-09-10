---
category: general
date: 2026-07-18
description: Buat kode batang PDF417 di C# menggunakan generator kode batang PDF417
  C#. Ikuti tutorial langkah demi langkah untuk membangun codetext yang diperluas,
  mengatur tampilan, dan menyimpan gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: id
lastmod: 2026-07-18
og_description: Buat kode batang PDF417 di C# secara instan. Panduan ini menunjukkan
  cara menggunakan generator kode batang PDF417 C#, mengonfigurasi mode ekstended,
  dan mengekspor PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Buat Kode Bar PDF417 di C# – Panduan Lengkap Generator
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Buat Kode Bar PDF417 di C# – Panduan Generator Kode Bar
url: /id/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Barcode PDF417 di C# – Panduan Generator Barcode

Pernah perlu **membuat barcode PDF417** dalam aplikasi C# tetapi tidak yakin harus mulai dari mana? Anda tidak sendirian—banyak pengembang mengalami hal yang sama saat pertama kali menangani barcode dua dimensi. Kabar baiknya? Dengan **generator barcode PDF417 C#** bawaan, Anda dapat membuat barcode lengkap hanya dengan beberapa baris kode.

Dalam tutorial ini kami akan membahas seluruh proses: membangun codetext yang diperluas yang mencampur set karakter berbeda, mengonfigurasi generator untuk gaya visual yang tepat, dan akhirnya menyimpan barcode sebagai file PNG. Pada akhir tutorial Anda akan memiliki potongan kode siap pakai yang dapat Anda sisipkan ke proyek .NET mana pun, serta tips untuk menangani kasus tepi seperti karakter Unicode atau lebar modul khusus.

---

## Apa yang Anda Butuhkan

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut di mesin Anda:

- **.NET 6.0** atau lebih baru (contoh ini juga bekerja dengan .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarcodeGenerator`, `EncodeTypes.Pdf417`, dll.)
- Editor kode—Visual Studio, Rider, atau bahkan VS Code sudah cukup
- Folder yang dapat Anda tulis, karena generator akan menyimpan PNG di sana

Itu saja—tidak ada paket NuGet tambahan selain perpustakaan barcode itu sendiri.

---

## Panduan Langkah‑per‑Langkah untuk **membuat barcode PDF417**

### 1. Instal perpustakaan barcode

Buka terminal Anda di folder proyek dan jalankan:

```bash
dotnet add package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang akan kita gunakan di seluruh contoh.

### 2. Bangun codetext yang diperluas

PDF417 mendukung **extended encoding**, memungkinkan Anda mencampur set karakter berbeda dalam satu barcode. Di bawah ini kami membuat tiga segmen:

- Segmen Windows‑1251 (Cyrillic)
- Segmen UTF‑8 yang berisi karakter Unicode (kanji Jepang untuk “dog” dan “right”)
- Segmen teks biasa

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Mengapa ini penting:**  
Jika Anda hanya menggunakan teks biasa, Anda terbatas pada subset ASCII default. Dengan secara eksplisit mendeklarasikan segmen ECI (Extended Channel Interpretation) Anda menjamin pemindai menginterpretasikan setiap bagian dengan benar, terlepas dari bahasa atau simbol yang terlibat.

### 3. Inisialisasi **generator barcode PDF417 C#**

Sekarang kita memiliki string codetext yang valid, kita serahkan ke generator. Pernyataan `using` memastikan sumber daya yang mendasari dilepaskan secara otomatis.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Konfigurasi tampilan dan mode enkoding

Pengaturan default memberi Anda barcode kecil yang mungkin sulit dibaca. Mari ubah beberapa parameter:

- **X‑Dimension** – mengontrol lebar setiap modul (ukuran piksel)
- **EncodeMode** – memberi tahu mesin untuk memperlakukan input sebagai mode diperluas
- **TwoDDisplayText** – teks yang dapat dibaca manusia opsional yang ditampilkan di bawah barcode

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Pro tip:** Jika Anda mencetak barcode pada printer label, naikkan `XDimension` menjadi 20 px atau lebih; kebanyakan pemindai menyukai sedikit ruang ekstra.

### 5. Simpan gambar barcode

Akhirnya, tulis gambar ke disk. Perpustakaan ini mendukung PNG, JPEG, BMP, dan beberapa format vektor—PNG adalah pilihan aman karena mempertahankan tepi yang tajam.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Pastikan `YOUR_DIRECTORY` ada dan dapat ditulisi. Setelah menjalankan program Anda seharusnya melihat file yang mirip dengan tangkapan layar di bawah ini.

![Barcode PDF417 yang dihasilkan dengan generator barcode PDF417 C#](https://example.com/images/pdf417-extended.png "Barcode PDF417 yang dihasilkan dengan generator barcode PDF417 C#")

---

## Menggunakan **generator barcode PDF417 C#** – penjelasan mendalam

### Menangani Unicode dan karakter khusus

Ketika Anda memasukkan simbol Unicode langsung ke dalam barcode teks biasa, generator mungkin beralih ke enkoding cadangan, menghasilkan output yang kacau. Dengan menggunakan `AddECICodetext` Anda secara eksplisit memberi tahu encoder set karakter mana yang harus diterapkan, menghilangkan tebakan. Jika Anda perlu mendukung **Arabic**, **Hebrew**, atau **emoji**, cukup pilih nilai `ECIEncodings` yang sesuai.

### Menyesuaikan tingkat koreksi kesalahan

PDF417 menawarkan empat tingkat koreksi kesalahan (0‑8). Tingkat yang lebih tinggi meningkatkan ketahanan tetapi juga memperbesar barcode. Sesuaikan melalui:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Skalasi untuk cetak vs. layar

Untuk tampilan di layar Anda mungkin tetap pada 96 dpi default. Untuk pencetakan resolusi tinggi (300 dpi atau lebih), atur:

```csharp
generator.Parameters.ImageResolution = 300;
```

Hal ini memastikan PNG yang disimpan mempertahankan detail yang cukup untuk printer laser.

### Kesalahan umum

- **Missing `using` directive** – Lupa menambahkan `using Aspose.BarCode.Encoding;` akan menyebabkan `ECIEncodings` tidak terdefinisi.
- **Directory not found** – Metode `Save` tidak akan membuat folder perantara; buatlah terlebih dahulu atau gunakan `Path.Combine` dengan `Environment.CurrentDirectory`.
- **Wrong encode mode** – Jika Anda membiarkan `EncodeMode` pada `Pdf417EncodeMode.Auto`, perpustakaan mungkin memperlakukan codetext yang diperluas sebagai teks biasa, menghapus penanda ECI.

---

## Contoh Lengkap yang Siap‑Jalankan

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cara membuat codetext dotcode yang diperluas dengan Aspose.BarCode untuk .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Buat gambar barcode c# – Konfigurasi Baris & Kolom Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}