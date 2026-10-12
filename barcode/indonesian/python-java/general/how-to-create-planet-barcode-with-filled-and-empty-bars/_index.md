---
category: general
date: 2026-09-29
description: Buat kode batang planet di C# dengan bar terisi dan kosong – panduan
  langkah demi langkah menggunakan Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: id
lastmod: 2026-09-29
og_description: Buat barcode planet dengan cepat menggunakan C#. Pelajari cara merender
  bar yang terisi, beralih ke bar kosong, dan menyesuaikan dimensi X dengan Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Buat barcode planet dengan bar terisi dan kosong – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cara membuat barcode planet dengan batang terisi dan kosong
url: /id/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode planet dengan batang terisi dan kosong

Jika Anda perlu **membuat gambar barcode planet** di C#, panduan ini menunjukkan cara menghasilkan versi batang‑terisi dan batang‑kosong. Anda akan melihat cara mengatur lebar batang (dimensi‑X), mengubah properti `FilledBars`, dan menyimpan hasilnya sebagai file PNG—semua dengan menggunakan pustaka Aspose.Barcode.

Membuat barcode pos adalah kebutuhan umum untuk sistem pengiriman, aplikasi daftar surat, dan dasbor logistik. Pada akhir tutorial ini Anda akan memiliki dua file PNG siap pakai yang dapat Anda sematkan dalam laporan, email, atau cetakan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

| Persyaratan | Mengapa penting |
|-------------|-----------------|
| .NET 6.0 atau lebih baru | Menyediakan runtime untuk contoh C#. |
| Visual Studio 2022 (atau IDE C# apa saja) | Memungkinkan Anda mengompilasi dan menjalankan kode. |
| **Aspose.Barcode for .NET** paket NuGet | Menyediakan kelas `BarcodeGenerator` dan `EncodeTypes.Planet`. Instal dengan `dotnet add package Aspose.Barcode`. |
| Izin menulis ke folder di disk | Metode `Save` menulis file PNG ke jalur yang Anda tentukan. |

## Langkah 1: Siapkan proyek dan impor namespace

Buat proyek konsol baru (atau tambahkan kode ke proyek yang sudah ada) dan referensikan namespace Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Arahan `using` ini memberi Anda akses ke kelas `BarcodeGenerator`, `EncodeTypes`, dan enum format gambar yang diperlukan untuk tutorial.

## Langkah 2: Buat barcode Planet dengan batang default (terisi)

Barcode pertama menggunakan rendering default pustaka, yang mengisi batang.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Mengapa ini berhasil:**  
`EncodeTypes.Planet` memberi tahu Aspose.Barcode untuk menggunakan simbol **Planet**, yaitu barcode pos yang dipakai oleh United States Postal Service. Properti `XDimension` mengontrol lebar tiap batang; mengaturnya ke 4 piksel menghasilkan barcode yang tercetak dengan baik pada printer label standar. Secara default, `FilledBars` bernilai `true`, sehingga batang muncul solid.

## Langkah 3: Buat barcode Planet dengan batang kosong

Untuk menghasilkan data yang sama dengan *batang kosong*, Anda hanya perlu membalik flag `FilledBars` sementara pengaturan lainnya tetap identik.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Mengapa ini penting:**  
Beberapa sistem pengiriman memerlukan gaya **batang‑kosong** untuk meningkatkan keterbacaan ketika barcode dicetak pada latar belakang gelap atau ketika skema warna kontras digunakan. Dengan mengatur `FilledBars = false`, generator hanya menggambar outline batang, meninggalkan bagian dalam transparan.

## Output yang diharapkan

Setelah menjalankan program, folder `C:\Barcodes` (atau jalur yang Anda pilih) berisi dua file PNG:

| Berkas | Deskripsi visual |
|--------|-------------------|
| `PlanetFilledBars.png` | Batang berupa persegi panjang hitam solid pada latar putih. |
| `PlanetEmptyBars.png`  | Batang berupa outline hitam; bagian dalam tiap batang transparan (menampilkan latar). |

Kedua gambar mengkodekan string numerik yang sama `"123456"` dan memiliki lebar batang 4 piksel, sehingga tampak konsisten kecuali gaya pengisian.

## Variasi umum dan kasus tepi

### Mengubah lebar batang

Jika printer label Anda mengharapkan lebar batang yang berbeda, ubah nilai `XDimension.Pixels`. Untuk printer resolusi tinggi, nilai **2** atau **3** piksel mungkin lebih cocok; untuk printer resolusi rendah, **5** atau **6** piksel dapat meningkatkan keandalan pemindaian.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Menggunakan format gambar yang berbeda

Aspose.Barcode mendukung PNG, JPEG, BMP, GIF, dan TIFF. Ganti `BarCodeImageFormat.Png` dengan nilai enum lain untuk menyesuaikan alur kerja Anda.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Membuat beberapa barcode dalam loop

Ketika Anda membutuhkan sekumpulan barcode Planet (misalnya untuk daftar surat), bungkus logika generator dalam loop `foreach` dan ubah string data pada setiap iterasi.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Menangani input tidak valid

Simbol Planet hanya menerima string numerik berjumlah **5‑8** digit. Memberikan nilai yang tidak valid akan memicu `ArgumentException`. Lindungi dari hal ini dengan metode validasi sederhana.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Tips pro: Verifikasi barcode dengan emulator pemindai

Aspose.Barcode menyertakan kelas `BarcodeReader` yang dapat Anda gunakan untuk memastikan gambar yang dihasilkan dapat didekode kembali ke data asli.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Jika output menampilkan `"123456"` untuk kedua file, barcode telah dihasilkan dengan benar.

## Kesimpulan

Anda kini tahu cara **membuat barcode planet** di C# dengan gaya batang terisi dan kosong, mengontrol **XDimension barcode Planet**, serta menyimpan hasilnya dalam format PNG menggunakan pustaka **Aspose.Barcode**. Sesuaikan lebar batang, ganti format gambar, atau lakukan loop pada koleksi nilai untuk memenuhi alur kerja kode pos apa pun.

Selanjutnya, Anda dapat menjelajahi:

* **Menambahkan teks yang dapat dibaca manusia** di bawah barcode (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Menyematkan barcode dalam dokumen PDF** dengan Aspose.PDF.
* **Membuat simbol pos lainnya** seperti **USPS POSTNET** atau **Intelligent Mail**.

Silakan bereksperimen dengan parameter dan integrasikan kode ke dalam sistem pengiriman atau surat Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang memperluas teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}