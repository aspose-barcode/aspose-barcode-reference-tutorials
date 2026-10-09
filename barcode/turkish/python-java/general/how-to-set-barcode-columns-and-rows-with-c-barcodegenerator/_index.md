---
category: general
date: 2026-09-16
description: C#'ta BarcodeGenerator kullanarak barkod sütunlarını nasıl ayarlayacağınızı
  ve DataBar Expanded Stacked barkodları için barkod satırlarını nasıl ayarlayacağınızı
  öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: tr
lastmod: 2026-09-16
og_description: C#'de barkod sütunlarını hızlıca ayarlayın. Bu kılavuz, BarcodeGenerator
  ile sütunları, satırları ve görüntü formatını nasıl yapılandıracağınızı gösterir.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: C#'ta barkod sütunlarını ve satırlarını ayarlayın – tam BarcodeGenerator
  rehberi
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C# BarcodeGenerator ile barkod sütunlarını ve satırlarını nasıl ayarlarsınız
url: /tr/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# BarcodeGenerator ile barkod sütunlarını ve satırlarını nasıl ayarlarsınız

Bir C# uygulamasında barkod sütunlarını ayarlamanız gerekiyorsa, bu öğretici gerekli adımları tam olarak gösterir. DataBar Expanded Stacked barkodu için hem sütunları hem de satırları nasıl yapılandıracağınızı görecek ve sonucu bir PNG görüntüsü olarak kaydedeceksiniz.

Barkodları programlı olarak oluşturmak, manuel tasarım işinden sizi kurtarır ve raporlar, faturalar ve ürün etiketleri arasında tutarlılığı garanti eder. Aşağıdaki örnek, kütüphaneyi kurmaktan iki görüntü üretmeye (biri özel sütun sayısı, diğeri özel satır sayısı ile) kadar tam iş akışını kapsar.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

* .NET 6.0 veya daha yeni bir sürüm.
* **Aspose.BarCode for .NET** NuGet paketine referans. Şu komutla kurun:

```bash
dotnet add package Aspose.BarCode
```

* Oluşturulan PNG dosyalarının kaydedileceği klasöre yazma izni.

Bu gereksinimler, kodun ek bir yapılandırma olmadan derlenip çalışmasını sağlar.

## C#’ta barkod sütunlarını nasıl ayarlarsınız

İlk büyük adım, **DataBar Expanded Stacked** sembolojisi için bir `BarcodeGenerator` örneği oluşturmak ve istenen sütun sayısını atamaktır.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Neden bu şekilde çalışır:**  
`EncodeTypes.DatabarExpandedStacked` kütüphaneye hangi sembolojinin oluşturulacağını söyler. `Parameters.Barcode.DataBar.Columns` değerini ayarlamak, iç modül düzenini değiştirir ve bu doğrudan barkodun görsel genişliğini etkiler. `Save` yöntemi, istenen `BarCodeImageFormat` içinde görüntüyü diske yazar.

### Beklenen sonuç
`C:\Barcodes\DatabarCols4.png` dosyasını herhangi bir görüntüleyicide açın. Varsayılandan daha geniş bir DataBar Expanded Stacked barkod görmelisiniz; çünkü dört sütun kullanılmıştır.

## C#’ta barkod satırlarını nasıl ayarlarsınız

Sütun‑temelli görüntüyü kaydettikten sonra, satırları ayarlayarak yüksekliği değiştiren bir barkod isteyebilirsiniz. İşlem, sütun yapılandırmasına benzer ancak `Rows` özelliğini kullanır.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Neden bu şekilde çalışır:**  
Üreteci yeniden başlatmak, önceki sütun ayarının satır yapılandırmasını etkilemesini önler. `Parameters.Barcode.DataBar.Rows` değerini değiştirmek, barkodun yüksekliğini değiştirir; satır sayısı varsayılandan yüksek olduğunda daha uzun bir görüntü elde edilir.

### Beklenen sonuç
`C:\Barcodes\DatabarRows3.png` dosyasını açın. Barkod, üç‑satır yapılandırmasını yansıtacak şekilde daha uzun görünecektir.

## Tam uçtan uca örnek

Aşağıda, tek bir program içinde her iki görüntüyü de oluşturan kod yer alıyor. Kodu tek bir dosyada tutmak, uygulamayı yeniden başlatmadan sütun ve satır yapılandırmaları arasında nasıl geçiş yapabileceğinizi gösterir.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Programı çalıştırdığınızda iki PNG dosyası üretilir:

* **DatabarCols4.png** – dört sütunlu barkod.  
* **DatabarRows3.png** – üç satırlı barkod.

Her iki dosya da **barkod görüntü formatı** PNG kullanır; bu format keskin kenarları korur ve kayıpsız sıkıştırma sağlar—baskı ve dijital gösterim için idealdir.

## Yaygın sorular ve ipuçları

| Soru | Cevap |
|----------|--------|
| *JPEG yerine PNG kullanabilir miyim?* | Evet. `BarCodeImageFormat.Png` yerine `BarCodeImageFormat.Jpeg` yazın. JPEG daha küçüktür ancak sıkıştırma artefaktları ekler; bu da tarayıcı güvenilirliğini etkileyebilir. |
| *Maksimum sütun veya satır sayısı nedir?* | Kütüphane, değerleri DataBar spesifikasyonuna göre doğrular. İzin verilen aralığın dışındaki değerler `ArgumentException` fırlatır. Kesin limitler için Aspose.BarCode dokümantasyonuna bakın. |
| *`BarcodeGenerator` nesnesini dispose etmem gerekiyor mu?* | Sınıf `IDisposable` uygular. Döngü içinde birden çok örnek oluşturuyorsanız, kaynakları hızlıca serbest bırakmak için `using` bloğu içinde kullanın. |
| *Sütun/satır sayısını değiştirmeden barkod boyutunu nasıl değiştiririm?* | Modül düzenini bozmadan çıktıyı ölçeklemek için `barcodeGenerator.Parameters.Image.Width` ve `Height` değerlerini kullanın. |

**Pro ipucu:** Yüksek çözünürlüklü baskı için barkod üretirken, sütun veya satır sayısını artırmak yerine çıktı görüntüsü boyutlarını (`Width`/`Height`) artırın. Bu yaklaşım, sembolojinin tanımlı standart modül boyutunu korurken daha keskin bir görüntü elde etmenizi sağlar.

## Sonuç

Artık **BarcodeGenerator** sınıfını kullanarak C#’ta barkod sütunlarını ve satırlarını nasıl ayarlayacağınızı biliyorsunuz. Kılavuz, üreticiyi başlatma, sütun ve satır sayılarını yapılandırma, barkodu PNG formatında kaydetme ve görüntü formatı değişiklikleri ile kaynak yönetimi gibi yaygın varyasyonları ele aldı.

Sonraki adımda **barkod renklerini özelleştirme**, **insan‑okunur metin ekleme** ve **barkodları PDF belgelerine gömme** gibi konuları keşfedin. Bu uzantıların tümü, burada gösterilen aynı yapılandırma desenine dayanır ve .NET uygulamanız için tam özellikli barkod çözümleri oluşturmanıza olanak tanır.


## Sonraki Öğrenmeniz Gerekenler


Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım‑adım açıklamalarla tam çalışan kod örnekleri içerir.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}