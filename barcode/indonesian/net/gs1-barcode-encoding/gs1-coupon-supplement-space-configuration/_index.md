---
date: 2026-09-28
description: Pelajari cara membuat ruang khusus barcode untuk kupon GS1 dengan Aspose.BarCode
  untuk .NET dan meningkatkan keterbacaan barcode. Ikuti panduan langkah demi langkah
  kami.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Konfigurasi Ruang Suplemen Kupon GS1
og_description: Pelajari cara membuat ruang khusus barcode untuk kupon GS1 dengan
  Aspose.BarCode untuk .NET dan meningkatkan keterbacaan barcode. Kode langkah demi
  langkah serta tips disertakan.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Buat ruang khusus barcode untuk suplemen kupon GS1 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Cara membuat ruang khusus barcode untuk suplemen kupon GS1
url: /id/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi ruang suplemen kupon GS1

Dalam tutorial ini Anda akan **membuat ruang khusus barcode** untuk Ruang Suplemen Kupon GS1 menggunakan Aspose.BarCode untuk .NET. Menyesuaikan ruang suplemen sangat penting ketika Anda perlu **meningkatkan keterbacaan barcode** pada pemindai beresolusi rendah atau mematuhi margin yang ditetapkan retailer. Pada akhir panduan ini Anda akan memahami mengapa ruang suplemen penting, cara mengaturnya secara programatik, dan cara menghasilkan gambar dengan nilai piksel yang berbeda.

## Jawaban cepat
- **Apa yang dikontrol oleh ruang suplemen?** Ini mendefinisikan area kosong (dalam piksel) antara data kupon dan sisa barcode.  
- **Jenis barcode apa yang digunakan?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Bisakah saya mengubah ukuran ruang?** Ya – atur `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` ke nilai integer apa pun.  
- **Apakah saya memerlukan lisensi untuk fitur ini?** Lisensi sementara berfungsi untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Format output apa yang didukung?** PNG, JPEG, BMP, GIF, TIFF, dan lainnya melalui `BarCodeImageFormat`.

## Apa itu ruang suplemen kupon GS1?
Ruang Suplemen Kupon GS1 adalah wilayah kosong yang didefinisikan yang muncul dalam barcode kupon GS1‑Databar. Sistem ritel menggunakan ruang ini untuk meningkatkan keandalan pemindaian dan mematuhi spesifikasi industri yang mengharuskan margin minimum di sekitar data suplemen.

## Mengapa mengonfigurasi ruang suplemen?
Ruang suplemen secara langsung **meningkatkan keterbacaan barcode** dan membantu Anda memenuhi pedoman ketat retailer. Dengan menambahkan piksel ekstra Anda mengurangi kemungkinan kesalahan baca pada pemindai beresolusi rendah, memastikan pemindaian konsisten pada berbagai ukuran label, serta memberi fleksibilitas visual untuk menyeimbangkan barcode dalam tata letak cetak.

## Prasyarat

Sebelum kita masuk ke konfigurasi Ruang Suplemen Kupon GS1 dengan Aspose.BarCode untuk .NET, pastikan Anda memiliki hal‑hal berikut:

1. **Visual Studio** – IDE utama untuk pengembangan .NET.  
2. **Aspose.BarCode untuk .NET** – Unduh pustaka dari [dokumentasi Aspose.BarCode untuk .NET](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework atau .NET 5+** – Diperlukan pemahaman tentang C# dan runtime .NET.

Setelah lingkungan siap, mari lanjut ke implementasinya.

## Impor namespace

Namespace `Aspose.BarCode.Generation` berisi kelas `BarcodeGenerator` dan pengaturan terkait.

```csharp
using Aspose.BarCode;
```

## Langkah 1: tentukan jalur

Pilih folder tempat gambar yang dihasilkan akan disimpan. Jalur harus diakhiri dengan pemisah direktori yang sesuai untuk sistem operasi Anda.

```csharp
string path = "Your Directory Path";
```

## Langkah 2: hasilkan konfigurasi ruang suplemen kupon GS1

Potongan kode berikut membuat barcode, mengatur dimensi X, dan menyesuaikan ruang suplemen.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

Dalam contoh ini kami:

1. **Membuat** instance `BarcodeGenerator` untuk tipe `UpcaGs1DatabarCoupon`.  
2. **Mengatur** dimensi X menjadi 2 piksel, yang menentukan lebar bar paling sempit.  
3. **Menyesuaikan** properti `SupplementSpace.Pixels` menjadi 30 px, menghasilkan gambar, lalu mengulangi dengan 50 px.  

Silakan bereksperimen dengan nilai piksel lain untuk menyesuaikan alur kerja pencetakan Anda.

## Masalah umum & tips

- **Jalur tidak valid** – Pastikan variabel `path` diakhiri dengan backslash (`\`) atau slash (`/`) yang sesuai untuk OS Anda.  
- **Izin tidak cukup** – Jalankan Visual Studio sebagai Administrator atau pilih folder di mana aplikasi memiliki akses menulis.  
- **Format data tidak tepat** – String data harus mengikuti sintaks GS1 (`(8110)` menandakan pengidentifikasi suplemen).  

## Mengapa ini penting bagi bisnis Anda

Aspose.BarCode mendukung **lebih dari 60 simbol barcode** dan dapat merender gambar hingga **10.000 × 10.000 piksel** tanpa menghabiskan memori. Untuk penerapan ritel skala besar, ini berarti Anda dapat menghasilkan kupon GS1 beresolusi tinggi secara batch sambil menjaga waktu pemrosesan di bawah satu detik per gambar pada perangkat server standar.

## Pertanyaan yang sering diajukan

**T: Apa tujuan Ruang Suplemen Kupon GS1 dalam barcode?**  
J: Ia menambahkan margin kosong wajib di sekitar data suplemen, meningkatkan keandalan pemindai dan memenuhi lebar minimum yang ditetapkan retailer.

**T: Bisakah saya menyesuaikan lebar Ruang Suplemen Kupon GS1 dengan Aspose.BarCode untuk .NET?**  
J: Ya, atur `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` ke nilai integer apa pun; pustaka akan langsung menerapkan perubahan pada gambar yang dihasilkan.

**T: Di mana saya dapat menemukan dokumentasi tambahan dan dukungan untuk Aspose.BarCode untuk .NET?**  
J: Lihat [dokumentasi Aspose.BarCode untuk .NET](https://reference.aspose.com/barcode/net/) dan kunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk bantuan komunitas.

**T: Apakah Aspose.BarCode untuk .NET cocok untuk pemula maupun pengembang berpengalaman?**  
J: Tentu saja. API menawarkan metode sederhana untuk tugas cepat dan opsi lanjutan untuk generasi barcode yang terperinci.

**T: Bisakah saya memperoleh lisensi sementara untuk Aspose.BarCode untuk .NET guna mengevaluasi fiturnya?**  
J: Ya, minta lisensi percobaan melalui [situs lisensi sementara Aspose](https://purchase.aspose.com/temporary-license/).

## Kesimpulan

Dengan mengikuti langkah‑langkah di atas, Anda kini tahu cara **membuat ruang khusus barcode** untuk Ruang Suplemen Kupon GS1, teknik kunci untuk **meningkatkan keterbacaan barcode** dan memenuhi standar ritel. Integrasikan kode ini ke dalam solusi pemindaian Anda yang ada, coba nilai piksel yang berbeda, dan jelajahi tipe barcode lain yang ditawarkan oleh Aspose.BarCode untuk .NET.

---

**Terakhir Diperbarui:** 2026-09-28  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Hasilkan barcode Databar Aspose.BarCode menggunakan API .NET – Konfigurasi Baris & Kolom](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Cara Menghasilkan Barcode DataMatrix Menggunakan Aspose.BarCode untuk .NET – Panduan Langkah‑per‑Langkah](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}