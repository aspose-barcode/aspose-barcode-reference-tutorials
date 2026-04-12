---
date: 2026-04-12
description: Pelajari cara membuat kode batang Code128 dengan bar kosong di Java menggunakan
  Aspose.BarCode. Panduan ini menunjukkan cara menghasilkan gambar kode batang Java
  dengan cepat.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Menghasilkan Kode Batang dengan Bar Kosong
second_title: Aspose.BarCode Java API
title: Cara Membuat Barcode Code128 dengan Bar Kosong di Java
url: /id/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Barcode Code128 dengan Bar Kosong di Java

## Pendahuluan

Mengintegrasikan pembuatan barcode ke dalam aplikasi Java adalah kebutuhan yang sering muncul, baik Anda membangun sistem inventaris, platform tiket, atau solusi point‑of‑sale. Dengan **Aspose.BarCode for Java**, Anda dapat **membuat gambar barcode Code128** dalam beberapa baris kode saja. Dalam tutorial ini kami akan memandu langkah‑langkah untuk **menghasilkan gambar barcode Java** yang menampilkan bar kosong (tidak terisi), memberi Anda kontrol penuh atas gaya visual barcode.

## Jawaban Cepat
- **Perpustakaan mana?** Aspose.BarCode for Java  
- **Kasus penggunaan utama?** Membuat barcode Code128 dengan bar kosong untuk desain UI khusus  
- **Prasyarat?** Java JDK 8+, Aspose.BarCode JAR, akses menulis ke folder untuk gambar output  
- **Waktu implementasi tipikal?** 5‑10 menit untuk contoh dasar  
- **Bisakah saya menyesuaikan warna?** Ya – API menyediakan opsi styling yang luas  

## Apa itu barcode Code128?

Code128 adalah simbologi barcode linear berkapasitas tinggi yang mengkodekan seluruh set karakter ASCII. Ini banyak digunakan dalam logistik, pengiriman, dan ritel karena dapat merepresentasikan data alfanumerik secara kompak. Secara default, Aspose.BarCode menampilkan bar Code128 sebagai persegi panjang padat; mengatur properti **FilledBars** ke `false` mengubahnya menjadi bar kosong (garis luar), yang berguna untuk branding bergaya.

## Mengapa menggunakan Aspose.BarCode untuk Java?

- **Set fitur kaya** – mendukung lebih dari 50 tipe barcode, termasuk QR, DataMatrix, dan PDF417.  
- **Tanpa dependensi eksternal** – satu JAR saja bekerja pada runtime Java apa pun.  
- **Kontrol detail** – Anda dapat menyesuaikan lebar bar, warna, font, dan properti `FilledBars`.  
- **Lintas platform** – bekerja pada Windows, Linux, dan macOS tanpa perpustakaan native.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih baru terpasang dan `JAVA_HOME` dikonfigurasi.  
2. **Aspose.BarCode untuk Java** – unduh JAR terbaru dari [halaman unduhan](https://releases.aspose.com/barcode/java/).  
3. **Direktori Dokumen** – sebuah folder di komputer Anda tempat gambar barcode yang dihasilkan akan disimpan.

## Impor Paket

Di proyek Java Anda, impor kelas‑kelas yang diperlukan untuk bekerja dengan Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Impor ini memberi Anda akses ke generator barcode, enumerasi format gambar, dan penanganan pengecualian.

## Langkah 1: Siapkan Direktori Sumber Daya

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan path absolut ke folder yang Anda buat pada prasyarat. Ini adalah tempat file PNG akan ditulis.

## Langkah 2: Buat Instance Generator Barcode Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Di sini kami menginstansiasi `BarcodeGenerator` dengan simbologi **CODE_128** dan teks contoh `"TEXT"`. Ini adalah **contoh generator barcode Java** yang dapat Anda sesuaikan untuk string apa pun yang ingin Anda enkode.

## Langkah 3: Atur Properti FilledBars ke False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Dengan mengatur `FilledBars` ke `false`, barcode yang dihasilkan akan menampilkan bar kosong alih‑alih bar padat, menghasilkan efek visual yang diinginkan.

## Langkah 4: Simpan Gambar Barcode

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Metode `save` menulis barcode ke direktori yang ditentukan dalam format PNG. Anda dapat mengubah `BarCodeImageFormat.PNG` menjadi `JPG`, `BMP`, atau `TIFF` jika tipe gambar lain diperlukan.

## Kasus Penggunaan Umum

- **Branding khusus** – bar kosong dapat ditumpangi pola latar atau warna.  
- **Aset siap cetak** – hasilkan PNG resolusi tinggi untuk dimasukkan ke faktur atau label pengiriman.  
- **Pembuatan dinamis** – buat barcode secara real‑time dalam layanan web atau aplikasi desktop.

## Tips Pemecahan Masalah

- **Path tidak valid** – pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) atau gabungkan menggunakan `File.separator`.  
- **Lisensi diperlukan** – versi percobaan berfungsi untuk evaluasi, tetapi lisensi penuh diperlukan untuk produksi.  
- **Karakter tidak didukung** – Code128 mendukung seluruh set ASCII; hindari karakter Unicode kecuali Anda beralih ke simbologi lain.

## Kesimpulan

Anda kini telah mempelajari cara **membuat gambar barcode Code128** dengan bar kosong menggunakan Aspose.BarCode untuk Java. Pendekatan sederhana ini memungkinkan Anda menghasilkan grafik barcode yang dapat disesuaikan dengan cepat, baik Anda membangun alat inventaris desktop maupun API berbasis cloud.

## FAQ

### Apakah Aspose.BarCode kompatibel dengan semua lingkungan pengembangan Java?
Ya, Aspose.BarCode dirancang untuk terintegrasi mulus dengan IDE atau sistem build Java apa pun, termasuk Maven, Gradle, dan proyek JAR biasa.

### Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?
Tentu! Selain `FilledBars`, Anda dapat mengubah warna, lebar bar, margin, dan bahkan menambahkan teks yang dapat dibaca manusia menggunakan API yang luas.

### Apakah tersedia versi percobaan untuk Aspose.BarCode?
Ya, Anda dapat menjelajahi kemampuan Aspose.BarCode dengan mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode?
Untuk pertanyaan atau bantuan, kunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Di mana saya dapat menemukan dokumentasi detail untuk Aspose.BarCode?
Dokumentasi lengkap tersedia [di sini](https://reference.aspose.com/barcode/java/).

**Pertanyaan Tambahan**

**T: Bagaimana cara menghasilkan gambar barcode dalam format berbeda, seperti JPEG?**  
J: Ubah argumen kedua dari `save` menjadi `BarCodeImageFormat.JPEG`.

**T: Bisakah saya menghasilkan beberapa barcode dalam loop?**  
J: Ya – buat instance baru `BarcodeGenerator` di dalam loop Anda atau gunakan kembali instance yang sama dengan `CodeText` baru.

---

**Terakhir Diperbarui:** 2026-04-12  
**Diuji Dengan:** Aspose.BarCode for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}