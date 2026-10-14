---
category: general
date: 2026-10-08
description: Pelajari cara membuat gambar kode batang di C# dan temukan cara menyesuaikan
  rasio aspek untuk kode batang DataBar stacked omni‑directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: id
lastmod: 2026-10-08
og_description: Buat gambar barcode dalam C# dan pelajari cara menyesuaikan rasio
  aspek untuk barcode DataBar stacked omni‑directional dengan contoh kode lengkap.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Buat gambar barcode di C# – panduan langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cara membuat gambar barcode dan mengatur rasio aspeknya di C#
url: /id/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode dan menyesuaikan rasio aspeknya di C#

Jika Anda perlu **membuat gambar barcode** secara programatik, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Anda akan melihat secara tepat **cara menyesuaikan rasio aspek** untuk barcode DataBar stacked omni‑directional, sebuah kebutuhan yang sering muncul dalam aplikasi ritel dan logistik.

Dalam tutorial ini Anda akan belajar cara:
* Menginisialisasi `BarcodeGenerator` Aspose.BarCode untuk simbol DataBar stacked omni‑directional.  
* Menetapkan dimensi X (lebar modul) dalam piksel untuk mengontrol ketebalan bar.  
* Menerapkan dua rasio aspek yang berbeda dan menyimpan masing‑masing hasilnya sebagai file PNG.  
* Memverifikasi output dan memahami mengapa rasio aspek penting.

Tidak diperlukan alat eksternal—hanya pustaka Aspose.BarCode untuk .NET dan lingkungan pengembangan .NET 6 (atau lebih baru).

## Cara membuat gambar barcode dengan Aspose.BarCode

Langkah pertama adalah menginstansiasi generator dengan simbol dan string data yang diinginkan. Enum `EncodeTypes.DatabarStackedOmniDirectional` memberi tahu Aspose.BarCode untuk menghasilkan barcode DataBar stacked omni‑directional, yang banyak digunakan untuk aplikasi GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Mengapa ini penting:** Objek `BarcodeGenerator` adalah titik masuk untuk semua tugas pembuatan barcode. Dengan menentukan simbol dan data mentah di awal, Anda menjamin bahwa gambar yang dihasilkan mematuhi standar GS1.

## Menetapkan dimensi X (lebar modul)

Dimensi X mendefinisikan lebar bar paling sempit (modul). Dimensi X yang lebih besar menghasilkan barcode yang lebih tebal, yang dapat membantu pada printer beresolusi rendah.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mengapa ini penting:** Menyesuaikan dimensi X merupakan bagian dari proses penyetelan visual. Ini tidak memengaruhi data yang dikodekan, tetapi memengaruhi keandalan pemindaian pada berbagai perangkat.

## Cara menyesuaikan rasio aspek – versi pertama (15)

Rasio aspek mengontrol hubungan tinggi‑dengan‑lebar barcode DataBar. Properti `DataBar.AspectRatio` menerima nilai integer; angka yang lebih besar menghasilkan bar yang lebih tinggi.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Mengapa ini penting:** Rasio aspek 15 adalah nilai default umum untuk pemindai ritel. PNG yang dihasilkan (`DatabarAspectRatio15.png`) akan memiliki tampilan yang lebih tinggi, yang dapat meningkatkan keberhasilan pemindaian pada perangkat genggam.

## Cara menyesuaikan rasio aspek – versi kedua (30)

Anda mungkin memerlukan barcode yang lebih tinggi untuk format label tertentu. Mengubah rasio aspek semudah menetapkan nilai integer baru sebelum memanggil `Save` lagi.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Mengapa ini penting:** Dengan mendemonstrasikan **cara menyesuaikan rasio aspek**, Anda dapat menghasilkan beberapa gambar barcode dari sumber data yang sama tanpa harus membuat ulang generator. Ini mengurangi penggunaan memori dan mempercepat pemrosesan batch.

### Output yang diharapkan

Setelah menjalankan program, Anda akan menemukan dua file PNG di direktori eksekusi:

| Nama file                     | Rasio aspek | Deskripsi visual |
|-------------------------------|-------------|-------------------|
| `DatabarAspectRatio15.png`    | 15          | Tinggi standar, cocok untuk kebanyakan pemindai titik penjualan. |
| `DatabarAspectRatio30.png`    | 30          | Bar lebih tinggi, berguna untuk label besar atau printer beresolusi rendah. |

Kedua gambar berisi GTIN yang sama `(01)12345678901231`, tetapi proporsi visualnya berbeda sesuai rasio aspek yang Anda tetapkan.

## Pertanyaan umum dan penanganan kasus tepi

### Bagaimana jika saya memerlukan dimensi X yang berbeda?

Anda dapat mengubah `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` ke nilai integer berapa pun yang lebih besar dari nol. Untuk output beresolusi sangat tinggi (misalnya 300 dpi), nilai 3‑4 piksel sering menghasilkan hasil yang lebih jelas.

### Bagaimana cara memilih rasio aspek yang tepat?

Rasio optimal tergantung pada lingkungan pemindaian:
* **Label profil rendah** – gunakan rasio yang lebih kecil (misalnya 10‑15) agar barcode tetap kompak.
* **Kontainer pengiriman besar** – rasio yang lebih tinggi (misalnya 25‑35) meningkatkan keterbacaan dari jarak jauh.
* **Persyaratan regulasi** – beberapa standar mewajibkan tinggi minimum; lihat spesifikasi GS1 untuk angka pasti.

### Bisakah saya menghasilkan format barcode lain dengan kode yang sama?

Ya. Ganti `EncodeTypes.DatabarStackedOmniDirectional` dengan nilai `EncodeTypes` lain (misalnya `EncodeTypes.Code128`). Sisanya—dimensi X, rasio aspek (jika berlaku), dan penyimpanan—tetap sama.

### Bagaimana jika saya ingin membuat gambar dalam format lain?

`BarCodeImageFormat` mendukung PNG, JPEG, BMP, GIF, dan TIFF. Cukup ubah argumen kedua pada `Save`, misalnya:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Tips pro: gunakan kembali generator untuk pemrosesan batch

Ketika Anda harus membuat puluhan barcode dengan pengaturan visual yang sama, instansiasi generator sekali saja, perbarui properti `CodeText` saja, dan panggil `Save` berulang kali. Ini menghindari beban alokasi buffer internal yang berulang-ulang.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Kesimpulan

Anda kini tahu cara **membuat gambar barcode** di C# menggunakan Aspose.BarCode dan secara tepat **menyesuaikan rasio aspek** untuk simbol DataBar stacked omni‑directional. Dengan mengontrol dimensi X dan rasio aspek, Anda dapat menghasilkan barcode yang memenuhi segala kebutuhan pemindaian atau tata letak sambil menjaga implementasi tetap sederhana dan mudah dipelihara.

### Langkah selanjutnya

* Jelajahi simbol lain seperti **Code128** atau **QR Code** dengan mengganti nilai `EncodeTypes`.  
* Gabungkan pembuatan barcode dengan pembuatan PDF (misalnya menggunakan Aspose.PDF) untuk menyematkan barcode langsung ke faktur.  
* Bereksperimenlah dengan pemilihan rasio aspek dinamis berdasarkan ukuran label—ini memperluas pola **cara menyesuaikan rasio aspek** menjadi mesin desain label yang lengkap.

Silakan sesuaikan contoh, bagikan hasil Anda, atau ajukan pertanyaan lanjutan di kolom komentar. Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}