---
date: 2026-10-19
description: Pelajari cara membuat QR code java dan menghasilkan beberapa barcode
  dalam satu gambar menggunakan Aspose.BarCode for Java. Termasuk pengaturan, kode,
  dan pemecahan masalah.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Menghasilkan beberapa barcode dalam satu gambar
og_description: Buat QR code java dan gabungkan beberapa jenis barcode menjadi satu
  gambar dengan Aspose.BarCode for Java. Ikuti panduan langkah demi langkah, lihat
  contoh kode, dan pelajari tips pemecahan masalah.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Buat QR code java – hasilkan beberapa barcode dalam satu gambar
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Buat QR code java – hasilkan beberapa barcode dalam satu gambar
url: /id/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat QR code java – hasilkan beberapa barcode pada satu gambar

## Pendahuluan

Dalam tutorial ini Anda akan belajar **cara membuat QR code java** dan menggabungkan beberapa jenis barcode yang berbeda ke dalam satu kanvas menggunakan **Aspose.BarCode for Java**. Apakah Anda membutuhkan label QR yang kompak, barcode produk, atau campuran simbol 2‑D dan linear, panduan ini akan memandu Anda melalui setiap langkah—dari penyiapan proyek hingga menyimpan gambar gabungan akhir—sehingga Anda dapat langsung mengintegrasikan pembuatan barcode ke dalam aplikasi Java Anda.

## Jawaban Cepat
- **Library apa yang harus saya gunakan?** Aspose.BarCode for Java menyediakan set simbol paling lengkap.  
- **Bisakah saya menghasilkan berbagai jenis barcode secara bersamaan?** Ya, Anda dapat mencampur CODE_39, QR, AZTEC, dan lainnya pada satu kanvas.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 dan yang lebih baru sepenuhnya kompatibel.  
- **Apakah format output dapat dikonfigurasi?** Anda dapat mengekspor gambar gabungan sebagai PNG, JPEG, BMP, atau TIFF.

## Apa itu create QR code java?

`create QR code java` mengacu pada proses mengubah string teks menjadi matriks dua‑dimensi yang dapat dipindai oleh smartphone atau pembaca barcode. Aspose.BarCode for Java melakukan enkoding dan rendering, sehingga Anda dapat fokus pada logika bisnis daripada penanganan gambar pada tingkat piksel.

## Mengapa menggunakan Aspose.BarCode Java untuk generate barcodes java?

Aspose.BarCode mendukung **lebih dari 50 simbol barcode**—termasuk QR, Data Matrix, Code 128, AZTEC, dan kode linear tradisional—menjadikannya perpustakaan barcode Java paling serbaguna. Ia merender **gambar anti‑aliased hingga 1200 dpi**, menjamin pemindaian yang tajam di layar dan cetakan. API hanya memerlukan JVM dan menyediakan model konfigurasi yang fluida untuk menyesuaikan ukuran, warna, margin, dan koreksi kesalahan dalam beberapa baris kode saja.

## Prasyarat

- Pemahaman yang kuat tentang dasar-dasar Java.  
- JDK 8 atau yang lebih baru terpasang dan dikonfigurasi di PATH Anda.  
- JAR Aspose.BarCode for Java (unduh dari halaman unduhan resmi Aspose.BarCode for Java).  
- IDE seperti IntelliJ IDEA atau Eclipse untuk mengedit dan menjalankan contoh.  

## Impor namespace

Pernyataan import membawa kelas Aspose.BarCode seperti `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat` ke dalam ruang lingkup, memungkinkan Anda merujuknya tanpa nama lengkap.  
`BarcodeGenerator` adalah kelas utama yang digunakan untuk mengkonfigurasi dan menghasilkan gambar barcode.  
`EncodeTypes` adalah enum di Aspose.BarCode yang menentukan simbol barcode yang akan dihasilkan.  
`BarCodeImageFormat` mendefinisikan format gambar output untuk barcode yang dihasilkan.

## Langkah 1: atur direktori sumber daya

**Direktori sumber daya** adalah folder pada sistem file Anda tempat semua gambar barcode yang dihasilkan akan disimpan. Menetapkannya sekali menjaga proyek Anda tetap teratur dan memudahkan pembersihan file lama.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Langkah 2: buat koleksi barcode

`HashMap<String, EncodeTypes>` menyimpan string data masing‑masing barcode bersama dengan simbol yang ingin Anda gunakan. `HashMap` adalah koleksi Java yang memetakan kunci ke nilai. Koleksi ini menggerakkan loop generasi yang berikutnya. `EncodeTypes` adalah enum yang menentukan tipe barcode yang akan dihasilkan.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Langkah 3: hasilkan gambar barcode

Loop generasi mengiterasi `HashMap`, membuat `BarcodeGenerator` untuk setiap entri, dan memanggil `generateBarCodeImage()` untuk memperoleh `BufferedImage`. `generateBarCodeImage()` membuat `BufferedImage` yang berisi barcode yang dirender. `BufferedImage` adalah kelas Java yang merepresentasikan gambar dalam memori. Semua gambar ditambahkan ke `ArrayList<BufferedImage>` untuk komposit selanjutnya. `ArrayList` adalah implementasi daftar yang dapat diubah ukurannya di Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Langkah 4: buat gambar gabungan

Pertama, algoritma menghitung **lebar maksimum** di antara semua gambar barcode dan **tinggi total** yang diperlukan untuk menumpuknya secara vertikal dengan spasi opsional. Kemudian ia membuat `BufferedImage` dengan ukuran tersebut dan menggambar setiap barcode ke kanvas menggunakan objek `Graphics2D`. `Graphics2D` adalah kelas Java yang menyediakan kemampuan rendering 2D untuk menggambar bentuk dan gambar.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Langkah 5: simpan hasil

Akhirnya, gambar komposit ditulis ke disk dengan `ImageIO.write`, menggunakan format yang Anda tentukan (PNG, JPEG, BMP, atau TIFF). `ImageIO.write` menulis `BufferedImage` ke file dalam format yang ditentukan. Jalur file relatif terhadap direktori sumber daya yang didefinisikan sebelumnya.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Kasus penggunaan umum untuk menghasilkan beberapa barcode

- **Label kemasan** – gabungkan kode produk, batch, dan pengiriman pada satu label untuk mengurangi biaya cetak.  
- **Tiket acara** – sisipkan identifier QR, Data Matrix, dan Code 128 untuk berbagai stasiun pemindaian di tempat acara.  
- **Manajemen inventaris** – tampilkan SKU, data tag RFID, dan nomor seri bersama-sama untuk audit cepat dan pelacakan.

## Pemecahan Masalah & Tips

- **Masalah ukuran gambar** – sesuaikan variabel `offset` untuk menambah atau mengurangi spasi antar barcode.  
- **Simbol tidak didukung** – pastikan versi Aspose.BarCode Anda mendukung tipe barcode yang diinginkan; rilis terbaru menambahkan kode 2‑D tambahan.  
- **Kinerja** – gunakan kembali satu objek `Graphics2D` saat menghasilkan banyak gambar dalam loop untuk meminimalkan overhead alokasi objek.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menyesuaikan tampilan barcode individual dalam gambar yang dihasilkan?**  
A: Ya. Gunakan properti `BarcodeGenerator` seperti `setBarColor`, `setBackgroundColor`, dan `setXDimension` untuk menata setiap barcode secara independen sebelum menambahkannya ke kanvas.

**Q: Apakah Aspose.BarCode kompatibel dengan berbagai simbol barcode?**  
A: Tentu saja. Perpustakaan ini mendukung lebih dari 50 simbol, termasuk CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, dan AZTEC, seperti yang ditunjukkan dalam tutorial ini.

**Q: Bagaimana cara mengintegrasikan Aspose.BarCode ke dalam proyek Java saya?**  
A: Unduh JAR dari halaman unduhan perpustakaan Aspose.BarCode for Java, tambahkan ke classpath proyek Anda, dan impor namespace yang diperlukan seperti yang ditunjukkan pada bagian “Import namespaces”.

**Q: Bisakah saya menggunakan Aspose.BarCode untuk aplikasi komersial?**  
A: Ya. Beli lisensi dari halaman pembelian lisensi Aspose.BarCode untuk menghapus batasan percobaan dan mendapatkan dukungan produksi penuh.

**Q: Apakah ada opsi percobaan yang tersedia untuk Aspose.BarCode?**  
A: Tentu. Lisensi percobaan gratis tersedia dari halaman unduhan percobaan gratis Aspose.BarCode, memberi Anda akses penuh ke API untuk evaluasi.

**Q: Bagaimana cara menghasilkan QR code resolusi tinggi untuk pencetakan?**  
A: Atur properti `setResolutionDpi` pada `BarcodeGenerator` sebelum memanggil `generateBarCodeImage()`, lalu simpan hasilnya dalam format lossless seperti PNG.

**Q: Apa yang harus saya lakukan jika gambar gabungan tampak terpotong?**  
A: Pastikan bahwa perhitungan `offset` dan ukuran kanvas memperhitungkan semua tinggi barcode dengan benar; meningkatkan tinggi kanvas atau mengurangi ukuran barcode individual menyelesaikan sebagian besar masalah pemotongan.

---

**Terakhir Diperbarui:** 2026-10-19  
**Diuji Dengan:** Aspose.BarCode for Java 24.11  
**Penulis:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Tutorial Terkait

- [Cara Membuat Gambar Barcode Java – Tambahkan Bingkai dengan Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Cara Menghasilkan Barcode Java: Simpan ke Stream dengan Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Cara Menghasilkan Barcode Java dan Mencetak Barcode dengan Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}