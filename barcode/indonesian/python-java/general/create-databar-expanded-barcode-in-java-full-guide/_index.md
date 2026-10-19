---
category: general
date: 2026-10-18
description: Buat barcode databar yang diperluas di Java dengan Aspose.BarCode. Pelajari
  cara menghasilkan databar, mengatur baris, dan mengekspor gambar barcode sebagai
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: id
lastmod: 2026-10-18
og_description: Buat barcode databar expanded di Java. Ikuti panduan ini untuk mempelajari
  cara menghasilkan databar, mengkonfigurasi baris, dan mengekspor gambar barcode
  sebagai PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: Buat kode batang Databar Expanded di Java – tutorial langkah demi langkah
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: Buat barcode Databar Expanded di Java – panduan lengkap
url: /id/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat barcode databar expanded di Java – panduan lengkap

Jika Anda perlu **membuat barcode databar expanded** di Java, tutorial ini menunjukkan secara tepat **cara menghasilkan gambar databar** menggunakan pustaka Aspose.BarCode. Anda juga akan belajar cara mengonfigurasi **baris generator barcode** dan **mengekspor file gambar barcode** dalam format PNG.

Pada bagian di bawah ini Anda akan menemukan program lengkap yang dapat dijalankan, penjelasan langkah‑demi‑langkah setiap panggilan API, serta tips untuk menangani kasus tepi umum seperti karakter yang tidak didukung atau ukuran tata letak khusus. Pada akhir panduan ini Anda akan dapat menghasilkan barcode Databar Expanded berukuran 4‑kolom dan 3‑baris serta menyimpannya di mana saja yang Anda perlukan.

## Prasyarat

* Java 17 atau lebih baru (kode dapat dikompilasi dengan JDK 11+ apa pun)
* Maven atau Gradle untuk mengelola dependensi
* Aspose.BarCode untuk Java – tambahkan versi terbaru ke `pom.xml` atau `build.gradle` Anda
* Familiaritas dasar dengan metode `main` Java dan konsep berorientasi objek

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **Pro tip:** Lisensi evaluasi gratis berfungsi untuk pengembangan; ganti dengan lisensi berbayar sebelum menerapkan ke produksi.

## Membuat barcode databar expanded – pengaturan awal

Langkah pertama adalah menginstansiasi `BarcodeGenerator` dengan tipe `EncodeTypes.DatabarExpandedStacked` dan payload contoh. Payload ini dapat berupa string alfanumerik apa pun yang sesuai dengan spesifikasi Databar.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*Mengapa ini penting*: `EncodeTypes.DatabarExpandedStacked` memberi tahu pustaka untuk menggunakan simbolologi Databar Expanded Stacked, yang mendukung string data lebih panjang dibandingkan Databar biasa.

## Cara menghasilkan databar dengan kolom khusus

Databar Expanded memungkinkan Anda mengontrol jumlah kolom dalam tata letak bertumpuk. Menetapkan kolom berguna ketika Anda memerlukan barcode yang kompak namun tetap memuat lebar data yang diperlukan.

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*Penjelasan*: `setColumns(4)` memaksa generator membagi barcode menjadi empat bagian vertikal. Pustaka secara otomatis menyesuaikan lebar modul agar ukuran keseluruhan tetap wajar.

## Mengekspor gambar barcode sebagai PNG – versi 4‑kolom

Setelah tata letak ditentukan, Anda dapat mengekspor barcode ke sebuah file. PNG adalah format loss‑less yang direkomendasikan untuk kebanyakan skenario UI.

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

Metode `save` menulis gambar ke direktori yang ditentukan. Jika direktori belum ada, Java akan membuatnya secara otomatis.

## Mengonfigurasi baris generator barcode

Selain kolom, simbolologi Databar Expanded Stacked mendukung tata letak berbasis baris. Beralih dari kolom ke baris dapat meningkatkan keterbacaan pada cetakan resolusi tinggi.

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*Mengapa menggunakan baris?* Tata letak 3‑baris menyebarkan data secara vertikal, yang dapat menguntungkan untuk label sempit di mana ruang horizontal terbatas.

## Mengekspor gambar barcode sebagai PNG – versi 3‑baris

Menyimpan tata letak kedua mengikuti pola yang sama seperti sebelumnya. Menjaga nama file tetap berbeda membantu Anda membandingkan perbedaan visual.

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### Output yang diharapkan

Menjalankan program menghasilkan dua file PNG:

| Nama file                     | Deskripsi tata letak               |
|------------------------------|------------------------------------|
| `DatabarExpandedCols4.png`   | Barcode bertumpuk 4‑kolom          |
| `DatabarExpandedRows3.png`   | Barcode bertumpuk 3‑baris          |

Kedua gambar menampilkan string yang sama, tetapi kepadatan visual berbeda sesuai pengaturan kolom/baris.

## Kesalahan umum dan cara menghindarinya

| Masalah                               | Penyebab                                 | Solusi |
|---------------------------------------|------------------------------------------|--------|
| Barcode terlihat buram                | Menyimpan dengan DPI rendah              | Gunakan `generator.getParameters().setResolution(300)` sebelum `save`. |
| Teks terpotong                        | Payload melebihi kapasitas Databar       | Kurangi payload atau beralih ke `EncodeTypes.DatabarExpanded` (non‑stacked). |
| `NullPointerException` pada `setRows` | Menggunakan versi Aspose.BarCode sebelum 20.12 | Tingkatkan ke versi pustaka terbaru. |

## Variasi lanjutan (opsional)

* **Mengubah warna latar depan/latar belakang** – panggil `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` dan `setBackColor(Color.WHITE)`.
* **Menghasilkan SVG alih-alih PNG** – ganti `BarCodeImageFormat.Png` dengan `BarCodeImageFormat.Svg`.
* **Menyematkan barcode dalam PDF** – gunakan Aspose.PDF untuk membuat dokumen dan tambahkan PNG sebagai gambar.

## Kesimpulan

Anda kini tahu cara **membuat barcode databar expanded** di Java, **cara menghasilkan databar** dengan konfigurasi kolom maupun baris, serta cara **mengekspor file gambar barcode** dalam format PNG. Kode sumber lengkap siap disalin, ditempel, dan dijalankan di proyek Java mana pun.

Silakan bereksperimen dengan tata letak, warna, atau format output lainnya. Jika Anda merasa panduan ini membantu, pertimbangkan untuk menjelajahi dokumentasi Aspose.BarCode untuk topik seperti *micro‑PDF417*, *koreksi kesalahan QR code*, dan *pemindaian barcode*.

Selamat coding!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang dapat dijalankan dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [Cara menghasilkan barcode java: Membuat Gambar Barcode yang Tepat](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Panduan barcode databar expanded stacked – cara menghasilkan dan mengatur ukurannya di C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Cara membuat barcode Databar omnidirectional di C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}