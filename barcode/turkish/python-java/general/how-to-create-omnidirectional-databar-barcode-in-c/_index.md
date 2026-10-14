---
category: general
date: 2026-09-29
description: C# ve Aspose.BarCode ile çok yönlü Databar barkodu oluşturmayı öğrenin.
  X‑boyutunu ayarlayın, en‑boy oranını belirleyin ve PNG görüntülerini kaydedin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: tr
lastmod: 2026-09-29
og_description: Aspose.BarCode kullanarak C#'ta çok yönlü Databar barkod oluşturun.
  X‑boyutunu ayarlamayı, en‑boy oranını düzenlemeyi ve PNG dosyalarını dışa aktarmayı
  öğrenin.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: C# ile çok yönlü Databar barkodu oluşturma – adım adım rehber
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C#'ta çok yönlü Databar barkodu nasıl oluşturulur
url: /tr/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta çok yönlü Databar barkod nasıl oluşturulur

Bir .NET uygulamasında **çok yönlü Databar barkod oluşturmanız** gerekiyorsa, bu kılavuz size tam adımları gösterir. DataBar stacked omnidirectional barkodu nasıl başlatacağınızı, X‑boyutunu nasıl yapılandıracağınızı, en‑boy oranını nasıl değiştireceğinizi ve Aspose.BarCode ile PNG görüntülerini nasıl oluşturacağınızı göreceksiniz.

**DataBar stacked omnidirectional barkod** oluşturmak, perakende tarayıcıları için ürün tanımlayıcılarını kodlamanız gerektiğinde yaygındır. Bu öğreticide **barkod en‑boy oranını ayarlamayı**, modül boyutunu kontrol etmeyi ve sonucu IDE'den çıkmadan dışa aktarmayı öğreneceksiniz.

## Önkoşullar

- .NET 6.0 veya daha yeni bir sürüm yüklü
- Visual Studio 2022 (veya C# uyumlu herhangi bir IDE)
- **Aspose.BarCode for .NET** NuGet paketi (sürüm 23.12 veya daha yeni)

Paketi NuGet Package Manager üzerinden ekleyebilirsiniz:

```bash
dotnet add package Aspose.BarCode
```

## Adım 1: Çok yönlü Databar barkodu başlatma

İlk adım, **DataBar stacked omnidirectional** sembolojisini hedefleyen bir `BarcodeGenerator` örneği oluşturmaktır. Yapıcı, kodlama türünü ve veri dizesini alır.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Neden önemlidir:** `EncodeTypes.DatabarStackedOmniDirectional` değeri, Aspose.BarCode'a her iki yönde de tarama için gerekli olan belirli çok yönlü Databar formatını oluşturmasını söyler.

## Adım 2: X‑boyutunu (modül boyutu) tanımlama

X‑boyut, tek bir barkod modülünün piksel cinsinden genişliğini kontrol eder. `2` piksel değeri, ekran üzerinde görüntüleme ve çoğu yazıcı için iyi çalışır.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Neden önemlidir:** Tutarlı bir X‑boyut, barkodun perakende tarayıcıları için minimum boyut gereksinimlerini karşılamasını sağlarken görüntü dosya boyutunun yönetilebilir kalmasını sağlar.

## Adım 3: İlk en‑boy oranını ayarlama ve görüntüyü kaydetme

**En‑boy oranı**, DataBar'ın yükseklik‑genişlik ilişkisini belirler. `15` en‑boy oranı, dar etiket alanları için ideal, kompakt ve yüksek bir barkod üretir.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Neden önemlidir:** En‑boy oranını ayarlamak, barkodu farklı etiket düzenlerine uyarlamanıza olanak tanır, okunabilirlikten ödün vermeden. Kaydedilen PNG, herhangi bir görüntü görüntüleyicide incelenebilir.

## Adım 4: En‑boy oranını değiştirip ikinci görüntüyü oluşturma

Bazen daha geniş bir barkod gerekir—örneğin, etiketin daha fazla yatay alanı olduğunda. Oranı `30` olarak değiştirmek daha düz bir görünüm oluşturur.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Neden önemlidir:** **set barcode aspect ratio** özelliğini ortaya çıkararak, tek bir kod tabanından birden fazla barkod varyasyonu üretebilir, otomatik etiket üretim hatlarını basitleştirebilirsiniz.

## Beklenen çıktı

Programı çalıştırdığınızda uygulamanın çıktı klasöründe iki PNG dosyası oluşur:

| Dosya adı                | En‑boy oranı | Görsel açıklama |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | Dar etiketler için uygun, yüksek, dar barkod |
| `DatabarAspectRatio30.png` | 30           | Daha geniş barkod, daha fazla yatay alanı doldurur |

Bu görüntüleri raporlara ekleyebilir, ürün ambalajına yazdırabilir veya daha ileri işleme için bir web servisine gönderebilirsiniz.

![Çok yönlü Databar barkod oluşturma örneği](databar-example.png "Çok yönlü Databar barkod oluşturma örneği")

*Ekran görüntüsü, iki oluşturulan PNG dosyasını yan yana gösterir.*

## Yaygın sorular ve uç durumlar

### Farklı bir X‑boyutuna ihtiyacım olsaydı ne olur?

`XDimension.Pixels`'a herhangi bir tam sayı değeri atayabilirsiniz. `1`'in altındaki değerler yok sayılır, `10`'un üzerindeki değerler ise yazıcı kenar boşluklarını aşan aşırı büyük modüller üretebilir. Her değişiklikten sonra görsel çıktıyı test edin.

### Diğer AI‑türetilmiş verileri (ör. UPC, EAN) nasıl kodlarım?

`BarcodeGenerator` yapıcısındaki veri dizesini uygun Application Identifier (AI) ile değiştirin. Bir UPC‑A kodu için, AI ön eki olmadan `"012345678905"` kullanın.

### PNG dışındaki formatlara dışa aktarabilir miyim?

Evet. `Save` metodu `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` ve `BarCodeImageFormat.Bmp` formatlarını kabul eder. İş akışınıza en uygun formatı seçin.

## Pro ipucu: Toplu işleme için jeneratörü yeniden kullanma

Farklı en‑boy oranlarına sahip onlarca barkod üretmeniz gerekiyorsa, `BarcodeGenerator` örneğini yaşamda tutun ve her `Save` işleminden önce sadece `DataBar.AspectRatio`'yu değiştirin. Bu, her görüntü için jeneratörü yeniden örneklemenin getirdiği yükü ortadan kaldırır.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Sonuç

Artık Aspose.BarCode kullanarak C#'ta **çok yönlü Databar barkod oluşturmayı** biliyorsunuz. Bir `BarcodeGenerator` başlatarak, X‑boyutunu ayarlayarak, **set barcode aspect ratio** özelliğini düzenleyerek ve PNG dosyalarını kaydederek, çeşitli etiket gereksinimlerini karşılayan barkod görüntüleri üretebilirsiniz.  

Sonra, QR kodları için **generate barcode image**, **DataBar stacked omnidirectional barcode** doğrulama veya oluşturulan PNG'leri Aspose.PDF ile PDF faturalarına entegre etme gibi ilgili konuları keşfedin. Farklı en‑boy oranları ve modül boyutlarıyla deney yaparak, özel baskı donanımınız için en uygun yapılandırmayı bulun.

---

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanıza ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak tam çalışan kod örnekleri ve adım‑adım açıklamalar içerir.

- [C#'ta bir barkod jeneratörü kullanarak DataBar Omni‑directional barkodları nasıl oluşturulur](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [C#'ta databar stacked omnidirectional barkod – Tam Kılavuz](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [C#'ta barkod nasıl oluşturulur – DataBar Expanded ile barkod görüntüsü oluşturma](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}