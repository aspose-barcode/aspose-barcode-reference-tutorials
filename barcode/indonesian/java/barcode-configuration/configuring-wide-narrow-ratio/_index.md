---
date: 2026-08-12
description: Pelajari cara meningkatkan keterbacaan kode batang dengan menyesuaikan
  rasio lebar‑tipis CODE_128 di Java menggunakan Aspose.BarCode, dan menghasilkan
  gambar PNG secara efisien. Ikuti tutorial pembuatan kode batang langkah‑demi‑langkah
  kami dalam Java.
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Mengonfigurasi rasio lebar‑tipis
og_description: Pelajari cara meningkatkan keterbacaan kode batang dengan menyesuaikan
  rasio lebar‑tipis CODE_128 di Java dengan Aspose.BarCode. Tutorial langkah‑demi‑langkah
  ini menunjukkan cara menghasilkan kode batang PNG dengan cepat.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Tingkatkan keterbacaan kode batang dengan rasio lebar‑tipis CODE_128 (58
  karakter)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Tingkatkan keterbacaan kode batang dengan rasio lebar‑tipis CODE_128
url: /id/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Meningkatkan keterbacaan kode batang dengan rasio lebar‑sempit CODE_128

## Pendahuluan

Jika Anda perlu **meningkatkan keterbacaan kode batang** untuk label inventaris, tag pengiriman, atau aplikasi apa pun yang menggunakan CODE_128, menyesuaikan rasio lebar‑sempit adalah teknik paling efektif. Dalam tutorial ini kami akan memandu proses **pembuatan kode batang langkah‑demi‑langkah** menggunakan Aspose.BarCode untuk Java, menunjukkan cara mengonfigurasi rasio, **menghasilkan gambar PNG kode batang**, dan **menyimpan gambar kode batang** ke disk. Anda juga akan melihat mengapa rasio penting untuk kinerja pemindai dan cara menyesuaikannya untuk lingkungan pencetakan spesifik Anda.

## Jawaban Cepat
- **Apa itu rasio lebar‑sempit?** Ini mengontrol lebar relatif antara bar lebar dan bar sempit dalam kode batang.  
- **Simbol apa yang mendukung penyesuaian rasio?** Sebagian besar simbol 1‑D, termasuk CODE_128, memungkinkan Anda mengatur rasio khusus.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia, tetapi lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan gambar kode batang dalam format PNG?** Ya—gunakan `generator.save(...)` untuk menghasilkan gambar PNG kode batang.  
- **Apakah kode ini kompatibel dengan Java 8+?** Tentu saja; Aspose.BarCode bekerja dengan semua versi Java modern.

## Prasyarat

Sebelum kita menyelam ke kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.BarCode untuk Java. Unduh dari [download link](https://releases.aspose.com/barcode/java/).

## Impor paket

Untuk memulai, impor kelas Aspose.BarCode yang penting ke dalam proyek Anda.  
`BarcodeGenerator` adalah kelas inti yang digunakan untuk menghasilkan gambar kode batang dengan simbol dan opsi yang ditentukan.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Apa itu rasio lebar‑sempit dan mengapa menyesuaikannya?

Rasio lebar‑sempit menentukan berapa kali lebar bar “lebar” dibandingkan dengan bar “sempit”. Menyesuaikan rasio ini meningkatkan kompatibilitas pemindai (kebanyakan pemindai membaca paling baik dengan rasio antara 2,0 dan 3,0), mengkompensasi keterbatasan DPI printer, dan memungkinkan Anda menyesuaikan gaya visual merek tanpa mengorbankan keandalan.

## Cara meningkatkan keterbacaan kode batang dengan membuat kode batang CODE_128 dengan rasio lebar‑sempit di Java

Mulailah dengan menambahkan perpustakaan Aspose.BarCode ke proyek Java Anda, kemudian buat instance `BarcodeGenerator` dengan menentukan `EncodeTypes.CODE_128`. Konfigurasikan generator dengan rasio lebar‑sempit yang diinginkan menggunakan `setWideNarrowRatio`, secara opsional sesuaikan pengaturan visual lainnya, dan akhirnya panggil `save` untuk menulis kode batang sebagai file PNG. Alur kerja singkat ini memastikan kualitas kode batang yang konsisten dan meningkatkan tingkat pembacaan pemindai pada berbagai perangkat.

### Langkah 1: atur direktori dokumen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Pastikan direktori ada dan Anda memiliki izin menulis; ini adalah tempat file **gambar kode batang yang disimpan** akan ditempatkan.

### Langkah 2: buat objek kode batang

Kelas `BarcodeGenerator` membuat gambar kode batang berdasarkan simbol dan opsi enkoding yang ditentukan.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Di sini kami **membuat kode batang CODE_128** dengan memberikan `EncodeTypes.CODE_128` ke konstruktor.

### Langkah 3: atur rasio lebar‑sempit

`setWideNarrowRatio` mengatur proporsi antara bar lebar dan bar sempit untuk kode batang yang dihasilkan.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metode `setWideNarrowRatio` memungkinkan Anda menyesuaikan jarak visual secara halus. Nilai `3.0f` berarti bar lebar tiga kali lebar bar sempit, yang berada dalam rentang optimal 2,0‑3,0 untuk kebanyakan pemindai.

### Langkah 4: simpan gambar ke disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Memanggil `save` akan **menghasilkan gambar kode batang** dan menyimpannya sebagai file PNG, menyelesaikan langkah **menyimpan gambar kode batang**.

## Mengapa menyesuaikan rasio lebar‑sempit?

Menyesuaikan rasio lebar‑sempit meningkatkan kompatibilitas pemindai karena kebanyakan pemindai industri membaca paling baik ketika rasio berada antara 2,0 dan 3,0. Ini juga meningkatkan kualitas cetak dengan mengkompensasi resolusi printer 150–300 dpi, mengurangi distorsi bar. Selain itu, rasio memungkinkan perusahaan menyelaraskan estetika kode batang dengan pedoman merek sambil mempertahankan kinerja pemindaian yang dapat diandalkan.

## Masalah umum dan solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Kode batang tampak terdistorsi | Rasio terlalu tinggi/rendah untuk printer | Sesuaikan nilai yang diberikan ke `setWideNarrowRatio` (mis., 2,0‑2,5). |
| File tidak dibuat | Path `dataDir` tidak valid atau izin tidak cukup | Verifikasi path direktori dan pastikan aplikasi memiliki akses menulis. |
| Pemindai tidak dapat membaca kode batang | Rasio di luar rentang yang direkomendasikan untuk simbol | Gunakan rasio standar (2,0‑3,0) atau uji dengan pemindai target. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.BarCode dengan kerangka kerja Java lainnya?**  
A: Ya, Aspose.BarCode bekerja mulus dengan Spring, Java EE, Android, dan lingkungan Java lainnya.

**Q: Bagaimana saya dapat menghasilkan kode batang dengan simbol yang berbeda?**  
A: Ubah tipe simbol dalam konstruktor `BarcodeGenerator`, misalnya `EncodeTypes.QR` untuk kode QR.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.BarCode?**  
A: Ya, Anda dapat mengakses versi percobaan gratis di [halaman percobaan gratis Aspose.BarCode](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.BarCode?**  
A: Lihat dokumentasi di [dokumentasi API Java Aspose.BarCode](https://reference.aspose.com/barcode/java/).

**Q: Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode?**  
A: Kunjungi forum komunitas Aspose.BarCode di [forum komunitas Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi komunitas.

---

**Terakhir Diperbarui:** 2026-08-12  
**Diuji Dengan:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Membuat Kode Batang Java – Atur Resolusi Gambar dengan Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Deteksi Orientasi Kode Batang di Java dengan Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Cara membuat gambar kode batang code128 di Java dengan Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}