---
date: 2026-03-07
description: Pelajari cara membuat kode batang databar satu dimensi yang dienkode
  GS1 di .NET menggunakan Aspose.BarCode. Panduan ini menunjukkan cara mengatur GS1,
  mengonfigurasi generator kode batang, dan menghasilkan kode batang dengan cepat.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Buat Pengkodean Databar Satu Dimensi GS1 dengan Aspose.BarCode
url: /id/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Databar Satu Dimensi dengan Enkoding GS1 menggunakan Aspose.BarCode

Dalam tutorial ini Anda akan **membuat barcode databar satu dimensi** yang mematuhi standar GS1, menggunakan pustaka Aspose.BarCode untuk .NET. Baik Anda memerlukan validasi GS1 yang ketat maupun barcode yang lebih fleksibel, kami akan memandu setiap langkah—dari menginstal pustaka hingga menangani pengecualian enkoding—sehingga Anda dapat menghasilkan barcode yang andal dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Apa arti “create one-dimensional databar”?** Itu berarti menghasilkan barcode linear (1‑D) dari keluarga Databar, yang sering digunakan untuk ritel dan logistik.  
- **Bagaimana cara mengatur validasi GS1?** Atur `IsAllowOnlyGS1Encoding` menjadi `true` pada parameter `DataBar`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Di mana saya dapat mengunduh pustaka?** Dari halaman rilis resmi Aspose (lihat prasyarat).

## Apa itu “create one-dimensional databar”?
Databar satu dimensi (juga dikenal sebagai RSS) adalah barcode linear yang kompak yang dapat mengenkode data numerik, tanggal, atau string AI (Application Identifier). Ketika dipasangkan dengan enkoding GS1, barcode mengikuti struktur data yang diakui secara global, menjadikannya ideal untuk skenario ritel, perawatan kesehatan, dan rantai pasokan.

## Mengapa menggunakan Aspose.BarCode untuk .NET?
Aspose.BarCode menawarkan API yang fluida, dukungan GS1 penuh, dan kemampuan untuk menyesuaikan setiap aspek visual barcode. Ini menghilangkan dugaan pada enkoding tingkat rendah dan memungkinkan Anda fokus pada logika bisnis.

## Prasyarat

1. **Aspose.BarCode for .NET** – unduh dan instal dari [here](https://releases.aspose.com/barcode/net/).  
2. **Your Directory Path** – ganti `"Your Directory Path"` dalam contoh dengan folder di mana Anda memiliki izin menulis.

## Mengimpor Namespace

Tambahkan pernyataan `using` yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.BarCode;
using System;
```

## Langkah 1: Inisialisasi Barcode Generator

Buat instance `BarcodeGenerator` dan tentukan simbolologi Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Langkah 2: Cara mengatur GS1 – Hasilkan barcode dengan validasi GS1 ketat

Aktifkan enkoding hanya GS1, tetapkan codetext yang sesuai dengan GS1, dan simpan gambar:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Langkah 3: Generasi barcode dengan Aspose – Enkoding variabel (tanpa pemeriksaan GS1)

Jika Anda memerlukan barcode yang **tidak** menegakkan aturan GS1, matikan pemeriksaannya:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Langkah 4: Pemeriksaan GS1 pada generator barcode – Menangani pengecualian

Ketika `IsAllowOnlyGS1Encoding` bernilai `true` tetapi codetext tidak sesuai GS1, Aspose akan melempar pengecualian. Pola berikut menunjukkan cara menangkap dan mencatatnya:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Kesalahan Umum & Tips
- **Kesalahan:** Menyediakan string non‑GS1 saat pemeriksaan GS1 diaktifkan akan menghentikan proses pembuatan barcode.  
- **Pro tip:** Validasi string AI Anda sebelum menetapkannya ke `CodeText` untuk menghindari kesalahan runtime.  
- **Tip:** Gunakan path absolut atau `Path.Combine` untuk membangun nama file secara aman di berbagai platform.

## Kesimpulan

Anda kini tahu cara **membuat barcode databar satu dimensi** dengan enkoding GS1, cara mengaktifkan atau menonaktifkan pemeriksaan GS1, dan cara menangani pengecualian terkait—semua menggunakan Aspose.BarCode untuk .NET. Jangan ragu untuk menjelajahi opsi styling tambahan seperti ukuran barcode, warna, dan margin melalui objek `Parameters.Barcode`.

Jika Anda menemui masalah, dokumentasi resmi dan forum komunitas adalah sumber daya yang sangat baik:

- [Dokumentasi Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Forum dukungan Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Pertanyaan yang Sering Diajukan

### 1. Apa itu enkoding GS1 pada barcode?
Enkoding GS1 adalah cara standar untuk menyusun data (misalnya, pengidentifikasi produk) di dalam barcode, memastikan interoperabilitas antar pengecer, produsen, dan penyedia logistik.

### 2. Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?
Ya. Aspose.BarCode memungkinkan Anda menyesuaikan ukuran, warna, margin, dan bahkan menambahkan teks yang dapat dibaca manusia melalui pengaturan `Parameters.Barcode`.

### 3. Di mana saya dapat menemukan sumber daya tambahan dan dokumentasi untuk Aspose.BarCode?
Anda dapat menemukan dokumentasi lengkap dan contoh di [Dokumentasi Aspose.BarCode](https://reference.aspose.com/barcode/net/). Ini merupakan sumber daya yang berharga untuk belajar dan memecahkan masalah.

### 4. Apakah ada versi percobaan yang tersedia untuk Aspose.BarCode?
Ya, Anda dapat memperoleh versi percobaan gratis Aspose.BarCode untuk .NET dari [di sini](https://releases.aspose.com/).

### 5. Bagaimana cara membeli lisensi untuk Aspose.BarCode untuk .NET?
Untuk membeli lisensi Aspose.BarCode untuk .NET, kunjungi [halaman pembelian](https://purchase.aspose.com/buy) di situs web Aspose.

---

**Terakhir Diperbarui:** 2026-03-07  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}