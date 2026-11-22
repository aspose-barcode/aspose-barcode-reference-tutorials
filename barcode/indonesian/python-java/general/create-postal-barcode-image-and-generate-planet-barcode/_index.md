---
category: general
date: 2026-11-20
description: Buat gambar barcode pos di C# dengan cepat. Pelajari cara menghasilkan
  barcode planet dan barcode RM4SCC dengan gaya bar yang dapat disesuaikan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: id
lastmod: 2026-11-20
og_description: Buat gambar kode pos barcode di C# dengan Aspose.BarCode. Tutorial
  ini menunjukkan cara menghasilkan barcode planet, menyesuaikan gaya bar, dan menghasilkan
  gambar RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Buat gambar kode batang pos di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Buat gambar kode batang pos dan hasilkan kode batang planet
url: /id/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat gambar barcode pos dan hasilkan barcode planet

Buat gambar barcode pos dalam C# menggunakan pustaka Aspose.BarCode. Jika Anda perlu menghasilkan barcode planet atau barcode RM4SCC untuk aplikasi pengiriman, tutorial ini menyediakan solusi lengkap yang siap dijalankan.

Menghasilkan barcode untuk layanan pos sering memerlukan dimensi yang tepat dan opsi untuk beralih antara gaya batang terisi dan kosong. Panduan ini akan menuntun Anda melalui penyiapan folder output, pembuatan barcode Planet dengan batang terisi dan kosong, serta menghasilkan barcode RM4SCC dengan pengaturan visual yang sama. Pada akhir tutorial Anda akan memiliki empat file PNG yang dapat langsung digunakan dalam alur kerja pengiriman Anda.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* .NET 6.0 atau lebih baru terinstal  
* Visual Studio 2022 (atau IDE C# lain yang Anda sukai)  
* Paket NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Tidak ada konfigurasi tambahan yang diperlukan; kode hanya menggunakan font default dan encoder PNG.

## Buat gambar barcode pos – ikhtisar

Inti proses adalah kelas `BarcodeGenerator`. Kelas ini menerima nilai `EncodeTypes` yang menentukan simbolologi barcode (misalnya, `EncodeTypes.Planet` untuk barcode Planet). Setelah mengonfigurasi generator, Anda memanggil `Save` untuk menulis file gambar.

![Contoh gambar barcode pos yang menunjukkan batang terisi dan kosong](/images/postal_barcode_example.png)

*Alt text: Contoh gambar barcode pos yang menunjukkan batang terisi dan kosong.*

## Langkah 1: Siapkan folder output

Pertama tentukan folder tempat file PNG akan disimpan. Menggunakan path absolut atau relatif bekerja dengan cara yang sama; pastikan folder tersebut ada atau biarkan kode membuatnya.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Membuat folder secara programatik mencegah `DirectoryNotFoundException` ketika tutorial dijalankan pada mesin baru.

## Langkah 2: Hasilkan barcode planet dengan batang terisi

Barcode Planet dengan batang terisi adalah gaya visual default. Kode berikut membuat barcode, mengatur dimensi X menjadi 4 piksel (ukuran umum untuk aplikasi pos), dan menyimpan gambar.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Mengapa ini berhasil:**  
* `EncodeTypes.Planet` memberi tahu generator untuk menggunakan simbol Planet, yang diperlukan untuk banyak layanan pos.  
* `XDimension.Pixels` mengontrol lebar setiap batang; 4 px menghasilkan gambar yang jelas dan dapat dipindai tanpa ukuran file berlebih.  
* Metode `Save` secara otomatis memilih encoder PNG berdasarkan enum `BarCodeImageFormat`.

## Langkah 3: Hasilkan barcode planet dengan batang kosong

Beberapa spesifikasi pos lebih menyukai batang kosong (putih) pada latar belakang gelap. Anda dapat mencapainya dengan mengatur `FilledBars` ke `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** Saat `FilledBars` bernilai `false`, generator melukis batang dengan warna latar belakang (putih secara default) dan ruangannya dengan warna latar depan (hitam). Jika Anda membutuhkan skema warna yang berbeda, sesuaikan `Parameters.Barcode.ForeColor` dan `BackColor`.

## Langkah 4: Hasilkan barcode RM4SCC dengan batang terisi

RM4SCC adalah simbolologi pos lain yang digunakan di Britania Raya. Langkah pembuatan meniru contoh Planet; hanya nilai `EncodeTypes` yang berubah.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Apa yang diharapkan:** PNG yang dihasilkan menampilkan barcode RM4SCC yang kompak dan sesuai dengan pedoman pos UK. Ukuran gambar akan mirip dengan barcode Planet karena dimensi X identik.

## Langkah 5: Verifikasi gambar yang dihasilkan

Setelah menjalankan program, buka empat file di folder `Barcodes`. Anda harus melihat:

* `PostalPlanetFilledBars.png` – batang gelap pada latar belakang terang  
* `PostalPlanetEmptyBars.png` – batang terang pada latar belakang gelap (inverse)  
* `PostalRM4SCCFilledBars.png` – pola RM4SCC standar  

Jika ada gambar yang tampak terdistorsi, periksa hal berikut:

* **X‑dimension** – terlalu kecil (< 2 px) dapat menyebabkan blur; terlalu besar (> 10 px) mungkin melebihi batas ukuran label.  
* **Data string** – nilai `"123456"` harus memenuhi persyaratan panjang simbolologi yang dipilih (Planet mengharuskan 6 digit, RM4SCC juga mengharuskan 6 digit).  
* **Folder permissions** – pastikan aplikasi memiliki akses menulis ke direktori output.

## Variasi umum dan kasus tepi

| Scenario | Adjustment |
|----------|------------|
| **Data barcode yang berbeda** | Ganti `"123456"` dengan string numerik yang valid apa pun. Untuk Planet, panjangnya harus tepat 6 digit; RM4SCC juga memerlukan 6 digit. |
| **Warna khusus** | Setel `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` dan `BackColor = System.Drawing.Color.LightYellow;`. |
| **Resolusi lebih tinggi** | Tingkatkan `XDimension.Pixels` menjadi 6 atau 8 untuk cetakan yang lebih besar. |
| **Format gambar lain** | Gunakan `BarCodeImageFormat.Jpeg` atau `BarCodeImageFormat.Bmp` dalam pemanggilan `Save`. |
| **Pembuatan batch** | Lakukan perulangan atas koleksi string dan panggil logika generator yang sama di dalam loop, menggunakan kembali path `outputFolder`. |

## Contoh lengkap yang dapat dijalankan

Salin kode di bawah ini ke dalam proyek konsol C# baru. Kode ini dapat dikompilasi dengan .NET 6.0 dan secara otomatis menghasilkan keempat gambar barcode.



## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat gambar barcode pos dengan tinggi khusus dalam C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Cara membuat barcode RM4SCC dan menghasilkan barcode planet dalam C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Buat gambar barcode pos dalam C# – panduan langkah demi langkah](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}