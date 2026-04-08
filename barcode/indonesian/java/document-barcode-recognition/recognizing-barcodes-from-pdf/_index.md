---
date: 2026-04-08
description: Pelajari cara membaca barcode dari PDF di Java menggunakan Aspose.BarCode.
  Panduan ini juga menunjukkan cara menghasilkan gambar barcode dengan Java dan mengekstrak
  gambar dari PDF dengan Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Mengenali Barcode dari PDF
second_title: Aspose.BarCode Java API
title: Cara membaca barcode dari PDF di Java menggunakan Aspose.BarCode
url: /id/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca barcode dari PDF Java

## Pendahuluan

Selamat datang di panduan langkah‑demi‑langkah kami tentang **cara membaca barcode dari PDF di Java** menggunakan Aspose.BarCode. Barcode sangat penting untuk otomatisasi pengambilan data, dan dengan Aspose.BarCode Anda dapat mendeteksi barcode secara mulus di dalam dokumen PDF. Pada tutorial ini kami akan memandu Anda melalui semua yang diperlukan—mulai dari menyiapkan lisensi hingga menghasilkan gambar barcode Java, menambahkannya ke PDF, mengekstrak gambar dari PDF Java, dan akhirnya membaca kembali barcode tersebut.

## Jawaban Cepat
- **Perpustakaan apa yang saya perlukan?** Aspose.BarCode untuk Java (ditambah Aspose.PDF untuk penanganan PDF).  
- **Apakah saya dapat menghasilkan gambar barcode di Java?** Ya – kelas `BarcodeGenerator` memungkinkan Anda membuat gambar PNG/JPEG.  
- **Bagaimana gambar diekstrak dari PDF?** Gunakan `PdfExtractor` dari Aspose.PDF.  
- **Jenis barcode apa yang ditunjukkan?** CODE‑39 (standar).  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.BarCode dan Aspose.PDF yang valid diperlukan untuk penggunaan produksi.

## Mengapa menggunakan Aspose.BarCode untuk Java?
- **Akurasi tinggi** – mendukung puluhan simbol dan bekerja pada gambar beresolusi rendah.  
- **Tanpa ketergantungan eksternal** – murni Java, tanpa perpustakaan native.  
- **Integrasi PDF penuh** – gabungkan dengan Aspose.PDF untuk membaca atau menyematkan barcode langsung dalam file PDF.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

1. **Lisensi Aspose.BarCode untuk Java** – dapatkan satu dari [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Lisensi Aspose.PDF** – diperlukan untuk manipulasi PDF; Anda dapat mengajukan lisensi [di sini](https://purchase.aspose.com/temporary-license/).  
3. **Perpustakaan Aspose.BarCode** – unduh JAR terbaru dari [di sini](https://releases.aspose.com/barcode/java/).  

Setelah Anda memiliki semua prasyarat yang diperlukan, mari impor paket yang dibutuhkan dan mulai menulis kode.

## Impor Paket

Di proyek Java Anda, tambahkan impor Aspose.BarCode dan Aspose.PDF. Blok ini tidak berubah dari tutorial asli:

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

## Langkah 1: Hasilkan gambar barcode Java

Pertama, kami membuat gambar barcode yang nanti akan disematkan ke dalam PDF. Ini menunjukkan kemampuan **generate barcode image java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Langkah 2: Buat PDF dan tambahkan gambar barcode

Selanjutnya, kami membangun dokumen PDF baru dan menyisipkan gambar barcode yang baru saja dihasilkan.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Langkah 3: Ekstrak gambar dari PDF Java

Setelah PDF siap, kami perlu menarik kembali gambar yang disematkan agar barcode dapat dibaca. Ini menggunakan **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Langkah 4: Kenali barcode dari gambar yang diekstrak

Akhirnya, kami memberi setiap gambar yang diekstrak ke `BarCodeReader` untuk mengambil teks yang terkodekan.

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

Ulangi langkah‑langkah ini sesuai kebutuhan, sesuaikan nama file dan jalur agar cocok dengan struktur proyek Anda.

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Tidak ada barcode terdeteksi** | Kualitas gambar terlalu rendah atau barcode terlalu kecil. | Tingkatkan resolusi gambar saat menyimpan (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` melempar pengecualian** | File PDF tidak ditemukan atau path tidak tepat. | Pastikan `strPdfDoc` mengarah ke file yang ada dan aplikasi memiliki izin membaca. |
| **Lisensi tidak diterapkan** | Komponen Aspose berjalan dalam mode percobaan, membatasi output. | Muat file lisensi di awal program Anda: `new License().setLicense("Aspose.BarCode.lic");` dan serupa untuk Aspose.PDF. |

## Pertanyaan yang Sering Diajukan (FAQ)

### Q: Bisakah saya menggunakan Aspose.BarCode untuk Java tanpa lisensi?
Meskipun Aspose.BarCode dapat digunakan tanpa lisensi, disarankan untuk memperoleh lisensi agar mendapatkan fungsionalitas penuh dan mematuhi ketentuan lisensi.

### Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk Java?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q: Apakah ada batasan pada jenis barcode yang didukung oleh Aspose.BarCode?
Aspose.BarCode mendukung berbagai jenis barcode. Lihat dokumentasi untuk daftar lengkapnya.

### Q: Apakah ada versi percobaan untuk Aspose.BarCode untuk Java?
Ya, Anda dapat mengunduh versi percobaan dari [di sini](https://releases.aspose.com/).

### Q: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk Java?
Kunjungi forum Aspose.BarCode [di sini](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi.

## Kesimpulan

Selamat! Anda telah mempelajari cara **membaca barcode dari PDF di Java** menggunakan Aspose.BarCode, cara **menghasilkan gambar barcode Java**, dan cara **mengekstrak gambar dari PDF Java** untuk pemrosesan lebih lanjut. Jelajahi fitur tambahan seperti pemrosesan batch, penanganan berbagai simbol barcode, atau integrasi dengan produk Aspose lainnya. Untuk detail lebih dalam, periksa [dokumentasi resmi](https://reference.aspose.com/barcode/java/).

---

**Terakhir Diperbarui:** 2026-04-08  
**Diuji Dengan:** Aspose.BarCode untuk Java 24.12, Aspose.PDF untuk Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}