---
category: general
date: 2026-09-29
description: C# kullanarak bir GS1 DataBar Omni‑Directional barkodunun genişliğini
  nasıl ayarlayacağınız ve yüksekliğini nasıl değiştireceğiniz. Tam kodlu adım adım
  rehberi izleyin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: tr
lastmod: 2026-09-29
og_description: C#'ta bir GS1 DataBar Omni‑Directional barkodunun genişliğini nasıl
  ayarlayacağınızı ve yüksekliğini nasıl değiştireceğinizi öğrenin. Tam API çağrılarını
  öğrenin ve çalışan bir örnek görün.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: GS1 DataBar barkodunun genişliğini ayarlama – C# rehberi
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: C#'ta GS1 DataBar Omni‑Directional barkodunun genişliğini ayarlama ve yüksekliğini
  düzenleme
url: /tr/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataBar Omni‑Directional barkodunun genişliğini ayarlama ve yüksekliğini ayarlama C#'ta

GS1 DataBar Omni‑Directional barkodunun genişliğini ayarlama, tarama ekipmanları için tam boyutlandırma gerektiğinde sıkça yapılan bir işlemdir. Bu öğreticide ayrıca **yüksekliği nasıl değiştireceğinizi** de öğrenecek ve barkodun tasarımınıza mükemmel oturmasını sağlayacaksınız. Kılavuz, proje kurulumundan tamamen çalıştırılabilir bir kod örneğine kadar tüm süreci adım adım anlatıyor.

Kapsanan konular:

* Gerekli NuGet paketi ve .NET sürümü.
* X‑dimension (modül genişliği) barkod okunabilirliği için neden önemlidir.
* **Genişliği nasıl ayarlayacağınız** ve **yüksekliği nasıl değiştireceğiniz** için kesin API çağrıları.
* Minimum modül genişliği ve yüksek çözünürlükte render gibi uç durumların ele alınması.
* Farklı bar yüksekliğiyle iki PNG dosyası üreten, kopyala‑yapıştır örneği.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

| Gereksinim | Sebep |
|------------|-------|
| .NET 6.0 SDK veya daha yeni bir sürüm | Örnek, modern C# özelliklerini kullanır ve Windows, Linux veya macOS üzerinde çalışır. |
| Visual Studio 2022 (veya herhangi bir C# IDE) | Aspose.Barcode API'si için IntelliSense sağlar. |
| **Aspose.Barcode for .NET** NuGet paketi | `BarcodeGenerator`, `EncodeTypes` ve görüntü formatı desteğini içerir. `dotnet add package Aspose.Barcode` ile kurun. |
| PNG dosyalarının kaydedileceği klasöre yazma izni | Üreteç, çıktı görüntülerini diske yazar. |

## Barkodun genişliğini ayarlama

**Genişliği nasıl ayarlayacağınız** adımı, barkod parametrelerinin `XDimension` özelliğini yapılandırarak gerçekleştirilir. `XDimension`, piksel, nokta veya milimetre cinsinden modül genişliğini (en küçük çubuk veya boşluk) temsil eder. Doğru ayarlanması, barkodun tarayıcı gereksinimlerini karşılamasını sağlar.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### X‑dimension neden önemlidir

* **Tarayıcı toleransı** – Çoğu tarayıcı minimum bir modül genişliği bekler; çok küçük bir değer okuma hatalarına yol açabilir.
* **Baskı çözünürlüğü** – 300 dpi'de 2 px modül yaklaşık 0.17 mm'ye denk gelir ve bu, GS1 DataBar için önerilen aralık içindedir.
* **Görüntü boyutu** – Daha büyük X‑dimension değerleri barkodun toplam genişliğini artırır, bu da yerleşim kısıtlamalarını etkileyebilir.

### Güvenilir genişlik ayarları için ipuçları

* **XDimension'ı 1 px'in altına asla ayarlamayın** – kütüphane değeri sınırlasa da ortaya çıkan barkod okunamaz olabilir.
* **Hedef DPI ile eşleştirin** – yüksek çözünürlüklü bir formata (ör. 600 dpi TIFF) render ediyorsanız, XDimension'ı orantılı olarak artırın.
* **Gerçek bir tarayıcıyla test edin** – genişliği değiştirdikten sonra, barkodu okuyacak cihazda doğrulayın.

## Barkodun yüksekliğini değiştirme

Genişlik tanımlandıktan sonra, dikey boyutu `BarHeight` özelliğiyle kontrol edebilirsiniz. Aşağıdaki kod, **yüksekliği 30 px'den 60 px'e nasıl değiştireceğinizi** gösterir ve iki ayrı görüntüyü kaydeder.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Bar yüksekliğini anlamak

* **Görsel denge** – Daha uzun çubuklar düşük kontrastlı arka planlarda okunabilirliği artırır ancak görüntünün dikey alanını genişletir.
* **Regülasyon limitleri** – Bazı standartlar (ör. perakende etiketleme) maksimum bar yüksekliği belirler; buna göre ayarlayın.
* **En‑boy oranı** – Yüksekliği değiştirmek modül genişliğini etkilemez; ikisini bağımsız olarak ince ayar yapabilirsiniz.

### Yükseklik ayarları için uç durum yönetimi

| Durum | Önerilen yaklaşım |
|-------|-------------------|
| Yükseklik < 10 px | En az 10 px'e yükseltin; çok kısa çubuklar tarayıcılar tarafından göz ardı edilebilir. |
| Çok yüksek çubuklar (≥ 100 px) | Çıktı ortamının (kağıt, etiket) ekstra alanı kaldırabileceğini doğrulayın. |
| Orantılı ölçekleme ihtiyacı | Görsel tutarlılığı korumak için `BarHeight = XDimension * istenenOran` hesaplayın. |

## Tam, çalıştırılabilir örnek

Aşağıda, **genişliği nasıl ayarlayacağınız** ve **yüksekliği nasıl değiştireceğiniz** adımlarını birleştiren tam program yer almaktadır. Kodu yeni bir console projesine kopyalayın, Aspose.Barcode NuGet paketini restore edin ve çalıştırın. `bin/Debug/net6.0` klasöründe iki PNG dosyası oluşacaktır.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Beklenen çıktı**

Programı çalıştırdığınızda iki PNG dosyası üretilir:

* `DatabarBarHeight30Pixels.png` – 30 px yüksekliğinde, 2 px genişliğinde modüllere sahip bir barkod.
* `DatabarBarHeight60Pixels.png` – aynı barkod, dikey boyutu iki katına çıkarılmış.

Her iki görüntüyü de herhangi bir görüntüleyicide açın; temiz bir GS1 DataBar Omni‑Directional sembolü göreceksiniz ve taramaya hazır olacaktır.

## Sık sorulan sorular

| Soru | Cevap |
|------|-------|
| *Milimetre cinsinden ayarlama yapabilir miyim?* | Evet. `generator.Parameters.Barcode.XDimension.Millimeters` ve `BarHeight.Millimeters` değerlerini ayarlayın. Kütüphane, görüntünün DPI'sına göre piksele dönüştürür. |
| *Farklı bir barkod türüne ihtiyacım olursa?* | `EncodeTypes.DatabarOmniDirectional` yerine istediğiniz başka bir `EncodeTypes` değerini (ör. `EncodeTypes.QR`) kullanın. Genişlik ve yükseklik özellikleri aynı şekilde çalışır. |
| *PNG yerine SVG üretmek mümkün mü?* | `Save` çağrısında `BarCodeImageFormat.Svg` kullanın. Genişlik/yükseklik ayarları aynı kalır. |
| *`generator.Dispose()` çağırmam gerekiyor mu?* | `BarcodeGenerator` `IDisposable` uygular. Konsol uygulamasında `using` bloğu içinde kullanabilirsiniz; kısa ömürlü örneklerde isteğe bağlıdır. |

## Sonuç

Artık Aspose.Barcode API'sını C# ile kullanarak **GS1 DataBar Omni‑Directional barkodunun genişliğini nasıl ayarlayacağınızı** ve **yüksekliğini nasıl değiştireceğinizi** biliyorsunuz. Tam örnek, bir üreteç oluşturmayı, `XDimension` ve `BarHeight` ayarlarını yapılandırmayı ve farklı dikey boyutlarda PNG dosyaları kaydetmeyi gösteriyor.

Bundan sonra şunları yapabilirsiniz:

* Diğer `EncodeTypes` (ör. QR, Code128) ile deneyler yapın.
* Baskı için TIFF gibi yüksek çözünürlükte formatlarda render edin.
* Üreteci, anlık barkod döndüren bir web API'sine entegre edin.

İyi kodlamalar, ve barkodlarınız her zaman sorunsuz taransın!

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ve ilgili konuları derinlemesine ele alan kaynaklardır. Her biri, tam çalışan kod örnekleri ve adım adım açıklamalar içerir; böylece API özelliklerini daha iyi kavrayabilir ve projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [C#’ta Barkod Yüksekliğini Değiştirme – Tam Kılavuz](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [C#’ta Barkod Üreteci Örneği – Genişlik ve Yükseklik Ayarı](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [C# ile DataBar Omni‑directional barkod oluşturmak için barkod üreteci kullanma](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}