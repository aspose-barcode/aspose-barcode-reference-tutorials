---
date: 2025-12-25
description: Pelajari cara mengekstrak teks dari gambar barcode, khususnya PDF417
  dengan karakter Cina, menggunakan Aspose.BarCode untuk Java. Ikuti panduan langkah
  demi langkah kami tentang cara membaca data barcode secara efisien.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Ekstrak Teks dari Barcode: Karakter Cina PDF417 dalam Java'
url: /id/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekstrak Teks dari Barcode: PDF417 Karakter Cina dalam Java

## Pendahuluan

Mengintegrasikan pengenalan barcode ke dalam aplikasi Java adalah keterampilan yang berharga, terutama ketika Anda perlu **ekstrak teks dari barcode** gambar yang berisi data multibahasa. Dalam tutorial ini, kami akan memandu Anda menggunakan Aspose.BarCode untuk Java untuk mengenali barcode PDF417 dengan karakter Cina. Pada akhirnya, Anda akan tahu persis cara membaca data barcode dan mendekodenya menjadi teks yang dapat dibaca.

## Jawaban Cepat
- **Perpustakaan apa yang mendukung PDF417 dengan karakter Cina?** Aspose.BarCode untuk Java.  
- **Set karakter apa yang diperlukan untuk dekoding Cina?** MS936 (GBK).  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Ya, lisensi komersial diperlukan.  
- **Bisakah saya menjalankannya pada versi Java apa pun?** Ini bekerja dengan Java 8 dan yang lebih baru.  
- **Apakah tersedia percobaan gratis?** Tentu – unduh dari situs Aspose.

## Apa itu “ekstrak teks dari barcode”?

Mengekstrak teks dari barcode berarti mengubah data yang terenkode kembali ke bentuk aslinya yang dapat dibaca manusia. Untuk barcode PDF417 yang menyimpan karakter Cina, ini juga melibatkan pemilihan pengkodean karakter yang tepat sehingga byte‑nya dipetakan ke glif yang sesuai.

## Mengapa menggunakan Aspose.BarCode untuk Java?

Aspose.BarCode menyediakan dukungan kuat untuk berbagai simbol barcode, termasuk PDF417, dan menangani set karakter kompleks secara langsung. Ini mengabstraksi pemrosesan gambar tingkat rendah, memungkinkan Anda fokus pada logika bisnis daripada kerumitan dekoding.

## Prasyarat

1. **Java Development Kit (JDK)** – versi terbaru disarankan.  
2. **Aspose.BarCode untuk Java** – unduh dari [sini](https://releases.aspose.com/barcode/java/).  
3. **Gambar barcode PDF417** yang berisi karakter Cina (misalnya `barcode.png`).

## Impor Paket

Dalam proyek Java Anda, impor kelas yang diperlukan untuk bekerja dengan Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Langkah 1: Atur Direktori Dokumen

Tentukan folder tempat gambar barcode Anda berada:

```java
String dataDir = "Your Document Directory";
```

Ganti `"Your Document Directory"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Muat Gambar Barcode

Buat instance `BarCodeReader` yang menunjuk ke file PNG dan memberi tahu pembaca untuk mencari simbol PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Langkah 3: Baca Barcode

Iterasi melalui hasil deteksi, ambil array byte mentah, dan dekode menggunakan set karakter GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Loop ini **mengekstrak teks dari barcode** dan mencetak karakter Cina yang didekode ke konsol.

## Cara membaca barcode dengan PDF417?

Kode di atas menunjukkan **cara membaca barcode** data langkah demi langkah:

1. **Inisialisasi** pembaca dengan `DecodeType` yang tepat.  
2. **Iterasi** pada setiap `BarCodeResult` yang dikembalikan.  
3. **Konversi** byte mentah menggunakan charset yang sesuai (`MS936` untuk Cina).  

Jika barcode Anda berisi bahasa lain, cukup ganti charset ke yang cocok dengan data Anda.

## Masalah Umum & Solusi

| Masalah | Solusi |
|-------|----------|
| Karakter rusak setelah dekoding | Pastikan Anda menggunakan charset yang tepat (`MS936` untuk GBK). |
| Tidak ada barcode terdeteksi | Pastikan kualitas gambar tinggi dan barcode tidak diputar; Anda dapat memproses gambar terlebih dahulu jika diperlukan. |
| Beberapa hasil dikembalikan | PDF417 dapat menyimpan beberapa segmen; iterasi semua hasil seperti yang ditunjukkan. |

## Pertanyaan yang Sering Diajukan (FAQ)

### Can I use Aspose.BarCode for Java in commercial projects?
Ya, Anda dapat menggunakan Aspose.BarCode untuk Java dalam proyek komersial. Untuk detail lisensi, kunjungi [sini](https://purchase.aspose.com/buy).

### Is there a free trial available?
Ya, Anda dapat mengakses percobaan gratis Aspose.BarCode untuk Java [sini](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode?
Kunjungi forum Aspose.BarCode [sini](https://forum.aspose.com/c/barcode/13) untuk dukungan atau pertanyaan.

### Can I obtain a temporary license for testing purposes?
Ya, Anda dapat memperoleh lisensi sementara [sini](https://purchase.aspose.com/temporary-license/).

### Where can I find the documentation?
Dokumentasi tersedia [sini](https://reference.aspose.com/barcode/java/).

**Additional Q&A**

**Q: Bagaimana jika gambar barcode saya dalam format JPEG?**  
A: `BarCodeReader` bekerja dengan JPEG, PNG, BMP, dan format gambar umum lainnya—cukup ubah ekstensi file sesuai.

**Q: Bisakah saya mendekode barcode dari aliran (stream) alih-alih file?**  
A: Ya, Anda dapat mengirimkan `InputStream` ke konstruktor `BarCodeReader` untuk dekoding secara langsung.

**Q: Apakah Aspose.BarCode mendukung set karakter lain?**  
A: Tentu saja. Gunakan `Charset.forName("<your‑charset>")` untuk mendekode byte untuk UTF‑8, ISO‑8859‑1, dll.

## Kesimpulan

Anda kini telah belajar cara **mengekstrak teks dari barcode** gambar, khususnya barcode PDF417 yang berisi karakter Cina, menggunakan Aspose.BarCode untuk Java. Kemampuan ini membuka peluang untuk sistem inventaris multibahasa, otomatisasi dokumen, dan lainnya. Silakan bereksperimen dengan simbol lain dan set karakter untuk memperluas jangkauan aplikasi Anda.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}