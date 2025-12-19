---
date: 2025-12-19
description: Pelajari cara membaca kode batang dengan Aspose.BarCode untuk Java, mengurutkannya
  dalam urutan tertentu, dan lihat contoh lengkap deteksi kode batang Java.
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: Cara Membaca Barcode dan Mengurutkannya dalam Urutan Tertentu di Java
url: /id/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Barcode dan Mengurutkannya dalam Urutan Tertentu di Java

## Pendahuluan

Dalam aplikasi Java modern, **cara membaca barcode** secara efisien adalah pertanyaan yang sering muncul. Baik Anda memproses daftar inventaris, label pengiriman, atau tiket acara, solusi barcode yang andal dapat menghemat berjam‑jam kerja manual. Pada tutorial ini kami akan menunjukkan cara membaca barcode dan mengurutkannya dalam urutan tertentu menggunakan **Aspose.BarCode for Java**. Anda akan mendapatkan contoh lengkap yang siap dijalankan yang mendemonstrasikan deteksi barcode, ekstraksi teks kode, dan logika pengurutan khusus.

## Jawaban Cepat
- **Pustaka apa yang harus saya gunakan?** Aspose.BarCode for Java
- **Apakah saya dapat mengurutkan barcode setelah membacanya?** Ya – cukup simpan hasilnya dan terapkan comparator
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru
- **Apakah ini contoh deteksi barcode Java?** Tentu – kode ini membaca barcode CODE_128 dan mengurutkannya

## Apa itu “cara membaca barcode” dalam Java?
Membaca barcode berarti mendekode pola visual gambar barcode menjadi nilai teks dasarnya. Aspose.BarCode menyediakan mesin **barcode reading aspose** berkinerja tinggi yang mendukung puluhan simbol, termasuk CODE_128, QR, DataMatrix, dan lainnya.

## Mengapa menggunakan Aspose.BarCode untuk membaca barcode aspose?
- **Akurasi tinggi** – berfungsi bahkan dengan gambar beresolusi rendah
- **API sederhana** – beberapa baris kode mengubah gambar menjadi teks
- **Lintas‑platform** – berfungsi pada lingkungan apa pun yang kompatibel dengan JVM
- **Dukungan pengurutan bawaan** – Anda dapat dengan mudah menggabungkan pembacaan dengan koleksi Java

## Prasyarat

Sebelum menyelam ke dalam kode, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK): Aspose.BarCode for Java memerlukan JDK yang berfungsi. Anda dapat mengunduh versi terbaru [di sini](https://www.oracle.com/java/technologies/javase-downloads.html).

- Pustaka Aspose.BarCode: Pastikan Anda memiliki pustaka Aspose.BarCode. Anda dapat memperolehnya dari [tautan unduhan](https://releases.aspose.com/barcode/java/).

## Impor Paket

Mulailah dengan mengimpor paket‑paket yang diperlukan ke dalam proyek Java Anda. Paket‑paket ini menyediakan kelas dan metode penting untuk bekerja dengan barcode.

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

Sekarang, mari kita uraikan kode menjadi panduan langkah‑demi‑langkah:

## Langkah 1: Siapkan Direktori Sumber Daya

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Tentukan Jalur Gambar Barcode dan Inisialisasi Reader

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Langkah 3: Baca Barcode dan Simpan Hasilnya

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

## Langkah 6: Tampilkan Barcode yang Telah Diurutkan

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

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **Tidak ada barcode yang terdeteksi** | `DecodeType` salah atau gambar ber kualitas rendah | Pastikan gambar berisi barcode CODE_128 dan gunakan `DecodeType` yang tepat. Anda juga dapat mencoba `DecodeType.ALL` untuk deteksi otomatis. |
| **Urutan pengurutan tidak tepat** | Comparator membandingkan string secara leksikografis | Jika Anda memerlukan pengurutan numerik, konversikan `CodeText` ke `int` sebelum membandingkan. |
| **Null pointer pada `BarCodeRegion`** | Jalur gambar salah atau file tidak ditemukan | Pastikan `path` mengarah ke file PNG yang valid dan file tersebut dapat dibaca oleh JVM. |

## Pertanyaan yang Sering Diajukan

**T: Di mana saya dapat menemukan dokumentasi Aspose.BarCode for Java?**  
J: Dokumentasi tersedia [di sini](https://reference.aspose.com/barcode/java/).

**T: Bagaimana cara mengunduh Aspose.BarCode for Java?**  
J: Anda dapat mengunduhnya dari [tautan unduhan](https://releases.aspose.com/barcode/java/).

**T: Apakah ada versi percobaan gratis?**  
J: Ya, Anda dapat menjelajahi versi percobaan gratis [di sini](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan informasi lisensi sementara?**  
J: Lisensi sementara dapat diperoleh [di sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan?**  
J: Kunjungi forum dukungan [di sini](https://forum.aspose.com/c/barcode/13).

## FAQ Tambahan (Dioptimalkan AI)

**T: Bisakah saya menggunakan kode ini dengan tipe barcode lain?**  
J: Tentu. Ganti `DecodeType.CODE_128` dengan simbol yang didukung, seperti `DecodeType.QR` atau `DecodeType.DATA_MATRIX`.

**T: Apakah Aspose.BarCode mendukung pemrosesan batch banyak gambar?**  
J: Ya. Loop melalui koleksi jalur file dan gunakan kembali logika `BarCodeReader` yang sama untuk setiap gambar.

**T: Bagaimana cara meningkatkan kinerja untuk kumpulan gambar besar?**  
J: Gunakan kembali instance `BarCodeReader` bila memungkinkan dan proses gambar secara paralel menggunakan `ExecutorService` Java.

## Kesimpulan

Pada tutorial ini kami mendemonstrasikan **cara membaca barcode** dengan Aspose.BarCode for Java, menyimpan setiap hasil, dan mengurutkan daftar dalam urutan khusus. Dengan mengikuti panduan langkah‑demi‑langkah, Anda dapat mengintegrasikan deteksi barcode yang kuat dan pengurutan ke dalam aplikasi Java apa pun—baik itu manajemen inventaris, logistik, atau tiket acara.

---

**Terakhir Diperbarui:** 2025-12-19  
**Diuji Dengan:** Aspose.BarCode for Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}