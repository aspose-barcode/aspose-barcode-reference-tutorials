---
title: Menghasilkan Banyak Barcode pada Satu Gambar di Java dengan Aspose.BarCode
linktitle: Menghasilkan Banyak Barcode pada Satu Gambar
second_title: Aspose.BarCode Java API
description: Hasilkan beberapa kode batang pada satu gambar dengan mudah menggunakan Aspose.BarCode untuk Java. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
weight: 19
url: /id/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghasilkan Banyak Barcode pada Satu Gambar di Java dengan Aspose.BarCode

## Perkenalan

Dalam dunia pemrograman Java yang dinamis, membuat dan mengelola kode batang secara efisien sangat penting untuk berbagai aplikasi. Aspose.BarCode untuk Java menyederhanakan proses ini, memungkinkan pengembang menghasilkan banyak kode batang pada satu gambar dengan mulus. Tutorial ini akan memandu Anda melalui langkah-langkah untuk mencapai hal ini menggunakan Aspose.BarCode di lingkungan Java.

## Prasyarat

Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:

- Pemahaman dasar pemrograman Java.
- Java Development Kit (JDK) diinstal pada sistem Anda.
- Aspose.BarCode untuk perpustakaan Java diunduh dan disiapkan. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/barcode/java/).
- Lingkungan pengembangan terintegrasi (IDE) seperti Eclipse atau IntelliJ IDEA.

## Impor Namespace

Di proyek Java Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.BarCode. Tambahkan pernyataan import berikut di awal kelas Java Anda:

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

## Langkah 1: Atur Direktori Sumber Daya

Tentukan jalur ke direktori sumber daya tempat kode batang yang dihasilkan akan disimpan. Direktori ini sangat penting untuk mengatur dan mengelola gambar barcode Anda.

```java
// Jalur ke direktori sumber daya.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Langkah 2: Buat Koleksi Barcode

Inisialisasi HashMap untuk menyimpan data kode batang. Setiap entri dalam koleksi mewakili kode batang dengan jenis pengkodeannya masing-masing.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Langkah 3: Hasilkan Gambar Barcode

Ulangi koleksi dan hasilkan gambar kode batang menggunakan pustaka Aspose.BarCode. Simpan gambar dalam ArrayList untuk diproses lebih lanjut.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Langkah 4: Buat Gambar Gabungan

Tentukan lebar maksimum dan tinggi total gambar barcode. Buat BufferedImage untuk menggabungkan masing-masing gambar kode batang menjadi satu gambar keluaran.

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
## Langkah 5: Simpan Hasilnya

Simpan gambar gabungan akhir ke lokasi file tertentu.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Kesimpulan

Selamat! Anda telah berhasil membuat beberapa kode batang pada satu gambar menggunakan Aspose.BarCode untuk Java. Pustaka yang kuat ini menyederhanakan penanganan kode batang, menjadikannya alat yang sangat berharga bagi pengembang Java.

## FAQ

### Q1: Dapatkah saya menyesuaikan tampilan masing-masing kode batang pada gambar yang dihasilkan?

A1: Ya, Aspose.BarCode menyediakan opsi penyesuaian ekstensif untuk tampilan kode batang, memungkinkan Anda menyesuaikan gaya setiap kode batang sesuai preferensi Anda.

### Q2: Apakah Aspose.BarCode kompatibel dengan simbologi kode batang yang berbeda?

A2: Tentu saja! Aspose.BarCode mendukung berbagai simbologi, termasuk CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, dan AZTEC, seperti yang ditunjukkan dalam tutorial ini.

### Q3: Bagaimana cara mengintegrasikan Aspose.BarCode ke dalam proyek Java saya?

 A3: Cukup unduh perpustakaan Aspose.BarCode untuk Java dari[Di Sini](https://releases.aspose.com/barcode/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

### Q4: Dapatkah saya menggunakan Aspose.BarCode untuk aplikasi komersial?

 A4: Ya, Anda bisa mendapatkan lisensi dari[Di Sini](https://purchase.aspose.com/buy) untuk menggunakan Aspose.BarCode untuk tujuan komersial.

### Q5: Apakah ada opsi uji coba yang tersedia untuk Aspose.BarCode?

 A5: Tentu saja! Anda dapat menjelajahi fitur Aspose.BarCode dengan mendapatkan lisensi uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
