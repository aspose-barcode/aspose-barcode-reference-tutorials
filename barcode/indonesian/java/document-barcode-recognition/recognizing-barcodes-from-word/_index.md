---
date: 2025-12-19
description: Pelajari cara membaca barcode Java dari dokumen Word menggunakan Aspose.BarCode.
  Panduan ini mencakup pembuatan gambar barcode, menyisipkannya ke dalam Word, dan
  mengekstrak gambar untuk pembacaan barcode.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Cara membaca barcode Java dari Dokumen Word
url: /id/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca barcode java dari Dokumen Word

## Pendahuluan

Bekerja dengan barcode dalam aplikasi Java adalah kebutuhan yang umum, terutama ketika barcode tersebut disematkan di dalam file Microsoft Word. Pada tutorial ini Anda akan mempelajari **cara membaca barcode java** dari dokumen Word menggunakan Aspose.BarCode for Java. Kami akan membahas cara menghasilkan gambar barcode, menambahkan barcode ke file Word, mengekstrak gambar dari dokumen Word, dan akhirnya mendekode barcode dengan contoh pembaca barcode Java.

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.BarCode for Java (dengan Aspose.Words untuk penanganan gambar)  
- **Bisakah saya menambahkan barcode ke Word?** Ya – buat gambar terlebih dahulu lalu sisipkan dengan Aspose.Words  
- **Bagaimana cara mengekstrak gambar dari Word?** Gunakan `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Apakah ada contoh pembaca barcode Java?** Kode pada Langkah 3 menunjukkan contoh lengkapnya  
- **Apa saja prasyaratnya?** JDK, Aspose.BarCode for Java, sebuah IDE (Eclipse/IntelliJ)

## Apa itu pengenalan barcode dalam Java?
Pengenalan barcode dalam Java mengacu pada proses mendeteksi dan mendekode simbol barcode dari gambar atau dokumen menggunakan perpustakaan seperti Aspose.BarCode. Ini memungkinkan aplikasi secara otomatis membaca kode produk, ID inventaris, atau data terenkode lainnya tanpa entri manual.

## Mengapa membaca barcode java dari dokumen Word?
Menyematkan barcode langsung di file Word berguna untuk kontrak, label pengiriman, atau laporan di mana representasi visual kode diperlukan. Kemampuan **mengekstrak gambar dari Word** dan mendekodenya secara programatik menghilangkan kebutuhan pemindaian manual dan mengurangi kesalahan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Java Development Kit (JDK)** – JDK terbaru terpasang di mesin Anda.  
- **Aspose.BarCode for Java** – unduh perpustakaan dari situs resmi [di sini](https://releases.aspose.com/barcode/java/).  
- **Integrated Development Environment (IDE)** – seperti Eclipse atau IntelliJ IDEA untuk menulis dan menjalankan kode.

## Impor Paket

Di proyek Java Anda, impor paket Aspose.BarCode dan Aspose.Words yang diperlukan:

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

## Langkah 1: Hasilkan gambar barcode (generate barcode image java)

Pertama, buat gambar barcode menggunakan Aspose.BarCode. Gambar ini nantinya akan **ditambahkan barcode ke word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Langkah 2: Sisipkan gambar barcode ke dokumen Word (insert image into word)

Sekarang kita akan menggunakan Aspose.Words untuk **menyisipkan gambar ke word** dan menyimpan dokumen:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Langkah 3: Kenali barcode dari dokumen Word (java barcode reader example)

Akhirnya, ekstrak setiap gambar dari file Word dan jalankan **java barcode reader example** untuk mendekode barcode:

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

> **Catatan:** Loop di atas memperlihatkan **mengekstrak gambar dari word**, menyimpan tiap gambar, dan kemudian mendekode barcode menggunakan jalur file gambar yang sama. Sesuaikan jalur file (`dataDir`) sesuai kebutuhan lingkungan Anda.

## Masalah Umum & Tips

- **Ketidaksesuaian jalur file** – Pastikan `dataDir` mengarah ke folder yang valid; jika tidak pembaca akan melempar `FileNotFoundException`.  
- **Tipe barcode tidak didukung** – Contoh ini menggunakan `CODE_39_STANDARD`. Jika Anda memerlukan QR, DataMatrix, dll., ubah baik `EncodeTypes` maupun `DecodeType` sesuai kebutuhan.  
- **Kinerja** – Untuk dokumen besar, pertimbangkan memproses gambar secara paralel menggunakan stream untuk mempercepat pengenalan.

## Pertanyaan yang Sering Diajukan (FAQ)

### Q: Bisakah saya menggunakan Aspose.BarCode for Java dalam proyek komersial?
Ya, Aspose.BarCode for Java tersedia untuk penggunaan komersial. Anda dapat menemukan detail lisensi [di sini](https://purchase.aspose.com/buy).

### Q: Apakah ada versi percobaan gratis untuk Aspose.BarCode for Java?
Ya, Anda dapat menjelajahi fitur Aspose.BarCode for Java dengan mengunduh versi percobaan gratis [di sini](https://releases.aspose.com/).

### Q: Bagaimana cara mendapatkan dukungan untuk Aspose.BarCode for Java?
Untuk bantuan atau pertanyaan, kunjungi forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13).

### Q: Apakah ada lisensi sementara untuk Aspose.BarCode for Java?
Ya, Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.BarCode for Java?
Lihat dokumentasi lengkap [di sini](https://reference.aspose.com/barcode/java/).

## FAQ Tambahan

**Q: Bisakah saya membaca simbol barcode lain selain Code 39?**  
A: Tentu saja. Cukup ubah `EncodeTypes` saat menghasilkan dan `DecodeType` saat membaca agar sesuai dengan simbol yang diinginkan (misalnya `EncodeTypes.QR`, `DecodeType.QR`).

**Q: Apakah pendekatan ini juga bekerja dengan file .docx?**  
A: Ya. Aspose.Words menangani format `.doc` dan `.docx` secara transparan; kode yang sama berfungsi untuk keduanya.

**Q: Bagaimana cara meningkatkan akurasi pengenalan untuk gambar beresolusi rendah?**  
A: Tingkatkan DPI saat menyimpan gambar barcode (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) atau gunakan format gambar berkualitas tinggi seperti PNG.

---

**Terakhir Diperbarui:** 2025-12-19  
**Diuji Dengan:** Aspose.BarCode for Java 24.11 dan Aspose.Words for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}