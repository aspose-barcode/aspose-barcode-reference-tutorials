---
date: 2026-01-15
description: Panduan tutorial barcode langkah demi langkah untuk membaca barcode DataMatrix
  dengan C# dan menghasilkan gambar barcode C# menggunakan Aspose.BarCode untuk .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Baca barcode DataMatrix C# – Mode Hasilkan DataMatrix (Otomatis)
url: /id/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Kode Batang DataMatrix C# – Hasilkan Mode DataMatrix (Auto)

Di dunia digital yang bergerak cepat saat ini, kemampuan untuk **read DataMatrix barcode C#** dengan cepat dan andal sangat penting untuk segala hal mulai dari pelacakan inventaris hingga penanganan dokumen yang aman. Tutorial ini memandu Anda melalui pembuatan kode DataMatrix dalam mode *Auto* dengan Aspose.BarCode untuk .NET dan kemudian menunjukkan cara membaca kembali kode tersebut di C#. Baik Anda mengikuti **barcode tutorial guide** atau hanya membutuhkan contoh kode yang solid, Anda akan menyelesaikan panduan ini dengan solusi yang dapat langsung digunakan dalam proyek Anda.

## Jawaban Cepat
- **What does “Auto” mode do?** It lets Aspose.BarCode automatically select the best encoding scheme for your data.  
- **Which library is required?** Aspose.BarCode for .NET (free trial available).  
- **Can I read the barcode in the same app?** Yes – use `BarCodeReader` with `DecodeType.DataMatrix`.  
- **Do I need a license for production?** A commercial license is required for production use.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu membaca DataMatrix barcode C#?
Membaca kode DataMatrix di C# berarti mendekode matriks dua dimensi berisi modul hitam‑putih kembali menjadi teks atau data asli. Aspose.BarCode menyediakan API sederhana yang menyembunyikan pemrosesan gambar tingkat rendah, memungkinkan Anda fokus pada logika bisnis.

## Mengapa menggunakan Aspose.BarCode untuk menghasilkan barcode image C#?
- **Reliability:** Handles all DataMatrix standards and automatically selects the optimal encoding.  
- **Flexibility:** Full control over dimensions, ECI encoding, and image format.  
- **Cross‑platform:** Works with .NET Framework, .NET Core, and .NET 5+ applications.  

## Prasyarat

1. **.NET Environment** – Install the latest .NET runtime from the [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Download the library from the [website](https://releases.aspose.com/barcode/net/).  

## Mengimpor Namespace

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Sekarang namespace sudah tersedia, mari kita bahas kode langkah demi langkah.

## Langkah 1: Atur Jalur Direktori

```csharp
string path = "Your Directory Path";
```

Ganti `"Your Directory Path"` dengan folder tempat Anda ingin menyimpan PNG (atau format lain) yang dihasilkan.

## Langkah 2: Buat DataMatrix barcode dalam mode Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Pengaturan `DataMatrixEncodeMode.Auto` memungkinkan perpustakaan menentukan enkoding terbaik untuk teks yang diberikan. Silakan ganti teks contoh dengan string apa pun yang ingin Anda **generate barcode image C#**.

## Langkah 3: Baca barcode (read DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Potongan kode ini mendekode gambar yang baru saja kami hasilkan dan mencetak teks asli ke konsol, memperlihatkan siklus lengkap dari pembuatan hingga pembacaan.

## Masalah Umum dan Solusinya

| Issue | Cause | Fix |
|-------|-------|-----|
| **Tidak ada kode batang terdeteksi** | Resolusi gambar terlalu rendah | Tingkatkan `XDimension.Pixels` (mis., menjadi 6) |
| **Karakter sampah** | Enkoding ECI salah | Atur `ECIEncoding` agar cocok dengan data Anda (UTF‑8, ASCII, dll.) |
| **Exception pada `ReadBarCodes`** | Bitmap dibuang sebelum pembacaan | Jaga agar instance `Bitmap` tetap hidup sampai setelah pembacaan |

## Pertanyaan yang Sering Diajukan

**Q: What is DataMatrix encoding mode "Auto"?**  
A: It allows Aspose.BarCode to automatically select the optimal encoding method for the provided data, simplifying the **how to generate datamatrix barcode** process.

**Q: Can I customize the dimensions of the generated barcode?**  
A: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change module size.

**Q: Is Aspose.BarCode for .NET suitable for commercial use?**  
A: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).

**Q: Is there a free trial available?**  
A: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).

**Q: What encoding options are available for DataMatrix barcodes?**  
A: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the desired value via `ECIEncoding`.

## Kesimpulan

Anda kini memiliki contoh lengkap yang siap produksi yang **reads DataMatrix barcode C#**, menghasilkan kode dalam mode Auto, dan memverifikasi hasilnya—semua menggunakan Aspose.BarCode untuk .NET. Bereksperimenlah dengan teks, ukuran, dan pengaturan ECI yang berbeda untuk menyesuaikan skenario Anda, dan lihat dokumentasi resmi [documentation](https://reference.aspose.com/barcode/net/) untuk kustomisasi lebih mendalam.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-15  
**Diuji Dengan:** Aspose.BarCode 24.12 for .NET  
**Penulis:** Aspose  

---