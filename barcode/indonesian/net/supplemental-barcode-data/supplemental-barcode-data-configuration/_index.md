---
date: 2026-03-07
description: Pelajari cara membuat kode batang EAN-13 dengan data tambahan di C# menggunakan
  Aspose.BarCode untuk .NET – hasilkan PNG kode batang dengan cepat.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Buat Kode Bar EAN-13 dengan Data Suplemen – Aspose.BarCode
url: /id/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Barcode EAN-13 dengan Data Tambahan – Aspose.BarCode untuk .NET

Dalam tutorial praktis ini Anda akan **membuat barcode EAN-13** yang mencakup data tambahan EAN‑2 atau EAN‑5, dan Anda akan melihat cara **menghasilkan file PNG barcode** dengan hanya beberapa baris C#. Baik Anda sedang membangun sistem checkout ritel, aplikasi logistik, atau alat inventaris sederhana, kemampuan menambahkan informasi tambahan membuat barcode Anda jauh lebih berguna.

## Jawaban Cepat
- **Apa arti “data tambahan”?** Digit ekstra (EAN‑2/EAN‑5) yang dicetak di samping barcode utama, biasanya digunakan untuk harga atau nomor edisi.  
- **Jenis barcode apa yang digunakan?** EAN‑13 sebagai simbol utama, dengan tambahan opsional EAN‑2 atau EAN‑5.  
- **Bisakah saya menghasilkan gambar PNG?** Ya – metode `Save` memungkinkan Anda mengekspor langsung ke PNG.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Apakah ini kompatibel dengan .NET Core / .NET 6?** Tentu – Aspose.BarCode mendukung semua runtime .NET modern.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki:

- Visual Studio (atau IDE kompatibel .NET apa pun).  
- Sebuah salinan Aspose.BarCode untuk .NET – unduh **[di sini](https://releases.aspose.com/barcode/net/)**.  
- Pengetahuan dasar C#.  
- Folder yang dapat ditulisi tempat file PNG yang dihasilkan akan disimpan.

## Mengimpor Namespace

Pertama, tambahkan namespace Aspose.BarCode sehingga Anda dapat mengakses kelas generator:

```csharp
using Aspose.BarCode.Generation;
```

> **Tip Pro:** Jika Anda menggunakan .NET Core, tambahkan paket NuGet `Aspose.BarCode` ke proyek Anda alih-alih merujuk DLL secara manual.

## Apa itu Barcode Tambahan?

Sebuah barcode tambahan adalah rangkaian numerik bantu yang dicetak di sebelah barcode utama.  
- **EAN‑2** – suplemen dua digit, sering digunakan untuk nomor edisi pada majalah.  
- **EAN‑5** – suplemen lima digit, biasanya digunakan untuk ekstensi harga pada barang ritel.

Menambahkan suplemen ini tidak mengubah data utama EAN‑13; ia hanya memberikan konteks ekstra yang dapat dibaca pemindai.

## Mengapa Menggunakan Aspose.BarCode untuk Data Tambahan?

- **API satu baris** – konfigurasikan barcode utama dan suplemennya dalam satu objek.  
- **Kontrol penuh atas dimensi** – sesuaikan dimensi X, jarak suplemen, dan format gambar.  
- **Lintas platform** – bekerja pada .NET Framework, .NET Core, dan .NET 5/6+.  

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Direktori Output

Tentukan di mana file PNG akan disimpan. Ganti placeholder dengan path nyata di mesin Anda.

```csharp
string path = "Your Directory Path";
```

### Langkah 2: Inisialisasi Barcode Generator (Barcode Generator C#)

Buat instance `BarcodeGenerator`, menentukan **EAN‑13** sebagai tipe utama dan menyediakan payload 13 digit.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Langkah 3: Sesuaikan Dimensi Barcode

Fine‑tune ukuran visual barcode dan ruang yang disediakan untuk suplemen.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Langkah 4: Tambahkan Suplemen EAN‑2

Setel data tambahan ke nilai dua digit (mis., “12”). Ini akan muncul di sebelah kanan barcode utama.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Langkah 5: Simpan Barcode EAN‑2 sebagai PNG

Ekspor gambar. Argumen `BarCodeImageFormat.Png` memastikan file PNG berkualitas tinggi.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Langkah 6: Beralih ke Suplemen EAN‑5

Ubah `SupplementData` menjadi string lima digit untuk ekstensi harga.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Langkah 7: Simpan Barcode EAN‑5 sebagai PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Mengapa ini berhasil:** Instance `BarcodeGenerator` yang sama digunakan kembali, sehingga Anda hanya perlu memodifikasi properti `SupplementData` sebelum setiap pemanggilan `Save`. Ini membuat kode tetap ringkas dan menghindari pembuatan objek yang tidak perlu.

## Masalah Umum & Tips

- **Path direktori tidak valid** – pastikan folder ada dan aplikasi memiliki izin menulis.  
- **Panjang suplemen tidak tepat** – EAN‑2 mengharuskan tepat 2 digit, EAN‑5 mengharuskan 5; jika tidak, akan dilemparkan pengecualian.  
- **Gambar tidak terlihat** – pastikan `BarCodeImageFormat.Png` digunakan; format lain (mis., JPEG) dapat menimbulkan artefak kompresi yang memengaruhi keterbacaan pemindai.  

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan Aspose.BarCode untuk .NET dalam proyek .NET Core saya?
Ya, Aspose.BarCode untuk .NET sepenuhnya kompatibel dengan .NET Core, .NET 5, dan .NET 6.

### Apakah tersedia percobaan gratis untuk Aspose.BarCode untuk .NET?
Ya, Anda dapat mencobanya secara gratis dengan mengunjungi **[tautan ini](https://releases.aspose.com/)**.

### Di mana saya dapat memperoleh lisensi sementara untuk Aspose.BarCode untuk .NET?
Anda dapat memperoleh lisensi sementara dari **[tautan ini](https://purchase.aspose.com/temporary-license/)**.

### Apakah Aspose.BarCode mendukung berbagai jenis barcode?
Tentu – ia mendukung EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417, dan banyak lagi.

### Bisakah saya menyesuaikan tampilan barcode yang dihasilkan?
Ya, Anda dapat memodifikasi warna, font, margin, dan bahkan menambahkan gambar latar menggunakan API `Parameters` yang luas.

## Kesimpulan

Anda kini tahu cara **membuat barcode EAN-13** dengan data tambahan EAN‑2 atau EAN‑5 dan **menghasilkan file PNG barcode** menggunakan Aspose.BarCode untuk .NET. Pendekatan ini memberi Anda kontrol penuh atas dimensi barcode, jarak suplemen, dan format output, menjadikannya ideal untuk ritel, logistik, dan skenario apa pun yang memerlukan informasi numerik ekstra.

Untuk eksplorasi lebih dalam, lihat panduan referensi lengkap: **[dokumentasi Aspose.BarCode untuk .NET](https://reference.aspose.com/barcode/net/)**.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}