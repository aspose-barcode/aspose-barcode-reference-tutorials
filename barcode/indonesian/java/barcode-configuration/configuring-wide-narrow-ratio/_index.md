---
date: 2026-02-12
description: Pelajari cara membuat barcode code128 dengan rasio lebar‑narrow khusus
  di Java menggunakan Aspose.BarCode, dan menghasilkan gambar PNG barcode secara efisien.
  Ikuti panduan langkah‑demi‑langkah kami.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Cara Membuat Barcode CODE_128 dengan Rasio Lebar‑Sempit di Java
url: /id/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Barcode CODE_128 dengan Rasio Wide‑Narrow di Java

## Pendahuluan

Jika Anda perlu **create code128 barcode** dengan proporsi visual yang tepat, menyesuaikan rasio wide‑narrow adalah kuncinya. Dalam tutorial ini kami akan memandu Anda melalui proses **step‑by‑step barcode** menggunakan Aspose.BarCode untuk Java, menunjukkan cara mengonfigurasi rasio, **generate barcode PNG** images, dan **save barcode image** ke disk. Baik Anda membuat label inventaris, tag pengiriman, atau aplikasi apa pun yang memerlukan barcode CODE_128 dengan gaya khusus, semua yang Anda butuhkan ada di sini.

## Jawaban Cepat
- **Apa itu rasio wide‑narrow?** Rasio ini mengontrol lebar relatif bar lebar dibandingkan bar narrow dalam barcode.  
- **Symbology mana yang mendukung penyesuaian rasio?** Sebagian besar symbology 1‑D, termasuk CODE_128, memungkinkan Anda mengatur rasio khusus.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia, tetapi lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan gambar barcode dalam format PNG?** Ya—gunakan `generator.save(...)` untuk **generate barcode PNG** images.  
- **Apakah kode ini kompatibel dengan Java 8+?** Tentu saja; Aspose.BarCode bekerja dengan semua versi Java modern.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.BarCode untuk Java. Unduh dari [download link](https://releases.aspose.com/barcode/java/).

## Impor Paket

Untuk memulai, impor kelas Aspose.BarCode yang penting ke dalam proyek Anda.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Apa itu rasio wide‑narrow dan mengapa menyesuaikannya?

Rasio wide‑narrow menentukan seberapa tebal bar “wide” dibandingkan dengan bar “narrow”. Menyesuaikan rasio ini dapat meningkatkan keterbacaan pemindai, memenuhi standar pencetakan tertentu, atau sekadar menyesuaikan gaya visual merek.

## Cara membuat code128 barcode dengan rasio wide‑narrow di Java

Berikut adalah panduan **step‑by‑step barcode** yang menguraikan setiap bagian proses.

### Langkah 1: Atur Direktori Dokumen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Pastikan direktori ada dan Anda memiliki izin menulis; ini adalah tempat file **save barcode image** akan disimpan.

### Langkah 2: Buat Instance Objek Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Di sini kami **create code128 barcode** dengan melewatkan `EncodeTypes.CODE_128` ke konstruktor.

### Langkah 3: Atur Rasio Wide‑Narrow

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metode `setWideNarrowRatio` memungkinkan Anda menyesuaikan spasi visual. Nilai `3.0f` berarti bar lebar tiga kali lebar bar narrow.

### Langkah 4: Simpan Gambar ke Disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Memanggil `save` akan **generate barcode image** dan menyimpannya sebagai file PNG, menyelesaikan langkah **save barcode image**.

## Mengapa menyesuaikan rasio wide‑narrow?

- **Kompatibilitas Pemindai:** Beberapa pemindai menyukai rasio antara 2.0 dan 3.0 untuk tingkat baca optimal.  
- **Kualitas Cetak:** Menyesuaikan rasio dapat mengkompensasi keterbatasan DPI printer, mencegah bar yang terdistorsi.  
- **Konsistensi Merek:** Beberapa perusahaan menginginkan barcode yang secara visual selaras dengan warna atau panduan desain korporat.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Barcode terlihat terdistorsi | Rasio terlalu tinggi/rendah untuk printer | Sesuaikan nilai yang diberikan ke `setWideNarrowRatio` (misalnya, 2.0‑2.5). |
| File tidak dibuat | Path `dataDir` tidak valid atau izin tidak cukup | Verifikasi path direktori dan pastikan aplikasi memiliki akses menulis. |
| Pemindai tidak dapat membaca barcode | Rasio di luar rentang yang direkomendasikan untuk symbology | Gunakan rasio standar (2.0‑3.0) atau uji dengan pemindai target. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.BarCode dengan kerangka kerja Java lainnya?**  
J: Ya, Aspose.BarCode dirancang untuk bekerja mulus dengan Spring, Java EE, Android, dan lingkungan Java lainnya.

**T: Bagaimana cara menghasilkan barcode dengan symbology yang berbeda?**  
J: Cukup ubah tipe symbology di konstruktor `BarcodeGenerator`, misalnya `EncodeTypes.QR` untuk kode QR.

**T: Apakah ada versi percobaan untuk Aspose.BarCode?**  
J: Ya, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.BarCode?**  
J: Lihat dokumentasi [di sini](https://reference.aspose.com/barcode/java/).

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode?**  
J: Kunjungi forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi komunitas.

---

**Terakhir Diperbarui:** 2026-02-12  
**Diuji Dengan:** Aspose.BarCode untuk Java 24.11 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}