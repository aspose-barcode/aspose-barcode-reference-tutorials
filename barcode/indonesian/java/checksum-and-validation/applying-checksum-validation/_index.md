---
date: 2025-12-19
description: Pelajari cara menonaktifkan validasi checksum di Java dengan Aspose.BarCode.
  Panduan langkah demi langkah ini menunjukkan cara membaca barcode, mematikan checksum,
  dan memastikan penanganan data yang andal.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Cara Menonaktifkan Validasi Checksum di Java
url: /id/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menonaktifkan Validasi Checksum di Java

Dalam aplikasi inventaris dan logistik modern, **cara menonaktifkan checksum** dapat menjadi kunci untuk membaca barcode warisan yang tidak menyertakan digit checksum. Aspose.BarCode untuk Java memudahkan menonaktifkan validasi checksum sambil tetap mengekstrak data yang dikodekan. Tutorial ini memandu Anda melalui seluruh proses—dari menyiapkan proyek hingga membaca barcode ONE‑CODE tanpa verifikasi checksum.

## Jawaban Cepat
- **Apa yang dilakukan dengan menonaktifkan checksum?** Itu memberi tahu pembaca untuk mengabaikan bidang checksum, memungkinkan barcode tanpa checksum yang valid diproses.  
- **Kapan Anda harus menonaktifkan checksum?** Saat bekerja dengan sistem warisan atau barcode non‑standar yang menghilangkan atau merusak checksum.  
- **Kelas mana yang mengontrol validasi checksum?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **Apakah menonaktifkan checksum aman?** Hanya jika Anda mempercayai sumber barcode; jika tidak, validasi membantu menangkap kesalahan.  
- **Apakah ini memengaruhi tipe barcode lain?** Pengaturan ini hanya berlaku pada instance `BarCodeReader` saat ini.

## Apa Itu Validasi Checksum?
Validasi checksum adalah pemeriksaan integritas data yang menghitung nilai kecil dari konten barcode dan membandingkannya dengan checksum yang tertanam. Jika tidak cocok, barcode dianggap tidak dapat dibaca. Menonaktifkan pemeriksaan ini memberi tahu Aspose.BarCode untuk melewatkan perbandingan tersebut.

## Mengapa Menonaktifkan Checksum dengan Aspose.BarCode?
- **Dukungan Warisan:** Pemindai lama sering menghasilkan barcode tanpa checksum.  
- **Kinerja:** Melewatkan perhitungan dapat mempercepat pembacaan massal.  
- **Fleksibilitas:** Anda dapat memutuskan per instance pembaca apakah akan menegakkan validasi.

## Prasyarat
- **Java Development Kit (JDK):** Pastikan Anda memiliki JDK terbaru terpasang.  
- **Pustaka Aspose.BarCode:** Unduh pustaka dari situs resmi [here](https://releases.aspose.com/barcode/java/).  

## Impor Paket
Di proyek Java Anda, impor kelas Aspose.BarCode yang diperlukan untuk bekerja dengan pengenalan barcode.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru (IDE pilihan Anda) dan tambahkan JAR Aspose.BarCode ke classpath proyek.

### Langkah 2: Inisialisasi `BarCodeReader`
Muatan gambar yang berisi barcode ONE‑CODE yang ingin Anda baca.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Langkah 3: Cara Menonaktifkan Checksum
Beri tahu pembaca untuk mengabaikan validasi checksum dengan mengatur properti ke `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Langkah 4: Baca Barcode
Iterasi melalui hasil dan cetak teks yang didekode serta tipe simbolologi.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Hasil:** Teks barcode ditampilkan meskipun gambar asli tidak memiliki checksum yang valid.

## Masalah Umum & Tips
- **Path file tidak tepat:** Verifikasi bahwa `dataDir` mengarah ke folder yang benar; gunakan path absolut untuk pengujian.  
- **Tipe barcode tidak didukung:** Pastikan `DecodeType` cocok dengan barcode yang Anda baca.  
- **Kinerja:** Menonaktifkan checksum pada batch besar dapat meningkatkan throughput, tetapi selalu aktifkan kembali untuk data penting.

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.BarCode kompatibel dengan berbagai tipe barcode?
Ya, Aspose.BarCode mendukung berbagai macam simbol barcode, mulai dari QR dan DataMatrix hingga kode linear tradisional.

### Apakah saya dapat menggunakan Aspose.BarCode untuk tujuan komersial?
Tentu saja. Lisensi komersial tersedia untuk bisnis yang membutuhkan fitur siap produksi.

### Bagaimana saya dapat mendapatkan dukungan untuk Aspose.BarCode?
Kunjungi [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) untuk terhubung dengan komunitas dan menerima bantuan dari tim produk.

### Apakah ada percobaan gratis yang tersedia?
Ya, Anda dapat menjelajahi semua fitur dengan mengunduh [free trial](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi terperinci?
Lihat [documentation](https://reference.aspose.com/barcode/java/) yang komprehensif untuk detail API, contoh kode, dan praktik terbaik.

---

**Terakhir Diperbarui:** 2025-12-19  
**Diuji Dengan:** Aspose.BarCode untuk Java (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}