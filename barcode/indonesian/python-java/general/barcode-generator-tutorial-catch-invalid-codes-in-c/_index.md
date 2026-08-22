---
category: general
date: 2026-08-22
description: Tutorial generator barcode yang menunjukkan cara menghasilkan gambar
  barcode, memvalidasi input, dan menangkap pengecualian barcode yang tidak valid
  di C# dengan Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- generate barcode image
- how to generate barcode
- invalid barcode example
- how to catch barcode
language: id
lastmod: 2026-08-22
og_description: Tutorial generator barcode menjelaskan cara menghasilkan gambar barcode,
  memvalidasi data, dan menangkap kesalahan barcode dalam C# menggunakan Aspose.BarCode.
og_image_alt: barcode generator tutorial showing exception handling for invalid codes
og_title: Tutorial pembuat barcode – tangkap kode tidak valid di C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Barcode generator tutorial showing how to generate barcode image, validate
    input, and catch invalid barcode exceptions in C# with Aspose.BarCode.
  headline: 'Barcode generator tutorial: catch invalid codes in C#'
  type: TechArticle
tags:
- barcode
- C#
- exception‑handling
title: 'Tutorial generator barcode: tangkap kode tidak valid di C#'
url: /id/python-java/general/barcode-generator-tutorial-catch-invalid-codes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial Generator Barcode – Menangkap Kode Tidak Valid di C#

Jika Anda mencari **tutorial generator barcode** yang tidak hanya membuat gambar barcode tetapi juga melindungi aplikasi Anda dari input yang buruk, Anda berada di tempat yang tepat. Panduan ini membawa Anda melalui alur kerja lengkap: menginstal pustaka, mengonfigurasi validasi, menghasilkan gambar, dan menangani pengecualian ketika teks kode tidak valid.

Membuat barcode merupakan kebutuhan umum untuk sistem pengiriman, inventaris, dan point‑of‑sale. Namun, memasukkan string yang salah ke dalam generator dapat menyebabkan kesalahan runtime atau menghasilkan barcode yang tidak dapat dibaca. Pada akhir tutorial ini Anda akan memahami **cara menghasilkan barcode** secara aman dan melihat **contoh barcode tidak valid** yang praktis dengan penanganan error yang tepat.

## Apa yang Anda Butuhkan

- .NET 6.0 (atau versi .NET terbaru)
- Visual Studio 2022 atau IDE C# lainnya
- Paket NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Familiaritas dasar dengan penanganan pengecualian C#

## Langkah 1: Instal dan Referensikan Aspose.BarCode

Buka proyek Anda di Visual Studio, lalu jalankan perintah NuGet berikut:

```powershell
Install-Package Aspose.BarCode
```

Paket ini menambahkan namespace `Aspose.BarCode`, yang berisi kelas `BarcodeGenerator` yang digunakan sepanjang tutorial ini.

## Langkah 2: Buat generator barcode dengan nilai yang sengaja salah

Bagian pertama dari **contoh barcode tidak valid** menunjukkan cara menginstansiasi generator untuk simbol *Planet* dengan kode yang melanggar spesifikasi.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Planet symbology – the string is too long and contains illegal characters
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
```

> **Mengapa ini penting** – `EncodeTypes.Planet` mengharapkan string numerik dengan panjang tertentu. Memberikan `"1234567WRONG"` memicu logika validasi di dalam pustaka.

## Langkah 3: Aktifkan validasi ketat sehingga pustaka melempar pengecualian

Secara default Aspose.BarCode berusaha memperbaiki kesalahan kecil. Untuk skenario **cara menangkap barcode** yang kuat, Anda harus mengaktifkan validasi eksplisit:

```csharp
            // Step 3.1: Tell the generator to throw when the code text is incorrect
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;
```

> **Penjelasan** – Menetapkan `ThrowExceptionWhenCodeTextIncorrect` ke `true` memaksa API untuk mengeluarkan `ArgumentException` jika teks yang diberikan tidak memenuhi aturan simbol. Ini adalah pendekatan yang disarankan ketika Anda perlu menjamin integritas data.

## Langkah 4: Hasilkan gambar barcode dalam blok try‑catch

Sekarang kita mencoba menghasilkan gambar dan menangkap error yang diharapkan:

```csharp
            try
            {
                // Step 4.1: Attempt to create the barcode image
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 4.2: Handle the validation error
                Console.WriteLine($"Planet error: {ex.Message}");
            }
```

**Output yang Diharapkan**

```
Planet error: The code text is invalid for the selected symbology.
```

Pesan pengecualian mengonfirmasi bahwa pustaka telah mengidentifikasi masalah dengan benar.

## Langkah 5: Ulangi proses untuk simbol lain (Postnet)

Untuk menunjukkan bahwa pola yang sama bekerja untuk jenis barcode apa pun, kami mengulangi langkah-langkah untuk **Postnet**, barcode pos yang umum:

```csharp
            // Step 5.1: Create a Postnet generator with an invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                // Step 5.2: Attempt to generate the Postnet image
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 5.3: Capture the validation error
                Console.WriteLine($"Postnet error: {ex.Message}");
            }
        }
    }
}
```

**Output yang Diharapkan**

```
Postnet error: The code text is invalid for the selected symbology.
```

Kedua blok menunjukkan **cara menghasilkan barcode** sambil menangani input yang tidak valid dengan aman.

## Langkah 6: Simpan gambar barcode yang valid (opsional)

Jika Anda kemudian memberikan string yang benar, Anda dapat menyimpan gambar yang dihasilkan ke file:

```csharp
            // Valid example – generate and save a QR code
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
```

> **Tip:** Selalu validasi input pengguna sebelum mengirimkannya ke `BarcodeGenerator`. Bahkan dengan `ThrowExceptionWhenCodeTextIncorrect` dinonaktifkan, string yang tidak valid dapat menghasilkan barcode yang tidak dapat dibaca.

## Kesalahan Umum dan Cara Menghindarinya

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| Menyediakan karakter alfabetik ke simbol yang hanya numerik (mis., Planet, Postnet) | Pustaka secara diam-diam memotong atau mengganti karakter kecuali validasi ketat diaktifkan | Set `ThrowExceptionWhenCodeTextIncorrect = true` |
| Lupa mereferensikan namespace `Aspose.BarCode` | Error pada waktu kompilasi “BarcodeGenerator does not exist” | Add `using Aspose.BarCode.Generation;` at the top of the file |
| Menggunakan paket NuGet yang usang | Simbol baru atau perbaikan bug mungkin tidak ada | Update the package regularly (`dotnet add package Aspose.BarCode --version x.x.x`) |

## Contoh Lengkap yang Dapat Dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan langsung:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet – invalid code
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Planet error: {ex.Message}");
            }

            // Postnet – invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Postnet error: {ex.Message}");
            }

            // Valid QR code – optional saving
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
        }
    }
}
```

Menjalankan program ini mencetak dua pesan error untuk barcode tidak valid dan membuat file `qr.png` untuk QR code yang valid.

## Kesimpulan

Tutorial **generator barcode** ini menunjukkan cara **menghasilkan objek gambar barcode**, menerapkan validasi ketat, dan **cara menangkap pengecualian terkait barcode** di C#. Dengan mengaktifkan `ThrowExceptionWhenCodeTextIncorrect`, Anda mengubah input yang tidak valid menjadi error yang dapat dikelola alih-alih kegagalan diam.

Dari sini Anda dapat:

- Jelajahi simbol lain seperti Code128, EAN13, atau DataMatrix.
- Sesuaikan warna, ukuran, dan margin melalui `GeneratorParameters`.
- Integrasikan pembuatan barcode ke dalam API ASP.NET Core atau aplikasi Windows Forms.

Ingat, memvalidasi input **sebelum** Anda memanggil `GenerateBarCodeImage` adalah cara paling aman untuk menjaga sistem Anda tetap andal dan pemindaian Anda bebas error. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara Menghasilkan Gambar Barcode dengan Kustomisasi Ruang Tambahan menggunakan Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah demi Langkah](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cara menghasilkan barcode Aztec dengan rasio aspek khusus menggunakan Aspose.BarCode untuk .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}