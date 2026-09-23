---
category: general
date: 2026-07-15
description: Aspose.BarCode ile C#'ta çok yönlü barkodu hızlıca oluşturun – ayarlanabilir
  çubuk yüksekliği ve X‑boyutu ile C#'ta barkod nasıl oluşturulur öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: tr
lastmod: 2026-07-15
og_description: C# ile Aspose.BarCode kullanarak çok yönlü barkod oluşturun. XDimension
  ve BarHeight ayarlarını değiştirerek mükemmel sonuçlar elde etmek için C#'ta barkod
  üretimini öğrenin.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: C#'ta çok yönlü barkod oluşturma – Tam Programlama Rehberi
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: C#'ta çok yönlü barkod oluşturma – Adım Adım Rehber
url: /tr/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta çok yönlü barkod oluşturma – Adım Adım Kılavuz

Hiç GS1 DataBar Omni‑Directional sembolojesine uygun bir C# barkod oluşturmanın nasıl olduğunu merak ettiniz mi? Tek başınıza değilsiniz. Bu öğreticide **çok yönlü barkod** görüntülerini sıfırdan oluşturacağız, X‑boyutunu ayarlayacağız ve çubuk yüksekliğiyle oynayacağız—hepsi Aspose.BarCode kütüphanesini kullanarak.

Gerçek bir senaryoyu adım adım inceleyeceğiz: perakende etiketi için kompakt, yüksek yoğunluklu bir barkoda ihtiyacınız var ve görsel boyutu üzerinde tam kontrol istiyorsunuz. Sonunda iki PNG dosyanız olacak—biri 30 px çubuk yüksekliği, diğeri 60 px—herhangi bir baskı iş akışına kolayca ekleyebileceksiniz.

## Önkoşullar

- .NET 6 (veya herhangi bir yeni .NET çalışma zamanı) makinenizde kurulu.  
- Visual Studio 2022 veya VS Code—sevdiğiniz IDE yeterli.  
- Ücretsiz Aspose.BarCode for .NET NuGet paketi (`Aspose.BarCode`).

Başka bir bağımlılık gerekmez. NuGet ile hiç çalışmadıysanız, Package Manager Console’u açıp şu komutu çalıştırın:

```powershell
Install-Package Aspose.BarCode
```

## çok yönlü barkod – Temelleri Anlamak

**GS1 DataBar Omni‑Directional** sembolü, her yönde taramaya uygun olacak şekilde tasarlanmıştır; raf kenarı etiketleri için mükemmeldir. `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` çağrısı yaptığınızda, kütüphane işi halleder: veriyi kodlar, semboloji kurallarını uygular ve raster görüntüyü hazırlar.

> **Pro tip:** Ham veriyi uygun Uygulama Tanımlayıcısı (AI) formatında sarmayı unutmayın, ör. GTIN‑14 için `"(01)12345678901231"`. Bu, tarayıcıya rakamların neyi temsil ettiğini söyler.

## Adım 1 – Barkod Üreteci Kurulumu (how to generate barcode c#)

İlk olarak üreteç nesnesini oluşturuyoruz. Bu, Aspose ile **how to generate barcode c#** konusunun temel taşıdır.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` enum değeri, motorun hangi sembolojiyi kullanacağını belirtir. İkinci argüman, zaten GTIN AI ile sarılmış ham veri dizesidir.

## Adım 2 – X‑Boyutunu Ayarlama (barcode XDimension)

**barcode XDimension** en küçük çubuğun genişliğini kontrol eder. Çoğu etiket yazıcısı için okunabilirlik ve kompaktlık arasında iyi bir denge sağlayan değer 2 px’dir.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Daha ince ya da kalın bir görünüm isterseniz sadece sayıyı değiştirin. Unutmayın: X‑boyutu temel birimdir; diğer tüm çubuk genişlikleri bu değerin katlarıdır.

## Adım 3 – 30 px Çubuk Yüksekliği ile İlk Görüntüyü Oluşturma (barcode BarHeight)

Şimdi **barcode BarHeight** değerini 30 px olarak ayarlayıp görüntüyü kaydediyoruz. Bu, standart bir etikete rahatça sığan mütevazı boyutta bir barkod üretir.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` metodu bir PNG dosyasını diske yazar. JPEG çıktısı isterseniz `BarCodeImageFormat.Jpeg` ile değiştirebilirsiniz.

## Adım 4 – Daha Büyük Etiketler İçin Çubuk Yüksekliğini 60 px'e Çıkarma (barcode BarHeight)

Bazen daha büyük bir barkod gerekir—örneğin tarayıcıdan daha uzakta duran bir raf etiketi için. Yüksekliği iki katına çıkaralım.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Görüyorsunuz ki **don’t** üreteci yeniden oluşturmak zorunda değiliz; sadece parametreyi değiştirip aynı nesneyi yeniden kullanıyoruz. Bu bellek tasarrufu sağlar ve kodu düzenli tutar.

## Adım 5 – İkinci Görüntüyü Kaydetme (how to generate barcode c#)

Son olarak ikinci PNG’yi kaydediyoruz. Artık yalnızca çubuk yüksekliği farklı olan iki dosyanız var.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Beklenen çıktı

- `DatabarBarHeight30Pixels.png` – 30 px yüksekliğinde bir omni‑directional barkod.  
- `DatabarBarHeight60Pixels.png` – aynı veri, ancak 60 px yüksekliğinde bir barkod.

Dosyaları herhangi bir görüntüleyicide açın; GS1 DataBar Omni‑Directional spesifikasyonuna uygun, net ve taranabilir çubuklar göreceksiniz.

## Sık Sorulan Sorular ve Kenar Durumları

### Farklı bir X‑boyuta ihtiyacım olsaydı ne olur?

`Save` çağrısından önce yeni bir değer atayın. Ultra yüksek yoğunluklu baskı için 1 px’e inebilirsiniz, ancak önce tarayıcınızla test edin—bazı cihazlar 2 px altındaki çubuklarda zorlanabilir.

### Barkodun altına insan tarafından okunabilir metin ekleyebilir miyim?

Evet. `barcodeGenerator.Parameters.Barcode.CodeText` özelliğine bir dize atayın ve isteğe bağlı olarak `barcodeGenerator.Parameters.Barcode.CodeLocation` değerini `BarCodeTextLocation.Below` olarak ayarlayın. Bu, sayısal GTIN’in görünür olması gereken perakende ortamları için kullanışlıdır.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### PNG, baskı için en iyi format mı?

PNG kayıpsızdır ve barkod tarayıcıları için gereken keskin kenarları korur. Alt sisteminiz farklı bir format (TIFF, BMP) bekliyorsa sadece `BarCodeImageFormat` enum’unu değiştirin.

## Tam Çalışan Örnek (create omni-directional barcode)

Aşağıda tamamen çalışır, hazır‑koşul program yer alıyor. Yeni bir konsol projesine kopyalayıp **F5** tuşuna basın.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Programı çalıştırın, çıktı klasörünü kontrol edin ve iki PNG dosyasını tam olarak tarif edildiği gibi göreceksiniz.

## Özet

**how to generate barcode C#** kodunu, Aspose.BarCode kullanarak **create omni-directional barcode** oluşturacak şekilde gösterdik. **barcode XDimension** ve **barcode BarHeight** ayarlarını değiştirerek, tarama güvenilirliğinden ödün vermeden görsel boyut üzerinde ince ayar yapabilirsiniz.

## Sıradaki Adım?

- `Color` veya `Margin` gibi diğer **GS1 DataBar Omni-Directional** ayarlarıyla deneyler yapın.  
- Karmaşık etiket tasarımları için `Graphics` kullanarak bir kanvas üzerinde birden fazla barkodu birleştirin.  
- Üreteci bir web API’ye entegre edin, böylece e‑ticaret platformunuz talep üzerine barkod üretebilir.

Paylaşmak istediğiniz bir farklılık var mı? Bir yorum bırakın, sohbeti sürdürelim. Mutlu kodlamalar!

## Sonra Ne Öğrenmelisin?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanıza ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak tam çalışan kod örnekleri ve adım adım açıklamalar içerir.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}