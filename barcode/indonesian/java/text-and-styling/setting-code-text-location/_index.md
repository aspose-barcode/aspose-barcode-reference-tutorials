---
date: 2025-12-27
description: Pelajari cara membuat barcode data matrix dan cara mengatur lokasi teks
  barcode di Java menggunakan Aspose.BarCode. Ikuti panduan langkah demi langkah kami
  untuk kustomisasi penuh.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Buat kode batang Data Matrix dan atur lokasi teks kode di Java
url: /id/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat kode batang Data Matrix dan atur lokasi teks kode di Java

## Pendahuluan

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.BarCode for Java  
- **Jenis kode batang apa yang ditunjukkan?** Data Matrix  
- **Bagaimana Anda menempatkan teks kode?** Menggunakan `CodeLocation.ABOVE`  
- **Apakah Anda memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan  
- **Apakah kode dapat dijalankan pada Java 8+?** Tentu saja, mendukung Java 8 dan versi selanjutnya  

## Apa itu kode batang Data Matrix?
Kode batang Data Matrix adalah simbol dua‑dimensi (2‑D) yang menyimpan sejumlah besar data dalam pola persegi atau persegi panjang yang kompak. Kode ini banyak digunakan untuk menandai barang kecil, elektronik, dan perangkat medis karena dapat mengkodekan hingga 2.335 karakter alfanumerik.

## Mengapa mengatur lokasi teks kode batang?
Menempatkan teks yang dapat dibaca manusia **di atas**, **di bawah**, atau **di samping** kode batang membantu pengguna dengan cepat memverifikasi data yang dikodekan tanpa pemindaian. Menyesuaikan lokasi teks meningkatkan konsistensi UI dan memenuhi pedoman merek.

## Prasyarat

- Pengetahuan dasar tentang pemrograman Java.  
- Java Development Kit (JDK) terpasang.  
- IDE seperti Eclipse atau IntelliJ IDEA.  
- Aspose.BarCode untuk Java (unduh dari [di sini](https://releases.aspose.com/barcode/java/)).  

## Impor Paket

Pertama, impor kelas Aspose.BarCode yang penting ke dalam proyek Anda:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: Tentukan Jalur Direktori
Tentukan lokasi tempat Anda ingin membaca/menulis file. Ganti placeholder dengan jalur sebenarnya pada mesin Anda.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Langkah 2: Buat Instance BarcodeGenerator
Instansiasi `BarcodeGenerator` dengan tipe **Data Matrix** dan berikan teks kode yang ingin Anda enkode.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Langkah 3: Cara mengatur lokasi teks kode batang
Gunakan enumerasi `CodeLocation` untuk memindahkan teks yang dapat dibaca manusia. Pada contoh ini kami menempatkannya **di atas** kode batang.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Langkah 4: Simpan Gambar Kode Batang yang Dihasilkan
Akhirnya, tulis gambar kode batang ke disk. File tersebut akan berisi simbol Data Matrix dengan teks yang ditempatkan di atasnya.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Masalah Umum dan Solusinya
- **Teks tidak muncul:** Pastikan Anda menggunakan versi Aspose.BarCode yang mendukung `CodeLocation`.  
- **Kesalahan jalur file:** Verifikasi bahwa `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Karakter tidak didukung:** Data Matrix hanya dapat mengkodekan sekumpulan karakter terbatas; hindari simbol khusus yang tidak ada dalam standar ISO/IEC 16022.  

## Pertanyaan yang Sering Diajukan (FAQ)

### T: Bisakah saya menyesuaikan tampilan kode batang yang dihasilkan?
J: Ya, Aspose.BarCode menyediakan opsi kustomisasi yang luas, memungkinkan Anda mengontrol warna, margin, dan gaya font.

### T: Apakah Aspose.BarCode kompatibel dengan Java 8 dan versi selanjutnya?
J: Tentu saja, perpustakaan ini bekerja dengan Java 8 dan semua rilis selanjutnya.

### T: Bagaimana cara mengintegrasikan Aspose.BarCode ke dalam proyek Java saya yang sudah ada?
J: Tambahkan file JAR Aspose.BarCode ke classpath proyek Anda, impor paket yang diperlukan, dan Anda siap menghasilkan kode batang.

### T: Apakah ada versi percobaan yang tersedia untuk Aspose.BarCode?
J: Ya, Anda dapat menjelajahi kemampuan Aspose.BarCode dengan mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

### T: Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.BarCode?
J: Kunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk bantuan komunitas dan dukungan resmi.

## FAQ Tambahan

**T: Bisakah saya menghasilkan kode batang dengan teks ditempatkan di bawah simbol?**  
J: Ya, atur `CodeLocation.BELOW` dalam metode `setLocation` yang sama.

**T: Apakah perpustakaan ini mendukung kode batang 2‑D lain seperti QR Code?**  
J: Tentu saja, cukup ubah `EncodeTypes.DATA_MATRIX` menjadi `EncodeTypes.QR`.

**T: Bagaimana cara mengubah ukuran font teks kode batang?**  
J: Gunakan `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Kesimpulan

Anda kini telah mempelajari cara **membuat kode batang Data Matrix** di Java dan mengontrol secara tepat **cara mengatur lokasi teks kode batang** menggunakan Aspose.BarCode. Bereksperimenlah dengan nilai `CodeLocation` lainnya serta opsi gaya untuk menyesuaikan kebutuhan desain aplikasi Anda.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}