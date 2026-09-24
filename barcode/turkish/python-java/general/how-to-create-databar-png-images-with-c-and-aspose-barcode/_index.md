---
category: general
date: 2026-08-19
description: Aspose.BarCode ile C#'ta databar PNG dosyaları oluşturun. Databar görüntülerini
  nasıl oluşturacağınızı, databar parametrelerini nasıl yapılandıracağınızı ve PNG
  çıktısını nasıl kaydedeceğinizi öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: tr
lastmod: 2026-08-19
og_description: Aspose.BarCode kullanarak C#'ta databar PNG dosyaları oluşturun. Bu
  öğretici, databar görüntülerini nasıl oluşturacağınızı, X‑boyutu ve en‑boy oranı
  gibi databar parametrelerini nasıl yapılandıracağınızı ve baskı veya web kullanımı
  için yüksek kaliteli PNG dosyalarını nasıl kaydedeceğinizi adım adım gösterir.
og_image_alt: create databar PNG example
og_title: C#'ta databar PNG görüntüleri oluşturma – adım adım rehber
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: C# ve Aspose.BarCode ile databar PNG görüntüleri nasıl oluşturulur
url: /tr/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# ve Aspose.BarCode ile databar PNG görüntüleri nasıl oluşturulur

Bir .NET uygulamasında **databar PNG** dosyaları oluşturmanız gerekiyorsa, bu kılavuz tam olarak nasıl yapılacağını gösterir. Yığılmış çok yönlü DataBar kodları üreten, ana parametreleri yapılandıran ve farklı en‑boy oranlarına sahip iki PNG dosyasını kaydeden eksiksiz, çalıştırılabilir bir örnek göreceksiniz.

Bir DataBar görüntüsü oluşturmak yalnızca tek bir yöntemi çağırmakla sınırlı değildir. Baskı veya tarama gereksinimlerini karşılamak için X‑boyutu (modül genişliği) ve en‑boy oranı gibi **databar parametrelerini yapılandırmanız** gerekir. Bu öğreticinin sonunda **databar** grafiklerini gerçek dünya senaryolarında güvenilir şekilde nasıl üreteceğinizi anlayacaksınız.

## Önkoşullar

- .NET 6.0 veya üzeri (kod .NET Framework 4.7+ ile de çalışır)
- Visual Studio 2022 veya herhangi bir C# uyumlu IDE
- **Aspose.BarCode for .NET** için geçerli bir lisans (ücretsiz değerlendirme testi için yeterlidir)
- C# sözdizimi hakkında temel bilgi

> **Pro tip:** Henüz lisansınız yoksa, Aspose portalından geçici bir değerlendirme anahtarı talep edebilirsiniz. API aynı şekilde çalışır; sadece filigran değişir.

## Adım 1: Aspose.BarCode NuGet paketini yükleyin

Projenizi Visual Studio’da açın, çözüme sağ‑tıklayın ve **Manage NuGet Packages** seçeneğini seçin. `Aspose.BarCode` paketini aratın ve en son kararlı sürümü yükleyin.

```bash
dotnet add package Aspose.BarCode
```

Bu komut `Aspose.BarCode` derlemesini projenize ekler ve `BarcodeGenerator` sınıfını kullanılabilir hâle getirir.

## Adım 2: Yığılmış çok yönlü DataBar için barkod üreteci başlatın

`BarcodeGenerator` yapıcı metodu iki argüman alır: barkod tipi ve ham veri dizesi. Yığılmış çok yönlü DataBar için `EncodeTypes.DatabarStackedOmniDirectional` kullanırsınız.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Neden önemli:** `EncodeTypes.DatabarStackedOmniDirectional` sabiti, kütüphaneye herhangi bir yönden okunabilen bir barkod üretmesini söyler; bu, perakende raf etiketleri için idealdir.

## Adım 3: X‑boyutunu (modül genişliğini) piksel olarak yapılandırın

X‑boyutu, en küçük çubuk elemanının boyutunu kontrol eder. Piksel cinsinden ayarlamak, son görüntü boyutu üzerinde kesin kontrol sağlar.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**2 piksel** değeri, çoğu etiket yazıcısı için okunabilirlik ve kompaktlık arasında iyi bir denge sunar. Daha büyük veya daha küçük modüllere ihtiyacınız varsa bu değeri ayarlayın.

## Adım 4: İlk en‑boy oranını ayarlayın ve PNG olarak kaydedin

En‑boy oranı, yığılmış DataBar’ın yüksekliğini etkiler. **15** en‑boy oranı nispeten kısa bir barkod üretirken, **30** daha uzun bir barkod oluşturur.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` metodu, oluşturulan barkodu bir PNG dosyasına yazar. PNG kayıpsızdır, bu da barkod tarayıcıları için gerekli keskin kenarların korunmasını sağlar.

## Adım 5: En‑boy oranını değiştirin ve ikinci bir PNG kaydedin

Aynı `BarcodeGenerator` örneğini yeniden kullanarak sadece en‑boy oranını değiştirerek farklı varyasyonlar üretebilirsiniz.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Artık iki PNG dosyanız var—`DatabarAspectRatio15.png` ve `DatabarAspectRatio30.png`—her biri farklı bir görsel yoğunluğa sahip.

## Adım 6: Çıktıyı doğrulayın

Oluşturulan PNG dosyalarını herhangi bir görüntüleyicide açın. Temiz, yüksek kontrastlı bir DataBar barkodu görmelisiniz. Akıllı telefon barkod tarayıcısıyla görüntüleri taradığınızda, her iki en‑boy oranının da orijinal GTIN değeri `12345678901231`i çözdüğünü doğrulayabilirsiniz.

![create databar PNG example](databar_example.png)

*Yukarıdaki görüntü, iki PNG dosyasını yan yana gösterir. Sol görüntü en‑boy oranı 15, sağ görüntü en‑boy oranı 30 kullanır.*

## Yaygın varyasyonlar ve kenar durumları

| Senaryo | Ne değiştirilmeli | Nedeni |
|----------|-------------------|--------|
| **Farklı veri** | `(01)12345678901231` dizesini geçerli bir GS1 Uygulama Tanımlayıcısı ve veri ile değiştirin | Ürün kimlikleri, seri numaraları vb. kodlamanızı sağlar |
| **Daha yüksek çözünürlük** | `XDimension.Pixels` değerini 3 veya 4’e yükseltin | Barkod büyük boyutlarda basılacak ya da uzaktan taranacaksa gerekir |
| **Diğer DataBar tipleri** | `EncodeTypes.DatabarStacked` veya `EncodeTypes.DatabarExpanded` kullanın | Etiket düzeninize en uygun tipi seçin |
| **Şeffaf arka plan** | `BarCodeImageFormat.Png` ile `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` geçirin | Barkodu renkli etiketlerin üzerine bindirirken faydalıdır |

> **Dikkat edilmesi gereken:** Çok küçük bir X‑boyutu (< 1 piksel) ayarlamak, barkodun bulanık görünmesine neden olabilir.

## Sonra Ne Öğrenmelisiniz?


Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanız ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmeniz için adım‑adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}