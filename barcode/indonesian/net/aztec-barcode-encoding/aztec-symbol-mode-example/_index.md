---
date: 2026-01-02
description: Pelajari cara menggunakan generator kode batang aztec dengan Aspose.BarCode
  untuk .NET – panduan langkah demi langkah tentang cara mengatur Mode Simbol aztec
  (Auto, FullRange, Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: Generator kode batang Aztec – Menguasai Mode Simbol Aztec dengan Aspose.BarCode
  untuk .NET
url: /id/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – Menguasai Aztec Symbol Mode dengan Aspose.BarCode untuk .NET

Jika Anda ingin menambahkan kemampuan pembuatan barcode yang kuat ke aplikasi .NET Anda, **barcode generator aztec** dari Aspose.BarCode untuk .NET adalah solusi yang fantastis. Pada tutorial ini kami akan menyelami Aztec Symbol Mode, menunjukkan **cara mengatur aztec** options, dan membimbing Anda melalui contoh kode praktis yang dapat langsung Anda gunakan dalam proyek.

## Jawaban Cepat
- **Kelas utama apa?** `BarcodeGenerator` dari `Aspose.BarCode.Generation`.
- **Symbol Mode apa saja yang tersedia?** Auto, FullRange, Compact, dan Rune.
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.
- **Bisakah saya mengubah teks kode?** Ya, set `gen.CodeText` sebelum menyimpan.
- **Format gambar apa yang didukung?** PNG, JPEG, BMP, GIF, TIFF, dan lainnya.

## Apa itu barcode generator aztec?
barcode generator aztec menghasilkan kode Aztec dua dimensi, sebuah barcode matriks kompak yang dapat menyimpan sejumlah besar data dalam ruang yang kecil. Ini ideal untuk tiket seluler, URL, dan data biner di mana ruang sangat terbatas.

## Mengapa menggunakan Aspose.BarCode untuk .NET?
- **Dukungan .NET penuh** – bekerja dengan .NET Framework, .NET Core, dan .NET 5/6.
- **Fitur lengkap** – berbagai symbol mode, koreksi kesalahan, dan kustomisasi ekstensif.
- **Tanpa ketergantungan eksternal** – menghasilkan barcode sepenuhnya dalam proses.
- **Lintas platform** – berjalan di Windows, Linux, dan macOS.

## Prasyarat

- Pengetahuan dasar tentang pengembangan .NET.  
- Visual Studio terpasang di mesin Anda.  
- Salinan Aspose.BarCode untuk .NET. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/barcode/net/).

Setelah Anda siap, mari jelajahi opsi Aztec Symbol Mode.

## Cara mengatur Aztec Symbol Mode dengan barcode generator aztec

### Mengimpor Namespace

Pertama, tambahkan namespace yang diperlukan di bagian atas file C# Anda:

```csharp
using Aspose.BarCode.Generation;
```

Dengan namespace yang diimpor, Anda dapat mulai membuat barcode Aztec.

### Langkah 1: Menyiapkan Barcode Generator

Inisialisasi generator dengan tipe enkoding Aztec dan berikan teks yang ingin Anda enkode:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Tip pro:** Gunakan string yang kompatibel UTF‑8 untuk karakter internasional, seperti yang ditunjukkan di atas.

### Langkah 2: Mengatur Symbol Mode ke Auto

Mode **Auto** membiarkan perpustakaan menentukan ukuran optimal berdasarkan panjang data:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

PNG yang dihasilkan akan disimpan ke folder yang Anda tentukan.

### Langkah 3: Mengatur Symbol Mode ke FullRange

Jika Anda ingin perpustakaan menggunakan seluruh rentang ukuran simbol Aztec, pilih **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Langkah 4: Mengatur Symbol Mode ke Compact

Untuk barcode yang lebih kompak namun tetap memiliki keterbacaan yang baik, gunakan **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Langkah 5: Mengatur Symbol Mode ke Rune

Mode **Rune** dirancang untuk kasus penggunaan khusus di mana gaya visual yang berbeda diperlukan:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Masalah Umum dan Solusinya

| Masalah | Solusi |
|-------|----------|
| Gambar barcode kosong | Pastikan `path` mengarah ke direktori yang ada dan dapat ditulisi. |
| Karakter tidak didukung | Gunakan hanya karakter yang didukung oleh standar Aztec atau beralih ke enkoding UTF‑8. |
| Ukuran simbol salah | Coba gunakan `AztecSymbolMode.Auto` agar perpustakaan memilih ukuran terbaik. |

## Pertanyaan yang Sering Diajukan

**T: Apa tujuan Aztec Symbol Mode dalam pembuatan barcode?**  
J: Mode ini memungkinkan Anda mengontrol kepadatan visual dan tingkat koreksi kesalahan kode Aztec, menyesuaikan barcode dengan kebutuhan ruang dan keterbacaan Anda.

**T: Bisakah saya mengubah teks kode untuk barcode Aztec di Aspose.BarCode untuk .NET?**  
J: Ya, cukup tetapkan string baru ke `gen.CodeText` sebelum memanggil `Save`.

**T: Apakah ada versi percobaan gratis Aspose.BarCode untuk .NET?**  
J: Ya, Anda dapat mengunduh percobaan gratis [di sini](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi lengkap Aspose.BarCode untuk .NET?**  
J: Referensi API lengkap tersedia [di sini](https://reference.aspose.com/barcode/net/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?**  
J: Lisensi sementara dapat diminta melalui [tautan ini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Dalam panduan ini kami membahas semua yang perlu Anda ketahui untuk menggunakan **barcode generator aztec** dengan Aspose.BarCode untuk .NET, mulai dari menyiapkan generator hingga menguasai setiap Symbol Mode (Auto, FullRange, Compact, Rune). Dengan contoh-contoh ini, Anda kini dapat menyematkan barcode Aztec yang serbaguna ke dalam aplikasi .NET apa pun dengan cepat dan andal.

Jika Anda memiliki pertanyaan lebih lanjut, silakan bergabung dengan komunitas Aspose.BarCode di [forum dukungan mereka](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-02  
**Diuji Dengan:** Aspose.BarCode 24.10 untuk .NET  
**Penulis:** Aspose