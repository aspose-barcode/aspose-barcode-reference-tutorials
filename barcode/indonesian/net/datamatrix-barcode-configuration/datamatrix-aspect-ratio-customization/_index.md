---
date: 2026-05-30
description: Pelajari cara membuat barcode PNG dengan rasio aspek DataMatrix khusus
  menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk menghasilkan
  barcode dan menyesuaikan ukuran.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Kustomisasi Rasio Aspek DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode
url: /id/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat PNG Barcode – Rasio Aspek DataMatrix – Aspose.BarCode

Membuat **barcode PNG** dengan rasio aspek DataMatrix khusus adalah kebutuhan umum ketika Anda perlu **membuat file barcode PNG** yang sesuai dengan batasan tata letak tertentu. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk **membuat file barcode PNG** menggunakan Aspose.BarCode untuk .NET, menjelaskan mengapa Anda mungkin ingin menyesuaikan rasio aspek, dan menunjukkan cara menyempurnakan output untuk aplikasi Anda.

## Jawaban Cepat
- **Apa yang dikontrol oleh “rasio aspek”?** Ini mendefinisikan proporsi lebar‑ke‑tinggi dari modul DataMatrix.  
- **Apakah saya dapat menghasilkan PNG, JPEG, atau SVG?** Ya – metode `Save` mendukung PNG, JPEG, BMP, GIF, TIFF, SVG, dan PDF.  
- **Apakah saya memerlukan lisensi untuk fitur ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa banyak nilai rasio‑aspek yang valid?** Semua nilai float positif; nilai tipikal adalah 0.5 – 2.0.

## Apa itu barcode DataMatrix dan mengapa menyesuaikan rasio aspeknya?
Barcode DataMatrix adalah kode matriks dua dimensi yang menyimpan sejumlah besar data dalam bentuk kotak yang kompak. Menyesuaikan **rasio aspek** memungkinkan Anda memperlebar atau mempersempit modul secara horizontal, yang berguna ketika Anda perlu menempatkan barcode ke dalam kolom sempit atau label lebar tanpa mengorbankan keandalan pemindaian.

## Mengapa menggunakan Aspose.BarCode untuk membuat PNG barcode?
Aspose.BarCode mendukung **7 format gambar** — PNG, JPEG, BMP, GIF, TIFF, SVG, dan PDF — dan dapat memproses **lebih dari 50 format input dan output** dalam memori, menangani dokumen ratusan halaman tanpa harus memuat seluruh file. Perpustakaan ini menyediakan API yang fluida yang memungkinkan Anda menghasilkan barcode DataMatrix dalam satu baris kode, menjamin rendering pixel‑perfect dan kompatibilitas penuh dengan .NET.

## Prasyarat

Sebelum kita mulai menyesuaikan rasio aspek DataMatrix, pastikan Anda memiliki prasyarat berikut:

1. **Visual Studio** – versi terbaru apa pun dapat digunakan.  
2. **Aspose.BarCode untuk .NET** – unduh di [sini](https://releases.aspose.com/barcode/net/).  
3. Anda juga dapat menjelajahi rilis produk Aspose lainnya [di sini](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – proyek Anda harus menargetkan versi yang didukung.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda:

`using Aspose.BarCode.Generation;` mengimpor namespace yang berisi kelas-kelas generasi barcode.  

```csharp
using Aspose.BarCode.Generation;
```

> **Tip Pro:** Simpan pernyataan `using` ini di bagian atas file Anda sehingga kelas `BarcodeGenerator` selalu tersedia.

## Cara membuat PNG barcode dengan rasio aspek khusus?

Muat `BarcodeGenerator`, atur tipe DataMatrix, sesuaikan properti `AspectRatio`, dan panggil `Save`. Pola satu baris ini membuat PNG barcode yang menghormati rasio yang Anda tentukan, dan perpustakaan secara otomatis menangani skala modul serta zona tenang.

`BarcodeGenerator` membuat gambar barcode dari simbologi dan data yang ditentukan.

### Langkah 1: Siapkan Proyek Anda
Buat proyek console atau Windows Forms baru di Visual Studio dan tambahkan referensi ke DLL Aspose.BarCode.

### Langkah 2: Inisialisasi Generator Barcode
Buat instance dengan simbologi DataMatrix dan data yang ingin Anda enkode:

`BarcodeGenerator` membuat gambar barcode dari simbologi dan data yang ditentukan.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Baris ini membuat generator yang siap menghasilkan barcode DataMatrix yang berisi teks contoh.

### Langkah 3: Sesuaikan Rasio Aspek dan Simpan File PNG
Sekarang Anda dapat mengubah **rasio aspek** dan menyimpan setiap versi sebagai gambar PNG:

`AspectRatio` mengatur proporsi lebar‑ke‑tinggi dari modul DataMatrix.  
`Save` menulis gambar barcode yang dihasilkan ke file dalam format yang dipilih.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Panggilan pertama membuat barcode dengan proporsi persegi (`AspectRatio = 1`).  
- Panggilan kedua mempersempit barcode secara horizontal (`AspectRatio = 0.5`), menghasilkan tampilan yang lebih lebar.

Sekarang Anda memiliki dua file **barcode PNG** dengan rasio aspek berbeda yang siap digunakan dalam laporan, label, atau elemen UI.

## Masalah Umum & Solusi

| Masalah | Solusi |
|-------|----------|
| **Gambar yang dihasilkan buram** | Tingkatkan parameter `Resolution` sebelum menyimpan (`gen.Parameters.ImageResolution = 300`). |
| **Barcode tidak dapat dipindai** | Pastikan rasio aspek tetap dalam rentang 0.5 – 2.0 dan pertahankan zona tenang yang cukup (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Kesalahan jalur file** | Gunakan `Path.Combine` untuk membangun jalur output dan pastikan folder ada. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menyesuaikan rasio aspek tipe barcode lain menggunakan Aspose.BarCode untuk .NET?**  
A: Ya, banyak barcode 2‑D (mis., QR, PDF417) mendukung penyesuaian rasio aspek melalui objek parameter khusus mereka.

**Q: Apakah tersedia percobaan gratis untuk Aspose.BarCode untuk .NET?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.BarCode untuk .NET [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli lisensi untuk Aspose.BarCode untuk .NET?**  
A: Anda dapat membeli lisensi di situs web Aspose [di sini](https://purchase.aspose.com/buy).

**Q: Apakah Aspose.BarCode untuk .NET kompatibel dengan berbagai versi .NET Framework?**  
A: Ya, ia bekerja dengan .NET Framework 4.x, .NET Core 3.1+, dan rilis .NET terbaru.

**Q: Bisakah saya menghasilkan barcode dalam format berbeda dengan Aspose.BarCode untuk .NET?**  
A: Tentu – PNG, JPEG, BMP, GIF, TIFF, SVG, dan PDF semuanya didukung secara langsung.

## Kesimpulan

Menyesuaikan **rasio aspek** barcode DataMatrix dan **membuat file barcode PNG** sangat mudah dengan Aspose.BarCode untuk .NET. Dengan mengikuti langkah‑langkah di atas, Anda dapat menghasilkan barcode berukuran tepat yang memenuhi persyaratan tata letak proyek Anda. Jelajahi parameter tambahan seperti `Resolution`, `Margin`, dan `Color` untuk menyesuaikan output lebih lanjut, dan pertimbangkan kemampuan `generate datamatrix barcode` saat membangun aplikasi yang ramah pemindaian di Visual Studio.

Untuk eksplorasi lebih mendalam, lihat [dokumentasi](https://reference.aspose.com/barcode/net/) resmi atau bergabung dengan komunitas di [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Terakhir Diperbarui:** 2026-05-30  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat Barcode DataMatrix – Panduan Pro dengan Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Kuasi Enkoding DataMatrix dalam ASCII dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}