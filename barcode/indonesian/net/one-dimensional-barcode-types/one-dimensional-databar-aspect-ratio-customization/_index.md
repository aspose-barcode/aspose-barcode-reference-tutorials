---
date: 2026-02-25
description: Pelajari cara menyesuaikan rasio aspek **databar stacked omnidirectional**
  saat Anda **menginstal Aspose.BarCode untuk .NET**. Desain barcode yang presisi
  menjadi mudah.
linktitle: One-Dimensional Databar Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Sesuaikan databar bertumpuk omnidireksional Rasio Aspek di .NET
url: /id/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sesuaikan rasio aspek databar stacked omnidirectional di .NET

Di dunia barcode, presisi dan penyesuaian adalah kunci untuk mencapai hasil yang diinginkan. Dalam tutorial ini Anda akan belajar cara **menyesuaikan rasio aspek databar stacked omnidirectional** menggunakan Aspose.BarCode untuk .NET. Kami akan memecah proses menjadi langkah‑langkah kecil, menjelaskan mengapa setiap pengaturan penting, dan menunjukkan secara tepat cara menghasilkan gambar akhir. Jadi, mari kita mulai!

## Jawaban Cepat
- **Apa yang dapat saya sesuaikan?** Rasio aspek barcode databar stacked omnidirectional.  
- **Perpustakaan apa yang diperlukan?** Aspose.BarCode untuk .NET (pasang Aspose.BarCode untuk .NET).  
- **Berapa banyak piksel yang dapat saya atur untuk X‑Dimension?** Nilai integer apa pun; contoh menggunakan 2 piksel.  
- **Di mana gambar yang dihasilkan disimpan?** Ke folder yang Anda tentukan melalui variabel `path`.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.

## Apa itu databar stacked omnidirectional?
`databar stacked omnidirectional` adalah tipe barcode satu‑dimensi yang didefinisikan oleh standar GS1. Ia mengkodekan data numerik dalam format kompak dan ber‑densitas tinggi yang dapat dibaca dari arah mana pun, menjadikannya ideal untuk barang kecil dan pemindaian seluler.

## Mengapa menyesuaikan rasio aspek?
Mengubah **rasio aspek** memungkinkan Anda mengontrol keseimbangan visual antara lebar dan tinggi. Ini berguna ketika Anda memerlukan barcode yang cocok dengan ukuran label tertentu, selaras dengan pedoman merek, atau meningkatkan keandalan pemindaian dalam kondisi pencetakan yang terbatas.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

### 1. Install Aspose.BarCode untuk .NET  
Anda dapat mengunduh versi terbaru dari situs resmi **[di sini](https://releases.aspose.com/barcode/net/)**. Ikuti panduan instalasi untuk menambahkan paket NuGet ke proyek Anda.

### 2. Buat Proyek .NET  
Aplikasi konsol sederhana atau aplikasi Windows sudah cukup. Pastikan Anda menargetkan .NET 6+ (atau .NET Framework 4.5+) agar perpustakaan berfungsi tanpa konfigurasi tambahan.

### 3. Path Direktori Anda  
Tentukan di mana Anda ingin file PNG yang dihasilkan disimpan dan catat path absolut atau relatifnya.

## Impor Namespace

Sebelum Anda mulai menyesuaikan rasio aspek, impor namespace yang diperlukan agar dapat mengakses kelas Aspose.BarCode.

### Langkah 1: Impor Namespace Aspose.BarCode

```csharp
using Aspose.BarCode;
```

Sekarang Anda siap membuat generator barcode.

## Pengaturan Rasio Aspek databar stacked omnidirectional

### Langkah 2: Inisialisasi `BarcodeGenerator`

Kami akan membuat generator untuk tipe **databar stacked omnidirectional** dan memberinya contoh string data GS1.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarAspectRatio:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Tip:* Ganti `"Your Directory Path"` dengan folder yang sebenarnya, misalnya `@"C:\Barcodes\"`.

### Langkah 3: Atur Piksel X‑Dimension

X‑Dimension menentukan lebar bar sempit. Pada contoh ini kami menggunakan 2 piksel, tetapi Anda dapat menyesuaikannya agar cocok dengan DPI printer Anda.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Langkah 4: Sesuaikan Rasio Aspek DataBar

Sekarang masuk ke inti tutorial – mengubah rasio aspek.

#### 4.1 Atur Rasio Aspek ke 15

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 15;
gen.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Barcode disimpan sebagai **DatabarAspectRatio15.png** dengan tampilan yang relatif tinggi.

#### 4.2 Atur Rasio Aspek ke 30

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 30;
gen.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Meningkatkan rasio menjadi **30** membuat barcode menjadi lebih lebar dan lebih pendek, yang dapat berguna untuk label lebar.

### Langkah 5: Verifikasi Output

Buka file PNG yang dihasilkan dengan penampil gambar apa pun. Anda akan melihat dua versi barcode yang sama, masing‑masing dengan proporsi lebar‑ke‑tinggi yang berbeda. Pindai keduanya dengan pemindai barcode standar untuk memastikan masih dapat dibaca.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| Barcode terlihat buram | X‑Dimension terlalu rendah untuk DPI printer | Tingkatkan `XDimension.Pixels` (mis., menjadi 3 atau 4). |
| Pemindai gagal membaca | Rasio aspek ekstrem (mis., > 50) | Jaga rasio antara 10‑40 untuk pemindaian yang dapat diandalkan. |
| File tidak disimpan | String `path` tidak valid | Gunakan `Path.Combine` dan pastikan folder ada (`Directory.CreateDirectory`). |

## Pertanyaan yang Sering Diajukan

**Q: Apa itu rasio aspek sebuah barcode, dan mengapa penting?**  
A: Rasio aspek adalah proporsi lebar‑ke‑tinggi. Ia memengaruhi cara barcode cocok pada label dan dapat memengaruhi keandalan pemindaian.

**Q: Bisakah saya mengubah rasio aspek tipe barcode lain dengan Aspose.BarCode untuk .NET?**  
A: Ya, banyak barcode satu‑dimensi dan dua‑dimensi menyediakan properti `AspectRatio` untuk penyesuaian halus.

**Q: Apakah ada batasan dalam mengubah rasio aspek?**  
A: Nilai ekstrem dapat melanggar standar enkoding dan membuat barcode tidak dapat dibaca. Uji dengan pemindai target Anda.

**Q: Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.BarCode untuk .NET?**  
A: Jelajahi panduan lengkap di **[dokumentasi resmi](https://reference.aspose.com/barcode/net/)**.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.BarCode untuk .NET?**  
A: Anda dapat meminta lisensi percobaan **[di sini](https://purchase.aspose.com/temporary-license/)**.

## Kesimpulan

Anda kini telah menguasai cara **menyesuaikan rasio aspek databar stacked omnidirectional** menggunakan Aspose.BarCode untuk .NET. Dengan mengatur `XDimension` dan `DataBar.AspectRatio`, Anda dapat menghasilkan barcode yang cocok sempurna dengan dimensi label Anda, meningkatkan konsistensi estetika, dan tetap menjaga keandalan pemindaian. Bereksperimenlah dengan rasio yang berbeda, integrasikan kode ke dalam alur kerja inventaris atau pengemasan Anda, dan nikmati fleksibilitas yang disediakan Aspose.

Untuk pendalaman lebih lanjut, lihat **[dokumentasi lengkap](https://reference.aspose.com/barcode/net/)** atau bergabung dengan komunitas di **[forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13)**.

---

**Terakhir Diperbarui:** 2026-02-25  
**Diuji Dengan:** Aspose.BarCode 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}