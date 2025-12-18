---
date: 2025-12-18
description: Pelajari cara membuat gambar kode batang codabar dan lihat contoh pembaca
  kode batang Java menggunakan Aspose.BarCode. Hasilkan dan kenali kode batang dengan
  mudah melalui panduan langkah demi langkah ini.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Cara membuat gambar barcode codabar dengan checksum di Java
url: /id/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat gambar barcode codabar dengan checksum di Java

## Pendahuluan

Dalam tutorial ini, Anda akan belajar cara **membuat gambar barcode codabar** dengan checksum di Java menggunakan Aspose.BarCode. Kami akan memandu Anda melalui pembuatan barcode CodaBar, mengaktifkan checksum, dan kemudian membacanya kembali dengan **contoh pembaca barcode java**. Pada akhir tutorial, Anda akan memiliki potongan kode siap pakai yang dapat Anda sisipkan ke dalam proyek Java mana pun.

## Jawaban Cepat
- **Apa fungsi checksum?** Ia memvalidasi integritas data barcode saat pemindaian.  
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode untuk Java.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menyesuaikan tampilan barcode?** Ya – warna, ukuran, dan font dapat diubah melalui parameter generator.  
- **Apakah ini kompatibel dengan semua versi Java?** Perpustakaan mendukung Java 8 dan yang lebih baru.

## Apa itu barcode CodaBar?

CodaBar adalah simbol linear (dimensi‑1) yang banyak digunakan di perpustakaan, bank darah, dan ritel. Ia mengkodekan data numerik dan beberapa karakter khusus, menjadikannya ideal untuk tag sederhana yang dapat dibaca mesin. Menambahkan checksum (Mod 10) meningkatkan akurasi pembacaan, terutama pada cetakan berkualitas rendah.

## Mengapa menggunakan Aspose.BarCode untuk Java?

Aspose.BarCode menawarkan **contoh pembaca barcode java** yang menyederhanakan detail tingkat rendah dari pembuatan dan pengenalan barcode. Ia menyediakan:

* Kontrol penuh atas mode checksum.  
* Integrasi mulus dengan IDE Java.  
* Dokumentasi dan dukungan yang luas.  

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.BarCode untuk Java. Anda dapat mengunduhnya dari [di sini](https://releases.aspose.com/barcode/java/).  
- Pemahaman dasar tentang pemrograman Java.  

## Impor Paket

Dalam proyek Java Anda, impor kelas yang diperlukan untuk bekerja dengan Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Lingkungan

Buat proyek Java baru dan tambahkan JAR Aspose.BarCode ke jalur build Anda. Tentukan folder tempat gambar yang dihasilkan akan disimpan.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Langkah 2: Hasilkan gambar barcode CodaBar dengan checksum

Buat instance `BarcodeGenerator`, aktifkan checksum, pilih mode Mod 10, dan simpan gambar.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### Langkah 3: Contoh pembaca barcode Java – Kenali barcode

Sekarang baca kembali barcode, mengaktifkan validasi checksum untuk memastikan data benar.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Menjalankan kode akan menampilkan teks yang didekode, tipe simbol, dan checksum yang dihitung, mengonfirmasi bahwa barcode telah dihasilkan dan divalidasi dengan benar.

## Masalah Umum dan Solusinya

| Masalah | Solusi |
|---------|--------|
| **Validasi checksum gagal** | Pastikan `EnableChecksum` diatur ke `YES` dan `CodabarChecksumMode` cocok dengan mode yang digunakan saat pembuatan (Mod 10). |
| **Kesalahan file tidak ditemukan** | Pastikan `dataDir` mengarah ke folder yang ada dan gambar yang dihasilkan (`Codabar_Mod10.png`) disimpan di sana sebelum dibaca. |
| **Versi Java tidak didukung** | Gunakan Java 8 atau yang lebih baru; versi lama mungkin tidak memiliki API yang diperlukan. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.BarCode kompatibel dengan semua versi Java?**  
A: Aspose.BarCode dirancang untuk bekerja dengan Java 8 dan yang lebih baru. Periksa dokumentasi resmi untuk kompatibilitas detail.

**Q: Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?**  
A: Ya, Anda dapat mengubah warna, font, dan format gambar melalui API parameter generator.

**Q: Apakah lisensi sementara tersedia untuk tujuan pengujian?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk Aspose.BarCode dari [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dukungan dan sumber daya tambahan?**  
A: Kunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk dukungan komunitas dan diskusi.

**Q: Apakah tersedia percobaan gratis?**  
A: Ya, Anda dapat menjelajahi fitur Aspose.BarCode dengan mengunduh percobaan gratis dari [di sini](https://releases.aspose.com/).

---

**Terakhir Diperbarui:** 2025-12-18  
**Diuji Dengan:** Aspose.BarCode for Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}