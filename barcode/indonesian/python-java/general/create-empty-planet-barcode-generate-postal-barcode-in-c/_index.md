---
category: general
date: 2026-10-08
description: Buat barcode planet kosong dengan C# dan pelajari cara menghasilkan barcode
  pos menggunakan Aspose.BarCode. Kode langkah demi langkah serta tips disertakan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: id
lastmod: 2026-10-08
og_description: Buat barcode planet kosong dengan Aspose.BarCode di C# dan lihat cara
  menghasilkan gambar barcode pos untuk aplikasi pengiriman.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Buat barcode planet kosong – Panduan barcode pos C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Buat barcode planet kosong, hasilkan barcode pos di C#
url: /id/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode planet kosong, hasilkan barcode pos dalam C#

Jika Anda perlu **membuat barcode planet kosong** untuk sistem pengiriman, panduan ini menunjukkan secara tepat cara melakukannya dengan Aspose.BarCode untuk .NET. Anda juga akan belajar **cara menghasilkan gambar barcode pos** seperti Planet dan RM4SCC, menyesuaikan lebar bar, dan mengontrol opsi filled‑bars.

Menghasilkan barcode pos tidak memerlukan perpustakaan grafis terpisah. Aspose.BarCode SDK menyediakan satu API yang menangani enkoding, rendering gambar, dan pemilihan format gambar. Pada akhir tutorial ini Anda akan memiliki tiga file PNG siap pakai:

* `PostalPlanetEmptyBars.png` – barcode Planet dengan bar kosong  
* `PostalPlanetFilledBars.png` – barcode Planet dengan bar terisi default  
* `PostalRM4SCCFilledBars.png` – barcode RM4SCC dengan bar terisi  

Anda dapat menempatkan file‑file ini ke dalam template label surat apa pun, mencetaknya pada amplop, atau mengirimkannya ke layanan pihak ketiga.

## Prasyarat

* .NET 6.0 atau yang lebih baru (kode ini juga berfungsi dengan .NET Framework 4.7+).  
* Visual Studio 2022 atau IDE C# apa pun.  
* Aspose.BarCode untuk .NET – instal melalui NuGet:

```bash
dotnet add package Aspose.BarCode
```

Tidak ada dependensi tambahan yang diperlukan.

## Buat barcode planet kosong dengan Aspose.BarCode

Simbol Planet merupakan bagian dari keluarga barcode United States Postal Service (USPS). Secara default SDK menggambar bar **terisi**. Untuk **membuat barcode planet kosong**, Anda menonaktifkan flag `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Mengapa ini berhasil:**  
`EncodeTypes.Planet` memberi tahu generator untuk menggunakan simbol Planet. `XDimension.Pixels` mengontrol lebar fisik setiap bar, yang penting bagi pemindai pos yang mengharapkan ukuran modul tertentu. Menetapkan `FilledBars` ke `false` memberi tahu renderer untuk menggambar hanya kontur setiap bar, menghasilkan tampilan *kosong* yang dibutuhkan oleh beberapa standar pengiriman.

### Output yang Diharapkan

Anda akan menemukan `PostalPlanetEmptyBars.png` di folder target. Gambar tersebut menampilkan barcode Planet di mana setiap bar merupakan kontur, bukan persegi panjang padat.

![Contoh barcode Planet kosong](empty-planet.png){: .align-center alt="Buat barcode planet kosong – contoh barcode Planet dengan bar kosong"}

## Cara menghasilkan gambar barcode pos (versi terisi)

Sebagian besar alur kerja pos menggunakan versi bar terisi default. API yang sama dapat menghasilkan barcode Planet terisi dan barcode RM4SCC dengan hanya beberapa baris kode.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Mengapa Anda mungkin memerlukan RM4SCC:**  
RM4SCC adalah barcode USPS yang lebih baru yang mengenkode data yang sama dengan Planet tetapi dengan kepadatan lebih tinggi. Beberapa carrier memerlukan RM4SCC untuk diskon pengiriman massal. Kode di atas menunjukkan **how to generate postal barcode** untuk kedua standar tanpa mengubah alur kerja secara keseluruhan.

### Output yang Diharapkan

* `PostalPlanetFilledBars.png` – barcode Planet klasik dengan bar terisi.  
* `PostalRM4SCCFilledBars.png` – barcode RM4SCC dengan bar terisi, secara visual mirip tetapi dengan jarak yang lebih rapat.

Kedua file dapat dibuka di penampil gambar apa pun untuk memverifikasi pola bar.

## Menyesuaikan lebar bar untuk resolusi cetak yang berbeda

Pemindai pos sering menentukan lebar modul minimum (mis., 0.013 inci). Jika printer Anda bekerja pada 300 dpi, modul 4‑pixel bersesuaian dengan 0.013 inci. Sesuaikan nilai `XDimension.Pixels` agar cocok dengan perangkat keras Anda:

| Modul yang diinginkan (inci) | DPI | Pixel yang dibutuhkan (`XDimension`) |
|------------------------------|-----|--------------------------------------|
| 0.013                        | 300 | 4                                    |
| 0.013                        | 600 | 8                                    |
| 0.015                        | 300 | 5                                    |

**Tips pro:** Selalu uji a

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat barcode planet PNG dengan C# – panduan langkah demi langkah](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Hasilkan Barcode Pos dalam C# – Panduan Lengkap dengan Barcode Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Cara menghasilkan barcode pos dalam C# dengan Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}