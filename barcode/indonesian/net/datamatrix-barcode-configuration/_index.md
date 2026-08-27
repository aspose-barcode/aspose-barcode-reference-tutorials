---
date: 2026-06-09
description: Pelajari cara menghasilkan datamatrix barcode dengan Aspose.BarCode untuk
  .NET, menyesuaikan aspect ratios, ECC modes, dan datamatrix c40 encoding untuk pembuatan
  barcode yang efisien.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Konfigurasi DataMatrix Barcode
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Buat DataMatrix Barcode – Panduan Pro dengan Aspose.BarCode
url: /id/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hasilkan Barcode DataMatrix – Panduan Pro dengan Aspose.BarCode

Selamat datang di seri tutorial komprehensif kami tentang **generate datamatrix barcode** menggunakan Aspose.BarCode untuk .NET. Baik Anda seorang pengembang berpengalaman yang menyempurnakan output barcode maupun pendatang baru yang ingin memahami dasar‑dasarnya, panduan ini akan membawa Anda melalui setiap langkah—dari konfigurasi dasar hingga teknik enkoding lanjutan—sehingga Anda dapat menghasilkan barcode yang dapat dipindai dengan andal dalam aplikasi .NET apa pun.

## Jawaban Cepat
- **Apa tujuan utama?** Untuk membuat dan menyesuaikan barcode DataMatrix secara programatis.  
- **Perpustakaan mana yang digunakan?** Aspose.BarCode untuk .NET.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk produksi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Bisakah saya menyesuaikan rasio aspek?** Ya – lihat bagian “Cara menyesuaikan rasio aspek DataMatrix”.

## Apa itu generate datamatrix barcode?
Barcode DataMatrix adalah matriks dua‑dimensi berisi sel hitam dan putih yang dapat menyimpan hingga 2 300 karakter alfanumerik. Menggunakan Aspose.BarCode, Anda dapat **generate datamatrix barcode** dalam bentuk gambar, PDF, atau SVG langsung dari kode .NET Anda, mengontrol ukuran, tingkat koreksi‑error, dan mode enkoding untuk memenuhi standar industri apa pun.

## Mengapa menggunakan Aspose.BarCode untuk DataMatrix?
Aspose.BarCode merender simbol DataMatrix hingga **600 dpi** tanpa pikselasi, menjamin pemindaian tajam pada printer beresolusi tinggi. Ia mendukung **lebih dari 50 mode ECC dan makro**—termasuk ECC 000‑140, ECC 200, dan Macro 05/06—sehingga Anda dapat memilih tingkat koreksi‑error optimal untuk ukuran data Anda. API menawarkan opsi enkoding **ASCII, C40, Text, X12, dan Bytes**, memungkinkan Anda mengemas data secara efisien. Integrasi hanya memerlukan satu paket NuGet dan tidak memerlukan pustaka native eksternal.

## Cara menyesuaikan rasio aspek DataMatrix
Properti `AspectRatio` pada `BarCodeGenerator` mengontrol proporsi lebar‑ke‑tinggi simbol DataMatrix yang dihasilkan. `BarCodeGenerator` adalah kelas utama di Aspose.BarCode yang digunakan untuk membuat gambar barcode.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (atau nilai apa pun antara 0.5 dan 2.0) sebelum memanggil `GenerateBarCodeImage()`. Perpustakaan secara otomatis menghitung ulang ukuran modul untuk mempertahankan keandalan pemindaian sambil menghormati rasio yang diminta.

### Langkah demi langkah
1. **Instansiasi** `BarCodeGenerator` dengan `EncodeTypes.DataMatrix`.  
2. **Sesuaikan** `AspectRatio` ke nilai yang diinginkan.  
3. **Hasilkan** gambar dan verifikasi dengan pemindai atau pembaca bawaan Aspose.

## Cara menghasilkan barcode DataMatrix ECC 000‑140
ECC 000‑140 ideal untuk string data pendek yang memerlukan simbol kompak, menawarkan hingga 140 kode koreksi‑error. `DataMatrixEccMode.Ecc000140` memilih skema koreksi‑error ECC 000‑140 untuk DataMatrix.  

**Jawaban langsung:** Gunakan `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` sebelum rendering. Ini mengalihkan enkoder ke algoritma ECC 000‑140, menghasilkan matriks sekecil mungkin untuk data yang diberikan sambil tetap menyediakan koreksi‑error yang kuat.

### Tips praktis
Saat mengenkripsi data numerik kurang dari 20 karakter, ECC 000‑140 biasanya menghasilkan matriks 10 × 10, yang menghemat ruang label berharga.

## Cara menghasilkan barcode DataMatrix ECC 200
ECC 200 adalah mode DataMatrix yang paling banyak diadopsi, mendukung hingga 2 335 karakter alfanumerik dan menawarkan koreksi‑error superior. `DataMatrixEccMode.Ecc200` memilih skema koreksi‑error ECC 200 untuk DataMatrix.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` dan berikan payload Anda melalui `CodeText`. Perpustakaan kemudian secara otomatis memilih ukuran matriks optimal.

### Kapan memilih ECC 200
Gunakan ECC 200 untuk string yang lebih panjang, data campuran, atau ketika Anda memerlukan ketahanan tertinggi terhadap kerusakan—hingga **30 %** simbol dapat dipulihkan.

## Cara menguasai enkoding DataMatrix dalam ASCII
Mode ASCII mengenkripsi karakter menggunakan satu byte per karakter, menjadikannya yang paling efisien ruang untuk teks biasa. `DataMatrixEncodeMode.Ascii` memberi tahu generator untuk menggunakan enkoding ASCII pada simbol DataMatrix.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` dan set `CodeText` ke string ASCII Anda. Mesin mengemas data tanpa overhead tambahan, menghasilkan matriks sekecil mungkin untuk konten ASCII murni.

### Contoh skenario
SKU gudang yang terdiri dari huruf kapital dan angka (misalnya “AB1234”) cocok sempurna dalam mode ASCII, sering menghasilkan matriks 12 × 12.

## Cara menghasilkan DataMatrix Mode (Auto)
Mode Auto memungkinkan Aspose.BarCode menganalisis input dan secara otomatis memilih enkoding paling efisien (ASCII, C40, Text, X12, atau Bytes). `DataMatrixEncodeMode.Auto` mengaktifkan fitur pemilihan otomatis ini.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Perpustakaan mengevaluasi payload, memilih mode optimal, dan merender barcode dalam satu langkah.

### Manfaat
Mode Auto mengurangi upaya pengembangan dan menjamin simbol sekecil mungkin untuk data campuran, meningkatkan kecepatan pemindaian.

## Cara menggunakan mode enkoding DataMatrix (Bytes)
Mode Bytes dirancang untuk data biner, seperti payload terenkripsi atau file terkompresi. `DataMatrixEncodeMode.Bytes` menginstruksikan generator memperlakukan setiap byte sebagai data mentah.  

**Jawaban langsung:** Gunakan `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` dan berikan string Base64‑encoded sebagai `CodeText`. Enkoder memperlakukan setiap byte sebagai data mentah, mempertahankan representasi biner yang tepat.

### Kasus penggunaan
Menyematkan GUID 128‑bit atau token terenkripsi kecil langsung ke dalam simbol DataMatrix.

## Cara menguasai mode enkoding DataMatrix (C40)
Mode C40 mengompresi data alfanumerik huruf kapital, mencapai pengurangan ukuran hingga **40 %** dibandingkan ASCII. `DataMatrixEncodeMode.C40` mengaktifkan algoritma kompresi ini.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` dan berikan string huruf kapital (misalnya “HELLO WORLD”). Mesin mengemas tiga karakter menjadi dua codeword, memperkecil matriks akhir.

### Tips pro
C40 bekerja paling baik ketika payload sebagian besar terdiri dari huruf kapital, angka, dan spasi. Untuk campuran huruf besar‑kecil, pertimbangkan mode Auto.

## Cara mengkonfigurasi teks kode DataMatrix
Properti `CodeText` menentukan data tepat yang disimpan dalam barcode. Bisa berisi teks biasa, string numerik, atau bahkan payload XML. `CodeText` adalah properti string utama pada `BarCodeGenerator` yang menyimpan payload barcode.  

**Jawaban langsung:** Tetapkan `generator.Parameters.Barcode.CodeText = "YourDataHere"` sebelum rendering. Properti ini menerima string UTF‑8 apa pun hingga panjang maksimum yang didukung oleh mode ECC yang dipilih.

### Tips lanjutan
Gabungkan `CodeText` dengan `ExtendedDataMatrix` untuk menyematkan metadata tambahan tanpa meningkatkan ukuran matriks yang terlihat.

## Cara menguasai konfigurasi macro DataMatrix
Mode macro (Macro 05 dan Macro 06) memungkinkan Anda menyematkan simbol DataMatrix sekunder di dalam simbol utama, berguna untuk menautkan ke sumber data eksternal. `DataMatrixMacroMode.Macro05` dan `DataMatrixMacroMode.Macro06` mengaktifkan fitur macro ini.  

**Jawaban langsung:** Aktifkan mode macro dengan `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (atau `Macro06`) dan atur properti `MacroPdf417` untuk payload sekunder. Generator membuat simbol komposit yang dapat diinterpretasikan pemindai sebagai dua kode terhubung.

### Contoh dunia nyata
Menyematkan URL pada bagian macro sambil mempertahankan pengidentifikasi produk pada matriks utama, memungkinkan integrasi web‑to‑barcode yang mulus.

*Daftar Tutorial Aspose.BarCode untuk .NET*

## Tutorial Konfigurasi Barcode DataMatrix
### [Menyesuaikan Rasio Aspek DataMatrix](./datamatrix-aspect-ratio-customization/)
Pelajari cara menyesuaikan rasio aspek barcode DataMatrix menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk pembuatan barcode.
### [Menghasilkan Barcode DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Buat barcode DataMatrix ECC 000-140 dengan mudah menggunakan Aspose.BarCode untuk .NET. Tingkatkan efisiensi dalam manajemen inventaris dan lainnya.
### [Menghasilkan Barcode DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Pelajari cara menghasilkan barcode DataMatrix ECC 200 di .NET menggunakan Aspose.BarCode. Sederhanakan operasi dengan pembuatan barcode yang efisien.
### [Menguasai Enkoding DataMatrix dalam ASCII](./datamatrix-encoding-mode-ascii/)
Pelajari cara membuat barcode DataMatrix dalam mode ASCII menggunakan Aspose.BarCode untuk .NET. Panduan langkah demi langkah untuk pengembang.
### [Menghasilkan DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
Pelajari cara menghasilkan DataMatrix Mode (Auto) dengan Aspose.BarCode untuk .NET. Panduan langkah demi langkah ini mencakup semua hal mulai dari prasyarat hingga pembacaan barcode.
### [Mode Enkoding DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Pelajari cara mengenkripsi data dalam format DataMatrix menggunakan mode Bytes dengan Aspose.BarCode untuk .NET. Ikuti panduan langkah demi langkah kami untuk pembuatan dan pengenalan barcode.
### [Menguasai Mode Enkoding DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Pelajari Mode Enkoding DataMatrix (C40) dengan Aspose.BarCode untuk .NET. Buat barcode khusus secara efisien. Jelajahi panduan langkah demi langkah.
### [Mengkonfigurasi Teks Kode DataMatrix](./datamatrix-extended-code-text-configuration/)
Pelajari cara mengkonfigurasi teks kode DataMatrix yang diperluas menggunakan Aspose.BarCode untuk .NET. Hasilkan, kenali, dan integrasikan barcode dalam aplikasi .NET Anda.
### [Menguasai Konfigurasi Macro DataMatrix](./datamatrix-macro-configuration/)
Pelajari cara mengkonfigurasi barcode Macro DataMatrix dengan Aspose.BarCode untuk .NET. Hasilkan, sesuaikan, dan kenali barcode DataMatrix dalam aplikasi .NET Anda.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana saya memutuskan mode ECC mana yang akan digunakan?**  
**A:** Pilih ECC 000‑140 untuk set data kecil dengan koreksi‑error terbatas, atau ECC 200 untuk data yang lebih besar dan keandalan lebih tinggi. Mode macro menambahkan lapisan data ekstra untuk penautan.

**Q: Bisakah saya menyematkan teks khusus dalam barcode DataMatrix?**  
**A:** Ya, atur properti `CodeText` ke string khusus Anda, lalu pilih mode enkoding yang sesuai (ASCII, C40, dll.) untuk mengontrol ukuran.

**Q: Apakah ada cara untuk secara otomatis memilih mode enkoding terbaik?**  
**A:** Set `EncodeMode` ke `Auto`; Aspose.BarCode akan mengevaluasi payload dan secara otomatis memilih mode paling efisien secara ruang.

**Q: Apa pertimbangan kinerja untuk batch barcode besar?**  
**A:** Gunakan satu instance `BarCodeGenerator`, aktifkan multi‑threading, dan hasilkan gambar PNG untuk kualitas lossless atau JPEG untuk ukuran file lebih kecil. Memproses 10 000 simbol biasanya selesai dalam kurang dari 30 detik pada server standar 8‑core.

**Q: Apakah Aspose.BarCode mendukung .NET Core dan .NET 5/6?**  
**A:** Tentu saja – perpustakaan ini sepenuhnya kompatibel dengan .NET Framework, .NET Core, dan rilis .NET terbaru, menawarkan set fitur yang sama di semua platform.

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Tutorial Terkait

- [Cara Menghasilkan Barcode DataMatrix (ECC 200) dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Menguasai Enkoding DataMatrix dalam ASCII dengan Aspose.BarCode untuk .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Buat Barcode PNG – Rasio Aspek DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}