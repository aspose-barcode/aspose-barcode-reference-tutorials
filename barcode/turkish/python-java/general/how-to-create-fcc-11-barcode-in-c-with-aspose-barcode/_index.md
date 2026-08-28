---
category: general
date: 2026-08-22
description: Aspose.BarCode kullanarak C#'de FCC 11 barkodu oluşturun. Adım adım kodu
  öğrenin, boyutları yapılandırın ve Australia Post için PNG görüntüleri üretin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: tr
lastmod: 2026-08-22
og_description: C# ile Aspose.BarCode kullanarak FCC 11 barkodu oluşturun. Avustralya
  Postu için PNG barkodları üretmek üzere bu özlü öğreticiyi izleyin; FCC 59 ve FCC
  62 varyantlarını da içerir.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: C#'te FCC 11 barkodu oluşturma – eksiksiz Aspose.BarCode rehberi
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Aspose.BarCode ile C#'ta FCC 11 barkodu nasıl oluşturulur
url: /tr/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# ile Aspose.BarCode kullanarak FCC 11 barkod nasıl oluşturulur

Bir .NET uygulamasında **FCC 11 barkod oluşturmanız** gerekiyorsa, bu kılavuz gerekli tam kodu gösterir. Barkod boyutlarını nasıl yapılandıracağınızı, doğru kodlama tablosunu nasıl seçeceğinizi ve sonucu PNG dosyası olarak nasıl kaydedeceğinizi göreceksiniz.

Australia Post barkodları oluşturmak, lojistik, posta sistemleri ve envanter takibi için yaygın bir gereksinimdir. Bu öğreticide FCC 11 formatı ele alınmakta ve ayrıca farklı kodlama tabloları ile FCC 59 ve FCC 62 barkodların nasıl üretileceği gösterilmektedir, böylece aynı deseni diğer posta hizmetleri için de yeniden kullanabilirsiniz.

## Gereksinimler

* .NET 6.0 SDK veya daha yeni bir sürüm yüklü  
* Visual Studio 2022 (veya herhangi bir C# uyumlu IDE)  
* **Aspose.BarCode for .NET** için geçerli bir lisans – topluluk sürümü değerlendirme için çalışır  
* PNG dosyalarının kaydedileceği klasöre yazma izni  

Bu önkoşullar, kodun ek yapılandırma olmadan derlenip çalışmasını garanti eder.

## Adım 1: Aspose.BarCode NuGet paketini yükleyin

Proje klasöründe bir terminal açın ve şu komutu çalıştırın:

```bash
dotnet add package Aspose.BarCode
```

Bu komut, kütüphanenin en son kararlı sürümünü proje dosyanıza ekler. Paket, bu öğreticide kullanılan `BarcodeGenerator` sınıfını içerir.

## Adım 2: Çıktı klasörünü tanımlayın

Oluşturulan görüntülerin saklanacağı bir klasör oluşturun. Yol, çalıştırılabilir dosyaya göre mutlak ya da göreli olabilir.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory`, klasörün var olduğundan emin olur ve `Save` yöntemi dosyayı yazarken çalışma zamanı hatalarını önler.

## Adım 3: FCC 11 barkodu oluşturun

FCC 11 formatı, Australia Post'un posta barkodları için varsayılan kodlamadır. Aşağıdaki kod, `1101234567` sayısal dizesini kodlayan bir barkod oluşturur.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Neden bu çalışır:**  
* `EncodeTypes.AustraliaPost`, kütüphaneye Australia Post kodlama kurallarını uygulamasını söyler.  
* Veri dizesi `1101234567`, FCC 11 spesifikasyonuna uyar: ilk iki rakam (`11`) formatı tanımlar, ardından 7 haneli müşteri referansı gelir.  
* `XDimension` ve `BarHeight`, basılan barkodun boyutunu kontrol eder; bu, tarayıcı okunabilirliği için önemlidir.

Programı çalıştırdıktan sonra, `Barcodes` klasöründe `PostalAustraliaPostFCC11.png` dosyasını bulacaksınız. Görüntü şu şekildedir:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Adım 4: Ek Australia Post barkodları oluşturun (isteğe bağlı)

Ana hedef **FCC 11 barkod oluşturmak** olsa da, farklı posta sınıfları için genellikle FCC 59 veya FCC 62 barkodlarına da ihtiyaç duyarsınız. Aşağıdaki kod aynı `BarcodeGenerator` örneğini yeniden kullanır, yalnızca veri dizesini ve isteğe bağlı kodlama tablosunu değiştirir.

### 4.1 N‑Tablo kodlamalı FCC 59

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 N‑Tablo kodlamalı FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 C‑Tablo kodlamalı FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 Diğer kodlamalı FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Tüm dört görüntü aynı klasörde yan yana kaydedilir, böylece görsel farkları karşılaştırmak kolay olur.

## Adım 5: Kodlama tablolarını anlayın

Australia Post üç kodlama tablosu tanımlar:

* **N‑Table** – sayısal müşteri bilgilerini yorumlar. Yük yalnızca rakamlardan oluştuğunda kullanın.  
* **C‑Table** – alfanümerik karakterleri destekler, harf içeren referans numaraları için faydalıdır.  
* **Other** – özel veya genişletilmiş veri formatları için bir geri dönüş seçeneğidir.

Doğru tabloyu seçmek, barkod tarayıcısının bilgiyi tam olarak amaçlandığı gibi çözmesini sağlar. `AustralianPostEncodingTable` özelliğini atladığınızda, kütüphane varsayılan olarak N‑Table'ı kullanır; bu, sayısal olmayan karakterlerin kesilmesine neden olabilir.

## İpuçları, uç durumlar ve yaygın hatalar

| Durum | Önerilen yaklaşım |
|-----------|----------------------|
| Veri dizesi uzunluğu gerekliden kısa | FCC spesifikasyonunu karşılamak için sayısal kısmı başına sıfır ekleyerek doldurun. |
| Barkod yazdırıldığında bulanık görünüyor | `XDimension` değerini 5 veya 6 piksele artırın ve yazıcının DPI ayarlarını kontrol edin. |
| Tarayıcı “geçersiz format” hatası veriyor | Doğru kodlama tablosunun (N‑Table, C‑Table, Other) veri yüküyle eşleştiğini doğrulayın. |
| GUI olmadan Linux'ta çalıştırma | `System.Drawing.Common` paketinin referans alındığından emin olun veya `BarCodeImageFormat.Png` ile `Save` metodunu kullanın; bu, bir görüntü bağlamı gerektirmez. |
| Farklı bir görüntü formatına ihtiyaç | `BarCodeImageFormat.Png` yerine `BarCodeImageFormat.Jpeg` veya `BarCodeImageFormat.Tiff` kullanın. |

Bu pratik ipuçları, posta barkodu çözümlerinin gerçek dünyadaki uygulamalarından elde edilmiştir.

## Tam çalıştırılabilir örnek

Aşağıda, yeni bir konsol projesine (`dotnet new console`) kopyalayıp değişiklik yapmadan çalıştırabileceğiniz bağımsız bir program bulunmaktadır.



## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Java ile barkod oluşturma – Aspose ile Australia Post Barkodu](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Aspose.BarCode ile Tek Boyutlu Databar GS1 Kodlaması Oluşturma](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Code 16K için .NET'te barkod sessiz bölgesi oluşturma – Aspose.BarCode kullanarak](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}