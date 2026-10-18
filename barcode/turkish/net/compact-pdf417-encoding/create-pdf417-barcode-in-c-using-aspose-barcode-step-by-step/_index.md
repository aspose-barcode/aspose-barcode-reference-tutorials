---
category: general
date: 2026-10-18
description: Aspose.BarCode ile C#'ta PDF417 barkod oluşturmayı öğrenin. Bu öğreticide
  temel, kompakt, makro ve mikro PDF417 üretimi tam kod ile ele alınmaktadır.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: tr
lastmod: 2026-10-18
og_description: Aspose.BarCode ile C#'ta PDF417 barkod oluşturun. Temel, kompakt,
  makro ve mikro PDF417 barkodları adım adım oluşturmak için bu kılavuzu izleyin.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: C#'ta PDF417 barkod oluşturma – tam Aspose.BarCode öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Aspose.BarCode kullanarak C#'ta PDF417 barkod oluşturma – adım adım rehber
url: /tr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# ile PDF417 barkod oluşturma – Aspose.BarCode kullanarak adım adım rehber

Eğer bir .NET uygulamasında **PDF417 barkod oluşturmanız** gerekiyorsa, bu öğretici size sürecin tamamını gösterir. Temel bir barkod nasıl oluşturulur, sıkıştırılmış (compact) mod nasıl etkinleştirilir, makro meta verileri nasıl eklenir ve mikro bir varyant nasıl üretilir – hepsini net açıklamalar ve çalıştırılabilir kodlarla öğreneceksiniz.

PDF417 barkodları lojistik, biletleme ve belge yönetiminde yaygın olarak kullanılır. Bu rehberin sonunda, dış araçlar kullanmadan herhangi bir C# projesine barkod oluşturma işlevi ekleyebileceksiniz.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

* .NET 6.0 veya daha yeni bir sürüm (kod .NET Framework 4.7+ ile de çalışır)
* Visual Studio 2022 veya herhangi bir C# IDE
* **Aspose.BarCode for .NET** NuGet paketi  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Oluşturulan PNG dosyalarının kaydedileceği klasöre yazma izni

Ek bir yapılandırma gerekmez; kütüphane tüm düşük‑seviye kodlama detaylarını halleder.

## Adım 1: Temel bir PDF417 barkod oluşturma

İlk adım, özel boyut ve sütun sayısı ile normal bir PDF417 barkod oluşturur.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Bu ayarların önemi**

* `XDimension.Pixels`, her barkod elemanının fiziksel boyutunu kontrol eder. 2 değeri, çoğu ekran ve yazıcıda net bir görüntü üretir.
* `Pdf417.Columns`, barkodun içerdiği veri sütun sayısını belirler. Daha az sütun genişliği azaltır; daha çok sütun veri kapasitesini artırır.

Kod çalıştırıldığında `Pdf417Basic.png` oluşturulur; bu dosya sağ tarafta tam bir meta veri sütunu bulunan tipik bir PDF417 sembolünü gösterir.

## Adım 2: Sıkıştırılmış (kısaltılmış) modu etkinleştirme

Sıkıştırılmış mod, sağ‑el meta veri sütununu kaldırarak barkodu daha dar hâle getirir. Alan sınırlı olduğunda, ancak verinin kalan satırlardan yeniden oluşturulabileceği durumlarda faydalıdır.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Neden kısaltılır?**  
`Truncate` `true` olduğunda, üretici hata düzeltme ve dosya‑seviyesi meta verileri tutan isteğe bağlı sağ‑el sütununu atar. Sonuçta barkod daha az sütun kaplar ve hâlâ çoğu PDF417 okuyucu tarafından taranabilir.

## Adım 3: Dosya‑seviyesi meta verili bir Macro PDF417 barkodu oluşturma

Macro PDF417, standart formatı segment tanımlayıcılarıyla genişleterek büyük bir belgenin birden fazla barkoda bölünmesini sağlar. Uzun metinler veya çok sayfalı dosyalar kodlamak için kullanışlıdır.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Macro alanlarının açıklaması**

| Özellik | Amaç |
|----------|------|
| `MacroPdf417FileID` | Tüm dosya için benzersiz tanımlayıcı; tüm segmentler bu değeri paylaşır. |
| `MacroPdf417SegmentID` | Mevcut segmentin indeksi (1’den başlar). |
| `MacroPdf417SegmentsCount` | Tam veri setini oluşturan toplam segment sayısı. |

Macro PDF417’yi anlayan bir tarayıcı, tüm segmentleri okuyarak ve bu tanımlayıcıları kullanarak orijinal veriyi yeniden birleştirebilir.

## Adım 4: Kısa veri için Micro PDF417 barkodu oluşturma

Micro PDF417, küçük veri yükleri (en fazla 90 karakter) için tasarlanmış sıkıştırılmış bir sürümdür. Sütun aralığını 1‑4 ile sınırlar; bu da barkodu çok küçük etiketler veya sınırlı ekran alanına sahip cihazlar için uygun hâle getirir.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Micro PDF417 ne zaman kullanılır?**  
Veri yükü kısa olduğunda ve mümkün olan en küçük barkodu istiyorsanız bu varyantı tercih edin. Envanter etiketleri, erişim kartları veya ekran alanının kritik olduğu diğer senaryolar için idealdir.

## Tam çalışan örnek

Aşağıda, tek bir çalıştırmada dört barkod tipini üreten bağımsız bir konsol uygulaması yer alıyor. Kodu yeni bir C# projesine kopyalayın, `YOUR_DIRECTORY` ifadesini mevcut bir klasör yolu ile değiştirin ve çalıştırın.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Beklenen çıktı**

Program çalıştırıldığında belirtilen klasörde dört PNG dosyası oluşturulur:

* `Pdf417Basic.png` – üç sütunlu standart barkod
* `CompactPdf417.png` – aynı veri, kısaltılmış sağ‑el sütunu
* `MacroPdf417.png` – segment meta verisi içeren macro barkod
* `MicroPdf417.png` – kısa metinler için sıkıştırılmış mikro barkod

Herhangi bir görüntü görüntüleyiciyle dosyaları açtığınızda PDF417 desenlerini göreceksiniz. Bunları bir mobil barkod okuyucu (ör. ZXing, Scandit) ile taradığınızda orijinal metin dizeleri geri dönecektir.

## Yaygın sorular ve ipuçları

* **Barkod bulanık çıkarsa ne yapmalıyım?**  
  `XDimension.Pixels` değerini 3 veya 4’e yükseltin. Daha büyük modül boyutları daha yüksek çözünürlüklü görüntüler üretir, ancak dosya boyutu artar.

* **PNG yerine SVG çıktı alabilir miyim?**  
  Evet. `Save` çağrılarındaki `BarCodeImageFormat.Png` ifadesini `BarCodeImageFormat.Svg` ile değiştirin.

* **Hata‑düzeltme seviyesini manuel olarak ayarlamam gerekir mi?**  
  Aspose.BarCode optimal bir seviyeyi otomatik seçer. Özel kullanım durumları için `Pdf417.ErrorCorrectionLevel` değerini ayarlayabilirsiniz.

* **Barkodu bir PDF belgesine nasıl gömebilirim?**  
  Oluşturulan PNG veya SVG’yi bir PDF sayfasına resim öğesi olarak eklemek için `Aspose.Pdf` kullanın.

* **Kütüphane çoklu iş parçacığı (thread) güvenli mi?**  
  Her `BarcodeGenerator` örneği bağımsızdır; paylaşılan bir durum olmadan birden fazla iş parçacığında jeneratör oluşturabilirsiniz.

## Sonuç

Artık Aspose.BarCode kullanarak C#’ta **PDF417 barkod oluşturmayı**, temel, sıkıştırılmış, macro ve mikro varyantları kapsayacak şekilde biliyorsunuz.

## Bir Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak ilgili konuları ayrıntılı bir şekilde ele alır. Her kaynak, adım adım açıklamalar ve tam çalışan kod örnekleri içerir; böylece ek API özelliklerini kavrayabilir ve projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}