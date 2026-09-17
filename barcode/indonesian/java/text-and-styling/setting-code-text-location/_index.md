---
date: 2026-05-04
description: Pelajari cara membuat barcode Data Matrix menggunakan perpustakaan barcode
  Java dan mengatur lokasi teks barcode di atas simbol dengan Aspose.BarCode. Ikuti
  contoh pembuatan barcode langkah demi langkah kami.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Pengaturan Lokasi Teks Kode
second_title: Aspose.BarCode Java API
title: Buat Barcode Data Matrix dengan Perpustakaan Barcode Java dan Atur Lokasi Teks
  Kode
url: /id/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kode Barcode Data Matrix dengan Java Barcode Library dan Atur Lokasi Teks Kode

## Pendahuluan

Jika Anda membangun sistem inventaris, pengiriman, atau pelacakan dalam Java, Anda akan segera menemukan bahwa **java barcode library** yang handal sangat penting. Dengan **Aspose.BarCode for Java** Anda dapat menghasilkan **Data Matrix barcode** hanya dalam beberapa baris kode dan sepenuhnya mengontrol tata letak visual, termasuk di mana teks yang dapat dibaca manusia muncul. Dalam tutorial ini kami akan membahas contoh **barcode generation example** lengkap, menunjukkan cara **customize barcode text** penempatan, dan menjelaskan mengapa menempatkan teks di atas simbol dapat meningkatkan kegunaan.

## Jawaban Cepat
- **Library apa yang digunakan?** Aspose.BarCode for Java  
- **Jenis barcode apa yang ditunjukkan?** Data Matrix  
- **Bagaimana cara menempatkan teks kode?** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **Apakah Anda memerlukan lisensi untuk produksi?** Yes, a commercial license is required  
- **Apakah kode dapat dijalankan pada Java 8+?** Absolutely, it supports Java 8 and later  

## Apa itu Java barcode library?
Sebuah **java barcode library** menyediakan API siap pakai bagi pengembang untuk membuat, membaca, dan menata barcode 1‑D dan 2‑D langsung dari aplikasi Java. Library ini mengabstraksi aturan enkoding yang kompleks dan memungkinkan Anda fokus pada logika bisnis alih-alih pemrosesan gambar tingkat rendah.

## Mengapa menggunakan Java barcode library untuk contoh pembuatan barcode?
- **Kecepatan:** Menghasilkan barcode berkualitas tinggi dalam milidetik.  
- **Keandalan:** Kepatuhan bawaan dengan standar ISO/IEC.  
- **Fleksibilitas:** Kontrol penuh atas ukuran, warna, margin, dan penempatan **barcode text**.  
- **Lintas‑platform:** Berfungsi pada lingkungan berbasis JVM apa pun, dari aplikasi desktop hingga layanan cloud.

## Apa itu Data Matrix barcode?
Data Matrix barcode adalah simbol dua‑dimensi (2‑D) yang menyimpan sejumlah besar data dalam pola persegi atau persegi panjang yang kompak. Ini banyak digunakan untuk menandai barang kecil, elektronik, dan perangkat medis karena dapat mengkodekan hingga 2.335 karakter alfanumerik.

## Mengapa mengatur lokasi teks barcode?
Menempatkan teks yang dapat dibaca manusia **di atas**, **di bawah**, atau **di samping** barcode membantu pengguna dengan cepat memverifikasi data yang dikodekan tanpa pemindaian. Menyesuaikan lokasi teks meningkatkan konsistensi UI, memenuhi pedoman merek, dan dapat mengurangi kesalahan dalam entri data manual.

## Prasyarat

- Pengetahuan dasar tentang pemrograman Java.  
- Java Development Kit (JDK) terpasang.  
- IDE seperti Eclipse atau IntelliJ IDEA.  
- Aspose.BarCode for Java library (unduh dari [di sini](https://releases.aspose.com/barcode/java/)).  

## Impor Paket

Pertama, impor kelas Aspose.BarCode yang penting ke dalam proyek Anda:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Impor ini memberi Anda akses ke generator barcode dan enumerasi yang mengontrol penempatan teks.

## Panduan langkah‑demi‑langkah

### Langkah 1: Tentukan Jalur Direktori
Tentukan di mana Anda ingin membaca/menulis file. Ganti placeholder dengan jalur sebenarnya di mesin Anda.

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

### Langkah 3: Atur lokasi teks barcode (sesuaikan teks barcode)
Gunakan enumerasi `CodeLocation` untuk memindahkan teks yang dapat dibaca manusia. Dalam contoh ini kami menempatkannya **di atas** barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro tip:** Untuk menempatkan teks **di bawah** simbol, cukup ubah `CodeLocation.ABOVE` menjadi `CodeLocation.BELOW`.

### Langkah 4: Simpan Gambar Barcode yang Dihasilkan
Akhirnya, tulis gambar barcode ke disk. File tersebut akan berisi simbol Data Matrix dengan teks yang ditempatkan di atasnya.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Masalah Umum dan Solusinya
- **Teks tidak muncul:** Pastikan Anda menggunakan versi Aspose.BarCode yang mendukung `CodeLocation`.  
- **Kesalahan jalur file:** Verifikasi bahwa `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Karakter tidak didukung:** Data Matrix hanya dapat mengkodekan set karakter terbatas; hindari simbol khusus yang tidak ada dalam standar ISO/IEC 16022.  

## Pertanyaan yang Sering Diajukan (FAQ)

### Q: Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?
A: Ya, Aspose.BarCode menyediakan opsi penyesuaian yang luas, memungkinkan Anda mengontrol warna, margin, dan gaya font.

### Q: Apakah Aspose.BarCode kompatibel dengan Java 8 dan versi selanjutnya?
A: Tentu saja, library ini bekerja dengan Java 8 dan semua rilis berikutnya.

### Q: Bagaimana cara mengintegrasikan Aspose.BarCode ke dalam proyek Java saya yang ada?
A: Tambahkan file JAR Aspose.BarCode ke classpath proyek Anda, impor paket yang diperlukan, dan Anda siap menghasilkan barcode.

### Q: Apakah ada versi percobaan tersedia untuk Aspose.BarCode?
A: Ya, Anda dapat menjelajahi kemampuan Aspose.BarCode dengan mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

### Q: Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.BarCode?
A: Kunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk bantuan komunitas dan dukungan resmi.

## Pertanyaan Tambahan yang Sering Diajukan

**Q: Bisakah saya menghasilkan barcode dengan teks yang ditempatkan di bawah simbol?**  
A: Ya, set `CodeLocation.BELOW` dalam metode `setLocation` yang sama.

**Q: Apakah library mendukung barcode 2‑D lain seperti QR Code?**  
A: Tentu saja, cukup ubah `EncodeTypes.DATA_MATRIX` menjadi `EncodeTypes.QR`.

**Q: Bagaimana cara mengubah ukuran font teks barcode?**  
A: Gunakan `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Kesimpulan

Anda kini telah mempelajari cara **membuat Data Matrix barcode** di Java menggunakan **java barcode library** dan mengontrol secara tepat **cara mengatur lokasi teks barcode** dengan Aspose.BarCode. Bereksperimenlah dengan nilai `CodeLocation` lainnya, pengaturan font, dan opsi warna untuk menyesuaikan kebutuhan desain aplikasi Anda.

---

**Terakhir Diperbarui:** 2026-05-04  
**Diuji Dengan:** Aspose.BarCode for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}