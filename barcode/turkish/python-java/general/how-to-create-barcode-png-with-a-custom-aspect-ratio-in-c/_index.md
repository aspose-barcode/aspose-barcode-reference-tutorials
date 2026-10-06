---
category: general
date: 2026-10-05
description: C#'ta barkod PNG'si oluşturun ve yığılmış DataBar çok yönlü barkodlar
  için en‑boy oranını 15 olarak ayarlamayı öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: tr
lastmod: 2026-10-05
og_description: C#'ta barkod PNG'si oluşturun ve birkaç adımda yığılmış DataBar çok
  yönlü barkodlar için en‑boy oranını 15 olarak ayarlamayı keşfedin.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: C#'ta barkod PNG oluşturma – en-boy oranını 15 olarak ayarlama öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: C#'ta özel en‑boy oranına sahip barkod PNG'si nasıl oluşturulur
url: /tr/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta özel en‑boy oranı ile barkod PNG nasıl oluşturulur

C#'ta **barcode PNG** oluşturmanız gerekiyorsa, bu kılavuz size yığılmış DataBar çok yönlü barkod için **en‑boy oranını** 15 olarak nasıl ayarlayacağınızı gösterir. Her API çağrısını adım adım inceleyecek, en‑boy oranının neden önemli olduğunu açıklayacak ve herhangi bir .NET projesine ekleyebileceğiniz tam, çalıştırılabilir bir örnek sunacağız.

Barkod görüntüsü oluşturmak, envanter sistemleri, nakliye etiketleri ve perakende satış noktası uygulamaları için yaygın bir gereksinimdir. Bu öğreticinin sonunda, iş ortağınızın talep ettiği tam görsel spesifikasyonlara uyan bir PNG dosyanız olacak. Harici araçlar, manuel görüntü düzenleme yok—sadece kod.

## Önkoşullar

* .NET 6.0 veya üzeri (örnek .NET 6 kullanıyor ancak .NET 5+ ile çalışır)
* Visual Studio 2022 (veya .NET'i destekleyen herhangi bir IDE)
* **Aspose.BarCode for .NET** NuGet paketi  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* PNG dosyasını kaydetmek istediğiniz klasöre yazma izni

Bu gereksinimler minimaldir; aynı kod .NET Core, .NET Framework veya bir konsol uygulamasında çalışır.

## Aspose.BarCode ile barcode PNG oluşturma

İlk adım, doğru barkod tipini kullanarak `BarcodeGenerator` sınıfının bir örneğini oluşturmaktır. Bu örnekte `EncodeTypes.DatabarStackedOmniDirectional` kullanıyoruz; bu, herhangi bir yönden okunabilen yığılmış bir DataBar üretir.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Neden önemli:* Yapıcı iki argüman alır—**barkod sembolojisi** ve **veri dizesi**. DataBar formatı bir GS1 uygulama tanımlayıcısı bekler, bu yüzden örnek veri `(01)` ile başlar.

## Yığılmış bir DataBar için en‑boy oranı nasıl ayarlanır

Bir DataBar'ın görsel genişliği **aspect ratio** özelliğiyle kontrol edilir. Daha yüksek oran, çubukları daha geniş yapar ve düşük çözünürlüklü yazıcılarda tarama güvenilirliğini artırabilir.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension`, tek bir modülün (en küçük çubuk veya boşluk) boyutunu tanımlar. Bunu 2 px olarak tutmak, çoğu etiket yazıcısı için uygun, net ve yüksek yoğunluklu bir görüntü sağlar.

## En‑boy oranı 15 olarak ayarlama – kod yürütmesi

Şimdi **set aspect ratio 15** gereksinimini uyguluyoruz. Bu, öğreticinin çekirdeğidir ve ihtiyacınız olan tam API çağrısını gösterir.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Neden 15?* Yığılmış DataBar için varsayılan en‑boy oranı 12'dir. 15'e yükseltmek, her çubuğun genişliğini %25 artırır; bu, daha geniş bir barkod gerektiren lojistik sağlayıcıların hızlı tarama için belirlediği spesifikasyonlarla sık sık eşleşir.

## Barkodu PNG olarak kaydetme

Üreteç yapılandırıldıktan sonra, son adım görüntüyü diske yazmaktır. `Save` yöntemi bir dosya yolu ve bir görüntü formatı enum'ı alır.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG formatı kayıpsız kaliteyi korur ve barkodun herhangi bir ekran veya yazıcıda tasarlandığı gibi tam olarak görüntülenmesini sağlar.

## Tam örnek ve beklenen çıktı

Aşağıda, bir konsol uygulamasının `Main` metoduna kopyalayabileceğiniz tam program yer alıyor. Yukarıda açıklanan tüm adımları ve küçük bir doğrulama mesajını içerir.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Beklenen çıktı**

Programı çalıştırdığınızda `DatabarAspectRatio15.png` adlı bir dosya oluşturulur; bu dosya net, geniş yığılmış bir DataBar barkodu içerir. PNG'yi açtığınızda, hâlâ GS1 DataBar spesifikasyonlarına uyan, yatay olarak uzatılmış bir barkod görmelisiniz.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **en‑boy oranı 15 olan yığılmış bir DataBar gösteren barcode PNG oluştur**

### İpuçları ve yaygın tuzaklar

| Situation | Recommendation |
|-----------|----------------|
| **Görüntü bulanık görünüyor** | `XDimension.Pixels` değerini 3 px veya daha yüksek bir değere artırın, ancak dosya boyutunun çok büyük olmasını önlemek için toplam görüntü boyutunu 500 px altında tutun. |
| **Tarayıcı kodu okuyamıyor** | Veri dizesinin GS1 formatına (`(01)` öneki) uygun olduğunu doğrulayın. Ayrıca, yazıcı çözünürlüğünün en az 300 dpi olduğundan emin olun. |
| **Farklı bir dosya formatına ihtiyaç var** | `BarCodeImageFormat.Png` yerine `Jpeg`, `Bmp` veya `Gif` kullanın—API tüm büyük raster formatlarını destekler. |
| **Web uygulamasında çalıştırma** | Dosya sistemine dokunmadan doğrudan HTTP yanıtına yazmak için `generator.Save(Stream, BarCodeImageFormat.Png)` kullanın. |

### Örneği genişletme

* **Tek bir görüntüde birden fazla barkod:** Ek `BarcodeGenerator` örnekleri oluşturun ve bunları `Graphics` kullanarak tek bir `Bitmap` üzerine çizin.  
* **İnsan tarafından okunabilir metin ekleme:** `generator.Parameters.Caption.Visible = true` olarak ayarlayın ve `generator.Parameters.Caption.Font` ile yazı tipini özelleştirin.  
* **Dinamik en‑boy oranı:** Oran değerini bir yapılandırma dosyasından veya veritabanından alarak barkodları anlık olarak farklı genişliklerde oluşturun.

## Sonuç

Bu öğreticide C#'ta **barcode PNG** oluşturmayı ve yığılmış DataBar çok yönlü barkod için tam olarak **en‑boy oranını** 15 olarak ayarlamayı öğrendiniz. Tam, çalıştırılabilir kod her gerekli API çağrısını gösterir, her ayarın neden önemli olduğunu açıklar ve gerçek dünya dağıtımları için pratik ipuçları sunar.  

Sonraki adımda, diğer barkod tipleri (ör. QR Code veya Code 128) için **en‑boy oranını nasıl ayarlayacağınızı** keşfedebilir veya üreticiyi, talep üzerine barkod görüntüleri döndüren bir ASP .NET Core hizmetine entegre edebilirsiniz. Kodlamanın tadını çıkarın!

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanıza ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [C# ve Aspose.Barcode ile databar PNG görüntüleri nasıl oluşturulur](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [C# ve Aspose.Barcode ile databar yığılmış barkod nasıl oluşturulur](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [.NET'te databar yığılmış çok yönlü En‑boy Oranını Özelleştirme](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}