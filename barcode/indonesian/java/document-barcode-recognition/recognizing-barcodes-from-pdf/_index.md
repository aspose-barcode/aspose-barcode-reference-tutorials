---
title: Mengenali Barcode dari PDF di Java
linktitle: Mengenali Barcode dari PDF
second_title: Aspose.BarCode Java API
description: Pelajari cara mengenali kode batang dari PDF di Java menggunakan Aspose.BarCode. Panduan langkah demi langkah dengan contoh kode. Tingkatkan efisiensi pengelolaan data Anda!
weight: 11
url: /id/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengenali Barcode dari PDF di Java


## Perkenalan

Selamat datang di panduan langkah demi langkah kami tentang mengenali kode batang dari PDF menggunakan Aspose.BarCode untuk Java. Barcode memainkan peran penting dalam manajemen dan organisasi data, dan dengan Aspose.BarCode, prosesnya menjadi lancar. Dalam tutorial ini, kami akan memandu Anda melalui seluruh proses, mulai dari menyiapkan prasyarat yang diperlukan hingga menerapkan kode untuk pengenalan kode batang dalam file PDF.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.BarCode untuk Lisensi Java: Dapatkan dan siapkan lisensi yang valid untuk Aspose.BarCode untuk Java. Anda dapat memperoleh lisensi dari[Asumsikan Pembelian](https://purchase.aspose.com/buy).

2.  Lisensi Aspose.PDF: Selain itu, siapkan lisensi untuk Aspose.PDF, yang diperlukan untuk bekerja dengan file PDF. Anda dapat mengajukan permohonan lisensi[Di Sini](https://purchase.aspose.com/temporary-license/).

3.  Unduh Aspose.BarCode untuk Java: Unduh perpustakaan Aspose.BarCode dari[Di Sini](https://releases.aspose.com/barcode/java/).

Sekarang Anda memiliki prasyarat yang diperlukan, mari lanjutkan mengimpor paket yang diperlukan dan memulai tutorial kami.

## Paket Impor

Dalam proyek Java Anda, sertakan paket Aspose.BarCode dan Aspose.PDF. Berikut cuplikan kode contoh untuk Anda mulai:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Langkah 1: Hasilkan Barcode dan Tambahkan ke PDF

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Langkah 2: Buat PDF dan Tambahkan Gambar Barcode

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Langkah 3: Ekstrak Gambar dari PDF

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Langkah 4: Kenali Barcode dari Gambar yang Diekstraksi

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Ulangi langkah-langkah ini sesuai kebutuhan, sesuaikan nama file dan jalurnya.

## Kesimpulan

 Selamat! Anda telah berhasil mempelajari cara mengenali barcode dari PDF menggunakan Aspose.BarCode untuk Java. Tutorial ini bertujuan untuk memberikan panduan komprehensif dengan tetap menjaga kesederhanaan dan kejelasan. Jangan ragu untuk menjelajahi lebih banyak fitur dan fungsi yang ditawarkan oleh Aspose.BarCode di[dokumentasi](https://reference.aspose.com/barcode/java/).

## Pertanyaan yang Sering Diajukan (FAQ)

### T: Dapatkah saya menggunakan Aspose.BarCode untuk Java tanpa lisensi?
Meskipun Aspose.BarCode dapat digunakan tanpa lisensi, disarankan untuk mendapatkannya agar berfungsi penuh dan untuk mematuhi persyaratan lisensi.

### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### T: Apakah ada batasan pada jenis kode batang yang didukung oleh Aspose.BarCode?
Aspose.BarCode mendukung berbagai jenis kode batang. Lihat dokumentasi untuk daftar lengkap.

### T: Apakah ada versi uji coba yang tersedia untuk Aspose.BarCode untuk Java?
 Ya, Anda dapat mengunduh versi uji coba dari[Di Sini](https://releases.aspose.com/).

### T: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk Java?
 Kunjungi Aspose.BarCode[forum](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
