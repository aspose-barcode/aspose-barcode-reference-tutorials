---
category: general
date: 2026-08-03
description: Tutorial generator barcode C# yang menunjukkan cara membuat barcode Planet
  dengan Aspose.BarCode, mengatur dimensi X, dan menyimpan sebagai gambar PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: id
lastmod: 2026-08-03
og_description: Tutorial generator barcode C# memandu Anda membuat barcode Planet,
  menyesuaikan dimensi X, dan menyimpan sebagai PNG menggunakan Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Generator barcode C# – buat barcode Planet langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator barcode C# – contoh pembuatan barcode Planet dan RM4SCC
url: /id/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator barcode C# – contoh pembuatan barcode Planet dan RM4SCC

Jika Anda membutuhkan **barcode generator C#** yang dapat menghasilkan simbol khusus pos, panduan ini menunjukkan secara tepat cara **membuat barcode Planet** dengan Aspose.BarCode. Anda akan melihat cara mengkonfigurasi X‑dimension, menghasilkan barcode RM4SCC yang cocok, dan menyimpan keduanya sebagai file PNG—semua dalam beberapa langkah singkat.

Tutorial ini mencakup semua yang Anda perlukan untuk menjalankan kode pada .NET 6 atau yang lebih baru, menjelaskan mengapa setiap pengaturan penting, dan menyoroti jebakan umum seperti lebar modul yang salah atau izin folder yang hilang. Pada akhir tutorial Anda akan memiliki dua gambar barcode siap cetak yang mematuhi standar Planet dan RM4SCC.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

* .NET 6 SDK (atau versi .NET apa pun yang didukung oleh Aspose.BarCode)
* Visual Studio 2022 atau IDE C# lain yang Anda sukai
* Referensi NuGet ke **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Izin menulis ke folder tempat Anda berencana menyimpan file PNG

Tidak ada layanan eksternal tambahan yang diperlukan; perpustakaan menangani semua proses enkoding secara lokal.

## Langkah 1: Inisialisasi objek barcode generator C# 

Tugas pertama adalah membuat instance `BarcodeGenerator`. Konstruktor menerima symbology barcode (`EncodeTypes.Planet`) dan data yang akan dienkode.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Mengapa langkah ini?*  
`BarcodeGenerator` adalah titik masuk untuk setiap barcode yang Anda hasilkan. Memilih `EncodeTypes.Planet` memberi tahu perpustakaan untuk mengikuti spesifikasi ISO/IEC 24723 yang digunakan oleh banyak layanan pos.

## Langkah 2: Atur X‑dimension (lebar modul) untuk barcode Planet

X‑dimension mendefinisikan lebar satu modul barcode (garis atau spasi terkecil). Nilai **4 piksel** biasanya cocok untuk sebagian besar printer label.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Mengapa ini penting*  
Jika modul terlalu sempit, barcode dapat menjadi tidak terbaca; terlalu lebar dan ukuran label menjadi tidak perlu besar. Menyesuaikan `Pixels` memungkinkan Anda menyetel barcode agar sesuai dengan resolusi printer spesifik Anda.

## Langkah 3: Simpan barcode Planet sebagai gambar PNG

Aspose.BarCode secara otomatis menghitung tinggi barcode berdasarkan symbology yang dipilih, jadi Anda hanya perlu menentukan jalur file dan formatnya.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
Ganti `YOUR_DIRECTORY` dengan jalur absolut atau relatif yang ada di mesin Anda. Jika folder tidak ada, metode `Save` akan melempar `DirectoryNotFoundException`.

**Output yang diharapkan** – sebuah file PNG yang terlihat serupa dengan ilustrasi di bawah (gambar sebenarnya tidak ditampilkan di sini, tetapi Anda akan melihat barcode Planet klasik dengan payload numerik `123456`).

## Langkah 4: Inisialisasi generator kedua untuk barcode RM4SCC

Banyak sistem pos memerlukan simbol Planet dan RM4SCC pada satu kiriman surat. Buat instance `BarcodeGenerator` baru untuk symbology RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Mengapa menggunakan instance terpisah?*  
Setiap symbology memiliki kumpulan parameter masing‑masing. Menggunakan generator yang sama dapat secara tidak sengaja membawa pengaturan (seperti X‑dimension) yang tidak optimal untuk barcode kedua.

## Langkah 5: Konfigurasikan X‑dimension untuk barcode RM4SCC

RM4SCC juga menghormati pengaturan X‑dimension, jadi kami menerapkan lebar piksel yang sama untuk konsistensi visual.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Jika Anda memerlukan barcode yang lebih tinggi (misalnya, untuk label yang lebih besar), Anda juga dapat mengatur `Height.Pixels`. Membiarkannya tidak diatur akan membuat perpustakaan menghitung tinggi ideal secara otomatis.

## Langkah 6: Simpan barcode RM4SCC sebagai gambar PNG

Akhirnya, simpan barcode RM4SCC ke disk.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Sekarang Anda memiliki dua file PNG—`PostalPlanetBarHeightNone.png` dan `PostalRM4SCCBarHeightNone.png`—yang dapat Anda sematkan dalam label pos, mencetak pada amplop, atau mengirim ke layanan cetak pihak ketiga.

## Opsional: Menyesuaikan tinggi atau menggunakan format gambar lain

Jika alur kerja Anda memerlukan tinggi barcode tertentu atau format gambar berbeda (misalnya JPEG atau BMP), Anda dapat memodifikasi parameter sebelum memanggil `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Kasus tepi** – Saat Anda menetapkan tinggi khusus, pastikan nilai tersebut memenuhi tinggi minimum yang diwajibkan oleh standar ISO; jika tidak, barcode dapat gagal validasi.

## Kesalahan umum dan cara menghindarinya

| Masalah | Mengapa terjadi | Solusi |
|---------|----------------|--------|
| `DirectoryNotFoundException` | Folder target tidak ada atau salah ketik. | Buat folder terlebih dahulu atau gunakan `Path.Combine` dengan `Environment.CurrentDirectory`. |
| Barcode tidak terbaca pada printer beresolusi rendah | X‑dimension terlalu kecil untuk DPI printer. | Tingkatkan `XDimension.Pixels` menjadi 5 – 6 untuk printer 203 dpi, atau uji dengan label contoh. |
| Symbology yang salah digunakan | Mengirim `EncodeTypes.Code128` alih‑alih `EncodeTypes.Planet`. | Periksa kembali nilai enum `EncodeTypes` agar sesuai dengan standar pos yang diperlukan. |
| Null reference pada `Parameters` | Menggunakan versi Aspose.BarCode yang lebih lama dimana API berbeda. | Tingkatkan ke paket NuGet terbaru (v23.12 atau lebih baru). |

## Contoh lengkap yang dapat dijalankan

Berikut adalah program lengkap yang dapat Anda salin, tempel, dan jalankan. Termasuk pernyataan `using`, penanganan error, dan komentar yang menjelaskan setiap baris.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Menjalankan program akan membuat folder `Barcodes` di samping executable dan menempatkan dua file PNG di dalamnya. Buka dengan penampil gambar apa pun untuk memverifikasi hasilnya.

## Kesimpulan

Anda kini memiliki solusi **barcode generator C#** yang dapat **membuat gambar barcode Planet**, menyesuaikan X‑dimension untuk pencetakan optimal, dan menghasilkan barcode RM4SCC yang cocok—semua dengan beberapa baris kode. Pendekatan ini bekerja dengan .NET 6+, hanya memerlukan paket NuGet Aspose.BarCode, dan dapat diperluas ke symbology lain seperti Code128, QR, atau DataMatrix dengan mengganti nilai `EncodeTypes`.

### Apa selanjutnya?

* Bereksperimen dengan nilai `XDimension.Pixels` yang berbeda untuk menyesuaikan DPI printer Anda.  
* Hasilkan barcode dalam format lain (PDF, SVG) dengan mengubah enum `BarCodeImageFormat`.  
* Gabungkan dua file PNG menjadi satu label menggunakan perpustakaan grafis seperti **SkiaSharp**.  
* Jelajahi seluruh API Aspose.BarCode untuk fitur lanjutan seperti validasi checksum atau font khusus.

Silakan sesuaikan kode untuk pemrosesan batch atau integrasikan ke layanan web ASP.NET Core yang mengembalikan gambar barcode sesuai permintaan. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Cara Menyimpan PNG menggunakan DataMatrix C40 dengan Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [tutorial generator barcode c# – Kustomisasi Rasio Aspek Barcode Code 16K dengan Aspose.BarCode untuk .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}