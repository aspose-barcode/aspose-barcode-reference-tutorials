---
date: 2026-09-23
description: Pelajari cara menggunakan Aspose.BarCode untuk menghasilkan barcode DataMatrix
  dengan teks kode yang diperluas di .NET, ideal untuk aplikasi inventaris dan logistik.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Konfigurasi Teks Kode DataMatrix yang Diperluas
og_description: Cara menggunakan Aspose.BarCode untuk menghasilkan barcode DataMatrix
  dengan teks kode yang diperluas di .NET. Ikuti panduan langkah demi langkah yang
  cepat untuk solusi inventaris dan logistik.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Cara menggunakan Aspose.BarCode untuk membuat teks kode DataMatrix di .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Cara menggunakan Aspose.BarCode untuk membuat teks kode DataMatrix di .NET
url: /id/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan Aspose.BarCode untuk membuat teks kode DataMatrix di .NET

Mengintegrasikan barcode ke dalam aplikasi .NET modern tidak lagi menjadi tugas niche—ini menjadi kebutuhan inti untuk inventaris, logistik, dan solusi pemindaian seluler. Dalam panduan ini Anda akan **mempelajari cara menggunakan Aspose.BarCode** untuk mengonfigurasi barcode DataMatrix dengan teks kode yang diperluas, menghasilkan gambar, dan memverifikasinya secara programatik. Anda akan melihat mengapa pendekatan ini ideal untuk membuat barcode untuk inventaris dan bagaimana ia cocok dalam proyek .NET Core atau .NET 6.

## Jawaban cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.BarCode untuk .NET  
- **Jenis barcode apa?** DataMatrix dengan teks kode yang diperluas  
- **Bisakah saya menggunakan .NET Core / .NET 6?** Ya, API bersifat lintas‑platform  
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar  

## Apa itu Aspose.BarCode untuk .NET?
Aspose.BarCode untuk .NET adalah perpustakaan komersial yang memungkinkan pengembang menghasilkan dan mengenali lebih dari 30 simbol barcode, termasuk DataMatrix, QR, dan Code 128, serta menghasilkan gambar hingga 10.000 × 10.000 piksel tanpa ketergantungan eksternal. Ia mendukung .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6/7.

## Mengapa menggunakan teks kode DataMatrix yang diperluas?
Teks kode DataMatrix yang diperluas memungkinkan Anda menyematkan beberapa skema enkoding—UTF‑8, C40, Text, X12—dalam satu simbol, memungkinkan hingga **3116 codewords** (sekitar 155 KB data) dalam satu kotak kompak. Kemampuan ini sempurna untuk pelabelan produk multibahasa, pelacakan perangkat medis, dan kemasan pintar di mana Anda perlu menggabungkan ID alfanumerik dengan muatan biner.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Aspose.BarCode untuk .NET** – unduh dari situs resmi **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Lingkungan pengembangan .NET** – Visual Studio, Rider, atau VS Code dengan .NET SDK.  
3. **Pengetahuan dasar C#** – Anda harus nyaman dengan kelas, namespace, dan direktif `using`.

## Impor namespace

Tambahkan namespace yang diperlukan di bagian atas file C# Anda agar kompilator mengetahui lokasi kelas barcode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Namespace ini memberi Anda akses ke fitur generasi dan pengenalan barcode.

## Cara mengonfigurasi teks kode DataMatrix yang diperluas?

Muat builder, tambahkan segmen yang diinginkan, dan biarkan Aspose.BarCode menangani penanda ECI secara otomatis. Paragraf jawaban langsung ini memberi Anda langkah‑langkah tepat: buat `DataMatrixExtCodetextBuilder`, tambahkan segmen Unicode, C40, teks biasa, dan mode Text, lalu ambil string gabungan untuk generator.

### Langkah 1: Tentukan folder output

Tentukan di mana gambar barcode yang dihasilkan akan disimpan. Ganti placeholder dengan jalur yang valid di mesin Anda.

```csharp
string path = "Your Directory Path";
```

### Langkah 2: Bangun teks kode yang diperluas

`DataMatrixExtCodetextBuilder` adalah kelas pembantu yang menyusun teks kode yang diperluas sesuai spesifikasi DataMatrix. Ia secara otomatis menyisipkan penanda ECI (Extended Channel Interpretation) yang diperlukan.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Campuran ini menunjukkan cara Anda dapat menggabungkan karakter Unicode, enkoding C40, teks biasa, dan mode Text dalam satu simbol DataMatrix.

### Langkah 3: Hasilkan string teks kode akhir

Setelah mengonfigurasi semua bagian, ambil string gabungan yang akan disematkan Aspose.BarCode ke dalam barcode.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Langkah 4: Buat barcode DataMatrix

`BarcodeGenerator` adalah kelas inti yang menghasilkan gambar barcode. Instansiasi dengan `EncodeTypes.DataMatrix` dan teks kode yang diperluas, lalu atur parameter visual seperti dimensi‑X, format gambar, dan teks yang dapat dibaca manusia secara opsional.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Kode di atas **membuat barcode aspose .net** dengan teks kode yang diperluas dan menyimpannya sebagai file PNG.

### Langkah 5: Verifikasi barcode dengan membacanya kembali

`BarCodeReader` memvalidasi bahwa simbol yang dihasilkan dapat didekode dengan benar, yang penting untuk pipeline pengujian otomatis dan jaminan kualitas.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Jika semuanya telah diatur dengan benar, konsol akan menampilkan teks kode yang diperluas persis seperti yang Anda buat sebelumnya.

## Kesalahan umum dan pemecahan masalah

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Barcode tidak dapat dibaca | Dimensi‑X terlalu rendah | Tingkatkan `XDimension.Pixels` (misalnya, 4 → 6) |
| Karakter kacau | Enkoding ECI salah | Pastikan `ECIEncodings.UTF8` cocok dengan set karakter |
| File tidak tersimpan | Jalur tidak valid | Gunakan jalur absolut atau pastikan folder ada |
| Pengecualian lisensi | Versi percobaan kedaluwarsa | Terapkan lisensi sementara atau penuh (lihat FAQ) |

## Pertanyaan yang Sering Diajukan

### Q1: Apa itu Aspose.BarCode untuk .NET?
A1: Aspose.BarCode untuk .NET adalah perpustakaan kuat yang memungkinkan pengembang menghasilkan dan mengenali berbagai simbol barcode, termasuk DataMatrix, QR, Code128, dan lainnya.

### Q2: Di mana saya dapat menemukan dokumentasi untuk Aspose.BarCode untuk .NET?
A2: Anda dapat mengakses referensi API lengkap **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Apakah ada versi percobaan gratis untuk Aspose.BarCode untuk .NET?
A3: Ya, versi percobaan gratis dapat diunduh dari **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Bagaimana cara memperoleh lisensi sementara untuk pengujian?
A4: Lisensi sementara disediakan untuk tujuan evaluasi dan dapat diminta melalui **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Di mana saya dapat mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk .NET?
A5: Forum resmi Aspose.BarCode adalah tempat terbaik untuk mencari bantuan: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Terakhir Diperbarui:** 2026-09-23  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah demi Langkah](/barcode/net/datamatrix-barcode-configuration/)
- [Buat barcode DataMatrix dalam mode ASCII dengan Aspose.BarCode untuk .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Buat Barcode Aztec dengan Enkoding Teks menggunakan Aspose.BarCode untuk .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}