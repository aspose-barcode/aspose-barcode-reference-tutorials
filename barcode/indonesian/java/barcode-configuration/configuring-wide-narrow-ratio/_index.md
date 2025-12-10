---
date: 2025-12-10
description: Pelajari cara menghasilkan barcode dengan rasio lebar‑narrow khusus di
  Java menggunakan Aspose.BarCode dan menghasilkan gambar barcode secara efisien.
  Ikuti panduan langkah demi langkah kami.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Cara Membuat Barcode dengan Rasio Lebar-Pengecil di Java
url: /id/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Barcode dengan Rasio Lebar-Pengecil di Java

## Introduction

Jika Anda perlu **cara membuat barcode** dengan proporsi visual yang tepat, mengatur rasio lebar‑pengecil adalah kuncinya. Dalam tutorial ini kami akan memandu Anda melalui proses pembuatan **barcode langkah demi langkah** menggunakan Aspose.BarCode for Java, menunjukkan cara mengonfigurasi rasio, menghasilkan gambar barcode, dan **menyimpan barcode png** ke disk. Baik Anda membuat label inventaris, tag pengiriman, atau aplikasi apa pun yang memerlukan barcode CODE_128 dengan gaya khusus, semua yang Anda butuhkan ada di sini.

## Quick Answers
- **Apa itu rasio lebar‑pengecil?** Ini mengontrol lebar relatif bar lebar dibandingkan bar sempit dalam barcode.  
- **Simbol apa yang mendukung penyesuaian rasio?** Kebanyakan simbol 1‑D, termasuk CODE_128, memungkinkan Anda mengatur rasio khusus.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia, tetapi lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghasilkan gambar barcode dalam format PNG?** Ya—gunakan `generator.save(...)` untuk menghasilkan gambar barcode sebagai PNG.  
- **Apakah kode ini kompatibel dengan Java 8+?** Tentu saja; Aspose.BarCode bekerja dengan semua versi Java modern.

## Prerequisites

Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Aspose.BarCode for Java library. Unduh dari [download link](https://releases.aspose.com/barcode/java/).

## Import Packages

Untuk memulai, impor kelas Aspose.BarCode yang penting ke dalam proyek Anda.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## What is the wide‑narrow ratio and why adjust it?

Rasio lebar‑pengecil menentukan seberapa tebal bar “lebar” dibandingkan dengan bar “sempit”. Menyesuaikan rasio ini dapat meningkatkan keterbacaan pemindai, memenuhi standar pencetakan tertentu, atau sekadar menyesuaikan gaya visual merek.

## How to generate barcode with wide‑narrow ratio in Java

Berikut adalah panduan **barcode langkah demi langkah** yang memandu Anda melalui setiap bagian proses.

### Step 1: Set Document Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Pastikan direktori ada dan Anda memiliki izin menulis; ini adalah tempat file **save barcode png** akan disimpan.

### Step 2: Instantiate Barcode Object

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Di sini kami **membuat barcode code_128** dengan memberikan `EncodeTypes.CODE_128` ke konstruktor.

### Step 3: Set Wide‑Narrow Ratio

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metode `setWideNarrowRatio` memungkinkan Anda menyesuaikan jarak visual secara halus. Nilai `3.0f` berarti bar lebar tiga kali lebar bar sempit.

### Step 4: Save Image to Disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Memanggil `save` akan **menghasilkan gambar barcode** dan menyimpannya sebagai file PNG, menyelesaikan langkah **save barcode png**.

## Common Issues and Solutions

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| Barcode terlihat terdistorsi | Rasio terlalu tinggi/rendah untuk printer | Sesuaikan nilai yang diberikan ke `setWideNarrowRatio` (mis., 2.0‑2.5). |
| File tidak dibuat | Path `dataDir` tidak valid atau izin tidak cukup | Verifikasi path direktori dan pastikan aplikasi memiliki akses menulis. |
| Pemindai tidak dapat membaca barcode | Rasio di luar rentang yang direkomendasikan untuk simbol | Gunakan rasio standar (2.0‑3.0) atau uji dengan pemindai target. |

## Frequently Asked Questions

**T: Bisakah saya menggunakan Aspose.BarCode dengan kerangka kerja Java lain?**  
J: Ya, Aspose.BarCode dirancang untuk bekerja mulus dengan Spring, Java EE, Android, dan lingkungan Java lainnya.

**T: Bagaimana saya dapat menghasilkan barcode dengan simbol yang berbeda?**  
J: Cukup ubah tipe simbol di konstruktor `BarcodeGenerator`, misalnya `EncodeTypes.QR` untuk kode QR.

**T: Apakah ada versi percobaan yang tersedia untuk Aspose.BarCode?**  
J: Ya, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.BarCode?**  
J: Lihat dokumentasi [di sini](https://reference.aspose.com/barcode/java/).

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode?**  
J: Kunjungi forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi komunitas.

---

**Terakhir Diperbarui:** 2025-12-10  
**Diuji Dengan:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}