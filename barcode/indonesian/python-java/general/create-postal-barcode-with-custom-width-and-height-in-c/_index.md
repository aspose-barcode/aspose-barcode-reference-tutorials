---
category: general
date: 2026-09-16
description: Buat kode batang pos di C# dan pelajari cara mengatur lebar serta mengubah
  tinggi kode batang untuk pemindaian yang sempurna.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: id
lastmod: 2026-09-16
og_description: Buat kode batang pos dalam C# dengan panduan langkah demi langkah
  ini, menunjukkan cara mengatur lebar dan mengubah tinggi kode batang untuk pemindaian
  pos yang handal.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Buat barcode pos dengan lebar dan tinggi khusus di C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Buat barcode pos dengan lebar dan tinggi khusus di C#
url: /id/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode pos dengan lebar dan tinggi khusus dalam C#

Jika Anda perlu **membuat barcode pos** dalam C#, panduan ini menunjukkan cara menghasilkan barcode Planet dan RM4SCC dengan dimensi yang tepat. Pada akhir dua kalimat pertama Anda akan mengetahui panggilan API yang tepat untuk **mengatur lebar** dan **mengubah tinggi barcode**, sehingga Anda dapat menghasilkan barcode yang dapat dipindai dan sesuai dengan spesifikasi layanan pos.

Anda akan belajar:
* Cara menginstansiasi generator barcode untuk format Planet dan RM4SCC.  
* Properti tepat untuk **mengatur lebar** (X‑dimension) dalam piksel.  
* Cara **mengubah tinggi barcode** untuk tipe barcode tertentu.  
* Di mana file PNG yang dihasilkan disimpan dan seperti apa tampilannya.

Satu-satunya prasyarat adalah referensi ke pustaka `Aspose.BarCode` (atau serupa) yang menyediakan kelas `BarcodeGenerator`. Tidak ada paket NuGet tambahan yang diperlukan selain SDK barcode itu sendiri.

---

## Buat barcode pos dengan dimensi khusus

Pertama, tambahkan direktif `using` yang diperlukan dan buat program konsol sederhana. Contoh lengkap yang dapat dijalankan disajikan setelah penjelasan langkah‑per‑langkah.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Mengapa ini berhasil:**  
* `EncodeTypes.Planet` dan `EncodeTypes.RM4SCC` memberi tahu generator standar pos mana yang harus diikuti.  
* `XDimension.Pixels` mengontrol **lebar** setiap modul barcode (elemen hitam/putih terkecil).  
* `BarHeight.Pixels` memungkinkan Anda **mengubah tinggi barcode** untuk format yang tidak menghitung tinggi secara otomatis, seperti RM4SCC.

Menjalankan program akan membuat dua file PNG di direktori kerja executable:
* `PostalPlanetBarWidth4.png` – barcode Planet dengan lebar modul 4 px.  
* `PostalRM4SCCHeight100.png` – barcode RM4SCC dengan lebar 4 px dan tinggi tetap 100 px.

---

## Cara mengatur lebar untuk barcode pos

Langkah **cara mengatur lebar** sama untuk setiap format pos yang didukung:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` adalah bilangan bulat yang mewakili ukuran piksel satu modul.  
* Nilai tipikal untuk barcode pos adalah **4 px**, tetapi Anda dapat meningkatkannya untuk pencetakan resolusi tinggi.  

**Tips profesional:** Saat mencetak pada printer yang dikontrol DPI, kalikan lebar piksel dengan faktor DPI printer untuk mempertahankan dimensi fisik.

---

## Mengubah tinggi barcode untuk barcode pos RM4SCC

Hanya sebagian kecil simbologi pos (misalnya RM4SCC) yang memerlukan tinggi eksplisit. Gunakan properti **mengubah tinggi barcode**:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` adalah total tinggi gambar barcode, bukan tinggi satu modul.  
* Menetapkan `BarHeight` ke **100 px** menghasilkan barcode tinggi, mudah dibaca, dan sesuai dengan banyak pedoman layanan pos.

**Kasus tepi:** Jika Anda menetapkan tinggi yang terlalu kecil, barcode dapat menjadi tidak terbaca oleh pemindai. Selalu uji dengan cetakan fisik sebelum penyebaran massal.

---

## File sumber lengkap untuk salin‑tempel cepat

Berikut adalah seluruh program yang dapat Anda salin ke proyek konsol baru. Tidak ada kode lain yang diperlukan.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Output yang diharapkan** (konsol):

```
Both postal barcodes have been saved.
```

Dan dua file PNG muncul di folder output, masing‑masing menampilkan barcode pos yang jelas siap untuk dicetak atau disematkan.

---

## Pertanyaan umum dan pemecahan masalah

| Pertanyaan | Jawaban |
|------------|---------|
| *Bagaimana jika saya memerlukan X‑dimension yang berbeda untuk setiap barcode?* | Buat instance `BarcodeGenerator` terpisah dan tetapkan nilai `XDimension.Pixels` yang berbeda sebelum memanggil `Save`. |
| *Mengapa barcode Planet mengabaikan `BarHeight`?* | Format Planet secara otomatis menghitung tinggi dari X‑dimension, sehingga pengaturan `BarHeight` tidak berpengaruh. |
| *Bisakah saya menghasilkan SVG alih‑alih PNG?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`. |
| *Bagaimana jika gambar menjadi buram saat dicetak?* | Tingkatkan X‑dimension (misalnya menjadi 6 px) dan hasilkan gambar pada DPI yang lebih tinggi menggunakan pengaturan `Resolution` pada generator. |

---

## Kesimpulan

Anda kini tahu cara **membuat barcode pos** dalam C# dan secara tepat **mengatur lebar** serta **mengubah tinggi barcode** menggunakan API `BarcodeGenerator`. Contoh ini mencakup format yang otomatis menyesuaikan ukuran (Planet) dan yang memerlukan penyesuaian manual (RM4SCC), memberikan fondasi yang kuat untuk proyek otomasi pos apa pun.

Selanjutnya, Anda dapat menjelajahi:
* Menambahkan teks yang dapat dibaca manusia di bawah barcode (`CodeTextParameters`).  
* Mengekspor ke format lain seperti SVG atau PDF untuk pencetakan berbasis vektor.  
* Mengintegrasikan generator ke dalam API web untuk menyajikan barcode secara dinamis.

Silakan bereksperimen dengan berbagai dimensi, enkoding, dan format output untuk menyesuaikan alur kerja pengiriman Anda. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑per‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Buat Gambar Barcode Pos dalam C# – Panduan Langkah‑per‑Langkah Lengkap](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Buat Barcode Pos dalam C# – Contoh Generator Lengkap](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Contoh generator barcode dalam C# – atur lebar dan tinggi](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}