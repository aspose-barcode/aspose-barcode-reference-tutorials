---
date: 2026-01-27
description: Pelajari cara membuat teks kode diperluas DotCode menggunakan Aspose.BarCode
  untuk .NET – panduan langkah demi langkah untuk menghasilkan kode batang DotCode
  dengan teks kode yang diperluas.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Cara membuat teks kode dotcode extended dengan Aspose.BarCode untuk .NET
url: /id/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat dotcode extended codetext dengan Aspose.BarCode untuk .NET

## Pendahuluan

Di bidang pembuatan dan pengelolaan barcode, Aspose.BarCode untuk .NET menonjol sebagai solusi yang serbaguna dan efisien. Baik Anda perlu menghasilkan barcode untuk produk, inventaris, atau aplikasi apa pun, Aspose.BarCode untuk .NET siap membantu. Dalam tutorial komprehensif ini, kami akan **membuat dotcode extended codetext** dan menjelaskan mengapa kemampuan ini penting untuk lingkungan modern yang kaya data. DotCode adalah barcode matriks dua dimensi yang dapat mengenkode data teks maupun biner, menjadikannya alat berharga di berbagai industri.

## Jawaban Cepat
- **Apa arti “create dotcode extended codetext”?** Itu berarti membuat barcode DotCode yang mencakup FNC1, ECICodetext, teks biasa, dan pemisah simbol dalam satu payload yang diperluas.  
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode for .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Cara membuat dotcode extended codetext

Berikut adalah panduan singkat langkah demi langkah yang menunjukkan secara tepat cara membangun extended code text dan merender gambar barcode.

## Prasyarat

Sebelum kita menyelami panduan langkah demi langkah, ada beberapa prasyarat yang perlu Anda siapkan agar dapat mengikuti dengan efektif:

1. Aspose.BarCode for .NET: Pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.BarCode for .NET. Jika belum, Anda dapat mengunduhnya dari [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

2. Lingkungan Pengembangan: Anda harus memiliki lingkungan pengembangan .NET yang berfungsi, sebaiknya Visual Studio, terpasang di sistem Anda.

Dengan prasyarat ini terpenuhi, kita dapat melanjutkan untuk menghasilkan DotCode Extended Code Text.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan ke proyek .NET Anda untuk mengakses fungsionalitas yang dibutuhkan dari pustaka Aspose.BarCode. Berikut cara melakukannya:

```csharp
using Aspose.BarCode.Generation;
```

Setelah prasyarat terpenuhi, mari kita uraikan proses menghasilkan DotCode Extended Code Text dalam panduan langkah demi langkah.

## Langkah 1: Tentukan Jalur Direktori

Pada langkah ini, Anda perlu menentukan jalur direktori tempat Anda ingin menyimpan gambar DotCode Extended Code Text yang dihasilkan.

```csharp
string path = "Your Directory Path";
```

Ganti `"Your Directory Path"` dengan jalur sebenarnya di sistem Anda.

## Langkah 2: Buat DotCode Extended Code Text

Untuk membuat DotCode Extended Code Text, ikuti sub‑langkah berikut:

### 2.1 Tambahkan Identifier Format FNC1

Identifier Format FNC1 digunakan untuk menunjukkan awal bidang data baru. Ini merupakan bagian penting dari DotCode Extended Code Text.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Tambahkan ECICodetext

ECICodetext adalah tempat Anda dapat mengenkode karakter khusus dan teks internasional. Pada contoh ini, kami mengenkode `"犬Right狗"` menggunakan enkoding UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Tambahkan Plain Codetext

Anda juga dapat menambahkan teks biasa ke DotCode Extended Code Text. Di sini, kami menambahkan `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Tambahkan Pemisah Simbol FNC3

Pemisah Simbol FNC3 digunakan untuk memisahkan bagian-bagian kode yang berbeda.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Tambahkan Inisialisasi Pembaca FNC3

Langkah ini menambahkan informasi Inisialisasi Pembaca FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Hasilkan Codetext

Sekarang, hasilkan DotCode Extended Codetext dengan memanggil metode `GetExtendedCodetext` pada objek `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Langkah 3: Hasilkan Gambar DotCode

Untuk menghasilkan DotCode Extended Code Text sebagai gambar, ikuti sub‑langkah berikut:

#### 4.1 Inisialisasi Barcode Generator

Inisialisasi `BarcodeGenerator` dengan parameter yang sesuai. Dalam kasus ini, kami menggunakan `EncodeTypes.DotCode` dan codetext yang dihasilkan.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Dan selesai! Anda telah berhasil menghasilkan DotCode Extended Code Text menggunakan Aspose.BarCode untuk .NET.

## Kesimpulan

Aspose.BarCode untuk .NET adalah alat yang kuat yang menyederhanakan pembuatan barcode. Dalam tutorial ini, kami fokus pada cara **membuat dotcode extended codetext**, yang penting di berbagai industri, terutama di mana enkoding karakter multibahasa dan khusus diperlukan. Dengan mengikuti langkah-langkah di atas, Anda dapat dengan mudah membuat DotCode Extended Code Text sesuai kebutuhan Anda.

Jika Anda memerlukan panduan lebih lanjut atau memiliki pertanyaan, jangan ragu mengunjungi [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) atau berinteraksi dengan komunitas di [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: Apa kegunaan DotCode?

A1: DotCode digunakan untuk mengenkode data teks maupun biner dan biasanya diterapkan di industri seperti kesehatan dan logistik untuk pelacakan serta tujuan enkoding data.

### Q2: Bisakah saya menyesuaikan tampilan barcode DotCode?

A2: Ya, Aspose.BarCode untuk .NET menyediakan opsi untuk menyesuaikan tampilan barcode DotCode, termasuk ukuran dan mode enkoding.

### Q3: Apakah Aspose.BarCode untuk .NET kompatibel dengan berbagai kerangka kerja .NET?

A3: Ya, Aspose.BarCode untuk .NET kompatibel dengan berbagai kerangka kerja .NET, memastikan fleksibilitas dan kemudahan integrasi.

### Q4: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?

A4: Anda dapat memperoleh lisensi sementara dari [Aspose's website](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi dan pengujian.

### Q5: Apakah Aspose.BarCode untuk .NET cocok untuk pembuatan barcode tingkat perusahaan?

A5: Tentu saja, Aspose.BarCode untuk .NET dirancang untuk memenuhi kebutuhan pembuatan barcode baik skala kecil maupun tingkat perusahaan, menawarkan skalabilitas dan keandalan.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan barcode yang dihasilkan dalam aplikasi seluler?**  
A: Ya. Gambar PNG yang dihasilkan oleh generator dapat disisipkan dalam iOS, Android, atau aplikasi seluler lintas platform apa pun.

**Q: Bagaimana jika saya perlu mengenkode data biner alih-alih teks?**  
A: Gunakan metode `AddECICodetext` dengan `ECIEncodings` yang sesuai (mis., `ECIEncodings.Base64`) untuk menyematkan payload biner.

**Q: Bagaimana cara mengubah ukuran barcode tanpa memengaruhi keterbacaan?**  
A: Sesuaikan properti `XDimension.Pixels`; nilai yang lebih tinggi meningkatkan ukuran modul, sementara nilai yang lebih rendah membuat barcode lebih kompak.

**Q: Apakah ada cara menambahkan zona tenang di sekitar barcode?**  
A: Ya. Atur `gen.Parameters.Barcode.Margin` untuk menentukan zona tenang yang diinginkan dalam piksel.

**Q: Apakah pustaka ini mendukung .NET 8?**  
A: Rilis terbaru Aspose.BarCode kompatibel dengan .NET 8; cukup referensikan versi paket NuGet yang sesuai.

---

**Terakhir Diperbarui:** 2026-01-27  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}