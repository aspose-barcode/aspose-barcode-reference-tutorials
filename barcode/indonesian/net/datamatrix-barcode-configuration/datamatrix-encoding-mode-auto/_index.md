---
date: 2026-08-02
description: Panduan langkah demi langkah tentang cara membaca barcode DataMatrix
  C# dan menghasilkan gambar barcode C# menggunakan Aspose.BarCode for .NET dengan
  enkoding otomatis.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Mode Enkoding DataMatrix (Auto)
og_description: Pelajari cara membaca barcode DataMatrix C# dan menghasilkan dalam
  mode Auto menggunakan Aspose.BarCode for .NET. Tutorial ini mencakup penyiapan,
  kode, dan pemecahan masalah.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Cara membaca barcode DataMatrix C# – Mode Otomatis
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Cara membaca barcode DataMatrix C# – Mode Otomatis
url: /id/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Kode DataMatrix C# – Mode Otomatis

Di dunia digital yang bergerak cepat saat ini, **cara membaca datamatrix** dengan cepat dan andal sangat penting untuk pelacakan inventaris, penanganan dokumen yang aman, dan banyak skenario perusahaan lainnya. Tutorial ini memandu Anda melalui pembuatan kode bar DataMatrix dalam mode *Auto* dengan Aspose.BarCode untuk .NET dan kemudian menunjukkan cara membaca kembali kode bar tersebut di C#. Baik Anda mengikuti panduan tutorial kode bar atau membutuhkan contoh kode siap pakai, Anda akan selesai dengan solusi siap produksi yang dapat Anda masukkan ke proyek .NET mana pun.

## Jawaban Cepat
- **Apa yang dilakukan mode “Auto”?** Ini memungkinkan Aspose.BarCode secara otomatis memilih skema enkoding terbaik untuk data Anda.  
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode untuk .NET (versi percobaan gratis tersedia).  
- **Bisakah saya membaca kode bar di aplikasi yang sama?** Ya – gunakan `BarCodeReader` dengan `DecodeType.DataMatrix`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` adalah kelas Aspose.BarCode untuk memindai gambar dan mengambil informasi kode bar.

## Apa itu Membaca Kode DataMatrix C#?
Membaca kode bar DataMatrix di C# berarti mendekode matriks dua‑dimensi dari modul hitam dan putih kembali menjadi teks atau data asli. Aspose.BarCode mengabstraksi pemrosesan gambar tingkat rendah, sehingga Anda dapat fokus pada logika bisnis sementara perpustakaan menangani koreksi kesalahan, pemilihan ukuran simbol, dan dukungan Unicode secara otomatis.

## Mengapa Menggunakan Aspose.BarCode untuk Menghasilkan Gambar Kode Bar C#?
Aspose.BarCode secara otomatis memilih enkoding optimal, mendukung **lebih dari 30 simbol kode bar**, dan dapat menghasilkan simbol DataMatrix hingga **1558 × 1558 modul** – jauh lebih besar daripada kebanyakan pesaing. Ia berjalan di Windows, Linux, dan macOS tanpa ketergantungan native, memberikan Anda satu API lintas‑platform untuk pembuatan dan pembacaan.

## Prasyarat

1. **Lingkungan .NET** – Instal runtime .NET terbaru dari [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode untuk .NET** – Unduh perpustakaan dari [situs web](https://releases.aspose.com/barcode/net/).  

## Mengimpor Namespace
Namespace `Aspose.BarCode` berisi semua kelas yang Anda perlukan untuk pembuatan dan pembacaan kode bar. Impor di bagian atas file Anda sebelum kode lainnya.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Setelah namespace tersedia, mari kita telusuri kode langkah demi langkah.

## Langkah 1: Atur Jalur Direktori
Pilih folder tempat PNG yang dihasilkan (atau format lain yang didukung) akan disimpan. Jalur ini dapat berupa absolut atau relatif terhadap proyek Anda.

```csharp
string path = "Your Directory Path";
```

Ganti `"Your Directory Path"` dengan folder yang Anda inginkan. Menjaga folder output dapat dikonfigurasi membuat tutorial dapat digunakan kembali di berbagai lingkungan.

## Langkah 2: Buat Kode Bar DataMatrix dalam Mode Auto
`DataMatrixEncodeMode.Auto` memberi tahu generator untuk secara otomatis memilih skema enkoding optimal untuk data yang diberikan.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Silakan ganti teks contoh dengan string apa pun yang Anda perlukan untuk **cara menghasilkan datamatrix**. Mode auto akan secara otomatis beralih antara Base‑256, ASCII, atau skema lain untuk menghasilkan simbol terkecil yang memungkinkan.

## Langkah 3: Baca Kode Bar (baca Kode DataMatrix C#)
`BarCodeReader` adalah kelas Aspose.BarCode untuk memindai gambar dan mengambil informasi kode bar. Ia mendukung pembacaan dari stream, file, dan objek bitmap, menjadikannya ideal untuk skenario **membaca kode bar dari file**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Potongan kode ini mendekode gambar yang baru saja kami hasilkan dan mencetak teks asli ke konsol, memperlihatkan siklus lengkap dari pembuatan hingga pembacaan.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Tidak ada kode bar terdeteksi** | Resolusi gambar terlalu rendah | Tingkatkan `XDimension.Pixels` (mis., menjadi 6) |
| **Karakter sampah** | Enkoding ECI salah | Setel `ECIEncoding` agar cocok dengan data Anda (UTF‑8, ASCII, dll.) |
| **Pengecualian pada `ReadBarCodes`** | Bitmap dibuang sebelum pembacaan | Pertahankan instance `Bitmap` tetap hidup sampai setelah pembacaan |

## Pertanyaan yang Sering Diajukan

**Q: Apa itu mode enkoding DataMatrix "Auto"?**  
A: Ini memungkinkan Aspose.BarCode secara otomatis memilih metode enkoding optimal untuk data yang diberikan, menyederhanakan proses **cara menghasilkan datamatrix**.

**Q: Bisakah saya menyesuaikan dimensi kode bar yang dihasilkan?**  
A: Ya – sesuaikan `generator.Parameters.Barcode.XDimension.Pixels` untuk mengubah ukuran modul.

**Q: Apakah Aspose.BarCode untuk .NET cocok untuk penggunaan komersial?**  
A: Tentu saja. Beli lisensi dari [situs web](https://purchase.aspose.com/buy).

**Q: Apakah tersedia versi percobaan gratis?**  
A: Ya, Anda dapat menjelajahi Aspose.BarCode dengan versi percobaan gratis dari [tautan ini](https://releases.aspose.com/).

**Q: Opsi enkoding apa yang tersedia untuk kode bar DataMatrix?**  
A: Aspose.BarCode mendukung UTF‑8, ASCII, dan enkoding ECI lainnya; atur nilai yang diinginkan melalui `ECIEncoding`.

## Kesimpulan

Anda kini memiliki contoh lengkap yang siap produksi yang **membaca kode bar DataMatrix C#**, menghasilkan kode bar dalam mode Auto, dan memverifikasi hasilnya—semua menggunakan Aspose.BarCode untuk .NET. Bereksperimenlah dengan teks, ukuran, dan pengaturan ECI yang berbeda untuk menyesuaikan skenario spesifik Anda, dan lihat [dokumentasi](https://reference.aspose.com/barcode/net/) resmi untuk kustomisasi lebih mendalam.

---

**Terakhir Diperbarui:** 2026-08-02  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membaca Kode Bar DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/)
- [Konfigurasi Structured Append DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Pemrograman Pembaca DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}