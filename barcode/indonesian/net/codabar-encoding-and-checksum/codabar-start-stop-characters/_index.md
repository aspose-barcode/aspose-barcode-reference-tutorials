---
date: 2026-05-24
description: Pelajari cara membuat kode batang codabar dengan karakter mulai dan berhenti
  menggunakan Aspose.BarCode untuk .NET. Tutorial langkah demi langkah tentang pembuatan
  kode batang untuk pengembang.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Karakter Mulai/Hentikan Codabar
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Buat Kode Batang Codabar dengan Karakter Mulai/Hentikan di Aspose.BarCode untuk
  .NET
url: /id/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kode Batang Codabar dengan Karakter Mulai/Hentikan di Aspose.BarCode untuk .NET

## Pendahuluan

Dalam tutorial ini Anda akan **membuat kode batang codabar** yang mencakup karakter mulai/hentikan eksplisit menggunakan Aspose.BarCode untuk .NET. Baik Anda sedang membangun sistem inventaris ritel, pelacak sampel laboratorium, atau solusi rekam medis, simbologi numerik Codabar bergantung pada simbol batas tersebut untuk menjamin pemindaian yang andal. Dalam beberapa menit ke depan kami akan membahas segala hal mulai dari penyiapan lingkungan hingga menyimpan file PNG, sehingga Anda dapat mulai menghasilkan kode batang Codabar segera.

## Jawaban Cepat
- **Apa pustaka yang saya butuhkan?** Aspose.BarCode untuk .NET  
- **Format apa yang dapat saya simpan barcode?** PNG (`BarCodeImageFormat.Png`)  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah simbol start/stop?** Ya – gunakan `CodabarSymbol.A`, `B`, `C`, atau `D`.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa Itu Codabar dan Mengapa Karakter Mulai/Hentikan Penting?

Codabar adalah simbologi kode batang numerik yang banyak digunakan di perpustakaan, layanan kesehatan, dan manajemen inventaris. Karakter mulai dan hentikan (A‑D atau dash) mendefinisikan batas kode batang, memungkinkan pemindai mendeteksi di mana data dimulai dan berakhir dengan akurasi pembacaan 99,9 %.

## Mengapa Menggunakan Aspose.BarCode untuk .NET?

Aspose.BarCode mendukung **30+ simbologi kode batang** dan dapat menghasilkan gambar hingga **10.000 × 10.000 px** tanpa harus memuat seluruh dokumen ke memori. Ia berjalan di Windows, Linux, dan macOS, serta kompatibel dengan .NET Framework, .NET Core, dan .NET 5+—memberikan fleksibilitas di semua platform modern.

## Prasyarat

1. **Penyiapan Lingkungan** – Pastikan lingkungan pengembangan .NET berfungsi. Jika Anda memerlukan panduan, lihat [documentation](https://reference.aspose.com/barcode/net/).  
2. **Pustaka Aspose.BarCode untuk .NET** – Unduh dan instal pustaka dari [source](https://releases.aspose.com/barcode/net/).  
3. **Pengetahuan Dasar .NET** – Familiaritas dengan C# dan IDE seperti Visual Studio, Rider, atau VS Code.  
4. **IDE** – Visual Studio, Rider, atau Visual Studio Code semuanya baik.

Sekarang setelah kami membahas prasyarat, mari selami kode sebenarnya.

## Bagaimana Saya Membuat Kode Batang Codabar dengan Karakter Mulai/Hentikan?

Muat `BarcodeGenerator`, atur tipe enkoding ke **Codabar**, dan berikan string data yang sudah berisi simbol start/stop yang diperlukan (misalnya, “-12345-”). Kemudian konfigurasikan X‑Dimension, pilih simbol start/stop lain bila diperlukan, dan akhirnya simpan gambar sebagai PNG. Alur end‑to‑end ini menciptakan kode batang siap pakai dalam hanya beberapa baris C#.

### Impor Namespace

`BarcodeGenerator` dan tipe terkait berada di namespace `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Langkah 1: Inisialisasi Barcode Generator

`BarcodeGenerator` adalah kelas inti yang membuat gambar kode batang. Ia menerima tipe simbologi dan string data sebagai argumen konstruktor.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro tip:** Dash (`-`) adalah salah satu simbol start/stop yang valid untuk Codabar. Anda juga dapat menggunakan `A`, `B`, `C`, atau `D` tergantung pada kebutuhan aplikasi Anda.

### Langkah 2: Atur X‑Dimension (lebar elemen kode batang)

`XDimension` mengontrol lebar bar paling sempit. Nilai yang lebih besar meningkatkan keterbacaan pada printer beresolusi rendah, sementara nilai yang lebih kecil menghemat ruang pada label berdensitas tinggi.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Mengapa penting:** Menyesuaikan `XDimension` membantu Anda memenuhi spesifikasi pemindai yang sering memerlukan lebar bar minimum 0,25 mm.

### Langkah 3: Tentukan Karakter Mulai dan Hentikan

Codabar mendukung empat simbol start/stop (A, B, C, D). Di bawah ini contoh untuk masing‑masing opsi. Pilih yang sesuai dengan spesifikasi sistem yang Anda integrasikan.

#### Mengatur Start A dan Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Mengatur Start B dan Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Mengatur Start C dan Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Mengatur Start D dan Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Anda dapat mengulangi konfigurasi untuk setiap simbol yang perlu dihasilkan; contoh di bawah menyimpan empat gambar terpisah—satu untuk setiap pasangan start/stop.

### Langkah 4: Simpan Gambar Kode Batang yang Dihasilkan (PNG)

`Save` menulis kode batang ke file. Menggunakan `BarCodeImageFormat.Png` menghasilkan gambar PNG lossless yang ideal untuk penggunaan web dan cetak.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Setiap file kini berisi **contoh kode batang codabar** dengan simbol start/stop yang bersesuaian.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Perbaikan |
|---------|--------------|-----|
| Barcode terlihat terdistorsi | X‑Dimension terlalu rendah untuk resolusi printer yang dipilih | Tingkatkan `XDimension.Pixels` (mis., menjadi 3 atau 4) |
| Pemindai tidak dapat membaca start/stop | Simbol start/stop salah untuk sistem target | Verifikasi simbol yang diperlukan (A‑D) dan atur sesuai |
| File PNG kosong atau rusak | Path output tidak valid atau izin menulis tidak cukup | Pastikan `path` mengarah ke folder yang ada dan aplikasi Anda memiliki akses menulis |

## Pertanyaan yang Sering Diajukan

**Q1: Apa itu Codabar, dan mengapa karakter start dan stop penting?**  
A: Codabar adalah simbologi kode batang numerik yang digunakan dalam inventaris, perpustakaan, dan layanan kesehatan. Karakter start/stop mendefinisikan batas kode batang, memastikan pemindai mengetahui di mana data dimulai dan berakhir.

**Q2: Bisakah saya menyesuaikan tampilan kode batang Codabar dengan Aspose.BarCode untuk .NET?**  
A: Ya. Selain X‑Dimension, Anda dapat mengubah warna, menambahkan margin, dan mengekspor ke PDF atau SVG menggunakan API yang sama.

**Q3: Apakah ada batasan pada kode batang Codabar terkait enkoding data?**  
A: Codabar terutama mendukung data numerik (0‑9) plus sejumlah karakter khusus terbatas. Ia tidak cocok untuk string alfanumerik penuh.

**Q4: Apakah Aspose.BarCode untuk .NET cocok untuk penggunaan komersial, dan bagaimana saya mendapatkan lisensi?**  
A: Ya, siap produksi. Beli lisensi di [Aspose's purchase page](https://purchase.aspose.com/buy).

**Q5: Di mana saya dapat mencari bantuan atau berdiskusi tentang masalah terkait Aspose.BarCode untuk .NET?**  
A: Bergabunglah dengan komunitas di [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13) untuk bantuan dari insinyur Aspose dan sesama pengembang.

---

**Terakhir Diperbarui:** 2026-05-24  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Karakter Mulai/Hentikan Codabar dan Checksum](/barcode/net/codabar-encoding-and-checksum/)
- [Cara Menambahkan Checksum ke Kode Batang Codabar Menggunakan Aspose.BarCode untuk .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Tutorial dan Contoh Komprehensif Aspose.BarCode untuk .NET](/barcode/net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}