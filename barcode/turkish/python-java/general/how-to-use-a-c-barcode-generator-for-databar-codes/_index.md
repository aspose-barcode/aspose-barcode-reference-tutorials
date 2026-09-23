---
category: general
date: 2026-09-23
description: c# barkod oluşturucu öğreticisi, Aspose.BarCode kütüphanesini kullanarak
  özelleştirilmiş en‑boy oranlarıyla barkod görüntüleri oluşturmayı gösterir.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: tr
lastmod: 2026-09-23
og_description: c# barkod oluşturucu rehberi, barkod görüntüleri oluşturmayı, en‑boy
  oranlarını ayarlamayı ve Aspose.BarCode kullanarak PNG dosyalarını dışa aktarmayı
  adım adım gösterir.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: C# barkod üreticisi ile yüksek kaliteli barkodlar oluşturun
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: DataBar kodları için C# barkod üreteci nasıl kullanılır
url: /tr/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar kodları için C# barkod üreteci nasıl kullanılır

Eğer DataBar yığılmış Omni‑Directional semboller üretebilen bir **c# barcode generator**'a ihtiyacınız varsa, bu kılavuz size eksiksiz, çalıştırmaya hazır bir çözüm sunar. Barkod görüntülerini nasıl oluşturacağınızı, X‑boyutunu nasıl kontrol edeceğinizi ve IDE'den çıkmadan en‑boy oranını nasıl değiştireceğinizi göreceksiniz.

Barkod oluşturma, envanter sistemleri, nakliye etiketleri ve satış noktası uygulamaları için yaygın bir gereksinimdir. Bu öğreticinin sonunda, istediğiniz herhangi bir en‑boy oranıyla PNG dosyaları oluşturabilir ve kodu diğer barkod türleri için nasıl uyarlayacağınızı anlayacaksınız.

## Önkoşullar

* .NET 6.0 SDK veya daha yeni bir sürüm yüklü  
* Visual Studio 2022 (veya tercih ettiğiniz herhangi bir C# editörü)  
* **Aspose.BarCode**'a bir NuGet referansı – `BarcodeGenerator` sınıfını sağlayan kütüphane  

Ayrı bir grafik kütüphanesine ihtiyacınız yok; Aspose.BarCode görüntü kodlamasını dahili olarak yönetir.

## Adım 1: Aspose.BarCode NuGet paketini kurun

Proje klasörünüzde bir terminal açın ve şu komutu çalıştırın:

```bash
dotnet add package Aspose.BarCode
```

Bu komut, kütüphanenin en son kararlı sürümünü proje dosyanıza ekler ve `BarcodeGenerator` sınıfının kullanımına hazır olmasını sağlar.

## Adım 2: Çıktı klasörünü tanımlayın

Oluşturulan PNG dosyalarının kaydedileceği bir klasör seçin. Mutlak ya da göreli bir yol kullanmak aynı şekilde çalışır, ancak göreli yol proje taşınabilirliğini korur.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Klasörü programlı olarak oluşturmak, klasör eksik olduğunda çalışma zamanı hatalarını önler.

## Adım 3: Örnek veriyle C# barkod üretecini örnekleyin

`BarcodeGenerator` yapıcı metodu iki argüman gerektirir: barkod türü ve veri dizesi. DataBar yığılmış Omni‑Directional sembolü için `EncodeTypes.DatabarStackedOmniDirectional` kullanırsınız.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Veri dizesi, GS1 Uygulama Tanımlayıcısı formatını izler. `EncodeTypes` enumu 150'den fazla barkod standardı içerir; enum değerini değiştirerek başka bir türe geçebilirsiniz.

## Adım 4: Barkod için X‑boyutunu (piksel boyutu) ayarlayın

X‑boyut, en dar çubuğun genişliğini kontrol eder. 2 piksel değeri, çoğu ekran için uygun keskin, yüksek çözünürlüklü bir görüntü üretir.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑boyutu ayarlamak isteğe bağlıdır, ancak barkodun görsel yoğunluğu üzerinde ayrıntılı kontrol sağlar.

## Adım 5: 15 en‑boy oranıyla bir barkod oluşturun ve PNG olarak kaydedin

`AspectRatio` özelliği `DataBar` alt nesnesine aittir. Bu değeri değiştirmek, kodlanmış veriyi korurken barkodu dikey olarak uzatır veya sıkıştırır.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` metodu barkodu belirtilen dosya yoluna yazar. `BarCodeImageFormat.Png` enumu kayıpsız sıkıştırma sağlar.

![c# barkod üreteci çıktı örneği](generated_barcode_example.png)

*Görsel: 15 en‑boy oranıyla oluşturulan barkod.*

## Adım 6: En‑boy oranını 30’a değiştirin ve ikinci bir görüntü oluşturun

Aynı `BarcodeGenerator` örneğini yeniden kullanmak yeni bir nesne tahsisinden kaçınır. Sadece `AspectRatio` değerini güncelleyip `Save` metodunu tekrar çağırın.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Artık yalnızca dikey ölçeklendirme açısından farklılık gösteren iki PNG dosyanız var. Bu teknik, aynı veriyi farklı etiket boyutları için oluşturmanız gerektiğinde faydalıdır.

## Yaygın varyasyonlar ve uç durumlar

### Başka bir barkod türüne geçiş

QR kod, Code 128 veya PDF417'ye ihtiyacınız varsa, yapıcıdaki enum değerini değiştirin:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Diğer tüm yapılandırma adımları (X‑boyutu, kaydetme) aynı kalır.

### Desteklenmeyen karakterlerle başa çıkma

`BarcodeGenerator`, giriş dizesini seçilen sembolojiye karşı doğrular. Geçersiz bir karakter sağlamak `ArgumentException` fırlatır. Kullanıcı dostu bir hata mesajı vermek için oluşturmayı try‑catch bloğuna alın:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Diğer görüntü formatlarına dışa aktarma

Aspose.BarCode BMP, JPEG, TIFF ve SVG formatlarını destekler. `Save` metodunun ikinci argümanını buna göre değiştirin:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Baskı için yüksek çözünürlüklü çıktı

Yüksek DPI'lı yazıcılarda baskı alırken X‑boyutunu artırın ve isteğe bağlı olarak `Resolution` özelliğini ayarlayın:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Bu ayarlar daha büyük dosyalar üretir ancak fiziksel ortamda keskin kenarları korur.

## Beklenen çıktı

Tam programı çalıştırdığınızda `GeneratedBarcodes/` içinde aşağıdaki dosyalar oluşturulur:

* `DatabarAspectRatio15.png` – standart yükseklikte bir DataBar kodu  
* `DatabarAspectRatio30.png` – dikey olarak uzatılmış bir versiyon  

Her iki görüntü de aynı kodlanmış GS1 verisini içerir ve herhangi bir barkod tarayıcı uygulamasıyla doğrulayabilirsiniz.

## Tam kaynak kodu

Aşağıdaki kodu yeni bir konsol projesine (`dotnet new console`) kopyalayın ve çalıştırın. Program durum mesajlarını konsola yazdırır ve PNG dosyalarını diske yazar.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Programı çalıştırmak, aşağıdakine benzer bir konsol çıktısı üretir:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Sonuç

Artık DataBar yığılmış Omni‑Directional semboller oluşturabilen, X‑boyutunu ayarlayabilen ve özel en‑boy oranlarıyla PNG dosyaları dışa aktarabilen bir **c# barcode generator**'a sahipsiniz. Aynı desen, Aspose.BarCode tarafından desteklenen diğer tüm barkod sembolojileri için de çalışır ve barkod oluşturmayı envanter, nakliye veya satış noktası çözümlerine entegre etmeyi kolaylaştırır.

Daha fazla keşfetmek isterseniz, şunları deneyin:

* QR kodları veya PDF417 sembolleri oluşturma (`how to generate barcode` mobil uygulamalar için)  
* Ölçeklenebilir web grafikleri için SVG'ye dışa aktarma  
* Oluşturulan görüntüleri doğrudan PDF faturalarına Aspose.PDF kullanarak gömme  

Farklı `AspectRatio` değerleri, X‑boyut boyutları ve çıktı formatlarıyla deney yaparak tam olarak eşleşmesini sağlayın

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Özel en‑boy oranı ile Aztec barkodu nasıl oluşturulur – Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Barkod Boyutunu Ayarlama – Codablock F En‑boy Oranı Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Tek Boyutlu Databar için Barkod Yüksekliğini Oluşturma ve Ayarlama – Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}