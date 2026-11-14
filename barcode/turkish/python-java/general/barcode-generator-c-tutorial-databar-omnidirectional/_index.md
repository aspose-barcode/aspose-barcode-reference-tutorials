---
category: general
date: 2026-11-14
description: DataBar Omnidirectional barkodları oluşturmayı, X‑boyutunu ayarlamayı
  ve çubuk yüksekliğini piksel cinsinden düzenlemeyi gösteren C# barkod oluşturucu
  öğreticisi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: tr
lastmod: 2026-11-14
og_description: Barcode generator C# öğreticisi, DataBar Omnidirectional barkodu nasıl
  oluşturulacağını, XDimension'ı piksel cinsinden tanımlamayı ve PNG çıktısı için
  çubuk yüksekliğini değiştirmeyi adım adım açıklar.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Barkod oluşturucu C# öğreticisi – DataBar barkodları oluşturma
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Barkod Oluşturucu C# Öğreticisi: DataBar Omnidirectional'
url: /tr/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

Eğer bir **barcode generator C# tutorial** arıyorsanız, doğru yere geldiniz. Bu kılavuz, DataBar Omnidirectional barkodu oluşturmayı, XDimension'ı piksel olarak ayarlamayı ve çubuk yüksekliğini değiştirerek PNG görüntüler üretmeyi adım adım gösterir.

Başlangıçtan sonuna kadar çalışan bir örnek göreceksiniz; jeneratörü başlatmaktan farklı çubuk yükseklikleriyle birden fazla görüntüyü kaydetmeye kadar her şey dahil. Harici bir dokümantasyona ihtiyaç yok—kodu kopyalayıp çalıştırın, iki barkod dosyanız hemen hazır olacak.

## Prerequisites

Başlamadan önce şunların yüklü olduğundan emin olun:

* .NET 6.0 veya daha yeni bir sürüm  
* `BarcodeGenerator`, `EncodeTypes` ve `BarCodeImageFormat` sağlayan barkod kütüphanesine referans (örneğin, Aspose.BarCode for .NET)  
* C# sözdizimi ve Visual Studio ya da tercih ettiğiniz IDE hakkında temel bilgi  

> **Pro tip:** Aspose.BarCode kullanıyorsanız, projenize `Aspose.BarCode` NuGet paketini ekleyin.

## Barcode generator C# tutorial – step 1: create the generator

İlk adım, `DatabarOmniDirectional` kodlama türü ve kodlamak istediğiniz veriyle bir `BarcodeGenerator` örneği oluşturmaktır.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` kütüphaneye barkodu her yönden okunabilecek şekilde üretmesini söyler; bu, perakende ambalajı ve lojistik için idealdir.

## Set XDimension pixels for the barcode

X‑dimension, barkod içindeki en küçük modülün (“piksel”) genişliğini tanımlar. Piksel cinsinden ayarlamak, barkodun görsel yoğunluğu üzerinde kesin kontrol sağlar.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* `2` piksel değeri, çoğu tarayıcı için yeterince keskin bir barkod üretirken görüntü dosya boyutunu makul tutar.

## Adjust bar height and save images

Bar yüksekliği, çubukların ne kadar uzun görüneceğini belirler. `BarHeight.Pixels` özelliğini değiştirip `Save` metodunu tekrar çağırarak farklı yüksekliklerde birden fazla görüntü oluşturabilirsiniz.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` enum değeri, çıktının kayıpsız bir PNG dosyası olmasını sağlar; bu format barkod grafikleri için önerilir çünkü tam boyutları korur.

## Change bar height to create multiple images

Aynı barkodu farklı boyutlarda kullanmanız sıkça gerekir—örneğin, bir etiket ve bir poster için. Bar yüksekliğini değiştirip aynı jeneratör örneğini yeniden kullanın:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* Bar yüksekliği çok düşük ayarlanırsa (ör. 10 px’nin altında), bazı tarayıcılar kodu okumakta zorlanabilir. Oluşturulan görüntüleri hedef tarayıcı donanımınızda mutlaka test edin.

## Full source code

Aşağıda yeni bir konsol projesine kopyalayıp yapıştırabileceğiniz tam program yer alıyor. Gerekli tüm `using` yönergelerini içerir ve hem bar‑yüksekliği varyasyonlarını hem de kaydetme işlemini gösterir.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Programı çalıştırın, `YOUR_DIRECTORY` ifadesini geçerli bir klasör yolu ile değiştirin ve iki PNG dosyası bulun:

* `DatabarBarHeight30Pixels.png` – 30 px yüksekliğinde çubuklar  
* `DatabarBarHeight60Pixels.png` – 60 px yüksekliğinde çubuklar  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Common questions

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG is preferred for lossless quality. |
| **What if I need a different XDimension?** | Adjust `generator.Parameters.Barcode.XDimension.Pixels` to any integer. Larger values increase overall barcode width. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | It is, provided the printed size meets the scanner’s minimum module size (usually 0.33 mm). The pixel‑based XDimension helps you meet that requirement. |
| **How do I embed the barcode in a PDF?** | After saving the PNG, use a PDF library (e.g., iTextSharp) to insert the image into a PDF page. |

## Conclusion

Bu **barcode generator C# tutorial**, DataBar Omnidirectional barkodu oluşturmayı, XDimension'ı piksel olarak ayarlamayı ve farklı bar yüksekliğiyle PNG dosyaları üretmeyi gösterdi. Artık barkod oluşturma ihtiyacı olan herhangi bir C# projesinde yeniden kullanılabilir bir kod parçacığınız var.

### What’s next?

* `EncodeTypes` içinde `Code128` veya `QR` gibi diğer seçenekleri keşfederek barkod yelpazenizi genişletin.  
* Oluşturulan PNG'yi bir PDF oluşturma kütüphanesiyle birleştirerek yazdırılabilir faturalar üretin.  
* `generator.Parameters.Barcode.Color` özelliğiyle tarayıcı standartlarına uygun özel renkler ekleyin.

Örneği istediğiniz gibi değiştirin, ek bar yükseklikleri deneyin veya çıktı formatını değiştirin. İyi kodlamalar!

## What Should You Learn Next?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakın konuları kapsar. Her kaynak, adım adım açıklamalar ve çalışan kod örnekleri içerir; böylece ek API özelliklerini öğrenebilir ve projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}