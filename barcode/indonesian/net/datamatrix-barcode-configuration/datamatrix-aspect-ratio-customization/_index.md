---
date: 2026-01-12
description: Pelajari cara membuat PNG barcode dengan rasio aspek DataMatrix khusus
  menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk menghasilkan
  barcode dan menyesuaikan ukuran.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode
url: /id/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membuat PNG Barcode – Rasio Aspek DataMatrix – Aspose.BarCode

Membuat **barcode PNG** dengan rasio aspek DataMatrix khusus adalah kebutuhan umum ketika Anda perlu barcode agar sesuai dengan batasan tata letak tertentu. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk **membuat file barcode PNG** menggunakan Aspose.BarCode untuk .NET, menjelaskan mengapa Anda mungkin ingin menyesuaikan rasio aspek, dan menunjukkan cara menyempurnakan output untuk aplikasi Anda.

## Jawaban Cepat
- **Apa yang dikontrol oleh “rasio aspek”?** Ini mendefinisikan proporsi lebar‑ke‑tinggi dari modul DataMatrix.  
- **Apakah saya dapat menghasilkan PNG, JPEG, atau SVG?** Ya – metode `Save` mendukung PNG, JPEG, BMP, GIF, dan lainnya.  
- **Apakah saya memerlukan lisensi untuk fitur ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Berapa banyak nilai rasio‑aspek yang valid?** Semua nilai float positif; nilai tipikal adalah 0.5 – 2.0.

## Apa itu barcode DataMatrix dan mengapa menyesuaikan rasio aspeknya?
DataMatrix adalah barcode matriks 2‑dimensi yang menyimpan sejumlah besar data dalam ruang kecil. Menyesuaikan **rasio aspek** memungkinkan Anda memperlebar atau mempersempit modul secara horizontal, yang dapat berguna untuk menempatkan barcode ke dalam kolom sempit atau label lebar tanpa mengorbankan keterbacaan.

## Prasyarat

Sebelum kita mulai menyesuaikan rasio aspek DataMatrix, pastikan Anda memiliki prasyarat berikut:

1. **Visual Studio** – versi terbaru apa pun dapat digunakan.  
2. **Aspose.BarCode untuk .NET** – unduh di [sini](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – proyek Anda harus menargetkan versi yang didukung.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.BarCode.Generation;
```

> **Tips Pro:** Simpan pernyataan `using` ini di bagian atas file Anda sehingga kelas `BarcodeGenerator` selalu tersedia.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Proyek Anda
Buat proyek konsol atau Windows Forms baru di Visual Studio dan tambahkan referensi ke DLL Aspose.BarCode.

### Langkah 2: Inisialisasi Barcode Generator
Buat instance `BarcodeGenerator` dengan tipe DataMatrix dan data yang ingin Anda enkode:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Baris ini membuat generator yang siap menghasilkan barcode DataMatrix yang berisi teks contoh.

### Langkah 3: Sesuaikan Rasio Aspek dan Simpan File PNG
Sekarang Anda dapat mengubah **rasio aspek** dan menyimpan setiap versi sebagai gambar PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Panggilan pertama membuat barcode dengan proporsi persegi (`AspectRatio = 1`).  
- Panggilan kedua mempersempit barcode secaraAspectRatio = 0.5`), menghasilkan tampilan yang lebih lebar.

Sekarang Anda memiliki dua file **barcode PNG** dengan rasio aspek berbeda yang siap digunakan dalam laporan, label, atau elemen UI.

## Masalah Umum & Solusi

| Masalah | Solusi |
|-------|----------|
| **Gambar yang dihasilkan buram** | Tingkatkan parameter `Resolution` sebelum menyimpan (`gen.Parameters.ImageResolution = 300`). |
| **Barcode tidak dapat dipindai** | Pastikan rasio aspek tetap dalam rentang 0.5 – 2.0 dan pertahankan zona tenang yang cukup (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Kesalahan jalur file** | Gunakan `Path.Combine` untuk membangun jalur output dan pastikan foldernya ada. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menyesuaikan rasio aspek tipe barcode lain menggunakan Aspose.BarCode untuk .NET?**  
A: Ya, banyak barcode 2‑D (misalnya QR, PDF417) mendukung penyesuaian rasio‑aspek melalui objek parameter khusus mereka.

**Q: Apakah tersedia versi percobaan gratis untuk Aspose.BarCode untuk .NET?**  
A: Ya, Anda dapat mengakses versi percobaan gratis Aspose.BarCode untuk .NET [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli lisensi untuk Aspose.BarCode untuk .NET?**  
A: Anda dapat membeli lisensi di situs web Aspose [di sini](https://purchase.aspose.com/buy).

**Q: Apakah Aspose.BarCode untuk .NET kompatibel dengan berbagai versi .NET Framework?**  
A: Ya, ia bekerja dengan .NET Framework 4.x, .NET Core 3.1+, dan rilis .NET terbaru.

**Q: Bisakah saya menghasilkan barcode dalam format berbeda dengan Aspose.BarCode untuk .NET?**  
A: Tentu – PNG, JPEG, BMP, GIF, TIFF, SVG, dan PDF semuanya didukung secara langsung.

## Kesimpulan

Menyesuaikan **rasio aspek** barcode DataMatrix dan **membuat file barcode PNG** sangat mudah dengan Aspose.BarCode untuk .NET. Dengan mengikuti langkah‑langkah di atas, Anda dapat menghasilkan barcode berukuran tepat yang memenuhi persyaratan tata letak proyek Anda. Jelajahi parameter lain seperti `Resolution`, `Margin`, dan `Color` untuk menyesuaikan output lebih lanjut.

Untuk eksplorasi lebih mendalam, lihat [dokumentasi resmi](https://reference.aspose.com/barcode/net/) atau bergabung dengan komunitas di [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Terakhir Diperbarui:** 2026-01-12  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}