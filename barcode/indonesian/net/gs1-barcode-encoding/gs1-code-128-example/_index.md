---
date: 2026-09-08
description: Pelajari cara membuat barcode code 128 dan menghasilkan barcode GS1 dalam
  C# dengan Aspose.BarCode untuk .NET. Panduan langkah demi langkah, prasyarat, dan
  kustomisasi tanpa kode.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Contoh GS1 Code 128
og_description: Pelajari cara membuat barcode code 128 dan menghasilkan barcode GS1
  dalam C# dengan Aspose.BarCode untuk .NET. Ikuti panduan langkah demi langkah untuk
  menghasilkan dan menyimpan gambar barcode dengan cepat.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Cara membuat barcode code 128 dengan GS1 menggunakan Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Cara membuat barcode code 128 dengan GS1 menggunakan Aspose.BarCode
url: /id/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat kode batang code 128 dengan GS1 menggunakan Aspose.BarCode

Dalam tutorial ini Anda akan belajar cara **membuat kode batang code 128** yang mematuhi standar GS1 menggunakan pustaka Aspose.BarCode untuk .NET. Baik Anda memerlukan kode batang untuk inventaris, pengiriman, atau point‑of‑sale, panduan ini akan memandu Anda melalui setiap langkah—dari menyiapkan lingkungan pengembangan hingga menyimpan gambar akhir—sehingga Anda dapat mulai menghasilkan kode batang yang handal dalam hitungan menit.

## Jawaban Cepat
- **Apa kelas utama untuk menghasilkan kode batang?** `BarcodeGenerator` membuat dan mengonfigurasi gambar kode batang.  
- **Simbol apa yang digunakan GS1 Code 128?** Ia menggunakan tipe `EncodeTypes.Code128` dengan format data khusus GS1.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah format gambar?** Ya—simpan sebagai PNG, JPEG, BMP, atau TIFF dengan mengubah ekstensi file.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, dan .NET 6+.

## Apa itu kode batang code 128?
`create code 128 barcode` mengacu pada pembuatan kode batang linear yang mengkodekan data alfanumerik menggunakan simbol Code 128, yang banyak diadopsi untuk logistik karena mendukung seluruh set ASCII dan dapat menyematkan GS1 Application Identifiers. Kode batang ini dapat menyimpan identifier produk, nomor seri, dan data khusus lainnya, menjadikannya cocok untuk berbagai skenario bisnis.

## Mengapa menggunakan Aspose.BarCode untuk GS1 Code 128?
Aspose.BarCode mendukung **lebih dari 30 simbol kode batang** dan dapat merender gambar hingga **10.000 × 10.000 px** tanpa kehilangan kualitas, menjadikannya cocok untuk pencetakan label beresolusi tinggi. Pustaka ini juga secara otomatis memvalidasi struktur data GS1, mengurangi risiko kode batang yang tidak tepat pada jalur produksi. Selain itu, ia menawarkan opsi kustomisasi yang luas untuk ukuran, warna, dan tata letak, yang membantu memenuhi standar industri yang ketat.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

1. **Lingkungan pengembangan .NET** – Visual Studio 2022, Rider, atau IDE apa pun yang mendukung .NET 6+.  
2. **Aspose.BarCode untuk .NET** – unduh dari **halaman unduhan Aspose.BarCode untuk .NET** di [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) dan tambahkan paket NuGet `Aspose.BarCode` ke proyek Anda.  
3. **Pengetahuan dasar C#** – Anda harus nyaman membuat aplikasi console atau Windows.  
4. **Pemahaman tentang GS1 Code 128** – opsional tetapi berguna; GS1 menggunakan Application Identifiers (AIs) seperti `(01)` untuk GTIN dan `(21)` untuk nomor seri.

## Cara membuat kode batang code 128 langkah demi langkah

Muat pustaka, konfigurasikan tipe kode batang, atur data GS1, sesuaikan dimensi, dan akhirnya simpan gambar. Jawaban langsung untuk pertanyaan “bagaimana cara membuat kode batang code 128?” adalah: **instansiasi `BarcodeGenerator` dengan `EncodeTypes.Code128` dan data berformat GS1, sesuaikan `XDimension` jika diperlukan, lalu panggil `Save` dengan nama file dan format yang diinginkan**. Bagian berikut memecah setiap langkah.

### Langkah 1: atur jalur direktori Anda
Tentukan folder tempat gambar yang dihasilkan akan disimpan. Menjaga jalur dapat dikonfigurasi membuat kode dapat digunakan kembali di berbagai lingkungan.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Ganti `"Your Directory Path"` dengan jalur absolut atau relatif yang dapat ditulis oleh aplikasi Anda, seperti `@"C:\Barcodes"` atau `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Langkah 2: buat kode batang GS1 Code 128
Buat generator kode batang, tentukan simbolnya, dan berikan data berformat GS1. String data harus menyertakan Application Identifiers yang dibungkus dalam tanda kurung.

```csharp
string path = "Your Directory Path";
```

Contoh ini menggunakan GTIN `(01)12345678901231`, nomor seri `(21)ASPOSE`, dan AI khusus tambahan `(30)9876`. Aspose.BarCode secara otomatis menyisipkan karakter FNC1 yang diperlukan untuk kepatuhan GS1.

### Langkah 3: sesuaikan parameter kode batang
Sesuaikan parameter visual seperti `XDimension` (lebar bar tipis) untuk mengontrol kepadatan kode batang. Anda juga dapat mengubah tinggi, warna, dan margin.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Menetapkan `XDimension = 2` menghasilkan kode batang yang mudah dipindai oleh kebanyakan pembaca genggam sambil menjaga ukuran gambar tetap wajar.

### Langkah 4: simpan gambar kode batang
Simpan kode batang yang dihasilkan ke disk. Anda dapat memilih PNG untuk kualitas lossless, JPEG untuk file yang lebih kecil, atau TIFF untuk alur kerja pencetakan. Metode `Save` menulis file gambar dalam format yang ditunjukkan oleh ekstensi file.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Ganti `GS1Code128Example.png` dengan nama file dan ekstensi yang valid sesuai format output yang Anda inginkan.

### Langkah 5: verifikasi kode batang (opsional)
Setelah menyimpan, Anda dapat memuat kembali gambar ke dalam aplikasi atau menggunakan pemindai kode batang untuk memastikan data yang dikodekan cocok dengan string asli. Langkah ini berguna selama pengembangan dan pengujian otomatis.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Masalah umum dan tips pemecahan masalah
- **FNC1 tidak terdeteksi** – Pastikan string data dimulai dengan tanda kurung buka dan menyertakan AI GS1 yang valid; pustaka hanya menyisipkan FNC1 secara otomatis untuk pola yang dikenali.  
- **Gambar tidak tersimpan** – Verifikasi bahwa direktori target ada dan aplikasi memiliki izin menulis. Gunakan `Directory.CreateDirectory(path)` untuk membuatnya secara otomatis.  
- **Kode batang terlalu padat** – Kurangi `XDimension` atau tingkatkan tinggi gambar untuk memberi pemindai lebih banyak ruang membaca bar tipis.  
- **Karakter tidak didukung** – Code 128 hanya dapat mengkodekan seluruh set ASCII; hindari karakter Unicode di luar rentang ini.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menghasilkan kode batang dalam API web tanpa menginstal .NET Framework lengkap?**  
A: Ya, Aspose.BarCode bekerja dengan .NET Core dan .NET 5/6, sehingga Anda dapat mengekspos endpoint REST ringan yang mengembalikan gambar kode batang sesuai permintaan.

**Q: Apakah pustaka mendukung pembuatan batch banyak kode batang?**  
A: Tentu saja. Loop melalui koleksi string data, buat instance `BarcodeGenerator` untuk masing‑masing, dan panggil `Save` di dalam loop. Pustaka ini thread‑safe untuk pemrosesan paralel.

**Q: Apakah ada cara menyematkan kode batang langsung ke PDF?**  
A: Gunakan Aspose.PDF untuk membuat dokumen PDF, lalu panggil `PdfPage.AddImage` dengan aliran gambar kode batang. Ini menghindari penulisan file perantara ke disk.

**Q: Bagaimana saya dapat memastikan kode batang memenuhi standar kualitas ISO/GS1?**  
A: Atur `BarcodeGenerator.Options.Barcode.XDimension` setidaknya 0,33 mm dan aktifkan `BarHeight` sesuai ukuran label. Aspose.BarCode memvalidasi format AI dan melemparkan pengecualian untuk data yang tidak valid.

**Q: Opsi lisensi apa yang tersedia untuk penggunaan produksi?**  
A: Aspose menawarkan model lisensi perpetual, berlangganan, dan berbasis cloud. Lisensi percobaan dapat digunakan untuk evaluasi, tetapi lisensi berbayar menghapus watermark evaluasi dan membuka semua fitur.

## Sumber daya tambahan

- **Dokumentasi** – Akses referensi API lengkap di [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Unduh** – Dapatkan rilis pustaka terbaru dari [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Trial gratis** – Mulai trial 30‑hari di [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Pembelian** – Beli lisensi komersial di [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Dukungan** – Bergabunglah dengan forum komunitas di [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) untuk bantuan pemecahan masalah.

---

**Last Updated:** 2026-09-08  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Cara Membuat ITF-14 Barcode .NET – Tutorial Komprehensif Aspose.BarCode](/barcode/net/)
- [Hasilkan Barcode Databar 2D Satu Dimensi Menggunakan Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}