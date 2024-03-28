---
title: Menghasilkan Barcode dengan Bar Kosong di Java
linktitle: Menghasilkan Barcode dengan Bar Kosong
second_title: Aspose.BarCode Java API
description: Hasilkan kode batang dengan bilah kosong dengan mudah di Java menggunakan Aspose.BarCode. Sesuaikan tampilan dan integrasikan dengan mulus. Jelajahi tutorialnya sekarang!
type: docs
weight: 14
url: /id/java/image-manipulation/generating-barcode-empty-bars/
---

## Perkenalan

Dalam dunia pengembangan perangkat lunak yang dinamis, mengintegrasikan kemampuan pembuatan barcode ke dalam aplikasi Java telah menjadi kebutuhan umum. Aspose.BarCode untuk Java menonjol sebagai solusi tangguh, memberikan pengembang seperangkat alat canggih untuk membuat berbagai jenis kode batang. Dalam tutorial ini, kita akan mempelajari proses menghasilkan barcode dengan bar kosong menggunakan Aspose.BarCode untuk Java.

## Prasyarat

Sebelum kita memulai perjalanan pembuatan kode batang, pastikan Anda memiliki prasyarat berikut:

1. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di mesin Anda.

2.  Aspose.BarCode untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.BarCode untuk Java dari[Unduh Halaman](https://releases.aspose.com/barcode/java/).

3. Direktori Dokumen: Buat direktori di sistem Anda untuk menyimpan gambar kode batang yang dihasilkan.

## Paket Impor

Di proyek Java Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Langkah 1: Siapkan Direktori Sumber Daya

```java
// Jalur ke direktori sumber daya.
String dataDir = "Your Document Directory";
```

 Mengganti`"Your Document Directory"`dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Buat Instance Generator Barcode

```java
// Buat instance BarcodeGenerator dan inisialisasi dengan CodeText dan Simbologi
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Di sini, kami membuat instance BarcodeGenerator dengan simbologi CODE_128 dan teks "TEXT" sebagai kode yang akan dikodekan.

## Langkah 3: Setel Properti FilledBars ke False

```java
// Setel properti FilledBars ke false
generator.getParameters().getBarcode().setFilledBars(false);
```

 Dengan mengatur`FilledBars` ke`false`, kami memastikan bahwa kode batang yang dihasilkan akan memiliki bilah kosong.

## Langkah 4: Simpan Gambar Barcode

```java
// Simpan gambar barcode yang dihasilkan pada disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Langkah ini melibatkan penyimpanan gambar barcode yang dihasilkan ke direktori tertentu dalam format PNG.

Ulangi langkah-langkah ini di aplikasi Java Anda untuk dengan mudah membuat kode batang dengan bilah kosong menggunakan Aspose.BarCode untuk Java.

## Kesimpulan

Sebagai kesimpulan, tutorial ini telah memandu Anda melalui proses pembuatan kode batang dengan bilah kosong di Java menggunakan pustaka Aspose.BarCode. Dengan API intuitif dan dokumentasi ekstensif, Aspose.BarCode menyederhanakan integrasi kode batang, menjadikannya aset berharga bagi pengembang.

## FAQ

### Apakah Aspose.BarCode kompatibel dengan semua lingkungan pengembangan Java?
Ya, Aspose.BarCode dirancang untuk berintegrasi secara mulus dengan berbagai lingkungan pengembangan Java.

### Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan?
Sangat! Aspose.BarCode menyediakan banyak opsi penyesuaian, memungkinkan Anda menyesuaikan kode batang dengan kebutuhan spesifik Anda.

### Apakah versi uji coba tersedia untuk Aspose.BarCode?
 Ya, Anda dapat menjelajahi kemampuan Aspose.BarCode dengan mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.BarCode?
 Untuk pertanyaan atau bantuan apa pun, kunjungi[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.BarCode?
 Dokumentasi komprehensif tersedia[Di Sini](https://reference.aspose.com/barcode/java/).