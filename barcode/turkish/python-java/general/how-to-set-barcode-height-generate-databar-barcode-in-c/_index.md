---
category: general
date: 2026-10-12
description: Aspose.BarCode kullanarak C#'ta barkod yüksekliğini nasıl ayarlayacağınız
  ve DataBar barkodu nasıl oluşturacağınız. Tam kod içeren adım adım bir kılavuzu
  izleyin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: tr
lastmod: 2026-10-12
og_description: C#'ta barkod yüksekliğini nasıl ayarlayacağınızı ve Aspose.BarCode
  ile DataBar barkodu nasıl oluşturacağınızı öğrenin. Tam kodu, her adımın neden önemli
  olduğunu ve barkod yüksekliğini nasıl değiştireceğinizi keşfedin.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: C#'ta barkod yüksekliğini ayarlama ve DataBar barkodu oluşturma
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barkod yüksekliğini nasıl ayarlarsınız, C#'ta DataBar barkodu nasıl oluşturulur
url: /tr/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barkod yüksekliğini ayarlama, C#'ta DataBar barkodu oluşturma

Programmatically barkod boyutlarını **how to set barcode** ayarlamanız gerekiyorsa, bu kılavuz size tam adımları gösterir. DataBar Omni‑directional barkodu nasıl oluşturacağınızı, yüksekliğini nasıl ayarlayacağınızı ve her iki versiyonu da PNG dosyaları olarak nasıl kaydedeceğinizi öğreneceksiniz.

Barkodun çubuk yüksekliğini değiştirmek, barkodları makbuzlara, ürün etiketlerine veya mobil ekranlara entegre ettiğinizde yaygın bir gereksinimdir. Aşağıdaki örnek, GS1 DataBar sembollerinin tam yelpazesini destekleyen Aspose.BarCode kütüphanesini kullanır.

## Öğrenecekleriniz

* **how to set barcode** yüksekliğini bir DataBar Omni‑directional barkod için  
* **generate barcode c#** kodu, farklı yüksekliklerde iki görüntü oluşturur  
* **how to create databar** sembollerini anlayın ve çubuk yüksekliğinin neden önemli olduğunu öğrenin  
* **change barcode height** mantığını, oluşturucuyu yeniden yaratmadan uygulayın  

Aspose.BarCode NuGet paketi ve .NET 6+ çalışma zamanı dışında dış araçlara gerek yoktur.

## Önkoşullar

* .NET 6 SDK veya daha yeni bir sürüm yüklü  
* Visual Studio 2022 (veya herhangi bir C# editörü)  
* Aspose.BarCode for .NET – `dotnet add package Aspose.BarCode` komutuyla kurun  

> **Pro tip:** Eğer ticari bir anahtarınız yoksa Aspose'tan ücretsiz deneme lisansını kullanın; API aynı şekilde çalışır.

## Adım 1: Aspose.BarCode paketini kurun

Proje klasörünüzde bir terminal açın ve şu komutu çalıştırın:

```bash
dotnet add package Aspose.BarCode
```

Paket, `Aspose.BarCode` ad alanını ekler; bu ad alanı, **generate barcode c#** görüntülerini oluşturmak için kullanacağımız `BarcodeGenerator` sınıfını içerir.

## Adım 2: Bir DataBar barkod oluşturucu oluşturun

**how to set barcode** parametreleri için ilk somut adım, istenen semboloji ve veri dizesiyle `BarcodeGenerator` örneği oluşturmaktır.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` produces a compact, omnidirectional DataBar that can be scanned from any angle—ideal for small labels.

## Adım 3: Ortak barkod parametrelerini ayarlayın (ilk çubuk yüksekliği dahil)

Şimdi, ilk görüntüyü kaydetmeden önce **how to set barcode** X‑dimension ve çubuk yüksekliğini ayarlıyoruz.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension, her bir çubuğun toplam genişliğini kontrol eder; 2 piksel ayarı, çoğu ekranda okunabilir, net bir görüntü sağlar. Daha sonra yapılacak **change barcode height** adımı aynı oluşturucuyu yeniden kullanacak, zaman ve bellek tasarrufu sağlayacaktır.

## Adım 4: İlk barkod görüntüsünü kaydedin (30‑piksel yükseklik)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

`DatabarHeight30.png` dosyası artık 30‑piksel çubuk yüksekliğine sahip bir DataBar barkodu içeriyor.

## Adım 5: Sadece çubuk yüksekliğini 60 piksele değiştirin

**change barcode height** göstermek için sadece `BarHeight` özelliğini değiştiriyoruz. Diğer tüm ayarlar aynı kalır; bu, tek bir oluşturucudan birden fazla boyut üretmenin en verimli yoludur.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Adım 6: İkinci barkod görüntüsünü kaydedin (60‑piksel yükseklik)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Artık iki PNG dosyanız var; her biri farklı çubuk yüksekliğine sahip ancak veri ve X‑dimension aynı.

## Tam, çalıştırılabilir örnek

Aşağıda, yeni bir konsol uygulamasına (`dotnet new console`) kopyalayıp yapıştırabileceğiniz ve hemen çalıştırabileceğiniz tam program bulunmaktadır.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Beklenen çıktı

Programı çalıştırmak, çalıştırılabilir dosyanın çalışma dizininde iki dosya oluşturur:

* `DatabarHeight30.png` – 30‑piksel yüksekliğinde çubuklara sahip bir DataBar barkodu.  
* `DatabarHeight60.png` – aynı barkod, ancak her çubuk iki kat daha uzun.

Her iki görüntü de herhangi bir görüntü görüntüleyicide açılabilir veya doğrudan PDF'lere, HTML sayfalara ya da basılı etiketlere yerleştirilebilir.

## Çubuk yüksekliğini ayarlamanın önemi

* **Scanning reliability:** Bazı tarayıcılar düşük çözünürlüklü medyada çok kısa çubuklarla zorlanır; yüksekliği artırmak algılamayı iyileştirir.  
* **Design constraints:** Bir mobil uygulama kompakt bir barkod (30 px) gerektirebilir, oysa bir basılı makbuz daha büyük bir barkod (60 px) isteyebilir.  
* **Regulatory compliance:** Belirli sektörler, GS1 DataBar sembolleri için minimum çubuk yüksekliği zorunluluğu getirir.

Aynı `BarcodeGenerator` örneğini yeniden kullanarak, veri dizesini yeniden ayrıştırma yükünden kaçınırsınız; bu, yüksek verimli ortamlarda özellikle faydalıdır.

## Yaygın varyasyonlar ve uç durumlar

| Durum | Önerilen ayar |
|-----------|-------------------|
| Farklı bir X‑dimension gerekir | İlk `Save` işleminden önce `XDimension.Pixels` değerini değiştirin. |
| Farklı bir semboloji isteniyor (ör. DataBar Stacked) | `BarcodeGenerator` oluştururken `EncodeTypes.DatabarStacked` kullanın. |
| Barkodu bir PDF'e gömmek gerekiyor | `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` kullanın ve akışı bir PDF kütüphanesine ekleyin. |
| .NET Framework 4.6 üzerinde çalıştırma | Aynı kod çalışır; sadece uygun Aspose.BarCode derlemesini referans gösterin. |

## Güvenilir barkod üretimi için pro ipuçları

* **Cache the generator** aynı veri ancak farklı boyutlarda birçok barkod oluşturduğunuzda  
* **

## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Aspose.BarCode for .NET kullanarak Tek Boyutlu Databar için Barkod Yüksekliğini Oluşturma ve Ayarlama](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [C# ve Aspose.BarCode ile databar PNG görüntüleri oluşturma](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [C#'ta barkodu özel boyutta oluşturma ve görüntüyü kaydetme](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}