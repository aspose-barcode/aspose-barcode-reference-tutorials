---
category: general
date: 2026-10-21
description: Cara membaca kode batang PDF417 di C# menggunakan pembaca kode batang
  dari gambar. Ikuti contoh pembaca kode batang C# langkah demi langkah ini untuk
  dekoding yang dapat diandalkan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: id
lastmod: 2026-10-21
og_description: Cara membaca kode batang PDF417 di C# dengan contoh pembaca kode batang
  lengkap. Pelajari cara mendekode gambar Macro PDF417 dan mengakses semua bidang
  tambahan.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Cara membaca barcode PDF417 di C# – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cara membaca kode batang PDF417 di C# – panduan lengkap pembaca kode batang
url: /id/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode PDF417 di C# – panduan lengkap pembaca barcode

Jika Anda perlu **cara membaca barcode PDF417** dalam aplikasi .NET, panduan ini menunjukkan solusi siap‑jalankan. Anda akan melihat cara **membaca barcode dari gambar C#** menggunakan perpustakaan barcode populer dan mendapatkan setiap atribut Macro PDF417 tanpa alat tambahan.

Tutorial ini mencakup semua yang diperlukan untuk **contoh pembaca barcode C#**: penyiapan proyek, penjelasan kode, dan tip untuk menangani kasus tepi. Pada akhir tutorial Anda dapat menempelkan kode ke proyek konsol dan mulai mendekode gambar PDF417 secara langsung.

## Apa yang Anda butuhkan

| Prasyarat | Alasan |
|--------------|--------|
| .NET 6.0 SDK or later | Menyediakan runtime untuk aplikasi konsol C# |
| Visual Studio 2022 (or any C# IDE) | Memungkinkan pembuatan proyek dan debugging yang mudah |
| Aspose.BarCode for .NET (NuGet package) | Menyediakan kelas `BarCodeReader` dan `DecodeType` |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | Berfungsi sebagai input untuk proses decoding |

Anda dapat menginstal perpustakaan dengan dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Cara membaca barcode PDF417 dari gambar di C#

Inti dari alur kerja **membaca barcode dari gambar C#** terdiri dari tiga tindakan:

1. Inisialisasi `BarCodeReader` untuk `DecodeType` tertentu.
2. Iterasi melalui koleksi `BarCodeResult` yang dikembalikan.
3. Akses bidang PDF417 dasar dan yang diperluas.

Berikut adalah kode lengkap yang dapat dijalankan. Simpan sebagai `Program.cs` di dalam proyek konsol.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Penjelasan setiap langkah

* **Langkah 1 – Inisialisasi pembaca**  
  Konstruktor `BarCodeReader` menerima path file gambar dan sebuah `DecodeType`. `DecodeType.MacroPdf417` memberi tahu perpustakaan untuk mencari simbol Macro PDF417, yang berisi metadata tambahan di luar barcode PDF417 biasa.

* **Langkah 2 – ReadBarCodes()**  
  Metode ini mengembalikan `IEnumerable<BarCodeResult>` yang dapat berisi beberapa barcode jika gambar memiliki lebih dari satu. Loop `foreach` memastikan setiap simbol yang terdeteksi diproses.

* **Langkah 3 – Informasi dasar**  
  `CodeTypeName` mengidentifikasi format barcode (misalnya, “MacroPDF417”). `CodeText` berisi string data mentah yang dikodekan dalam simbol.

* **Langkah 4 – Bidang yang diperluas**  
  Macro PDF417 menambahkan sekumpulan properti yang diperluas di bawah `barcodeResult.Extended.Pdf417`. Bidang-bidang ini menampilkan data tingkat‑file seperti `FileID`, `SegmentID`, dan `FileName`. Mengaksesnya secara langsung memungkinkan Anda membangun kembali dokumen multi‑segmen atau memverifikasi integritas.

#### Output konsol yang diharapkan

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Nilai tepat mencerminkan konten yang dikodekan dalam `MacroPdf417.png` Anda. Jika gambar berisi satu segmen, `SegmentsCount` akan menjadi 1 dan `SegmentID` akan menjadi 0.

## Siapkan lingkungan pembaca barcode C#

Contoh **pembaca barcode C#** yang handal bergantung pada konfigurasi proyek yang bersih:

1. **Buat proyek konsol baru**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Tambahkan paket Aspose.BarCode** (seperti yang ditunjukkan sebelumnya).  
3. **Salin file gambar** ke dalam folder proyek atau referensikan dengan path absolut.  
4. **Bangun dan jalankan**  
   ```bash
   dotnet run
   ```

Jika proses build gagal dengan kesalahan referensi yang hilang, pastikan pernyataan `using Aspose.BarCode;` sesuai dengan versi paket yang diinstal. API perpustakaan stabil di .NET 6 dan .NET 8, sehingga Anda dapat meningkatkan runtime tanpa mengubah kode.

## Dekode barcode Macro PDF417

Saat Anda memanggil `ReadBarCodes()`, perpustakaan melakukan hal berikut secara internal:

* **Pra‑pemrosesan gambar** – mengubah bitmap menjadi matriks biner, memperbaiki rotasi dan noise.  
* **Deteksi pola** – memindai pola start/stop PDF417 dan mengekstrak lebar modul.  
* **Koreksi kesalahan** – menerapkan kode Reed‑Solomon untuk memulihkan codeword yang rusak.  
* **Ekstraksi Macro** – mengurai header segmen PDF417 yang diperluas dan mengisi objek `Extended.Pdf417`.

Memahami pipeline ini membantu Anda memutuskan kapan harus menyesuaikan opsi decoder. Misalnya, jika gambar Anda berkontras rendah, Anda dapat mengaktifkan properti `BarCodeReader` `ReadQuality` (tersedia pada versi selanjutnya) untuk meningkatkan tingkat deteksi.

## Interpretasikan bidang PDF417 yang diperluas

Bidang yang diperluas memetakan langsung ke spesifikasi Macro PDF417:

| Bidang | Arti |
|-------|---------|
| `MacroPdf417FileID` | Pengidentifikasi unik untuk seluruh file di semua segmen |
| `MacroPdf417SegmentID` | Indeks berbasis nol dari segmen saat ini |
| `MacroPdf417SegmentsCount` | Jumlah total segmen yang membentuk file |
| `MacroPdf417FileName` | Nama file asli yang disimpan saat enkoding |
| `MacroPdf417Checksum` | Checksum 16‑bit untuk verifikasi integritas |
| `MacroPdf417FileSize` | Ukuran file asli dalam byte |
| `MacroPdf417TimeStamp` | Timestamp UTC saat barcode dihasilkan |
| `MacroPdf417Addressee` | Penerima yang dimaksud dari dokumen |
| `MacroPdf417Sender` | Pengirim dokumen |
| `MacroPdf417Terminator` | String literal “END” menandai segmen terakhir |

Anda dapat menggunakan nilai-nilai ini untuk merekonstruksi PDF multi‑segmen, memverifikasi bahwa tidak ada segmen yang hilang, atau mencatat informasi audit untuk tujuan kepatuhan.

## Kesalahan umum dan pemecahan masalah

| Gejala | Penyebab kemungkinan | Perbaikan |
|---------|--------------|-----|
| Tidak ada output yang muncul | Path gambar salah atau format tidak didukung | Gunakan path absolut dan pastikan file berupa PNG/JPEG yang didukung oleh Aspose.BarCode |
| `CodeType` menampilkan “PDF417” bukan “MacroPDF417” | Gambar berisi simbol PDF417 biasa, bukan varian macro | Verifikasi barcode sumber dienkode dengan ekstensi Macro PDF417 |
| Beberapa bidang kosong | Barcode dihasilkan tanpa bidang macro tersebut | Enkode barcode dengan payload macro lengkap, atau tangani nilai null dalam kode |
| Decoder melempar `ArgumentException` | `DecodeType` yang salah ditentukan | Ubah `DecodeType.MacroPdf417` menjadi `DecodeType.Pdf417` jika Anda hanya membutuhkan data PDF417 standar |

**Tips pro:** Bungkus akses bidang dengan pengecekan null jika Anda mengantisipasi barcode non‑macro. Objek `Extended.Pdf417` mengembalikan nilai default (mis., `0` untuk bidang numerik) ketika data tidak ada.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Ringkasan contoh lengkap yang berfungsi

Menggabungkan semua, program akhir terdiri dari direktif using, metode `Main`, dan loop empat langkah yang ditunjukkan sebelumnya. Tidak diperlukan file konfigurasi tambahan. Kompilasi dan jalankan proyek untuk melihat output konsol dengan semua properti Macro PDF417.

## Kesimpulan

Anda kini mengetahui **cara membaca barcode PDF417** di C# menggunakan **contoh pembaca barcode C#** yang ringkas. Panduan ini membawa Anda melalui penyiapan lingkungan, implementasi kode, dan interpretasi setiap bidang Macro PDF417 yang diperluas. Dengan dasar ini Anda dapat mengintegrasikan pemindaian barcode ke dalam sistem inventaris, alur kerja manajemen dokumen, atau backend seluler.

### Selanjutnya

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara membaca PDF417 di C# – panduan lengkap pembaca barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Cara mendekode PDF417 di C# dengan contoh pembaca barcode](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Cara membuat gambar barcode PDF417 di C# dengan opsi Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}