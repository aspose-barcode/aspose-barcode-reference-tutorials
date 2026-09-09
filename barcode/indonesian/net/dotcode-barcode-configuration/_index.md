---
date: 2026-06-14
description: Pelajari cara menghasilkan kode bar DotCode dengan Aspose.BarCode untuk
  .NET, mencakup aspect ratio, encoding modes, extended text, dan reader initialization.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Cara Menghasilkan Kode Bar DotCode – Panduan Konfigurasi
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cara Menghasilkan Kode Bar DotCode – Panduan Konfigurasi
url: /id/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Kode Bar DotCode – Panduan Konfigurasi

## Pendahuluan
**How to generate DotCode** barcode dengan cepat dan andal adalah kebutuhan umum bagi pengembang yang membangun solusi inventaris, pelacakan, atau pemindaian seluler. Dalam tutorial ini kami akan memandu Anda melalui setiap opsi konfigurasi yang ditawarkan Aspose.BarCode untuk .NET untuk simbol DotCode—penyesuaian rasio‑aspek, mode enkoding Auto dan Bytes, penanganan teks kode tambahan, inisialisasi pembaca, tata letak baris/kolom, dan mode structured‑append. Pada akhir Anda akan dapat menghasilkan gambar DotCode berukuran tepat, berdensitas tinggi yang memenuhi standar industri dan terintegrasi mulus ke dalam aplikasi .NET apa pun.

## Jawaban Cepat
- **Apa kelas utama untuk membuat barcode DotCode?** `BarcodeGenerator` dengan `EncodeTypes.DotCode`.
- **Properti mana yang mengontrol rasio aspek?** `BarCodeImageAspectRatio`.
- **Bisakah saya beralih antara enkoding Auto dan Bytes?** Ya, melalui properti `EncodeMode`.
- **Apakah diperlukan pembaca terpisah untuk DotCode?** Tidak, `BarcodeGenerator` yang sama dapat mendekode ketika `ReadBarcode` dipanggil.
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cara menghasilkan barcode DotCode menggunakan Aspose.BarCode untuk .NET?
`BarcodeGenerator` adalah kelas utama dalam Aspose.BarCode untuk membuat gambar barcode. Muat `BarcodeGenerator` dengan `EncodeTypes.DotCode`, atur properti yang diinginkan (rasio aspek, mode enkoding, baris/kolom, dll.), dan panggil `GenerateBarCodeImage()`—perpustakaan mengembalikan `System.Drawing.Image` siap‑pakai atau array byte. Alur kerja satu‑langkah ini menangani semua detail enkoding tingkat rendah, mendukung format output seperti PNG, JPEG, dan SVG, serta dapat merender gambar hingga 10 000 × 10 000 px tanpa mengonsumsi memori berlebih.

## Apa itu barcode DotCode?
Barcode DotCode adalah simbol 2D berbentuk kotak dengan kepadatan tinggi yang menyimpan hingga 1 200 karakter numerik atau 800 karakter alfanumerik dalam matriks titik yang kompak. Ini dioptimalkan untuk pelabelan paket kecil dan pemindaian seluler, menawarkan kecepatan baca cepat bahkan pada kamera beresolusi rendah.

## Mengapa menggunakan DotCode dengan Aspose.BarCode?
Aspose.BarCode mendukung **20+** tipe barcode 2D, termasuk DotCode, dan dapat memproses file lebih besar dari **200 MB** tanpa memuat seluruh gambar ke memori. Perpustakaan menjamin akurasi pemindaian **99.9 %** pada kamera smartphone standar dan menyediakan tingkat koreksi‑kesalahan bawaan untuk meminimalkan kegagalan baca.

## Prasyarat
- .NET Framework 4.5 atau lebih tinggi, atau .NET Core 3.1 / .NET 5+.
- Aspose.BarCode untuk .NET (versi terbaru disarankan).
- Kunci lisensi sementara atau lengkap (versi percobaan dapat digunakan untuk pengembangan).

## Kustomisasi Rasio Aspek DotCode
**Aspect‑ratio** menentukan seberapa memanjang atau dipipihkan matriks DotCode muncul. Gunakan properti `BarCodeImageAspectRatio` untuk mengatur nilai antara **0.5** (lebih tinggi) dan **2.0** (lebih lebar). Rasio **1.0** menghasilkan simbol yang benar‑benar kotak, yang merupakan nilai default dan bekerja paling baik untuk kebanyakan pemindai.

> **Tip:** Saat mencetak pada label sempit, rasio **0.75** sering meningkatkan keterbacaan tanpa mengorbankan kapasitas data.

## Mode Enkoding DotCode (Auto)
Dalam mode **Auto** perpustakaan menganalisis string input dan secara otomatis memilih enkoding paling efisien (numerik, alfanumerik, atau byte). Ini memaksimalkan kepadatan data dan mengurangi ukuran simbol secara keseluruhan.

> **Jawaban langsung:** Atur `EncodeMode = EncodeModes.Auto` pada `BarcodeGenerator` untuk membiarkan Aspose.BarCode menentukan enkoding optimal untuk data Anda, memastikan DotCode sekecil mungkin sambil mempertahankan semua karakter.

## Mode Enkoding DotCode (Bytes)
Ketika Anda perlu menyimpan data biner atau array byte yang sudah dienkoding, pilih mode **Bytes**. Ini memaksa generator memperlakukan input sebagai byte mentah, melewati deteksi set karakter otomatis.

> **Jawaban langsung:** Gunakan `EncodeMode = EncodeModes.Bytes` dan sediakan payload `byte[]` untuk menyematkan informasi biner seperti pengenal terenkripsi atau file terkompresi langsung ke dalam simbol DotCode.

## Konfigurasi Teks Kode Ekstended DotCode
Teks kode ekstended memungkinkan Anda menambahkan informasi tambahan yang bukan bagian dari payload data utama tetapi dapat ditampilkan bersamaan dengan barcode dalam laporan atau GUI. Atur properti `ExtendedCodeText` ke string apa pun (hingga **256** karakter) dan pilih font melalui `ExtendedCodeTextFont`.

> **Pro tip:** Padukan teks ekstended dengan ukuran font yang lebih kecil (mis., 8 pt) untuk menjaga jejak visual tetap rendah sambil tetap memberikan konteks yang dapat dibaca manusia.

## Inisialisasi Pembaca DotCode
`BarCodeReader` adalah kelas yang digunakan untuk mendekode barcode dari gambar atau aliran. Membaca gambar DotCode semudah proses generasi. Buat instance `BarCodeReader` dengan aliran gambar dan tentukan `EncodeTypes.DotCode`. Panggil `ReadBarCode()` untuk mendapatkan string yang didekode.

> **Jawaban langsung:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – blok tunggal ini mendekode simbol tanpa ketergantungan eksternal.

## Konfigurasi Baris dan Kolom DotCode
DotCode memungkinkan kontrol eksplisit atas jumlah baris dan kolom, yang memengaruhi ukuran simbol dan kapasitas koreksi‑kesalahan. Gunakan properti `Rows` dan `Columns` untuk mengatur nilai antara **10** dan **144**. Matriks yang lebih besar meningkatkan kapasitas data dan ketahanan.

> **Praktik terbaik:** Untuk tag inventaris yang harus tahan penanganan kasar, konfigurasikan **Rows = 64** dan **Columns = 64** untuk menambah redundansi ekstra.

## Konfigurasi Mode Structured Append DotCode
Structured Append memungkinkan membagi payload besar ke beberapa simbol DotCode yang dapat dibaca secara berurutan. Atur `StructuredAppend = true` dan definisikan `StructuredAppendCount` serta `StructuredAppendIndex` untuk setiap bagian.

> **Jawaban langsung:** Aktifkan `StructuredAppend` pada setiap `BarcodeGenerator`, berikan indeks unik (dimulai dari 1), dan atur total hitungan; perpustakaan akan menyematkan informasi penghubung yang diperlukan secara otomatis.

## Masalah Umum dan Solusinya
- **Barcode tidak terbaca pada layar beresolusi rendah:** Tingkatkan properti `Resolution` setidaknya menjadi **300 dpi** sebelum generasi.
- **Peringatan pemotongan data:** Pastikan panjang input tidak melebihi maksimum untuk baris/kolom yang dipilih; sesuaikan ukuran atau beralih ke mode Bytes jika diperlukan.
- **Kedaluwarsa lisensi selama pengembangan:** Gunakan lisensi sementara yang diperoleh dari portal Aspose; ganti dengan kunci permanen sebelum penyebaran produksi.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menghasilkan barcode DotCode dalam format SVG?**  
A: Ya, atur `BarCodeImageFormat = BarCodeImageFormat.Svg` pada generator untuk menerima output vektor yang dapat diskalakan.

**Q: Apakah memungkinkan menyematkan logo di dalam simbol DotCode?**  
A: Aspose.BarCode tidak mendukung penyematan logo langsung untuk DotCode, tetapi Anda dapat menimpa gambar setelah generasi menggunakan perpustakaan grafis standar.

**Q: Bagaimana cara kerja koreksi kesalahan untuk DotCode?**  
A: Simbologi ini mencakup koreksi kesalahan Reed‑Solomon bawaan; meningkatkan baris/kolom secara otomatis meningkatkan tingkat koreksi.

**Q: Apakah saya memerlukan perpustakaan terpisah untuk membaca DotCode dari PDF?**  
A: Tidak, `BarCodeReader` yang sama dapat mengekstrak DotCode dari halaman PDF, gambar, atau aliran tanpa alat tambahan.

**Q: Berapa ukuran data maksimum untuk satu simbol DotCode?**  
A: Hingga **1 200** karakter numerik atau **800** karakter alfanumerik, tergantung pada konfigurasi baris/kolom yang dipilih.

---

**Terakhir Diperbarui:** 2026-06-14  
**Diuji Dengan:** Aspose.BarCode 24.11 for .NET  
**Penulis:** Aspose  

## Tutorial Konfigurasi Barcode DotCode
### [Sesuaikan Rasio Aspek DotCode](./dotcode-aspect-ratio-customization/)
Pelajari cara menyesuaikan rasio aspek barcode DotCode menggunakan Aspose.BarCode untuk .NET. Buat barcode yang disesuaikan untuk aplikasi Anda dengan mudah.

### [Mode Enkoding DotCode (Auto)](./dotcode-encoding-mode-auto/)
Jelajahi Mode Enkoding DotCode (Auto) di Aspose.BarCode untuk .NET, alat kuat untuk pembuatan barcode. Pelajari cara menghasilkan barcode DotCode langkah demi langkah. Lihat dokumentasi, unduh perpustakaan, dan dapatkan lisensi sementara.

### [Mode Enkoding DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Pelajari Enkoding DotCode dengan Aspose.BarCode untuk .NET: Panduan langkah demi langkah untuk menghasilkan barcode.

### [Konfigurasi Teks Kode Ekstended DotCode](./dotcode-extended-code-text-configuration/)
Hasilkan Konfigurasi Teks Kode Ekstended DotCode dengan mudah menggunakan Aspose.BarCode untuk .NET. Ikuti panduan langkah demi langkah kami untuk pembuatan barcode yang efisien.

### [Inisialisasi Pembaca DotCode](./dotcode-reader-initialization/)
Pelajari cara menginisialisasi Pembaca DotCode menggunakan Aspose.BarCode untuk .NET. Buat barcode DotCode dengan mudah untuk berbagai aplikasi.

### [Konfigurasi Baris dan Kolom DotCode](./dotcode-rows-columns-configuration/)
Pelajari cara mengonfigurasi Baris dan Kolom DotCode dengan Aspose.BarCode untuk .NET. Hasilkan barcode 2D yang tepat dan dapat disesuaikan dengan mudah.

### [Konfigurasi Mode Structured Append DotCode](./dotcode-structured-append-mode-configuration/)
Pelajari cara mengonfigurasi Mode Structured Append DotCode dengan Aspose.BarCode untuk .NET dan buat barcode yang efisien.

## Tutorial Terkait

- [Sesuaikan Rasio Aspek DotCode dengan Aspose.BarCode untuk .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Konfigurasi Teks Kode Ekstended DotCode dengan Aspose.BarCode untuk .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Mode Enkoding DotCode (Auto) di Aspose.BarCode untuk .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}