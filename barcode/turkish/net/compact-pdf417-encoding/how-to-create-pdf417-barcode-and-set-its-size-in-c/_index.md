---
category: general
date: 2026-09-22
description: C#'ta PDF417 barkod nasıl oluşturulur, barkod boyutu nasıl ayarlanır
  ve net adım‑adım kod örnekleriyle barkod görüntü dosyaları nasıl üretilir öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: tr
lastmod: 2026-09-22
og_description: C#'ta PDF417 barkodu hızlıca oluşturun. Bu öğreticide barkod boyutunu
  nasıl ayarlayacağınız, kompakt modu nasıl etkinleştireceğiniz ve herhangi bir .NET
  projesi için PNG görüntülerini nasıl dışa aktaracağınız gösterilmektedir.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C#'ta PDF417 barkod oluşturma – adım adım rehber
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: C#'ta PDF417 barkod nasıl oluşturulur ve boyutu nasıl ayarlanır
url: /tr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#’ta PDF417 barkod nasıl oluşturulur ve boyutu nasıl ayarlanır

Eğer C#’ta **PDF417 barkod oluşturmanız** gerekiyorsa, bu kılavuz barkodu nasıl üreteceğinizi, boyutlarını nasıl kontrol edeceğinizi ve sonucu bir görüntü dosyası olarak nasıl kaydedeceğinizi gösterir. Biletleme sistemi, lojistik etiketi ya da güvenli kimlik gibi bir uygulama geliştiriyor olun, PDF417 formatını ustalıkla kullanmak büyük miktarda veriyi kompakt bir görsel biçimde kodlamanızı sağlar.

Bu öğreticide şunları öğreneceksiniz:

* **Aspose.BarCode (veya uyumlu herhangi bir) kütüphanesi** ile **PDF417 barkod oluşturma**.  
* X‑dimension ve sütun sayısını ayarlayarak **barkod boyutunu ayarlama**.  
* PNG, JPEG veya BMP çıktısı için **C#’ta barkod resmi oluşturma**.  

Örnek, Aspose.BarCode for .NET’in ücretsiz topluluk sürümünü kullanır, ancak aynı kavramlar benzer özellikler sunan diğer kütüphanelerde de geçerlidir.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

* .NET 6.0 SDK veya daha yeni bir sürüm.  
* Bir C# IDE’si (Visual Studio, Visual Studio Code, Rider vb.).  
* `Aspose.BarCode` NuGet paketi (`dotnet add package Aspose.BarCode`).  

Ek bir yapılandırma gerekmez; kütüphane Windows, Linux ve macOS’ta çalışır.

## Adım 1: Temel bir PDF417 barkod oluşturun ve boyutunu ayarlayın

İlk adım, `EncodeTypes.Pdf417` enum’u ile bir `BarcodeGenerator` nesnesi oluşturup kodlamak istediğiniz metni vermektir. Ardından **X‑dimension** (modül genişliği) ve **sütun** sayısını ayarlayarak genel boyutu kontrol edersiniz.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Bu ayarların önemi**

* `XDimension.Pixels` en dar çubuk genişliğini belirler. Daha küçük değerler daha sıkı bir barkod üretirken, daha büyük değerler düşük çözünürlüklü tarayıcılarda okunabilirliği artırır.  
* `Pdf417.Columns` barkodun en-boy oranını etkiler. Daha az sütun barkodu daha yüksek yapar; daha çok sütun ise düzleştirir. Sütun sayısını ayarlamak, kodlanan veriyi değiştirmeden **barkod boyutunu ayarlamanın** temel yoludur.

Kodu çalıştırdıktan sonra belirtilen klasörde `Pdf417Basic.png` dosyasını bulacaksınız. Görüntü aşağıdaki ekran görüntüsüne benzer:

<img src="images/pdf417-basic.png" alt="temel barkod düzenini gösteren PDF417 barkod örneği">

## Adım 2: Aynı boyutta sıkıştırılmış PDF417 barkod (truncate modu) oluşturun

Bazen sınırlı alan için daha kısa bir barkod gerekir. PDF417, durdurma desenini kaldıran ve toplam yüksekliği azaltan bir *truncate* (sıkıştırılmış) modu sunar. Bu davranışı `Truncate` özelliği kontrol eder.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true` olduğunda ne değişir?**

* Barkod, dikey olarak yaklaşık %15‑20 daha kısa olur; bu, küçük etiketler veya mobil ekranlar için faydalıdır.  
* Veri tamamen geri getirilebilir; çoğu modern tarayıcı truncate modunu otomatik olarak anlar.

Ortaya çıkan `CompactPdf417.png`, temel barkodun daha ince bir versiyonu olarak görünür.

## Adım 3: Micro PDF417 barkod oluşturun, sütunları ayarlayın ve kaydedin

Micro PDF417, çok küçük alanlar (ör. kimlik kartları) için tasarlanmış yeni, yüksek yoğunluklu bir varyanttır. Sadece 1‑4 sütun destekler ve kütüphane aynı `XDimension` özelliğiyle boyut kontrolüne izin verir.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Micro PDF417 için önemli noktalar**

* `EncodeTypes.MicroPdf417` enum’u mikro varyantı otomatik olarak seçer.  
* Sembol daha yoğun olduğundan, barkodun okunabilirliğini korumak için daha yüksek DPI’li bir yazıcı (300 dpi veya üzeri) gerekebilir.  
* Sütun sayısını ayarlamak tek boyut kontrol düğmesidir; kütüphane yine `XDimension`’ı dikkate alır.

## Farklı çıktı formatları için barkod boyutu nasıl ayarlanır

Yukarıdaki örnekler PNG kullanıyor, ancak aynı `Save` metodu JPEG, BMP veya TIFF ile de çalışır. Belirli bir görüntü boyutu (ör. 300 × 150 px) istiyorsanız, `XDimension` ile `ResolutionX`/`ResolutionY`’yi birleştirin:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

`ImageResolution`’ı artırırken `XDimension`’ı ölçeklendirmek, yüksek çözünürlüklü baskılarda görsel kaliteyi korur.

## Yaygın hatalar ve uzman ipuçları

| Sorun | Neden oluşur | Çözüm |
|-------|--------------|------|
| Barkod ekranda bulanık görünüyor | Düşük DPI ve küçük `XDimension` | `ImageResolution` ve/veya `XDimension.Pixels` değerlerini artırın |
| Tarayıcı truncate modunu okuyamıyor | Eski tarayıcı firmware’i desteği yok | Eski donanım için tam (truncate olmayan) modu kullanın |
| Micro PDF417 okunamıyor | 300 dpi’den düşük baskı veya yetersiz kontrast | 300 dpi veya daha yüksek mat kağıt üzerinde yazdırın, koyu ön plan sağlayın |
| Çıktı dosyası bozuk | Hedef klasöre yazma izni yok | `YOUR_DIRECTORY`’nin varlığını ve yazılabilirliğini kontrol edin |

**Uzman ipucu:** Barkodu kayıpsız kalite gerektiren durumlarda (ör. PDF’e gömme) her zaman PNG olarak üretin. PNG, tam piksel değerlerini korurken JPEG sıkıştırma artefaktları ekleyerek barkod okunabilirliğini etkileyebilir.

## Tam, çalıştırılabilir örnek

Aşağıda, tek bir çalıştırmada üç barkod tipini gösteren eksiksiz bir konsol uygulaması yer alıyor. Kodu yeni bir .NET konsol projesine kopyalayıp çalıştırın.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Beklenen çıktı**

Program çalıştırıldığında `Barcodes` klasörü içinde üç PNG dosyası oluşturulur:

* `Pdf417Basic.png` – üç sütunlu standart PDF417 barkodu.  
* `CompactPdf417.png` – aynı veri, truncate (sıkıştırılmış) modda, biraz daha kısa.  
* `MicroPdf417.png` – dört sütunlu yüksek yoğunluklu Micro PDF417 varyantı.

Herhangi bir görüntü görüntüleyicide bir resmi açın; yığılmış barkodun ayırt edilebilir yapısını göreceksiniz.


## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ilgili konuları kapsar. Her kaynak, tam çalışan kod örnekleri ve adım adım açıklamalar içerir; böylece ek API özelliklerini ustalaşabilir ve projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}