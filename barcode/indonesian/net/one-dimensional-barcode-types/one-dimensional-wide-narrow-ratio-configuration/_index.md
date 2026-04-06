---
date: 2026-03-02
description: Pelajari cara menghasilkan barcode dengan Aspose.BarCode untuk .NET,
  termasuk tips Visual Studio untuk pembuatan barcode, dalam panduan langkah demi
  langkah tentang konfigurasi rasio lebar‑sempit.
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: Cara Membuat Barcode – Konfigurasi Rasio Lebar‑Pendek
url: /id/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasi Rasio Lebar‑Pengecil Satu‑Dimensi

Apakah Anda ingin **cara menghasilkan barcode** dengan mudah dalam aplikasi .NET Anda? Aspose.BarCode untuk .NET membuat pembuatan barcode dalam proyek Visual Studio menjadi sederhana dan kuat. Dalam tutorial ini kami akan membahas cara membuat barcode satu‑dimensi dengan rasio lebar‑pengecil khusus, menjelaskan mengapa rasio tersebut penting, dan menunjukkan cara menyesuaikannya untuk berbagai lingkungan pemindaian.

## Jawaban Cepat
- **Apa yang dikontrol oleh rasio lebar‑pengecil?** Rasio ini menentukan lebar relatif bar “lebar” dibandingkan bar “pengecil” dalam barcode 1D.  
- **Jenis barcode apa yang digunakan dalam contoh?** Code 39 Extended, sebuah simbol populer untuk data alfanumerik.  
- **Apakah saya dapat mengubah rasio saat runtime?** Ya – cukup setel `gen.Parameters.Barcode.WideNarrowRatio` ke nilai yang diinginkan sebelum menyimpan.  
- **Apakah saya memerlukan lisensi untuk fitur ini?** Rasio lebar‑pengecil berfungsi dengan versi percobaan gratis; lisensi penuh membuka semua opsi rendering.  
- **Apakah ini kompatibel dengan .NET Core?** Tentu – Aspose.BarCode mendukung .NET Framework, .NET Core, dan .NET 5/6+.

## Apa Itu Rasio Lebar‑Pengecil?
Pada barcode satu‑dimensi setiap bar memiliki status “lebar” atau “pengecil”. Rasio (misalnya 2 atau 5) menentukan berapa kali lebar bar lebar dibandingkan bar pengecil. Menyesuaikan rasio ini dapat meningkatkan keterbacaan pada printer atau pemindai beresolusi rendah.

## Mengapa Menggunakan Aspose.BarCode untuk .NET?
* **Kontrol penuh** – Setiap aspek visual, termasuk rasio lebar‑pengecil, dapat diatur secara programatis.  
* **Lintas platform** – Berfungsi di Visual Studio, Visual Studio Code, dan runtime .NET apa pun.  
* **Tanpa dependensi eksternal** – Tidak memerlukan DLL native atau alat pihak ketiga.  
* **Dokumentasi dan dukungan lengkap** – Termasuk contoh, forum, dan panduan cepat.

## Prasyarat

Sebelum kita menyelami dunia barcode dengan Aspose.BarCode untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:

### 1. Lingkungan Visual Studio
   - Pastikan Visual Studio terpasang di sistem Anda untuk bekerja dengan aplikasi .NET.

### 2. Perpustakaan Aspose.BarCode untuk .NET
   - Anda harus memiliki perpustakaan Aspose.BarCode untuk .NET terinstal. Unduh dari [website](https://releases.aspose.com/barcode/net/).

### 3. Kunci Lisensi (Opsional)
   - Jika Anda memiliki kunci lisensi, dapat digunakan untuk membuka fitur tambahan perpustakaan. Dapatkan lisensi sementara dari [sini](https://purchase.aspose.com/temporary-license/).

Setelah semua prasyarat tersedia, mari kita mulai membuat barcode satu‑dimensi dengan konfigurasi rasio lebar‑pengecil menggunakan Aspose.BarCode untuk .NET.

## Impor Namespace

Pertama, Anda perlu menyertakan namespace yang diperlukan dalam proyek Anda untuk mengakses fitur Aspose.BarCode untuk .NET. Lakukan ini dengan menambahkan pernyataan `using` berikut di bagian atas kode Anda:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Langkah 1: Tentukan Jalur Direktori Anda

Mulailah dengan mendefinisikan jalur tempat Anda ingin menyimpan gambar barcode yang dihasilkan. Lakukan ini dengan kode berikut:

```csharp
string path = "Your Directory Path";
```

Ganti `"Your Directory Path"` dengan jalur direktori aktual tempat Anda ingin menyimpan gambar barcode.

## Langkah 2: Buat Barcode Satu‑Dimensi dengan Rasio Lebar‑Pengecil

Sekarang, mari buat barcode satu‑dimensi dengan konfigurasi rasio lebar‑pengecil menggunakan Aspose.BarCode untuk .NET. Pada contoh ini, kami akan menggunakan tipe enkoding Code39Extended dan mengatur data menjadi `"ASPOSE"`:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Baris kode ini menginisialisasi generator barcode dengan tipe enkoding dan data yang ditentukan.

## Langkah 3: Atur Rasio Lebar/Pengecil

Rasio lebar‑pengecil menentukan perbandingan antara elemen lebar dan pengecil dalam barcode. Pada langkah ini, kami akan mengatur rasio lebar‑pengecil menjadi **2**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

Kemudian, kami akan menyimpan gambar barcode yang dihasilkan ke jalur yang telah ditentukan:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Langkah 4: Sesuaikan Rasio Lebar‑Pengecil

Anda dapat bereksperimen dengan rasio lebar‑pengecil yang berbeda untuk mencapai tampilan barcode yang diinginkan. Misalnya, jika Anda menginginkan barcode yang lebih lebar, atur rasio lebar‑pengecil menjadi **5**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

Dan simpan gambar barcode:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Sekarang Anda telah berhasil membuat barcode satu‑dimensi dengan rasio lebar‑pengecil yang berbeda menggunakan Aspose.BarCode untuk .NET. Perpustakaan ini memberikan fleksibilitas untuk menghasilkan barcode yang disesuaikan dengan kebutuhan spesifik Anda.

## Masalah Umum dan Solusinya
- **Gambar tidak tersimpan** – Pastikan variabel `path` mengarah ke folder yang ada dan aplikasi Anda memiliki izin menulis.  
- **Barcode tampak terdistorsi** – Coba gunakan rasio lebih rendah (misalnya 2) untuk printer beresolusi rendah; rasio tinggi dapat menyebabkan artefak cetak.  
- **Karakter tidak didukung** – Code 39 Extended mendukung seluruh set ASCII; pastikan string data Anda tidak mengandung karakter kontrol yang dilarang.

## Kesimpulan

Aspose.BarCode untuk .NET adalah perpustakaan serbaguna yang menyederhanakan pembuatan dan penyesuaian barcode dalam aplikasi .NET Anda. Dalam tutorial ini, kami membahas dasar‑dasar pembuatan barcode satu‑dimensi dengan konfigurasi rasio lebar‑pengecil. Dengan kemampuan menyesuaikan berbagai parameter, Anda dapat membuat barcode yang tepat untuk kebutuhan Anda, baik saat membangun fitur **cara menghasilkan barcode** dalam aplikasi desktop maupun layanan **barcode generation visual studio**.

## Pertanyaan yang Sering Diajukan

### 1. Bagaimana cara mendapatkan lisensi untuk Aspose.BarCode untuk .NET?
Anda dapat membeli lisensi di [situs Aspose](https://purchase.aspose.com/buy).

### 2. Bisakah saya menggunakan Aspose.BarCode untuk .NET tanpa lisensi?
Ya, Anda dapat menggunakannya dengan lisensi sementara, yang menyediakan fungsionalitas terbatas.

### 3. Apakah Aspose.BarCode untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.BarCode untuk .NET kompatibel dengan .NET Core dan .NET Framework.

### 4. Apakah ada batasan pada jenis barcode yang dapat saya hasilkan?
Aspose.BarCode untuk .NET mendukung berbagai simbol barcode, termasuk QR Code, Code 39, dan banyak lagi.

### 5. Bagaimana cara mendapatkan dukungan atau mengajukan pertanyaan tentang Aspose.BarCode untuk .NET?
Anda dapat mengunjungi [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) untuk dukungan dan diskusi.

### Tambahan Q&A

**T: Apakah mengubah rasio lebar‑pengecil memengaruhi kecepatan pemindaian?**  
J: Rasio yang lebih tinggi dapat membuat bar menjadi lebih tebal, yang mungkin meningkatkan keterbacaan pada pemindai berkualitas rendah tetapi dapat sedikit meningkatkan jumlah data yang diproses pemindai.

**T: Bisakah saya mengatur rasio untuk simbol lain seperti Code128?**  
J: Ya, properti `WideNarrowRatio` berlaku untuk semua simbol 1D yang mendukung elemen lebar dan pengecil.

---

**Terakhir Diperbarui:** 2026-03-02  
**Diuji Dengan:** Aspose.BarCode 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}