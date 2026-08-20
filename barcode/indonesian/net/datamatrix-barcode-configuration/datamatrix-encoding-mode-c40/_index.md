---
date: 2026-06-09
description: Pelajari cara menghasilkan barcode DataMatrix dan menyimpan PNG menggunakan
  pengkodean C40 dengan Aspose.BarCode – panduan lengkap untuk pembuatan barcode .NET
  Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Mode Pengkodean DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cara Membuat PNG DataMatrix dengan C40 menggunakan Aspose.BarCode
url: /id/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master DataMatrix Encoding Mode (C40) dengan Aspose.BarCode untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan belajar **cara menghasilkan datamatrix** barcode dan menyimpannya sebagai file PNG menggunakan mode enkoding C40 dengan Aspose.BarCode untuk .NET. Baik Anda sedang membangun sistem inventaris, generator label pengiriman, atau solusi apa pun yang memerlukan simbol kompak dan berkapasitas tinggi, menguasai C40 memberi Anda simbol yang lebih kecil tanpa mengorbankan keterbacaan. Kami akan membimbing Anda melalui setiap langkah—dari menyiapkan lingkungan hingga menghasilkan PNG akhir—sehingga Anda dapat langsung mengintegrasikan kode ke dalam proyek Anda.

## Jawaban Cepat

- **Apa yang dimaksud dengan “how to generate datamatrix”?** Membuat gambar barcode DataMatrix secara programatik.  
- **Mode enkoding mana yang dibahas?** DataMatrix C40, skema alfanumerik yang efisien.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menjalankannya di .NET Core?** Ya, Aspose.BarCode sepenuhnya mendukung .NET Core, .NET 5, .NET 6, dan versi selanjutnya.  
- **Format file apa yang dihasilkan?** PNG – format gambar tanpa kehilangan kualitas, ramah web.

## Cara Menghasilkan DataMatrix dengan Enkoding C40

Muat data Anda, konfigurasikan generator, dan panggil `Save` – itu adalah alur kerja lengkap dalam tiga langkah singkat. Kelas `BarcodeGenerator` menangani pembuatan simbol, sementara enum `BarCodeImageFormat.Png` memberi tahu Aspose.BarCode untuk menulis hasilnya sebagai file PNG. `Save` menulis gambar barcode yang dihasilkan ke jalur file yang ditentukan dalam format yang dipilih. Paragraf jawaban langsung ini memberi Anda solusi end‑to‑end sebelum kami menyelami setiap baris kode.

## Apa itu Mode Enkoding DataMatrix (C40)?

`DataMatrixEncodeMode` adalah sebuah enumerasi yang menentukan skema enkoding mana yang harus digunakan Aspose.BarCode untuk simbol DataMatrix. Opsi `DataMatrixEncodeMode.C40` memilih enkoding alfanumerik C40, yang mengemas huruf, digit, dan sekumpulan tanda baca terbatas ke dalam modul yang lebih sedikit, mengurangi ukuran simbol secara keseluruhan sambil mempertahankan keterbacaan untuk teks inventaris tipikal. Skema efisien ini ideal ketika Anda perlu mengenkode data alfanumerik dalam bentuk yang kompak.

## Mengapa Menggunakan Aspose.BarCode untuk .NET?

Aspose.BarCode menyediakan **lebih dari 30 parameter yang dapat dikonfigurasi** untuk dimensi, tingkat koreksi kesalahan, dan mode enkoding, serta mendukung **lebih dari 50 format gambar dan barcode**. Perpustakaan ini berjalan pada **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, memberikan generasi tanpa ketergantungan yang berfungsi di server, desktop, dan perangkat seluler.

## Prasyarat

Sebelum kami menyelami kode, pastikan Anda memiliki hal berikut:

1. **.NET Development Environment** – Visual Studio, Rider, atau IDE apa pun yang mendukung C#.  
2. **Aspose.BarCode for .NET** – diinstal melalui NuGet atau installer resmi. Lihat [documentation](https://reference.aspose.com/barcode/net/) untuk detail.  
3. **Basic C# knowledge** – Anda harus nyaman dengan namespace, kelas, dan pernyataan using.  
4. **Write‑access folder** – sebuah direktori di mesin Anda tempat PNG akan disimpan.

## Mengimpor Namespace yang Diperlukan

Kelas `BarcodeGenerator` adalah titik masuk untuk membuat barcode apa pun. Tambahkan namespace yang diperlukan di bagian atas file sumber C# Anda sehingga Anda dapat mengakses API generasi:

```csharp
using Aspose.BarCode.Generation;
```

## Generasi Barcode Langkah‑per‑Langkah

Berikut adalah panduan **barcode langkah‑per‑langkah**. Setiap langkah dijelaskan dengan bahasa sederhana, dan placeholder asli tetap tidak diubah untuk kemudahan salin‑tempel.

### Langkah 1: Tentukan Jalur Direktori
Tentukan folder tempat gambar PNG akan disimpan. Ganti placeholder dengan jalur sebenarnya di mesin Anda.

```csharp
string path = "Your Directory Path";
```

### Langkah 2: Siapkan Generasi Barcode
Buat instance `BarcodeGenerator`, tentukan `EncodeTypes.DataMatrix`, dan berikan data yang ingin Anda enkode.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Langkah 3: Kustomisasi Barcode
Konfigurasikan X‑dimension (lebar piksel modul) dan alihkan mode enkoding ke C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Langkah 4: Simpan Gambar Barcode
Akhirnya, simpan barcode yang dihasilkan sebagai file PNG. Ini adalah jawaban konkret untuk **cara menyimpan png** dengan Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Saat Anda menjalankan program, Anda akan menemukan `DataMatrixEncodeModeC40.png` di folder yang Anda tentukan, siap digunakan dalam laporan, label, atau halaman web.

## Masalah Umum & Tips

- **Invalid Path** – Pastikan direktori ada dan Anda memiliki izin menulis; jika tidak, `gen.Save` akan melemparkan pengecualian.  
- **Incorrect Encoding Mode** – Jika Anda perlu mengenkode karakter di luar set C40, alihkan ke `DataMatrixEncodeMode.Auto` atau mode lain yang sesuai.  
- **Image Size** – Sesuaikan `XDimension.Pixels` untuk memperbesar atau memperkecil ukuran barcode secara keseluruhan tanpa memengaruhi keterbacaan.

## Pertanyaan yang Sering Diajukan

**Q: Apa itu Mode Enkoding DataMatrix (C40)?**  
A: C40 adalah skema enkoding alfanumerik yang kompak untuk simbol DataMatrix, ideal untuk teks yang mencakup huruf, angka, dan sekumpulan karakter khusus terbatas.

**Q: Di mana saya dapat menemukan dokumentasi Aspose.BarCode untuk .NET?**  
A: Anda dapat menemukan dokumentasi [di sini](https://reference.aspose.com/barcode/net/). Dokumentasi tersebut memberikan panduan terperinci tentang semua jenis barcode dan opsi enkoding.

**Q: Apakah Aspose.BarCode untuk .NET kompatibel dengan semua versi .NET?**  
A: Ya, perpustakaan ini mendukung berbagai versi .NET, mulai dari .NET Framework 4.5+ hingga .NET 6 dan versi selanjutnya.

**Q: Bisakah saya mencoba Aspose.BarCode untuk .NET sebelum membeli?**  
A: Ya, Anda dapat menjelajahi percobaan gratis Aspose.BarCode untuk .NET dengan mengunjungi [tautan ini](https://releases.aspose.com/). Ini memungkinkan Anda menguji fitur dan kemampuan perpustakaan.

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.BarCode untuk .NET?**  
A: Anda dapat menemukan komunitas yang mendukung dan mengakses dukungan untuk Aspose.BarCode untuk .NET di [forum Aspose](https://forum.aspose.com/c/barcode/13).

## Kesimpulan

Dengan mengikuti panduan **barcode langkah‑per‑langkah** ini, Anda kini tahu persis **cara menghasilkan datamatrix** barcode dan menyimpannya sebagai file PNG menggunakan mode enkoding C40 dengan Aspose.BarCode untuk .NET. Pendekatan ini memberi Anda kontrol penuh atas tampilan, ukuran, dan representasi data barcode, memudahkan penyisipan barcode berkualitas tinggi ke dalam aplikasi .NET apa pun.

---

**Terakhir Diperbarui:** 2026-06-09  
**Diuji Dengan:** Aspose.BarCode 24.11 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Enkoding DataMatrix dalam Bytes dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master Enkoding DataMatrix dalam ASCII dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}