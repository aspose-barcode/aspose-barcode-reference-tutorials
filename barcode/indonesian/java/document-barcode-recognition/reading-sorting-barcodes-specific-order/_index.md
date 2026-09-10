---
date: 2026-04-08
description: Pelajari cara membaca barcode dan mengurutkannya dalam urutan tertentu
  menggunakan Aspose.BarCode untuk Java. Panduan langkah demi langkah ini menunjukkan
  cara menggunakan Aspose, pembaca barcode Java, dan mendekode barcode Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: Membaca dan Mengurutkan Kode Bar dalam Urutan Tertentu
second_title: Aspose.BarCode Java API
title: Cara Membaca Barcode dalam Urutan Tertentu Menggunakan Java
url: /id/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Barcode dalam Urutan Tertentu Menggunakan Java

## Pendahuluan

Jika Anda perlu **cara membaca barcode** dan kemudian menyusunnya dalam urutan tertentu, Aspose.BarCode untuk Java memberikan cara yang bersih dan berkinerja tinggi untuk melakukannya. Dalam banyak aplikasi Java—sistem inventaris, solusi pengiriman, atau terminal titik penjualan—membaca beberapa barcode dan mengurutkannya berdasarkan nilai teksnya adalah kebutuhan yang sering muncul. Tutorial ini memandu Anda melalui proses lengkap, mulai dari menyiapkan lingkungan hingga menampilkan hasil yang telah diurutkan, sehingga Anda dapat mengintegrasikan penanganan barcode dengan cepat dan percaya diri.

## Jawaban Cepat
- **Perpustakaan apa yang menangani pembacaan barcode?** Aspose.BarCode untuk Java  
- **Jenis barcode apa yang digunakan dalam contoh?** CODE_128  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Dapatkah saya mengurutkan berdasarkan kriteria lain?** Ya—ubah comparator untuk mengurutkan berdasarkan lokasi, tingkat kepercayaan, dll.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih baru (setiap JDK yang mendukung pustaka Aspose).

## Apa itu “cara membaca barcode” dalam Java?

Membaca barcode berarti mendekode pola visual menjadi string data aslinya. Aspose.BarCode menyediakan kelas `BarCodeReader` yang mengabstraksi pemrosesan gambar tingkat rendah, memungkinkan Anda fokus pada logika bisnis seperti pengurutan atau validasi.

## Mengapa menggunakan Aspose.BarCode untuk Java?

- **Dekode yang kuat** – mendukung lebih dari 50 simbol, termasuk Code 128, QR, DataMatrix, dan lainnya.  
- **Akurasi tinggi** – algoritma yang dioptimalkan mengurangi pembacaan salah, bahkan pada gambar beresolusi rendah.  
- **API sederhana** – beberapa baris kode membawa Anda dari gambar ke teks.  
- **Lintas platform** – berfungsi pada runtime Java apa pun, dari desktop hingga lingkungan server.

## Prasyarat

Sebelum menyelam ke dalam kode, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK): Aspose.BarCode untuk Java memerlukan JDK yang berfungsi. Anda dapat mengunduh versi terbaru [di sini](https://www.oracle.com/java/technologies/javase-downloads.html).

- Pustaka Aspose.BarCode: Pastikan Anda memiliki pustaka Aspose.BarCode. Anda dapat memperolehnya dari [tautan unduhan](https://releases.aspose.com/barcode/java/).

## Impor Paket

Mulailah dengan mengimpor paket yang diperlukan ke dalam proyek Java Anda. Paket-paket ini menyediakan kelas dan metode penting untuk bekerja dengan barcode.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Sekarang, mari kita uraikan kode menjadi panduan langkah demi langkah:

## Langkah 1: Siapkan Direktori Sumber Daya

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Tentukan Jalur Gambar Barcode dan Inisialisasi Pembaca

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Langkah 3: Baca Barcode dan Simpan Hasil

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Langkah 4: Definisikan Comparator untuk Pengurutan

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Langkah 5: Urutkan Barcode

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Langkah 6: Tampilkan Barcode yang Diurutkan

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Kesalahan Umum & Tips

- **Jalur gambar tidak tepat** – periksa kembali bahwa `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) sehingga jalur lengkap dapat diselesaikan dengan benar.  
- **Jenis barcode tidak didukung** – jika Anda perlu mendekode simbol lain, ubah `DecodeType.CODE_128` ke nilai enum yang sesuai (mis., `DecodeType.QR`).  
- **Pengurutan berdasarkan nilai numerik** – comparator default mengurutkan secara leksikografis. Untuk pengurutan numerik, ubah `CodeText` menjadi integer di dalam comparator.  
- **Pembersihan sumber daya** – `BarCodeReader` mengimplementasikan `Closeable`. Pada kode produksi, bungkuslah dalam blok try‑with‑resources untuk memastikan aliran dasar dilepaskan.

## Pertanyaan yang Sering Diajukan

### Q: Di mana saya dapat menemukan dokumentasi Aspose.BarCode untuk Java?
Dokumentasi tersedia [di sini](https://reference.aspose.com/barcode/java/).

### Q: Bagaimana cara mengunduh Aspose.BarCode untuk Java?
Anda dapat mengunduhnya dari [tautan unduhan](https://releases.aspose.com/barcode/java/).

### Q: Apakah ada percobaan gratis yang tersedia?
Ya, Anda dapat menjelajahi percobaan gratis [di sini](https://releases.aspose.com/).

### Q: Bagaimana cara mendapatkan informasi lisensi sementara?
Lisensi sementara dapat diperoleh [di sini](https://purchase.aspose.com/temporary-license/).

### Q: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan?
Kunjungi forum dukungan [di sini](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode 24.10 untuk Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}