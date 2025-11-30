---
date: 2025-11-30
description: Pelajari cara menilai kualitas pembacaan barcode di Java dengan Aspose.Barcode.
  Panduan langkah demi langkah untuk mengambil persentase kualitas pengenalan.
language: id
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – Mendapatkan Kualitas Pengenalan Barcode dalam Persen
url: /java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Mendapatkan Kualitas Pengenalan Barcode dalam Persen

## Pendahuluan

Jika Anda perlu **menilai kualitas pembacaan barcode** dalam aplikasi Java, **Aspose.Barcode Java** menyediakan API sederhana yang mengembalikan kualitas pengenalan sebagai persentase. Pada tutorial ini kami akan membimbing Anda melalui langkah‑langkah tepat untuk mengambil persentase tersebut, menjelaskan mengapa metrik ini penting, dan menunjukkan cara mengintegrasikan pemanggilan tersebut ke dalam basis kode Anda yang sudah ada.

## Jawaban Cepat
- **Apa arti “kualitas pembacaan”?** Itu adalah skor kepercayaan (0‑100 %) yang diberikan perpustakaan untuk setiap barcode yang berhasil didekode.  
- **Versi perpustakaan apa yang diperlukan?** Versi Aspose.Barcode Java terbaru apa pun (contoh menggunakan seri 24.x terbaru).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya membaca semua tipe barcode?** Ya – flag `DecodeType.ALL_SUPPORTED_TYPES` mengaktifkan semua format yang didukung oleh Aspose.Barcode.  
- **Apakah nilai kualitas dapat diandalkan untuk QR code?** Tentu – algoritma kepercayaan yang sama diterapkan pada simbol 1‑D dan 2‑D.

## Apa itu Aspose.Barcode Java dan Bagaimana Menilai Kualitas Pembacaan Barcode?

**Aspose.Barcode Java** adalah perpustakaan yang sepenuhnya dikelola yang memungkinkan pengembang menghasilkan, membaca, dan menganalisis barcode tanpa ketergantungan eksternal. Salah satu diagnostik paling berguna adalah metrik **kualitas pembacaan**, yang memberi tahu seberapa yakin mesin dalam mendekode simbol. Metrik ini penting ketika Anda harus memutuskan apakah menerima hasil pemindaian, meminta pengambilan ulang, atau memicu logika penanganan kesalahan.

## Mengapa Menggunakan Aspose.Barcode Java untuk Kualitas Pembacaan Barcode?

- **Skor kepercayaan konsisten** di semua simbol yang didukung.  
- **Tanpa DLL native** – murni Java, sehingga dapat berjalan di platform apa pun yang kompatibel dengan JVM.  
- **Kontrol detail**: Anda dapat mengambil kualitas per barcode, bukan hanya hasil lulus/gagal secara global.  
- **Mesin pembaca yang dioptimalkan** untuk kinerja, dapat diskalakan dari desktop hingga layanan cloud.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Lingkungan Pengembangan Java** – JDK 8 atau lebih baru, dengan IDE pilihan Anda (IntelliJ, Eclipse, VS Code, dll.).  
- **Perpustakaan Aspose.Barcode Java** – unduh JAR terbaru dari situs resmi: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Gambar barcode contoh** – tutorial ini menggunakan `code39Extended.jpg` yang berada di folder `BarcodeReader/advanced_features/`.

Sekarang setelah semuanya siap, mari kita selami kode.

## Impor Namespace

Impor berikut memberi Anda akses ke kelas pembaca dan hasil yang diperlukan untuk mengekstrak kualitas.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Langkah 1: Atur Path Direktori Sumber Daya

Tentukan folder yang berisi gambar contoh. `Utils.getDataDir` adalah helper yang menghasilkan path absolut untuk proyek saat ini.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Langkah 2: Inisialisasi Objek BarCodeReader

Buat instance `BarCodeReader`, arahkan ke file gambar, dan beri tahu untuk mencoba **semua tipe barcode yang didukung**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Langkah 3: Baca Barcode dan Dapatkan Persentase Kualitas

Iterasi melalui setiap barcode yang terdeteksi, cetak teks, tipe, dan persentase **kualitas pembacaan** yang dikembalikan oleh `getReadingQuality()`.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**Apa yang terjadi di sini?**  
- `readBarCodes()` mengembalikan koleksi objek `BarCodeResult`, satu untuk setiap barcode yang ditemukan.  
- `getReadingQuality()` menghasilkan nilai `double` antara `0` dan `100`, yang mewakili tingkat kepercayaan.  
- Anda dapat menggunakan nilai ini untuk memutuskan apakah pemindaian dapat diterima atau apakah perlu meminta pengguna mencoba lagi.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Kualitas selalu 0** | Gambar beresolusi rendah atau sangat blur. | Gunakan sumber dengan resolusi lebih tinggi atau terapkan pra‑pemrosesan gambar (misalnya, penajaman). |
| **Tidak ada barcode terdeteksi** | Flag `DecodeType` salah. | Pastikan Anda menggunakan `DecodeType.ALL_SUPPORTED_TYPES` atau tentukan tipe yang tepat yang Anda harapkan. |
| **Exception pada `Utils.getDataDir`** | Struktur proyek berbeda dari contoh. | Ganti pemanggilan helper dengan path absolut yang ditulis keras atau path relatif yang sesuai dengan tata letak Anda. |

## Pertanyaan yang Sering Diajukan

### Q1: Apakah Aspose.Barcode kompatibel dengan semua tipe barcode?

A1: Aspose.Barcode mendukung berbagai simbol barcode, termasuk standar 1‑D (Code‑39, Code‑128, UPC) dan 2‑D (QR, DataMatrix, PDF417).

### Q2: Bisakah saya menggunakan Aspose.Barcode untuk tujuan komersial?

A2: Ya, Anda dapat menggunakan Aspose.Barcode dalam proyek pribadi maupun komersial. Detail lisensi tersedia [di sini](https://purchase.aspose.com/buy).

### Q3: Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?

A3: Dapatkan lisensi sementara dari portal Aspose [di sini](https://purchase.aspose.com/temporary-license/).

### Q4: Di mana saya dapat menemukan dukungan tambahan dan diskusi komunitas?

A4: Kunjungi [forum Aspose.Barcode](https://forum.aspose.com/c/barcode/13) untuk dukungan sesama pengguna dan bantuan resmi.

### Q5: Apakah ada contoh kode yang tersedia dalam dokumentasi?

A5: Ya, contoh kode lengkap disediakan dalam dokumentasi resmi [di sini](https://reference.aspose.com/barcode/java/).

## Kesimpulan

Dengan memanfaatkan **Aspose.Barcode Java**, Anda dapat dengan mudah mengambil persentase **kualitas pembacaan barcode** untuk simbol apa pun yang dipindai. Metrik ini memungkinkan Anda membangun logika validasi yang lebih cerdas, meningkatkan pengalaman pengguna, dan menjaga integritas data yang tinggi dalam aplikasi Java Anda.

---

**Terakhir Diperbarui:** 2025-11-30  
**Diuji Dengan:** Aspose.Barcode Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}