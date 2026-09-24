---
date: 2026-05-30
description: Pelajari cara menghasilkan kode bar DataMatrix dalam mode Bytes dan membaca
  kode bar DataMatrix menggunakan Aspose.BarCode untuk .NET – panduan kode bar langkah
  demi langkah.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Mode Pengodean DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hasilkan Kode Bar DataMatrix dalam Mode Bytes dengan Aspose.BarCode untuk .NET
url: /id/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan Kode Batang DataMatrix dalam Mode Bytes dengan Aspose.BarCode untuk .NET

Dalam tutorial ini Anda akan belajar cara **menghasilkan kode batang DataMatrix** menggunakan mode pengkodean Bytes dan kemudian **membaca kode batang DataMatrix** kembali dengan Aspose.BarCode untuk .NET. Baik Anda sedang membangun sistem manajemen gudang atau aplikasi tiket seluler, panduan kode batang langkah demi langkah di bawah ini menunjukkan secara tepat cara mengkonfigurasi pengaturan generator kode batang, menghasilkan gambar berkualitas tinggi, dan mendekodenya kembali—semua dalam beberapa baris C#.

## Jawaban Cepat
- **Bisakah saya menghasilkan kode batang DataMatrix di .NET?** Ya, gunakan `BarcodeGenerator` dengan `EncodeTypes.DataMatrix` dan atur `DataMatrixEncodeMode.Bytes`.
- **Metode mana yang membaca kode batang?** `BarCodeReader` membaca gambar dan mengembalikan teks yang dienkode.
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; percobaan gratis tersedia.
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Berapa banyak byte yang dapat saya enkode?** Hingga 1,555 byte dalam satu simbol DataMatrix.

## Apa itu menghasilkan kode batang DataMatrix?
**Generate DataMatrix barcode** berarti membuat kode batang dua dimensi berbentuk persegi yang dapat menyimpan data biner. Aspose.BarCode merender simbol tersebut sebagai gambar PNG, JPG, atau SVG yang dapat didekode oleh pemindai apa pun. Ini banyak digunakan untuk pelacakan inventaris, manajemen dokumen, dan otentikasi karena menyediakan kepadatan data tinggi dan kemampuan koreksi kesalahan, menjadikannya dapat diandalkan bahkan pada cetakan berkualitas rendah.

## Mengapa menggunakan mode pengkodean Bytes?
Mode Bytes memungkinkan Anda menyematkan data biner mentah (hingga 1,555 byte) tanpa mengubahnya menjadi teks, yang ideal untuk nomor seri, GUID, atau muatan terenkripsi. Aspose.BarCode mendukung **lebih dari 30 simbol kode batang** dan dapat memproses **dokumen ratusan halaman** tanpa memuat seluruh file ke memori, memastikan kinerja cepat bahkan dalam skenario throughput tinggi.

## Prasyarat

Sebelum kita menyelami proses pengkodean, Anda perlu menyiapkan prasyarat berikut:

1. Aspose.BarCode untuk .NET: Untuk memulai, Anda harus memiliki perpustakaan Aspose.BarCode untuk .NET terpasang. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/barcode/net/). Anda juga dapat menemukan produk Aspose lainnya di [here](https://releases.aspose.com/).
2. Lingkungan Pengembangan Anda: Pastikan Anda memiliki lingkungan pengembangan yang disiapkan, termasuk Visual Studio atau IDE lain pilihan Anda.
3. Pengetahuan Dasar tentang C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

Untuk bantuan, kunjungi [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

Dengan prasyarat ini siap, Anda dapat mulai mengkodekan data dalam format DataMatrix menggunakan mode Bytes.

## Impor Namespace

Untuk menggunakan Aspose.BarCode untuk .NET, impor namespace yang diperlukan di bagian atas file C# Anda:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Sekarang lingkungan siap, mari kita jalani langkah‑langkah tepat untuk **menghasilkan kode batang DataMatrix** dan kemudian membacanya kembali.

## Cara menghasilkan kode batang DataMatrix dalam mode Bytes?

Muat `BarcodeGenerator`, atur mode enkode ke Bytes, konfigurasikan teks tampilan opsional, simpan gambar, dan akhirnya gunakan `BarCodeReader` untuk memverifikasi hasil—semua dalam enam langkah singkat. Pendekatan ini menjamin kode batang yang dapat diandalkan dan mematuhi standar ISO/IEC 16022.

### Langkah 1: Inisialisasi BarcodeGenerator

`BarcodeGenerator` adalah kelas utama yang digunakan untuk menghasilkan gambar kode batang untuk simbol dan data tertentu.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Langkah 2: Atur Mode Enkode DataMatrix ke Bytes

`DataMatrixEncodeMode.Bytes` memberi tahu generator untuk memperlakukan input sebagai byte biner mentah, bukan teks.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Langkah 3: Atur Teks Tampilan

Properti `CodeText` mengatur teks yang dapat dibaca manusia yang ditampilkan di bawah simbol kode batang.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Langkah 4: Simpan Gambar Kode Batang

Metode `Save` menulis kode batang yang dihasilkan ke file gambar dalam format yang ditentukan.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Langkah 5: Coba Mengenali

`BarCodeReader` membaca gambar kode batang dan mengekstrak data yang dienkode.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Langkah 6: Iterasi dan Tampilkan Hasil

Iterasi melalui `reader.ReadBarCodes()` untuk mengakses setiap kode batang yang terdeteksi dan `CodeText`‑nya.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Dengan langkah‑langkah ini, Anda telah berhasil **menghasilkan kode batang DataMatrix** dalam mode Bytes dan memverifikasinya menggunakan Aspose.BarCode untuk .NET. Perpustakaan ini mengabstraksi detail enkoding tingkat rendah, sehingga Anda dapat fokus pada logika bisnis daripada matematika kode batang.

## Masalah Umum dan Solusinya
- **Data yang dienkode terpotong** – Pastikan array byte tidak melebihi 1,555 byte; jika tidak, perpustakaan akan otomatis beralih ke ukuran simbol yang lebih besar atau melemparkan pengecualian.
- **Gambar tampak buram** – Simpan gambar dengan resolusi lebih tinggi (mis., 300 dpi) dengan mengatur `generator.Parameters.ImageResolution` sebelum memanggil `Save`.
- **Reader mengembalikan null** – Pastikan jalur gambar benar dan file tidak rusak; juga pastikan `BarCodeReader` diinstansiasi dengan `DecodeType.DataMatrix`.

## Pertanyaan yang Sering Diajukan

**Q: Apa itu mode pengkodean DataMatrix?**  
A: Mode pengkodean DataMatrix menentukan bagaimana data input diubah menjadi pola dua dimensi; mode Bytes menyimpan byte biner mentah secara langsung.

**Q: Bagaimana saya bisa mendapatkan percobaan gratis Aspose.BarCode untuk .NET?**  
A: Anda dapat memperoleh percobaan gratis Aspose.BarCode untuk .NET dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.BarCode untuk .NET?**  
A: Dokumentasi untuk Aspose.BarCode untuk .NET tersedia [here](https://reference.aspose.com/barcode/net/).

**Q: Apakah Aspose.BarCode untuk .NET cocok untuk penggunaan komersial?**  
A: Ya, Aspose.BarCode untuk .NET cocok untuk penggunaan komersial. Anda dapat membeli lisensi dari [here](https://purchase.aspose.com/buy).

**Q: Bisakah saya menggunakan lisensi sementara untuk Aspose.BarCode untuk .NET?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk Aspose.BarCode untuk .NET dari [here](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-05-30  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Menguasai Pengkodean DataMatrix dalam ASCII dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Baca kode batang DataMatrix C# – Hasilkan Mode DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cara Menghasilkan Kode Batang DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}