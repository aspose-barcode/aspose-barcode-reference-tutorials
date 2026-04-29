---
date: 2026-01-09
description: Pelajari cara membuat kode batang Aztec dengan tingkat koreksi kesalahan
  yang dapat disesuaikan menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi
  langkah dengan contoh kode.
linktitle: Aztec Error Level Example
second_title: Aspose.BarCode .NET API
title: Cara membuat barcode Aztec dengan koreksi kesalahan di .NET
url: /id/net/aztec-barcode-encoding/aztec-error-level-example/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat kode batang Aztec dengan koreksi kesalahan di .NET

Dalam tutorial langkah‑demi‑langkah ini, Anda akan belajar cara **membuat gambar kode batang Aztec** yang mencakup berbagai tingkat koreksi kesalahan menggunakan pustaka Aspose.BarCode untuk .NET. Baik Anda memerlukan kode batang yang kuat untuk kemasan, tiket, atau pemindaian seluler, mengontrol tingkat kesalahan membantu Anda menyeimbangkan kapasitas data dan ketahanan terhadap kerusakan. Kami akan membahas setiap opsi konfigurasi, menunjukkan kode yang tepat, dan menjelaskan mengapa setiap pengaturan penting.

## Jawaban Cepat
- **Pustaka apa yang digunakan?** Aspose.BarCode untuk .NET  
- **Apakah saya dapat mengatur tingkat kesalahan khusus?** Ya – angka bulat apa pun dari 0 % hingga 100 %  
- **IDE apa yang direkomendasikan?** Visual Studio (edisi apa saja) atau VS Code dengan dukungan .NET  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi  
- **Format output yang didukung?** PNG, JPEG, BMP, GIF, dan lainnya  

## Apa itu pembuatan kode batang Aztec dengan koreksi kesalahan?
Kode batang Aztec adalah kode matriks dua dimensi yang dapat menyimpan sejumlah besar data dalam kotak persegi yang kompak. Koreksi kesalahan menambahkan data redundan sehingga kode batang tetap dapat dibaca meskipun sebagian dari kode tersebut rusak atau tertutup. Menyesuaikan tingkat koreksi kesalahan memungkinkan Anda memilih antara kapasitas data yang lebih tinggi (tingkat kesalahan lebih rendah) atau ketahanan yang lebih besar (tingkat kesalahan lebih tinggi).

## Mengapa menggunakan Aspose.BarCode untuk .NET?
Aspose.BarCode menyediakan API yang fluens yang menyembunyikan detail enkoding tingkat rendah, memungkinkan Anda fokus pada logika bisnis. Pustaka ini mendukung beragam standar kode batang, menawarkan kustomisasi ekstensif (ukuran, warna, margin), dan bekerja di .NET Framework, .NET Core, serta .NET 5/6+. Hal ini menjadikannya pilihan ideal untuk aplikasi kelas perusahaan di mana keandalan dan fleksibilitas sangat penting.

## Prasyarat

- Pengetahuan dasar tentang C# dan ekosistem .NET.  
- Visual Studio, Visual Studio Code, atau IDE kompatibel C# lainnya.  
- Pustaka Aspose.BarCode untuk .NET – unduh dari [tautan ini](https://releases.aspose.com/barcode/net/).  
- (Opsional) Lisensi sementara untuk percobaan tanpa hambatan – dapatkan [di sini](https://purchase.aspose.com/temporary-license/).

## Mengimpor Namespace

Untuk memulai, bawa namespace Aspose.BarCode yang diperlukan ke dalam proyek Anda:

```csharp
using Aspose.BarCode.Generation;
```

## Langkah 1: Menyiapkan Barcode Generator

Buat instance `BarcodeGenerator`, tentukan tipe **Aztec**, dan berikan data yang ingin Anda enkode.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecErrorLevelExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde© is a powerful library to generate & recognize 1D & 2D barcodes");
```

> **Tips pro:** Ganti `"Your Directory Path"` dengan jalur absolut atau relatif di mana Anda memiliki izin menulis.

## Langkah 2: Menentukan X‑Dimension

X‑Dimension mengontrol lebar modul terkecil (piksel) dalam kode batang. Menetapkannya ke 4 piksel menghasilkan gambar yang jelas dan dapat dipindai.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## Langkah 3: Memilih Mode Simbol Aztec

Aztec mendukung beberapa mode simbol. Menggunakan `FullRange` memungkinkan pustaka secara otomatis memilih ukuran optimal berdasarkan data dan pengaturan koreksi kesalahan Anda.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
```

## Langkah 4: Menetapkan Kapasitas Koreksi Kesalahan

Sekarang kita sesuaikan tingkat koreksi kesalahan. Dalam contoh ini kami membuat dua kode batang—satu dengan tingkat kesalahan 5 % yang sederhana dan satu lagi dengan tingkat 50 % yang kuat—untuk memperlihatkan perbedaan visual.

```csharp
// Set error correction capacity to 5%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 5;
gen.Save($"{path}AztecErrorLevel5.png", BarCodeImageFormat.Png);

// Set error correction capacity to 50%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 50;
gen.Save($"{path}AztecErrorLevel50.png", BarCodeImageFormat.Png);
```

Menjalankan kode akan menghasilkan dua file PNG di folder yang ditentukan. Versi 50 % berisi lebih banyak data redundan, sehingga lebih toleran terhadap kerusakan dengan biaya simbol yang sedikit lebih besar.

## Masalah Umum & Solusi

| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| Gambar kode batang buram | X‑Dimension terlalu rendah untuk ukuran output yang dipilih | Tingkatkan `XDimension.Pixels` (mis., menjadi 6 atau 8). |
| Operasi penyimpanan melempar *AccessDenied* | Jalur tidak valid atau tidak dapat ditulisi | Pastikan variabel `path` mengarah ke folder yang dapat Anda tulis. |
| Pemindai tidak dapat membaca kode | Tingkat kesalahan terlalu tinggi untuk jumlah data | Kurangi `AztecErrorLevel` atau pendekkan teks yang dienkode. |

## Pertanyaan yang Sering Diajukan

**T: Apa tujuan koreksi kesalahan pada kode batang Aztec?**  
J: Koreksi kesalahan memastikan kode batang tetap dapat dibaca meskipun sebagian rusak, tergores, atau tertutup. Tingkat yang lebih tinggi menambahkan lebih banyak redundansi, meningkatkan keandalan.

**T: Bisakah saya menyesuaikan tampilan kode batang Aztec yang dihasilkan?**  
J: Ya. Selain X‑Dimension dan tingkat kesalahan, Anda dapat mengubah warna, margin, bahkan menyematkan logo menggunakan parameter Aspose.BarCode lainnya.

**T: Apakah Aspose.BarCode untuk .NET kompatibel dengan format kode batang lain?**  
J: Tentu. Kelas `BarcodeGenerator` yang sama mendukung QR Code, DataMatrix, PDF417, Code128, dan banyak lagi.

**T: Apakah saya memerlukan lisensi untuk menggunakan Aspose.BarCode untuk .NET?**  
J: Lisensi sementara tersedia untuk evaluasi. Untuk penggunaan produksi, beli lisensi penuh dari [tautan ini](https://purchase.aspose.com/buy).

**T: Di mana saya dapat menemukan dokumentasi resmi?**  
J: Referensi API lengkap tersedia [di sini](https://reference.aspose.com/barcode/net/).

## Kesimpulan

Anda kini tahu cara **membuat gambar kode batang Aztec** dengan tingkat koreksi kesalahan yang dapat disesuaikan menggunakan Aspose.BarCode untuk .NET. Dengan mengatur X‑Dimension, mode simbol, dan tingkat kesalahan, Anda dapat menghasilkan kode batang yang memenuhi persyaratan keandalan dan ukuran aplikasi Anda. Jangan ragu bereksperimen dengan string data dan persentase kesalahan yang berbeda untuk melihat bagaimana kode batang beradaptasi.

Jika Anda menghadapi tantangan, komunitas aktif di [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), dan dokumentasi resmi menyediakan wawasan lebih dalam tentang kustomisasi lanjutan.

---

**Terakhir Diperbarui:** 2026-01-09  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
