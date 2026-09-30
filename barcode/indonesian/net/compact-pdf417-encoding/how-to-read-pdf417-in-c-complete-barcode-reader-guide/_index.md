---
category: general
date: 2026-08-09
description: Cara membaca PDF417 di C# menggunakan BarCodeReader. Pelajari cara membaca
  file PNG barcode, menangani beberapa barcode, dan mengekstrak metadata tambahan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: id
lastmod: 2026-08-09
og_description: Cara membaca PDF417 di C# dengan Aspose.BarCode. Tutorial ini menunjukkan
  cara membaca file PNG barcode, memproses beberapa barcode dalam satu gambar, dan
  mengambil metadata PDF417 yang diperluas.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Cara membaca PDF417 di C# – tutorial pembaca barcode
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cara membaca PDF417 di C# – panduan lengkap pembaca kode batang
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca PDF417 di C# – panduan lengkap pembaca barcode

Jika Anda perlu **cara membaca PDF417** dalam aplikasi .NET, panduan ini memberikan solusi siap‑pakai. Anda akan melihat cara membaca PNG barcode, memproses beberapa barcode dalam gambar yang sama, dan mengambil bidang PDF417 yang diperluas yang disembunyikan oleh banyak pemindai.

Membaca barcode PDF417 umum dalam logistik, tiket, dan manajemen dokumen. Pada akhir tutorial ini Anda dapat mendekode gambar Macro PDF417, menampilkan setiap hasil, dan menggunakan informasi tambahan (ID file, jumlah segmen, cap waktu, dll.) dalam logika bisnis Anda sendiri.

## Prasyarat

- .NET 6.0 atau lebih baru (kode juga bekerja dengan .NET Framework 4.7+)
- Visual Studio 2022 atau IDE C# apa saja
- **Aspose.BarCode for .NET** (versi percobaan gratis atau paket NuGet berlisensi)
- Sebuah gambar PNG yang berisi barcode Macro PDF417 (file contoh bernama `ExtPDF417Meta.png`)

> **Tip pro:** Instal perpustakaan dengan konsol NuGet:  
> `dotnet add package Aspose.BarCode`

## Cara membaca PDF417 dengan BarCodeReader di C#

Inti dari solusi ini adalah kelas `BarCodeReader`. Kelas ini menerima jalur gambar dan enum `DecodeType` yang memberi tahu mesin simbol apa yang harus dicari.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Mengapa ini berhasil

- **`DecodeType.MacroPdf417`** memberi tahu pembaca untuk mencari varian Macro PDF417, yang menyimpan bidang tambahan yang Anda lihat pada langkah 4.
- Blok `using` secara otomatis membuang pembaca, melepaskan handle file.
- `ReadBarCodes()` mengembalikan **semua** barcode yang cocok dengan tipe yang diminta, yang memenuhi persyaratan *membaca beberapa barcode* bahkan jika gambar hanya berisi satu.

Menjalankan program mencetak output serupa dengan:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Menggunakan pembaca barcode C# untuk membaca beberapa barcode

Jika sebuah gambar berisi beberapa simbol Macro PDF417 (misalnya, halaman yang dipindai dengan sekumpulan tiket), loop `foreach` yang sama memproses masing‑masing. Tidak diperlukan kode tambahan; pembaca menggabungkan hasil secara internal.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Kesalahan umum

- **Format gambar:** Pembaca mendukung PNG, JPEG, BMP, dan TIFF. Jika Anda mencoba format yang tidak dapat didekode, Anda akan mendapatkan koleksi kosong. Itulah mengapa tutorial menekankan *membaca barcode PNG*.
- **Resolusi:** Gambar beresolusi rendah (< 300 dpi) dapat menyebabkan segmen terlewat. Tingkatkan skala atau minta pemindaian dengan kualitas lebih tinggi bila memungkinkan.
- **Flag macro:** Lupa menambahkan `DecodeType.MacroPdf417` membatasi mesin pada PDF417 biasa dan mengabaikan data yang diperluas. Selalu tentukan tipe macro ketika Anda memerlukan bidang *membaca barcode yang diperluas*.

## Membaca file PNG barcode – praktik terbaik

Bekerja dengan file PNG mudah karena format ini mempertahankan data piksel lossless. Berikut daftar periksa singkat:

1. Verifikasi file ada sebelum membuat pembaca.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Gunakan `Image.FromFile` hanya ketika Anda perlu pra‑proses (memutar, memotong). `BarCodeReader` dapat membuka file secara langsung, yang menghindari alokasi memori tambahan.
3. Jika PNG mengandung transparansi, pembaca tetap berfungsi karena barcode ditampilkan pada piksel tidak transparan.

## Mengakses metadata PDF417 yang diperluas

Objek `Extended.Pdf417` menampilkan setiap bidang opsional yang didefinisikan oleh spesifikasi PDF417. Anda dapat memetakan bidang-bidang ini ke model domain, menyimpannya di basis data, atau menggunakannya untuk validasi.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Populate the model:



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Cara Membuat Barcode – PDF417 Kompak dengan Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Baca barcode DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}