---
category: general
date: 2026-10-18
description: Hasilkan gambar barcode untuk simbol Planet menggunakan Java. Pelajari
  cara membuat barcode planet dengan dimensi barcode khusus dan bar kosong.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: id
lastmod: 2026-10-18
og_description: Buat gambar barcode untuk simbol Planet di Java. Tutorial ini menunjukkan
  cara membuat barcode planet dengan dimensi barcode khusus dan garis tepi.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Buat gambar barcode untuk simbol planet – Panduan Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Buat gambar kode batang untuk simbol planet di Java
url: /id/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan gambar barcode untuk simbol Planet dalam Java

Jika Anda perlu **menghasilkan gambar barcode** untuk simbol Planet, panduan ini akan memandu Anda melalui proses lengkap. Baik Anda sedang membangun sistem otomatisasi pos atau solusi pelacakan khusus, Anda akan belajar cara **membuat barcode planet** dengan **dimensi barcode khusus** dan bar outline (kosong).

Contoh ini menggunakan pustaka Aspose.BarCode untuk Java, yang menyediakan API yang mudah digunakan untuk setiap standar barcode utama. Tidak diperlukan alat pemrosesan gambar tambahan, dan kode dapat dijalankan pada runtime Java 8+ apa pun.

## Prasyarat

* Java 8 atau yang lebih baru terpasang (tutorial ini diuji dengan JDK 17).
* Maven atau Gradle untuk mengelola dependensi.
* Familiaritas dasar dengan sintaks Java dan konsep barcode.

Jika Anda baru mengenal Maven, Anda dapat membuat proyek sederhana dengan `mvn archetype:generate` dan menambahkan dependensi Aspose.BarCode seperti yang ditunjukkan di bawah.

## Tambahkan dependensi Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Tips pro:** Kunci nomor versi untuk menghindari perubahan yang merusak secara tak terduga ketika pustaka diperbarui.

## Langkah 1: Inisialisasi generator barcode untuk simbol Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Mengapa langkah ini penting:**  
`EncodeTypes.PLANET` memberi tahu pustaka untuk menggunakan spesifikasi barcode Planet, yang umum digunakan untuk layanan pos. String data `"123456"` adalah payload yang akan muncul dalam gambar yang dihasilkan.

## Langkah 2: Atur dimensi barcode khusus (dimensi X)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Mengapa langkah ini penting:**  
*Dimensi X* menentukan seberapa lebar setiap bar individu. Dengan mengaturnya menjadi **4 piksel**, Anda memperoleh barcode yang mudah dibaca oleh kebanyakan pemindai sekaligus tetap muat pada label standar. Mengubah nilai ini adalah cara utama untuk mencapai **dimensi barcode khusus**.

## Langkah 3: Gunakan bar kosong (outline) alih-alih bar padat

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Mengapa langkah ini penting:**  
`setFilledBars(false)` memberi tahu renderer untuk menggambar hanya outline bar, meninggalkan bagian dalam transparan. Gaya ini sering diperlukan untuk barcode pos dimana latar belakang mungkin berisi informasi cetak lainnya.

## Langkah 4: Simpan gambar barcode sebagai PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Mengapa langkah ini penting:**  
Memilih `BarCodeImageFormat.Png` memberikan Anda gambar lossless yang mempertahankan tepi tajam dari bar outline. Path file dapat berupa direktori apa pun yang Anda miliki akses menulis; contoh ini menggunakan folder `output` relatif terhadap root proyek.

### Output yang diharapkan

Menjalankan program akan membuat file serupa dengan gambar di bawah:

![Gambar barcode yang dihasilkan untuk simbol Planet](/images/planet-barcode.png){.align-center alt="Gambar barcode yang dihasilkan menampilkan barcode Planet dengan bar outline kosong"}

Gambar tersebut menampilkan **barcode Planet** dengan bar tipis dan kosong, persis sesuai dengan dimensi khusus yang Anda atur.

## Variasi umum dan kasus tepi

| Situasi | Penyesuaian |
|-----------|------------|
| **Panjang data yang berbeda** | Barcode Planet mendukung hingga 12 karakter numerik. Ubah argumen konstruktor kedua sesuai. |
| **Resolusi lebih tinggi** | Tingkatkan dimensi X (`setPixels`) atau atur `YDimension` untuk mengontrol tinggi bar. |
| **Barcode berwarna** | Gunakan `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` untuk mengubah warna bar. |
| **Menyimpan sebagai SVG** | Ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg` untuk output vektor. |
| **Menjalankan di Android** | Gunakan Aspose.BarCode untuk Android yang kompatibel dan ganti path sistem file dengan `Context.getFilesDir()`. |

> **Waspadai:** Menetapkan dimensi X terlalu rendah (mis., 1 piksel) dapat membuat barcode tidak dapat dibaca pada printer beresolusi rendah. Selalu uji dengan pemindai nyata setelah mengubah dimensi.

## Kode sumber lengkap untuk salin‑tempel cepat

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Salin kode ke dalam file bernama `PlanetBarcodeDemo.java`, letakkan di `src/main/java/com/example/barcode/`, jalankan `mvn compile exec:java`, dan Anda akan melihat hasil **menghasilkan gambar barcode** di folder `output`.

## Kesimpulan

Anda sekarang tahu cara **menghasilkan gambar barcode** untuk simbol Planet dalam Java, cara **membuat barcode planet** dengan **dimensi barcode khusus**, dan cara beralih dari bar padat ke bar kosong untuk gaya visual yang lebih bersih. Contoh lengkap ini menunjukkan setiap panggilan API yang diperlukan, mulai dari inisialisasi generator hingga menyimpan file PNG.

**Langkah selanjutnya** – jelajahi tipe barcode lain (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) dan bereksperimen dengan opsi gambar tambahan seperti warna latar belakang, margin, dan pengaturan DPI. Jika Anda perlu menyematkan barcode dalam PDF, gabungkan kode ini dengan Aspose.PDF untuk Java untuk solusi menyeluruh end‑to‑end.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang sangat terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara membuat barcode planet dengan bar terisi dan kosong](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Buat gambar barcode planet – Panduan Langkah‑per‑Langkah](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Cara menghasilkan barcode java: Membuat Gambar Barcode yang Tepat](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}