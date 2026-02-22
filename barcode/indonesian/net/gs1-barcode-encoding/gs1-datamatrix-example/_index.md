---
date: 2026-02-22
description: Pelajari cara membuat gambar barcode C# menggunakan Aspose.BarCode untuk
  .NET dan menghasilkan barcode GS1 DataMatrix dengan cepat dan efisien.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Buat gambar barcode C# – Contoh GS1 DataMatrix
url: /id/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh GS1 DataMatrix

Jika Anda mencari cara yang handal untuk **create barcode image C#** dalam aplikasi .NET Anda, Aspose.BarCode for .NET membuat prosesnya sederhana. Perpustakaan kuat ini mendukung berbagai macam simbol, termasuk GS1 DataMatrix, dan menyediakan API yang bersih yang memungkinkan Anda fokus pada logika bisnis alih‑alih detail barcode tingkat‑rendah. Dalam beberapa menit berikutnya, kami akan membimbing Anda melalui contoh lengkap, langsung yang menunjukkan cara menghasilkan barcode GS1 DataMatrix, menyesuaikan tampilannya, dan menyimpannya sebagai file gambar.

## Jawaban Cepat
- **Apa yang dihasilkan contoh ini?** Sebuah barcode GS1 DataMatrix yang berisi data produk contoh.  
- **Perpustakaan mana yang digunakan?** Aspose.BarCode for .NET.  
- **Bisakah saya mengubah format output?** Ya, Anda dapat menyimpan sebagai PNG, JPEG, BMP, dll.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Apakah kode ini kompatibel dengan .NET Core?** Tentu – API yang sama berfungsi pada .NET Framework dan .NET Core/5/6.

## Apa itu barcode GS1 DataMatrix?
GS1 DataMatrix adalah barcode dua dimensi yang mengkodekan informasi tingkat produk (seperti GTIN, nomor seri, dan pengidentifikasi aplikasi tambahan). Ini banyak digunakan dalam ritel, perawatan kesehatan, dan logistik untuk penyimpanan data yang kompak dan berkapasitas tinggi.

## Mengapa menggunakan Aspose.BarCode untuk membuat barcode image C#?
- **Full‑featured API** – mendukung standar GS1, koreksi kesalahan, dan kontrol ukuran.  
- **No external dependencies** – perpustakaan .NET murni, mudah diintegrasikan.  
- **Cross‑platform** – berfungsi di Windows, Linux, dan macOS.  
- **Extensive documentation** – mencakup contoh seperti ini untuk memulai dengan cepat.

## Prasyarat

Sebelum kita memulai tutorial, pastikan Anda memiliki prasyarat berikut:

1. **Aspose.BarCode for .NET** – Anda perlu menginstal Aspose.BarCode for .NET. Jika belum, Anda dapat [download it here](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – Anda harus memiliki lingkungan pengembangan .NET yang terpasang di sistem Anda (Visual Studio, VS Code, atau IDE apa pun yang Anda sukai).

Setelah Anda menyiapkan prasyarat, mari mulai menghasilkan barcode GS1 DataMatrix.

## Impor Namespace

Pertama, impor namespace yang diperlukan untuk bekerja dengan Aspose.BarCode for .NET. Namespace ini memberi Anda akses ke kemampuan pembuatan barcode.

```csharp
using Aspose.BarCode;
using System;
```

## Cara membuat barcode image C# – Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Barcode Generator

Untuk memulai, buat instance `BarcodeGenerator` dan tentukan simbol **GS1 DataMatrix** bersama data yang ingin Anda enkode. Dalam contoh ini kami mengenkripsi string **"(01)12345678901231(21)ASPOSE(30)9876"**, yang mengikuti format GS1 Application Identifier.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro tip:* Ganti data contoh dengan identifier GS1 Anda sendiri agar sesuai dengan katalog produk Anda.

### Langkah 2: Sesuaikan Properti Barcode

Anda dapat menyesuaikan tampilan barcode menggunakan objek `Parameters`. Di sini kami mengatur X‑dimension (ukuran modul terkecil) menjadi 8 piksel, dan mendefinisikan ukuran matriks 36 kolom x 12 baris. Sesuaikan nilai-nilai ini untuk memenuhi kebutuhan pemindaian Anda.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Why adjust X‑dimension?* Dimensi X yang lebih besar membuat barcode lebih mudah dipindai pada perangkat beresolusi rendah, sementara nilai yang lebih kecil mengurangi ukuran gambar.

### Langkah 3: Simpan Gambar Barcode

Terakhir, simpan barcode yang dihasilkan ke disk. Contoh ini menggunakan PNG, tetapi Anda dapat memilih JPEG, GIF, BMP, dan format lain yang didukung oleh Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Saat Anda menjalankan kode, Anda akan menemukan **Gs1DataMatrixExample.png** di folder yang ditentukan, siap digunakan dalam label, kemasan, atau aplikasi digital.

## Kasus Penggunaan Umum

- **Retail product labeling** – Enkode GTIN, nomor batch, dan tanggal kedaluwarsa.  
- **Pharmaceutical tracking** – Memenuhi persyaratan regulasi dengan data yang sesuai GS1.  
- **Warehouse logistics** – Menyimpan informasi lokasi dan inventaris secara kompak.  

## Pemecahan Masalah & Tips

- **Incorrect data format** – Pastikan string Anda mengikuti sintaks GS1 Application Identifier; jika tidak, barcode mungkin tidak dapat dipindai.  
- **Image size issues** – Jika gambar yang dihasilkan terlihat buram, tingkatkan nilai `XDimension.Pixels`.  
- **License errors** – Lisensi percobaan dapat digunakan untuk evaluasi, tetapi lisensi penuh diperlukan untuk penerapan produksi.

## Pertanyaan yang Sering Diajukan

### Apa itu GS1 DataMatrix?
GS1 DataMatrix adalah simbol barcode dua dimensi yang digunakan untuk mengkodekan data terkait produk dan identifikasinya, khususnya di industri ritel dan perawatan kesehatan.

### Apakah Aspose.BarCode for .NET cocok untuk tipe barcode lain?
Ya, Aspose.BarCode for .NET mendukung berbagai jenis barcode, menjadikannya serbaguna untuk berbagai aplikasi.

### Bisakah saya menghasilkan barcode dalam format gambar lain selain PNG?
Ya, Aspose.BarCode for .NET memungkinkan Anda menyimpan barcode yang dihasilkan dalam berbagai format gambar, seperti JPEG, GIF, dan BMP, selain PNG.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.BarCode for .NET?
Ya, lisensi yang valid diperlukan untuk penggunaan komersial Aspose.BarCode for .NET. Anda dapat memperoleh lisensi dari [Aspose website](https://purchase.aspose.com/buy).

### Di mana saya dapat mendapatkan dukungan untuk Aspose.BarCode for .NET?
Anda dapat menemukan jawaban atas pertanyaan Anda dan mencari dukungan di [Aspose.BarCode for .NET forum](https://forum.aspose.com/c/barcode/13).

## FAQ Tambahan (AI‑Optimized)

**Q: Bagaimana cara menghasilkan barcode DataMatrix di C# tanpa format GS1?**  
A: Gunakan `EncodeTypes.DataMatrix` alih‑alih `EncodeTypes.GS1DataMatrix` dan berikan string data biasa ke `BarcodeGenerator`.

**Q: Bisakah saya mengubah warna barcode secara programatis?**  
A: Ya, atur `gen.Parameters.Barcode.ForeColor` dan `gen.Parameters.Barcode.BackColor` untuk menyesuaikan warna latar depan dan latar belakang.

**Q: Apakah memungkinkan untuk menyematkan barcode yang dihasilkan langsung ke PDF?**  
A: Tentu – ambil barcode sebagai `System.Drawing.Image` dan tambahkan ke PDF menggunakan Aspose.PDF atau perpustakaan PDF lainnya.

**Q: Versi .NET apa yang didukung?**  
A: Aspose.BarCode for .NET mendukung .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6, dan versi selanjutnya.

**Q: Bagaimana cara meningkatkan keandalan pemindaian untuk label kecil?**  
A: Tingkatkan X‑dimension, tambahkan zona tenang (`gen.Parameters.Barcode.Margin`), dan pastikan kontras yang cukup antara barcode dan latar belakang.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi cara **create barcode image C#** menggunakan Aspose.BarCode for .NET untuk menghasilkan barcode GS1 DataMatrix. Dengan hanya beberapa baris kode, Anda dapat menyematkan barcode berkualitas tinggi ke dalam aplikasi Anda, baik Anda membangun solusi ritel, sistem perawatan kesehatan, atau platform logistik. Jelajahi lebih lanjut perpustakaan ini untuk menemukan simbol tambahan, opsi rendering lanjutan, dan skenario integrasi.

Untuk informasi lebih lanjut dan dokumentasi detail, silakan merujuk ke [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-02-22  
**Diuji Dengan:** Aspose.BarCode for .NET (versi terbaru)  
**Penulis:** Aspose