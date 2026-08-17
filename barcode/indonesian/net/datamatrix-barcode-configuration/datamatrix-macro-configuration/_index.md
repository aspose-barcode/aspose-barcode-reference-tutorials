---
date: 2026-08-17
description: Pelajari cara membuat barcode DataMatrix dengan macro characters menggunakan
  Aspose.BarCode untuk .NET dan temukan cara menggunakan DataMatrix dalam aplikasi
  Anda.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Konfigurasi Macro DataMatrix
og_description: Pelajari cara membuat barcode DataMatrix dengan macro characters menggunakan
  Aspose.BarCode untuk .NET. Panduan ini menyediakan kode langkah‑demi‑langkah, opsi
  kustomisasi, dan tips verifikasi untuk menghasilkan barcode yang andal.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Buat barcode DataMatrix dengan macro characters menggunakan Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Cara membuat barcode DataMatrix dengan macro characters di .NET
url: /id/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode DataMatrix dengan karakter makro di .NET

## Pendahuluan

Membuat **barcode DataMatrix** yang mencakup karakter makro memungkinkan Anda menyimpan informasi referensi tambahan ke dalam simbol kotak kecil. Dalam tutorial ini Anda akan belajar cara **membuat barcode DataMatrix** dengan karakter makro menggunakan Aspose.BarCode untuk .NET, menyesuaikan ukuran dan koreksi kesalahan, serta langsung memverifikasi hasilnya. Pada akhir tutorial Anda akan siap menyematkan barcode dengan makro dalam label produk, dokumen, atau perangkat medis.

## Jawaban Cepat
- **Apa perpustakaan utama?** Aspose.BarCode for .NET  
- **Bisakah saya membuat barcode DataMatrix dengan karakter makro?** Yes – set the `MacroCharacters` property.  
- **Apakah saya memerlukan lisensi untuk produksi?** A valid Aspose license is required for production use.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Apakah tersedia percobaan gratis?** Absolutely – download it from the official Aspose site.

## Prasyarat

Sebelum menyelami konfigurasi makro, pastikan Anda memiliki hal berikut:

1. **Visual Studio** – versi terbaru apa pun akan berfungsi.  
2. **Aspose.BarCode untuk .NET** – unduh dari [the download link](https://releases.aspose.com/barcode/net/).  
3. **Pengetahuan dasar .NET** – familiaritas dengan C# dan ekosistem .NET.

## Impor namespace

Kami mulai dengan mengimpor namespace yang diperlukan untuk pembuatan dan pengenalan barcode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Apa itu “generate DataMatrix barcode” dengan karakter makro?

`MacroCharacters` memungkinkan barcode DataMatrix menyertakan simbol makro yang merujuk ke data tambahan. Dengan menggunakan karakter makro seperti Macro05 atau Macro06, satu barcode dapat menunjuk ke kumpulan data yang lebih besar atau urutan barcode terkait, yang berguna dalam logistik, manufaktur, dan pelacakan dokumen di mana pengkodean kompak informasi terhubung diperlukan.

## Mengapa menggunakan Aspose.BarCode untuk menghasilkan barcode DataMatrix?

Aspose.BarCode memberi Anda kontrol yang tepat atas ukuran DataMatrix, tingkat koreksi kesalahan, dan pengaturan makro, mendukung lebih dari 30 simbol barcode serta menangani file hingga 10 MB tanpa memuat seluruh gambar ke memori. Implementasi .NET lintas‑platformnya bekerja pada .NET Framework, .NET Core, dan .NET 5/6, serta menyertakan pengenalan bawaan sehingga Anda dapat memvalidasi barcode secara langsung.

## Panduan langkah demi langkah

### Langkah 1: menyiapkan proyek Anda

Buat aplikasi Konsol baru (atau proyek .NET apa pun) di Visual Studio. Tambahkan referensi ke DLL Aspose.BarCode yang Anda dapatkan dari unduhan.

### Langkah 2: konfigurasi makro DataMatrix

Inti tutorial – di sini kami benar‑benar **membuat barcode DataMatrix** dengan karakter makro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Pro tip:** Ganti `"ASPOSE"` dengan string apa pun yang ingin Anda enkode. Karakter makro (`Macro05`) memberi tahu pemindai bahwa barcode ini merupakan bagian dari urutan makro.

### Langkah 3: sesuaikan parameter barcode untuk koreksi kesalahan

Sebelum menyimpan, Anda dapat menyesuaikan pengaturan tambahan:

- **XDimension** – mengontrol ukuran setiap modul (piksel).  
- **Margin**, **ErrorCorrection**, dan **EncodingMode** – semua dapat diakses melalui `gen.Parameters.Barcode.DataMatrix`.

### Langkah 4: simpan barcode

Potongan kode di atas menyimpan gambar sebagai `DataMatrixMacro.png` di folder yang Anda tentukan. PNG bersifat loss‑less, menjadikannya ideal untuk pemrosesan lebih lanjut.

### Langkah 5: kenali barcode

`BarCodeReader` adalah kelas Aspose.BarCode untuk mendekode barcode dari gambar. Dengan menggunakan `BarCodeReader` kami langsung membaca kembali gambar yang dihasilkan untuk memastikan bahwa karakter makro dan data sudah benar. Validasi putar‑balik ini sangat berguna selama pengujian otomatis.

## Bagaimana cara menggunakan DataMatrix dalam skenario dunia nyata?

Anda dapat menerapkan barcode DataMatrix dengan karakter makro pada pelabelan produk, menghubungkan nomor seri ke basis data pusat, pada pelacakan dokumen dengan menyematkan referensi ke catatan digital, dan pada tag peralatan kesehatan yang menyimpan data pasien atau perangkat dalam simbol kecil yang dapat dipindai. Kasus penggunaan ini mengurangi entri data manual dan meningkatkan keterlacakan.

## Masalah umum & solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Barcode tidak dikenali | `XDimension` tidak tepat atau resolusi gambar rendah | Tingkatkan `XDimension.Pixels` menjadi 4‑6 dan simpan sebagai PNG atau TIFF |
| Karakter makro diabaikan | Pembaca tidak mendukung mode makro | Gunakan pemindai/pembaca yang secara eksplisit mendukung makro DataMatrix (misalnya versi ZXing yang lebih baru) |
| Path tidak ditemukan | Variabel `path` tidak valid | Pastikan direktori ada atau gunakan `Path.Combine` dengan `Environment.CurrentDirectory` |

## Pertanyaan yang sering diajukan

**Q: Apa itu Aspose.BarCode untuk .NET?**  
A: Aspose.BarCode untuk .NET adalah perpustakaan kuat yang memungkinkan pengembang .NET menghasilkan dan mengenali barcode dalam berbagai format, termasuk DataMatrix, QR, dan lainnya.

**Q: Mengapa saya harus menggunakan barcode DataMatrix?**  
A: Barcode DataMatrix bersifat kompak, sangat handal, dan dapat menyimpan sejumlah besar data, menjadikannya ideal untuk manufaktur, logistik, dan perawatan kesehatan.

**Q: Di mana saya dapat menemukan dokumentasi Aspose.BarCode untuk .NET?**  
A: Anda dapat menemukan dokumentasi di [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q: Apakah tersedia percobaan gratis untuk Aspose.BarCode untuk .NET?**  
A: Ya, Anda dapat mengunduh percobaan gratis dari [the free trial link](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.BarCode untuk .NET?**  
A: Jika Anda memiliki pertanyaan atau membutuhkan dukungan, Anda dapat mengunjungi forum Aspose.BarCode untuk .NET di [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Terakhir Diperbarui:** 2026-08-17  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat barcode aspose .net - Mengonfigurasi Teks Kode DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Konfigurasi Structured Append DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}