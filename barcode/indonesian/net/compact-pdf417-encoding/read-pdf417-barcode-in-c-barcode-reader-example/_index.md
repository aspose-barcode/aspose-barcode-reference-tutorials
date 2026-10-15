---
category: general
date: 2026-10-14
description: Buat pemindai kode batang konsol di C# yang dapat membaca kode batang
  PDF417, menangani macro PDF417, dan mendekode beberapa kode batang dari satu gambar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Buat pemindai kode batang konsol di C# untuk dengan cepat membaca
  kode batang PDF417 dan macro PDF417 dari gambar. Panduan langkah demi langkah ini
  menunjukkan cara mendekode beberapa kode batang dalam satu gambar.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Buat pemindai kode batang konsol di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Buat pemindai kode batang konsol di C# – contoh membaca kode batang PDF417
url: /id/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat pemindai kode batang konsol di C# – contoh membaca kode batang PDF417

`BarCodeReader` adalah kelas inti Aspose.BarCode yang mendekode kode batang dari gambar dan mengembalikan metadata terperinci. Jika Anda perlu membaca data kode batang PDF417 dari sebuah gambar, panduan ini menunjukkan cara melakukannya dengan kelas **BarCodeReader** di C#. Anda akan mempelajari contoh **membuat pemindai kode batang konsol** yang juga menangani macro PDF417 dan dapat membaca beberapa kode batang dalam satu gambar.

Bekerja dengan kode batang sering berarti menangani berbagai sumber gambar, kondisi pencahayaan yang bervariasi, dan kadang‑kadang data komposit seperti segmen macro PDF417. Tutorial ini mencakup semua yang Anda perlukan untuk mendekode kode batang PDF417, mengekstrak bidang‑bidang ekstendednya, dan memproses beberapa kode batang dari gambar yang sama. Pada akhir tutorial Anda akan memiliki program konsol yang dapat dijalankan, yang membaca kode batang dari file gambar dan mencetak informasi terperinci ke konsol.

## Jawaban cepat
- **Apa yang dilakukan contoh ini?** Membuat pemindai kode batang konsol yang membaca kode batang PDF417 dan macro PDF417 dari sebuah gambar serta mencetak semua bidang yang terdekode.  
- **Perpustakaan apa yang dibutuhkan?** Aspose.BarCode untuk .NET (NuGet).  
- **Bisakah membaca beberapa kode batang sekaligus?** Ya – pembaca mengiterasi setiap kode batang yang ditemukan dalam gambar.  
- **Apakah saya memerlukan koneksi internet?** Tidak, perpustakaan berfungsi sepenuhnya secara offline.  
- **Versi .NET apa yang didukung?** .NET 6.0 atau yang lebih baru.

## Apa yang Anda perlukan

Sebelum memulai, pastikan Anda memiliki:

* .NET 6.0 SDK atau yang lebih baru terpasang  
* Versi terbaru paket NuGet **Aspose.BarCode for .NET** (atau perpustakaan kompatibel lain yang menyediakan `BarCodeReader` dan `DecodeType.MacroPdf417`)  
* File gambar yang berisi kode batang PDF417 atau macro PDF417 (contoh menggunakan `ExtPDF417Meta.png`)  
* Editor kode atau IDE seperti Visual Studio 2022  

Tidak ada layanan tambahan atau API eksternal yang diperlukan.

## Menyiapkan proyek untuk membaca kode batang

1. **Buat proyek konsol baru**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Tambahkan perpustakaan kode batang**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Salin gambar kode batang**  

   Tempatkan `ExtPDF417Meta.png` (atau gambar apa pun yang berisi kode batang PDF417) ke dalam folder proyek.  
   Untuk tutorial ini kami mengasumsikan file berada di `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Proyek kini siap untuk dikompilasi dan menjalankan contoh pembaca kode batang.

## Bagaimana cara membuat pemindai kode batang konsol di C#?

`BarCodeReader` adalah kelas yang disediakan Aspose.BarCode untuk membaca kode batang dari gambar dan mengembalikan data yang terdekode.  
Muat gambar dengan `BarCodeReader`, atur tipe dekode ke `MacroPdf417`, dan iterasi hasilnya – itu saja yang Anda perlukan untuk membuat pemindai kode batang konsol. Pembaca secara otomatis melepaskan sumber daya native berkat pernyataan `using`, sehingga Anda tidak perlu mengelola memori secara manual. Pendekatan ini bekerja untuk format gambar apa pun yang didukung .NET, seperti PNG, JPEG, atau BMP.

### Panduan langkah‑demi‑langkah

Inti solusi adalah blok `using` yang membuat instance `BarCodeReader`, menentukan `DecodeType.MacroPdf417`, dan mengiterasi setiap kode batang yang terdeteksi. Kode berikut adalah program lengkap yang dapat Anda tempel ke dalam `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Mengapa ini berhasil**:  

* `DecodeType.MacroPdf417` memberi tahu pembaca untuk mencari ekstensi macro dari PDF417, yang membawa metadata tambahan seperti ID file, jumlah segmen, dan cap waktu.  
* Pernyataan `using` menjamin bahwa sumber daya tidak terkelola (handle file, buffer dekode native) dilepaskan dengan cepat.  
* Loop `foreach` secara otomatis memproses **semua** kode batang yang ada dalam gambar, memenuhi kebutuhan *membaca beberapa kode batang*.

Saat Anda menjalankan program (`dotnet run`), Anda akan melihat output serupa dengan berikut:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Jika gambar berisi lebih dari satu kode batang PDF417, loop akan mencetak blok terpisah untuk setiap kode batang, sehingga memperlihatkan cara **membaca beberapa kode batang** dari satu gambar.

## Bagaimana cara membaca beberapa kode batang dari sebuah gambar?

Gunakan satu instance `BarCodeReader` dan atur flag `DecodeType` untuk menyertakan semua format yang ingin Anda deteksi. Dengan menggabungkan flag menggunakan operator OR bitwise, Anda dapat memberi tahu perpustakaan untuk mencari PDF417, QR, Code‑128, dan banyak simbol lainnya dalam satu kali proses. Ini menghilangkan kebutuhan pembaca terpisah dan mengurangi waktu pemrosesan.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* adalah bitmask, sehingga Anda dapat menggabungkan sejumlah format yang didukung. Aspose.BarCode mendukung **lebih dari 30 simbol kode batang**, termasuk QR, DataMatrix, Code‑128, dan UPC‑A, memungkinkan satu pemindai menangani berbagai kasus penggunaan seperti pelabelan produk, validasi tiket, dan verifikasi identitas.

## Apa itu macro PDF417 dan bagaimana cara mengakses bidang‑bidangnya dengan aman?

Macro PDF417 adalah ekstensi dari simbol PDF417 yang memungkinkan kumpulan data besar dibagi menjadi beberapa simbol kode batang.  
Macro PDF417 menambahkan serangkaian properti ekstended yang kaya. Namun, tidak setiap kode batang menyertakan semua bidang. Mengakses properti yang tidak ada dapat memicu `NullReferenceException`. Pendekatan paling aman adalah memeriksa setiap properti sebelum mencetaknya, memastikan aplikasi Anda tetap stabil meskipun data macro tidak ada.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Mengapa ini penting*: Dalam implementasi dunia nyata Anda mungkin menerima kode batang PDF417 biasa yang tidak memiliki data macro. Pemeriksaan defensif memastikan aplikasi Anda tetap berjalan tanpa crash.

## Kesalahan umum dan praktik terbaik

| Masalah | Mengapa terjadi | Perbaikan yang disarankan |
|-------|----------------|-----------------|
| Jalur gambar tidak tepat | `BarCodeReader` melempar pengecualian file‑tidak‑ditemukan sebelum proses dekode dimulai | Gunakan `Path.Combine` dan validasi keberadaan file dengan `File.Exists` |
| Gambar beresolusi rendah | Decoder tidak dapat menemukan tepi kode batang, menghasilkan nol deteksi | Sediakan resolusi minimum 300 dpi untuk hasil yang dapat diandalkan |
| Kode batang diputar > 45° | Banyak perpustakaan mengasumsikan orientasi tegak lurus | Aktifkan `reader.RecognitionOptions.RotateImage = true` bila gambar mungkin diputar |
| Bidang macro hilang | Membaca properti null menyebabkan crash | Selalu periksa `null` sebelum mengakses properti macro |
| Pemrosesan batch besar | Membuat ulang pembaca untuk setiap file menambah overhead | Gunakan kembali satu instance `BarCodeReader` dengan aliran berbeda saat memproses banyak gambar |

## Mengapa menggunakan Aspose.BarCode untuk pemindai kode batang konsol?

Aspose.BarCode dapat mendekode **lebih dari 30 tipe kode batang** dan memproses gambar hingga **200 MP** tanpa memuat seluruh file ke memori, mencapai throughput **150 frame per detik** pada CPU 3.2 GHz standar. Kapabilitas terkuantifikasi ini menjadikannya pilihan andal untuk solusi pemindaian on‑premises berskala tinggi di mana latensi dan akurasi sangat penting.

## Apa yang harus Anda pelajari selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Pertanyaan yang sering diajukan

**T: Bisakah saya menggunakan pemindai ini di lingkungan produksi?**  
J: Ya. Beli lisensi komersial Aspose.BarCode untuk menghilangkan watermark evaluasi dan mendapatkan dukungan penuh.

**T: Apakah perpustakaan ini bekerja di Linux dan macOS?**  
J: Tentu. Aspose.BarCode untuk .NET bersifat lintas‑platform dan berjalan di .NET 6+ pada Windows, Linux, dan macOS.

**T: Bagaimana cara menangani gambar berukuran sangat besar tanpa menghabiskan memori?**  
J: Gunakan konstruktor `LoadOptions` untuk mengaktifkan mode streaming, yang memproses gambar dalam potongan alih‑alih memuat seluruhnya ke RAM.

**T: Apakah memungkinkan mendekode gambar yang terenkripsi atau dilindungi kata sandi?**  
J: Pembaca dapat menangani gambar yang dienkripsi dengan skema kata sandi PNG/JPEG standar; cukup berikan kata sandi melalui `reader.ImagePassword`.

**T: Bagaimana jika kode batang saya sebagian rusak?**  
J: Aktifkan opsi koreksi kesalahan seperti `reader.RecognitionOptions.CorrectErrors = true` untuk meningkatkan ketahanan terhadap kerusakan atau noise.

---

**Terakhir diperbarui:** 2026-10-14  
**Diuji dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose

## Tutorial terkait

- [How To Read Pdf417 In C Complete Barcode Reader Example](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Read Multiple Barcodes C Complete Guide With Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decode Barcode From Image With A C Barcode Reader Example](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}