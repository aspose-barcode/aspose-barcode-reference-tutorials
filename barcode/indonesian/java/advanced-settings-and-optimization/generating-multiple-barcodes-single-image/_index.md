---
date: 2026-04-03
description: Pelajari cara membuat QR code Java dan menghasilkan beberapa barcode
  pada satu gambar menggunakan Aspose.BarCode untuk Java. Termasuk pengaturan, kode,
  dan pemecahan masalah.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Menghasilkan Beberapa Kode Batang pada Satu Gambar
second_title: Aspose.BarCode Java API
title: Buat QR Code Java – Hasilkan Beberapa Barcode pada Satu Gambar
url: /id/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat QR Code Java – Menghasilkan Beberapa Barcode dalam Satu Gambar

## Pendahuluan

Dalam tutorial ini, Anda akan belajar **how to create QR code java** dan menggabungkan beberapa jenis barcode yang berbeda ke dalam satu gambar menggunakan **Aspose.BarCode for Java**. Baik Anda membutuhkan label QR yang kompak, barcode produk, atau campuran simbol 2‑D dan linear, panduan ini akan memandu Anda melalui setiap langkah—dari penyiapan proyek hingga menyimpan gambar gabungan akhir—sehingga Anda dapat segera mengintegrasikan pembuatan barcode ke dalam aplikasi Java Anda.

## Jawaban Cepat
- **Perpustakaan apa yang harus saya gunakan?** Aspose.BarCode for Java menyediakan set simbol paling lengkap.  
- **Bisakah saya menghasilkan berbagai jenis barcode secara bersamaan?** Ya, Anda dapat mencampur CODE_39, QR, AZTEC, dan lainnya pada satu kanvas.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru sepenuhnya kompatibel.  
- **Apakah format output dapat dikonfigurasi?** Anda dapat mengekspor gambar gabungan sebagai PNG, JPEG, BMP, dll.  

## Apa itu create QR code java?

Membuat QR code di Java berarti mengubah string teks menjadi matriks dua‑dimensi yang **dapat dipindai oleh smartphone atau pembaca barcode**. **Aspose.BarCode for Java** menangani proses enkoding dan rendering, memungkinkan Anda fokus pada logika bisnis alih‑alih **pemrosesan gambar tingkat rendah**.

## Mengapa menggunakan Aspose.BarCode Java untuk generate barcodes java?

- **Dukungan simbol yang luas** – dari **kode linear klasik** hingga **matriks 2‑D modern**.  
- **Rendering berkualitas tinggi** – output anti‑alias yang berfungsi pada perangkat apa pun.  
- **API sederhana** – buat, sesuaikan, dan gabungkan barcode dengan hanya beberapa pemanggilan metode.  
- **Tanpa dependensi eksternal** – semua berjalan di JVM tanpa perpustakaan native.  

## Prasyarat

- Pemahaman dasar tentang pemrograman Java.  
- Java Development Kit (JDK) terpasang di sistem Anda.  
- Perpustakaan Aspose.BarCode for Java yang telah diunduh dan disiapkan. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/barcode/java/).  
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

Tetapkan jalur ke direktori sumber daya tempat barcode yang dihasilkan akan disimpan. Direktori ini penting untuk mengatur dan mengelola gambar barcode Anda.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Langkah 2: Buat Koleksi Barcode

Inisialisasi `HashMap` untuk menyimpan data barcode. Setiap entri dalam koleksi mewakili sebuah barcode dengan tipe enkoding masing‑masing.

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

Lakukan iterasi melalui koleksi dan hasilkan gambar barcode menggunakan perpustakaan Aspose.BarCode. Simpan gambar-gambar tersebut dalam `ArrayList` untuk pemrosesan lebih lanjut.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Langkah 4: Buat Gambar Gabungan

Tentukan lebar maksimum dan total tinggi gambar barcode. Buat `BufferedImage` untuk menggabungkan gambar barcode individual menjadi satu gambar output.

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

## Langkah 5: Simpan Hasil

Simpan gambar gabungan akhir ke lokasi file yang ditentukan.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Kasus Penggunaan Umum untuk Menghasilkan Beberapa Barcode

- **Label kemasan** – gabungkan kode produk, batch, dan pengiriman pada satu label.  
- **Tiket acara** – sematkan identifier QR, Data Matrix, dan Code 128 untuk berbagai stasiun pemindaian.  
- **Manajemen inventaris** – tampilkan SKU, data tag RFID, dan nomor seri bersama‑sama untuk audit cepat.

## Pemecahan Masalah & Tips

- **Masalah ukuran gambar** – sesuaikan variabel `offset` untuk menambah atau mengurangi jarak antar barcode.  
- **Simbol tidak didukung** – pastikan versi Aspose.BarCode Anda mendukung tipe barcode yang diinginkan.  
- **Kinerja** – gunakan kembali satu objek `Graphics` jika Anda menghasilkan banyak gambar dalam loop.

## Pertanyaan yang Sering Diajukan

**Q1: Bisakah saya menyesuaikan tampilan barcode individual dalam gambar yang dihasilkan?**  
A1: Ya, Aspose.BarCode menyediakan opsi kustomisasi yang luas untuk tampilan barcode, memungkinkan Anda menyesuaikan gaya setiap barcode sesuai keinginan.

**Q2: Apakah Aspose.BarCode kompatibel dengan berbagai simbol barcode?**  
A2: Tentu saja! Aspose.BarCode mendukung berbagai macam simbol, termasuk CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, dan AZTEC, seperti yang ditunjukkan dalam tutorial ini.

**Q3: Bagaimana cara mengintegrasikan Aspose.BarCode ke dalam proyek Java saya?**  
A3: Cukup unduh perpustakaan Aspose.BarCode for Java dari [di sini](https://releases.aspose.com/barcode/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

**Q4: Bisakah saya menggunakan Aspose.BarCode untuk aplikasi komersial?**  
A4: Ya, Anda dapat memperoleh lisensi dari [di sini](https://purchase.aspose.com/buy) untuk menggunakan Aspose.BarCode untuk tujuan komersial.

**Q5: Apakah ada opsi percobaan yang tersedia untuk Aspose.BarCode?**  
A5: Tentu! Anda dapat menjelajahi fitur Aspose.BarCode dengan memperoleh lisensi percobaan gratis [di sini](https://releases.aspose.com/).

**Q6: Bagaimana cara menghasilkan QR code beresolusi tinggi untuk pencetakan?**  
A6: Atur DPI yang diinginkan pada `BarcodeGenerator` sebelum memanggil `generateBarCodeImage()`, kemudian simpan gambar dalam format loss‑less seperti PNG.

**Q7: Apa yang harus saya lakukan jika gambar gabungan terlihat terpotong?**  
A7: Pastikan bahwa perhitungan `offset` dan ukuran kanvas secara tepat memperhitungkan semua tinggi barcode; meningkatkan tinggi kanvas atau mengurangi ukuran barcode individual biasanya menyelesaikan masalah pemotongan.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}