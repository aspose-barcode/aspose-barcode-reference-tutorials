---
date: 2026-04-12
description: Pelajari cara mengenali kode batang dari dokumen Word menggunakan Aspose.BarCode
  untuk Java. Panduan ini juga menunjukkan cara menambahkan kode batang ke Word dan
  mengekstrak gambar dari Word.
keywords:
- how to recognize barcode
- add barcode to word
- read barcode from image
- extract images from word
- barcode detection java
linktitle: Mengenali Kode Batang dari Dokumen Word
second_title: Aspose.BarCode Java API
title: Cara Mengenali Barcode dari Dokumen Word – Panduan Java
url: /id/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengenali Barcode dari Dokumen Word – Panduan Java

## Pendahuluan

Jika Anda perlu **cara mengenali barcode** yang tertanam dalam file Microsoft Word, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan membahas contoh lengkap end‑to‑end yang menggunakan Aspose.BarCode for Java untuk menghasilkan barcode, menyisipkannya ke dalam dokumen Word, mengekstrak gambar kembali, dan akhirnya membaca data barcode. Pada akhir tutorial Anda juga akan melihat cara **menambahkan barcode ke Word**, **mengekstrak gambar dari Word**, dan melakukan operasi **deteksi barcode java**‑style — semuanya hanya dengan beberapa baris kode.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode for Java (plus Aspose.Words untuk menangani file .docx).  
- **Bisakah saya membaca barcode dari gambar?** Ya – `BarCodeReader` dapat mendekode gambar yang diekstrak dari Word.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan; versi percobaan gratis tersedia.  
- **Versi Java mana yang didukung?** Semua runtime JDK 8 + dapat digunakan.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk prototipe dasar.

## Apa itu pengenalan barcode dari dokumen Word?

Pengenalan barcode berarti memindai gambar yang berada di dalam file Word dan mengubah pola visual kembali menjadi string data aslinya (mis., “test‑123”). Aspose.BarCode menyediakan mesin dekoding, sementara Aspose.Words memungkinkan kami mengekstrak gambar dari kontainer .doc/.docx.

## Mengapa menggunakan Aspose.BarCode untuk Java?

- **Akurasi tinggi** pada lebih dari 60 simbol, termasuk Code 39, QR, DataMatrix, dll.  
- **Tanpa dependensi eksternal** – Java murni, tanpa pustaka native.  
- **Integrasi mulus** dengan Aspose.Words, memudahkan **mengekstrak gambar dari Word** dan kemudian **membaca barcode dari gambar**.  
- **Lisensi yang kuat** yang berfungsi di lingkungan desktop, server, dan cloud.

## Prasyarat

Sebelum kami menyelam ke dalam kode, pastikan Anda memiliki:

- **Java Development Kit (JDK)** – versi terbaru disarankan.  
- **Aspose.BarCode for Java** – unduh dan instal pustaka dari situs resmi [di sini](https://releases.aspose.com/barcode/java/).  
- **IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.

## Impor Paket

Dalam proyek Java Anda, impor kelas Aspose.BarCode dan Aspose.Words yang diperlukan:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Langkah 1: Hasilkan Gambar Barcode

Pertama, buat gambar barcode yang nanti akan kami sematkan ke dalam file Word.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Langkah 2: Tambahkan Barcode ke Dokumen Word

Sekarang kami akan menyisipkan gambar yang baru saja dihasilkan ke dalam dokumen Word baru. Ini menunjukkan skenario **add barcode to word**.

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Langkah 3: Ekstrak Gambar dan Kenali Barcode

Setelah dokumen disimpan, kami dapat mengekstrak setiap gambar (termasuk barcode kami) dan menjalankan **barcode detection java** pada masing‑masing.

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Tip profesional:** Jika Anda perlu **membaca barcode dari gambar** yang tidak berada di dalam dokumen Word, cukup berikan jalur file ke `BarCodeReader` – logika dekoding yang sama berlaku.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| `NullPointerException` pada `shape.getImageData()` | Bentuk tidak berisi gambar. | Tambahkan pemeriksaan `shape.hasImage()` (sudah ditunjukkan). |
| Tipe barcode yang salah dikembalikan | Menggunakan `DecodeType` yang salah. | Cocokkan `EncodeTypes` yang Anda gunakan saat menghasilkan (mis., `CODE_39_STANDARD`). |
| Gambar tidak tersimpan dengan benar | Izin menulis yang hilang di `dataDir`. | Pastikan direktori ada dan dapat ditulisi. |
| Lisensi tidak diterapkan | Mode evaluasi membatasi fungsionalitas. | Muat lisensi Aspose Anda saat aplikasi dimulai: `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` |

## Pertanyaan yang Sering Diajukan

### T: Bisakah saya menggunakan Aspose.BarCode untuk Java dalam proyek komersial?
J: Ya, Aspose.BarCode untuk Java tersedia untuk penggunaan komersial. Anda dapat menemukan detail lisensi [di sini](https://purchase.aspose.com/buy).

### T: Apakah tersedia percobaan gratis untuk Aspose.BarCode untuk Java?
J: Ya, Anda dapat menjelajahi fitur Aspose.BarCode untuk Java dengan mengunduh percobaan gratis [di sini](https://releases.aspose.com/).

### T: Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode untuk Java?
J: Untuk bantuan atau pertanyaan, kunjungi forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13).

### T: Apakah lisensi sementara tersedia untuk Aspose.BarCode untuk Java?
J: Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### T: Di mana saya dapat menemukan dokumentasi untuk Aspose.BarCode untuk Java?
J: Lihat dokumentasi lengkap [di sini](https://reference.aspose.com/barcode/java/).

---  

**Terakhir Diperbarui:** 2026-04-12  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk Java  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}