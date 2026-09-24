---
date: 2026-08-17
description: Pelajari cara membuat datamatrix barcode aspose menggunakan Aspose.BarCode
  untuk .NET – ideal untuk pembuatan barcode, manajemen inventaris, dan proyek generator
  barcode C#.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 Konfigurasi
og_description: Buat datamatrix barcode aspose menggunakan Aspose.BarCode untuk .NET
  – solusi cepat dan berperforma tinggi untuk manajemen inventaris dan proyek barcode
  C#.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Buat datamatrix barcode aspose dengan Aspose.BarCode untuk .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Cara membuat datamatrix barcode aspose dengan Aspose.BarCode
url: /id/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat barcode datamatrix aspose dengan Aspose.BarCode

Dalam perangkat lunak rantai pasokan modern, Anda sering perlu **membuat barcode datamatrix aspose** dengan cepat dan dapat diandalkan. Tutorial ini memandu Anda menghasilkan simbol DataMatrix ECC 000‑140 dengan Aspose.BarCode untuk .NET, sebuah perpustakaan yang menangani beban berat enkoding, koreksi kesalahan, dan rendering gambar. Pada akhir panduan, Anda akan memiliki potongan kode C# siap pakai yang dapat disisipkan ke dalam proyek manajemen inventaris .NET apa pun.

## Jawaban Cepat
- **Apa perpustakaan utama?** Aspose.BarCode untuk .NET  
- **Jenis barcode apa yang dibahas?** DataMatrix ECC 000‑140  
- **Bahasa apa yang digunakan?** C# (C Sharp)  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi  
- **Waktu implementasi tipikal?** Sekitar 10‑15 menit untuk generator dasar  

## Apa itu DataMatrix ECC 000‑140?
DataMatrix adalah barcode dua dimensi yang menyimpan volume data besar dalam bentuk kotak kompak. Tingkat koreksi kesalahan **ECC 000‑140** dapat memulihkan hingga 140 % kode yang rusak, menjadikannya sempurna untuk lingkungan gudang keras di mana label dapat tergores atau ternoda.

## Mengapa memilih Aspose.BarCode untuk .NET?
Aspose.BarCode untuk .NET menyediakan API komprehensif dan berkinerja tinggi yang menyederhanakan pembuatan barcode di berbagai simbol, menawarkan koreksi kesalahan bawaan, penentuan ukuran otomatis, dan dukungan platform yang luas, menjadikannya ideal untuk solusi inventaris dan pelabelan tingkat perusahaan.

- **API yang kuat:** Menangani lebih dari 30 simbol barcode dan secara otomatis menerapkan aturan enkoding.  
- **Lintas platform:** Berjalan di Windows, macOS, dan Linux tanpa ketergantungan native.  
- **Kinerja tinggi:** Menghasilkan DataMatrix 200 × 200 piksel dalam kurang dari 50 ms pada CPU 2.5 GHz standar, memungkinkan jalur pelabelan berkecepatan tinggi.  

## Prasyarat
Sebelum Anda mulai, pastikan Anda memiliki:

1. **Visual Studio** – edisi terbaru apa pun (Community, Professional, atau Enterprise).  
2. **Aspose.BarCode untuk .NET** – unduh dari [tautan unduhan](https://releases.aspose.com/barcode/net/). Anda juga dapat mengunjungi [tautan ini](https://releases.aspose.com/) untuk sumber daya tambahan.  
3. **Proyek .NET** – siap untuk merujuk assembly Aspose.BarCode.  

## Impor namespace
Di file C# Anda, tambahkan direktif `using` yang diperlukan sehingga Anda dapat mengakses kelas barcode.

```csharp
using Aspose.BarCode.Generation;
```

**Kelas `BarcodeGenerator` adalah inti mesin Aspose.BarCode untuk membuat gambar barcode.**  
**Kelas `BarcodeGenerator` adalah inti mesin Aspose.BarCode yang membuat dan mengkonfigurasi gambar barcode.**  
```csharp
using Aspose.BarCode.Generation;
```

## Kasus penggunaan pembuatan barcode untuk manajemen inventaris
Bayangkan Anda harus memberi label ribuan palet di pusat distribusi. Dengan menghasilkan barcode DataMatrix ECC 000‑140, Anda dapat menyematkan ID produk, nomor batch, dan tanggal kedaluwarsa dalam satu simbol yang tahan kesalahan yang dapat dibaca pemindai genggam secara instan, mengurangi kesalahan entri manual hingga 95 %.

## Cara membuat barcode datamatrix aspose di C#
Muat data, konfigurasikan generator, dan simpan gambar – semua dalam tiga langkah singkat. `BarcodeGenerator` secara otomatis memilih ukuran modul optimal dan menerapkan tingkat koreksi ECC 140, sehingga Anda tidak perlu menghitung nilai checksum secara manual, dengan cepat dan efisien.

### Langkah 1: tentukan direktori output
Pilih folder tempat file PNG akan ditulis. Path harus ada sebelum Anda memanggil `Save`.

```csharp
string path = "Your Directory Path";
```

### Langkah 2: buat generator barcode
Instansiasi `BarcodeGenerator`, atur simbolologi ke DataMatrix, berikan payload, dan pilih tingkat koreksi kesalahan tertinggi.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

Dalam potongan kode ini kami:

* Pilih **DataMatrix** sebagai jenis barcode.  
* Berikan nilai contoh (`"Åspóse.Barcóde©"`).  
* Atur **XDimension** untuk mengontrol ukuran modul (4 piksel di sini).  
* Pilih tingkat koreksi kesalahan tertinggi (**ECC 140**).  
* Simpan output sebagai file PNG.  

## Masalah umum dan solusinya
| Masalah | Solusi |
|-------|----------|
| **Path tidak valid** | Pastikan `path` diakhiri dengan pemisah direktori (`\` atau `/`) dan folder tersebut ada. |
| **Karakter tidak didukung** | DataMatrix mendukung UTF‑8; hindari karakter kontrol dan gunakan enkoding yang tepat. |
| **Lisensi tidak diterapkan** | Kelas `Aspose.BarCode.License` menerapkan lisensi komersial untuk membuka semua fungsi. Panggil sebelum menghasilkan barcode apa pun. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.BarCode untuk .NET di server Linux?**  
A: Ya. Perpustakaan ini sepenuhnya lintas platform dan berjalan pada .NET 5+, .NET 6+, serta .NET Core di Linux tanpa ketergantungan tambahan.

**Q: Bagaimana perpustakaan menangani batch besar barcode?**  
A: Anda dapat menggunakan kembali satu instance `BarcodeGenerator` dalam loop; setiap pemanggilan `Save` merender ulang gambar dalam kira‑kira 40‑60 ms, membuatnya cocok untuk menghasilkan ribuan label per menit.

**Q: Apakah saya perlu mengenkode data secara manual untuk ECC 140?**  
A: Tidak. Menetapkan `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` secara otomatis menerapkan algoritma koreksi kesalahan yang tepat.

**Q: Apakah versi percobaan cukup untuk pengembangan?**  
A: Versi percobaan gratis memberikan akses penuh ke semua fitur, termasuk ECC 140, tetapi menambahkan watermark pada gambar yang dihasilkan. Terapkan lisensi untuk produksi guna menghapus watermark.

**Q: Bisakah saya menyesuaikan warna barcode?**  
A: Tentu saja. Gunakan `generator.Parameters.Barcode.Color` dan `generator.Parameters.Barcode.BackColor` untuk menyesuaikan dengan merek Anda.

---

**Terakhir Diperbarui:** 2026-08-17  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Menguasai Encoding DataMatrix dalam ASCII dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cara Membaca Barcode DataMatrix dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}