---
date: 2026-02-25
description: Pelajari cara menghasilkan gambar barcode dan menyimpan barcode PNG menggunakan
  Aspose.BarCode untuk .NET – contoh lengkap barcode Aspose.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Buat gambar barcode – Code 93 dengan Aspose.BarCode
url: /id/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan gambar barcode – Kode 93 Satu Dimensi dengan Aspose.BarCode

## Pendahuluan

Pada era digital saat ini, barcode telah menjadi bagian integral dari kehidupan kita, menyederhanakan proses seperti manajemen inventaris, pelabelan produk, dan pelacakan point‑of‑sale. **Generating a barcode image** sering menjadi langkah pertama dalam mengintegrasikan pengenal ini ke dalam aplikasi Anda. Aspose.BarCode untuk .NET menyediakan API yang kuat dan mudah‑digunakan yang memungkinkan Anda membuat barcode Code 93 berkualitas tinggi hanya dengan beberapa baris kode C#. Baik Anda membangun sistem gudang, aplikasi ritel, atau alat pelaporan khusus, tutorial ini memandu Anda melalui **aspose barcode example** lengkap yang menunjukkan cara menghasilkan, menyesuaikan, dan **save barcode PNG** file.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Membuat dan menyimpan gambar barcode Code 93 dengan penanganan checksum.  
- **Perpustakaan mana yang digunakan?** Aspose.BarCode untuk .NET (rilis stabil terbaru).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah format output?** Ya – Anda dapat menyimpan sebagai PNG, JPEG, BMP, dll., dengan mengubah `BarCodeImageFormat`.  
- **Apa persyaratan minimum?** .NET Framework 4.6+ atau .NET Core 3.1+ dan Visual Studio.

## Apa itu barcode Code 93?
Code 93 adalah simbol alfanumerik berkapasitas tinggi yang mendukung seluruh set karakter ASCII. Ini sering dipilih karena ukuran yang kompak dan checksum bawaan, yang membantu memastikan integritas data saat pemindaian.

## Mengapa menghasilkan gambar barcode dengan Aspose.BarCode?
- **Kontrol penuh** atas tipe enkoding, checksum, ukuran, dan format gambar.  
- **Tanpa ketergantungan eksternal** – perpustakaan ini berjalan di platform .NET apa pun.  
- **Kualitas rendering yang luar biasa**, cocok untuk tampilan di layar maupun pencetakan resolusi tinggi.  
- **Dokumentasi komprehensif** dan banyak contoh yang mempercepat pengembangan.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

1. **Visual Studio** (edisi terbaru apa pun).  
2. **Aspose.BarCode untuk .NET** terpasang – Anda dapat mengunduhnya dari halaman unduhan resmi.  
3. Familiaritas dasar dengan **C#** dan struktur proyek .NET.

Setelah semuanya siap, mari lanjut ke panduan langkah demi langkah.

## Impor Namespace

Pertama, impor namespace yang diperlukan agar Anda dapat mengakses kelas pembuatan barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Langkah 1: Atur Jalur Direktori

Tentukan lokasi penyimpanan gambar barcode yang dihasilkan. Ganti placeholder dengan folder yang valid di mesin Anda.

```csharp
string path = "Your Directory Path";
```

## Langkah 2: Buat Barcode Code 93 Satu‑Dimensi

Buat instance `BarcodeGenerator` dengan tipe `Code93Extended` dan data yang ingin Anda enkode.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Langkah 3: Aktifkan Checksum (Opsional)

Code 93 secara default sudah menyertakan checksum. Anda dapat mengaktifkan atau menonaktifkannya menggunakan properti `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Langkah 4: Simpan Gambar Barcode (Save Barcode PNG)

Hasilkan gambar dan simpan sebagai file PNG di folder yang Anda tentukan sebelumnya.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Langkah 5: Menangani Pengecualian – Menghasilkan Tanpa Checksum

Jika Anda perlu membuat barcode **tanpa** checksum, Anda harus menangani kemungkinan pengecualian yang mungkin muncul.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Masalah Umum dan Solusinya
- **Jalur tidak valid** – pastikan direktori ada dan aplikasi memiliki izin menulis.  
- **Karakter tidak didukung** – Code 93 mendukung seluruh set ASCII, tetapi karakter kontrol dapat menyebabkan error.  
- **Lisensi tidak diatur** – tanpa lisensi yang valid, perpustakaan berjalan dalam mode evaluasi dan mungkin menambahkan watermark.

## Pertanyaan yang Sering Diajukan (FAQ)

### Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.BarCode untuk .NET?
A: Anda dapat menemukan dokumentasi di [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: Bagaimana cara mengunduh Aspose.BarCode untuk .NET?
A: Anda dapat mengunduh Aspose.BarCode untuk .NET dari situs web di [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: Apakah ada percobaan gratis untuk Aspose.BarCode untuk .NET?
A: Ya, Anda dapat mendapatkan percobaan gratis Aspose.BarCode untuk .NET dari [here](https://releases.aspose.com/).

### Q: Bagaimana cara membeli lisensi untuk Aspose.BarCode untuk .NET?
A: Anda dapat membeli lisensi di halaman pembelian di [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Di mana saya dapat mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk .NET?
A: Anda dapat menemukan forum komunitas untuk dukungan dan diskusi di [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}