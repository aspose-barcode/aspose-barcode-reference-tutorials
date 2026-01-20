---
date: 2026-01-20
description: Pelajari cara menghasilkan kode batang DataMatrix dan mendekode kode
  batang DataMatrix dengan konfigurasi structured append di .NET menggunakan Aspose.BarCode
  untuk organisasi data yang sangat efisien.
linktitle: DataMatrix Structured Append Configuration
second_title: Aspose.BarCode .NET API
title: Cara menghasilkan kode batang DataMatrix dengan Structured Append menggunakan
  Aspose.BarCode untuk .NET
url: /id/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Structured Append DataMatrix dengan Aspose.BarCode untuk .NET

Jika Anda seorang pengembang yang ingin **menghasilkan barcode DataMatrix** dengan konfigurasi structured append dalam aplikasi .NET Anda, Aspose.BarCode untuk .NET adalah solusi pilihan Anda. Dalam panduan langkah‑demi‑langkah ini kami akan menjelaskan cara membuat dan membaca barcode tersebut, memecah setiap contoh menjadi bagian‑bagian yang mudah diikuti sehingga Anda dapat menguasai alur kerja dengan cepat.

## Quick Answers
- **Perpustakaan apa yang harus saya gunakan?** Aspose.BarCode for .NET  
- **Berapa banyak baris kode?** Sekitar 30 baris untuk menghasilkan dan membaca barcode DataMatrix terstruktur  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Platform yang didukung?** .NET Framework, .NET Core, .NET 5/6/7  
- **Apakah saya juga dapat mendekode barcode?** Ya – lihat bagian “How to decode DataMatrix barcode”  

## Prerequisites

Sebelum memulai tutorial, pastikan Anda memiliki:

1. **Aspose.BarCode for .NET Library** – unduh dari [here](https://releases.aspose.com/barcode/net/).  
2. **Lingkungan Pengembangan** – Visual Studio (versi terbaru apa pun) atau IDE lain yang kompatibel dengan .NET.

Sekarang, mari kita mulai panduan langkah‑demi‑langkah untuk bekerja dengan structured append DataMatrix menggunakan Aspose.BarCode untuk .NET.

## Import Namespaces

Pertama, impor namespace yang memberi Anda akses ke kelas pembuatan dan pengenalan barcode.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Sekarang Anda siap untuk menghasilkan dan membaca **barcode DataMatrix**.

## How to generate DataMatrix barcode with Structured Append

Cara menghasilkan barcode DataMatrix dengan Structured Append

Untuk membuat barcode DataMatrix structured append, Anda perlu mengkonfigurasi beberapa parameter seperti ID barcode, total jumlah barcode dalam urutan, dan file ID yang menghubungkannya.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Dalam potongan kode ini kami telah mengatur properti penting yang mengaktifkan fitur structured‑append.

## How to decode DataMatrix barcode using Aspose.BarCode

Cara mendekode barcode DataMatrix menggunakan Aspose.BarCode

Setelah menghasilkan barcode, Anda sering perlu membaca informasi yang tertanam di dalamnya. Kode berikut menggunakan `BarCodeReader` untuk mengekstrak detail structured‑append dari gambar yang baru saja kami buat.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Blok ini **mendekode informasi barcode DataMatrix** seperti ID barcode, total hitungan, dan file ID, memastikan bahwa data structured‑append telah tertanam dengan benar.

## Common Issues and Tips

Masalah Umum dan Tips

- **Dimensi tidak tepat:** Pastikan `XDimension.Pixels` sesuai dengan resolusi printer atau layar; jika tidak, barcode mungkin tidak dapat dibaca.  
- **Jumlah tidak cocok:** `StructuredAppendBarcodesCount` harus sama di semua bagian urutan.  
- **Kesalahan lisensi:** Jika Anda melihat peringatan lisensi, pastikan file lisensi percobaan atau komersial telah direferensikan dengan benar dalam proyek Anda.

## Conclusion

Kesimpulan

Aspose.BarCode untuk .NET memudahkan **menghasilkan barcode DataMatrix** dan **mendekode barcode DataMatrix** dengan konfigurasi structured append. Dengan mengikuti langkah‑langkah di atas, Anda dapat meng: DataMatrix structured append adalah fitur yang memungkinkan Anda membagi sejumlah besar data menjadi beberapa barcode yang lebih kecil. Ini sangat berguna ketika Anda memiliki ruang terbatas untuk satu barcode atau perlu mengatur data secara efisien. Fitur ini umum digunakan di industri seperti logistik, perawatan kesehatan, dan manufaktur.

### Q2: Bisakah saya menggunakan Aspose.BarCode untuk .NET dalam proyek open-source saya?

J2: Ya, Aspose.BarCode untuk .NET menyediakan versi percobaan gratis yang dapat Anda gunakan dalam proyek open-source. Anda dapat menemukan versi percobaan [here](https://releases.aspose.com/).

### Q3: Apakah ada dukungan komunitas yang tersedia untuk Aspose.BarCode untuk .NET?

J3: Ya, Anda dapat mencari dukungan komunitas dan berinteraksi dengan pengguna lain di forum Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

J4: Jika Anda memerlukan lisensi sementara untuk evaluasi atau pengujian, Anda dapat memperoleh satu dari [here](https://purchase.aspose.com/temporary-license/).

### Q5: Apakah Aspose.BarCode untuk .NET mendukung jenis barcode lain?

J5: Ya, Aspose.BarCode untuk .NET mendukung berbagai jenis barcode, termasuk QR code, Code 128, EAN-13, dan banyak lagi. Anda dapat menjelajahi dokumentasi lengkap [here](https://reference.aspose.com/barcode/net/) untuk melihat daftar lengkap jenis barcode yang didukung.

---

**Terakhir Diperbarui:** 2026-01-20  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}