---
date: 2025-12-22
description: Pelajari cara membuat gambar barcode dengan bar kosong menggunakan Aspose.BarCode
  untuk Java. Contoh pembuatan barcode langkah demi langkah ini membantu Anda menghasilkan
  barcode Java dengan cepat.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Cara Membuat Gambar Barcode dengan Bar Kosong di Java
url: /id/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Gambar Barcode dengan Bar Kosong di Java

## Pendahuluan

Pada aplikasi Java modern, kemampuan untuk **create barcode image** secara langsung merupakan fitur berharga untuk manajemen inventaris, sistem tiket, dan banyak skenario bisnis lainnya. Aspose.BarCode for Java menyediakan API yang kuat dan mudah‑digunakan yang memungkinkan Anda menghasilkan barcode berkualitas tinggi hanya dengan beberapa baris kode. Dalam tutorial ini kami akan membahas proses pembuatan **step‑by‑step barcode** yang menghasilkan barcode dengan bar kosong (tidak terisi), sempurna untuk desain yang memerlukan tampilan berongga.

## Jawaban Cepat
- **What does “empty bars” mean?** Bar ditampilkan tanpa isian padat default, memberikan tampilan berongga.  
- **Which barcode type is used?** Code 128 (sebuah simbologi linear yang didukung luas).  
- **Do I need a license to try it?** Versi percobaan gratis tersedia; lisensi diperlukan untuk penggunaan produksi.  
- **What output formats are supported?** PNG, JPEG, BMP, GIF, TIFF, dan lainnya.  
- **Is this compatible with all Java versions?** Ya, perpustakaan ini bekerja dengan Java 8 dan versi lebih baru.

## Apa itu create barcode image?
Membuat gambar barcode berarti mengubah string data menjadi representasi visual yang dapat dibaca oleh pemindai. Gambar yang dihasilkan dapat disimpan sebagai PNG, JPEG, atau format umum lainnya serta disisipkan dalam PDF, dicetak pada label, atau ditampilkan pada antarmuka pengguna.

## Mengapa menggunakan perpustakaan Aspose.BarCode Java?
- **Rich feature set** – mendukung lebih dari 50 simbologi barcode, termasuk Code 128, QR, DataMatrix, dan lainnya.  
- **Fine‑grained control** – properti seperti `FilledBars`, warna, margin, dan ukuran gambar dapat dengan mudah dikonfigurasi.  
- **No external dependencies** – satu file JAR menangani semuanya, menyederhanakan penyebaran.  
- **Comprehensive documentation** – contoh, referensi API, dan forum membantu Anda memulai dengan cepat.

## Prasyarat

Sebelum kita memulai proses pembuatan barcode, pastikan Anda memiliki prasyarat berikut:

1. **Java Development Environment** – Pastikan Anda memiliki Java 8+ terpasang serta IDE atau alat build yang kompatibel.  
2. **Aspose.BarCode for Java Library** – Unduh dan instal perpustakaan Aspose.BarCode for Java dari [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – Buat direktori di sistem Anda untuk menyimpan gambar barcode yang dihasilkan.

## Impor Paket

Dalam proyek Java Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Cara Membuat Gambar Barcode dengan Bar Kosong

### Langkah 1: Siapkan Direktori Sumber Daya

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan file output.

### Langkah 2: Buat Instance Barcode Generator (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Di sini, kami menggunakan simbologi **Code 128**—salah satu barcode linear paling populer—menjadikannya contoh klasik **code128 barcode java**.

### Langkah 3: Atur Properti FilledBars ke False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Mengatur `FilledBars` ke `false` memberi tahu Aspose.BarCode untuk merender bar sebagai bentuk kosong (berongga) alih-alih blok padat.

### Langkah 4: Simpan Gambar Barcode

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Gambar disimpan dalam format PNG, tetapi Anda dapat mengubah enum `BarCodeImageFormat` untuk menghasilkan JPEG, BMP, atau tipe lain yang didukung.

Ulangi langkah-langkah ini dalam aplikasi Java Anda untuk dengan mudah **create barcode image** file dengan bar kosong menggunakan Aspose.BarCode for Java.

## Kesimpulan

Sebagai kesimpulan, tutorial ini telah memandu Anda melalui proses pembuatan **step‑by‑step barcode** yang menunjukkan cara **create barcode image** file dengan bar kosong di Java. Dengan API yang intuitif dan opsi kustomisasi yang luas, Aspose.BarCode menyederhanakan integrasi barcode, menjadikannya aset berharga bagi pengembang yang membutuhkan **java barcode library** yang handal.

## FAQ

### Apakah Aspose.BarCode kompatibel dengan semua lingkungan pengembangan Java?
Ya, Aspose.BarCode dirancang untuk terintegrasi secara mulus dengan berbagai lingkungan pengembangan Java.

### Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?
Tentu saja! Aspose.BarCode menyediakan banyak opsi kustomisasi, memungkinkan Anda menyesuaikan barcode sesuai kebutuhan spesifik Anda.

### Apakah tersedia versi percobaan untuk Aspose.BarCode?
Ya, Anda dapat menjelajahi kemampuan Aspose.BarCode dengan mendapatkan percobaan gratis [here](https://releases.aspose.com/).

### Bagaimana saya dapat mendapatkan dukungan untuk Aspose.BarCode?
Untuk pertanyaan atau bantuan, kunjungi [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Di mana saya dapat menemukan dokumentasi detail untuk Aspose.BarCode?
Dokumentasi lengkap tersedia [here](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose