---
category: general
date: 2026-08-15
description: BarCodeReader kullanarak C#'ta görüntüden barkod okuyun. Birden fazla
  barkodu C#'ta nasıl okuyacağınızı, PDF417 barkodunu nasıl okuyacağınızı öğrenin
  ve tam bir C# BarCodeReader örneğini görün.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: tr
lastmod: 2026-08-15
og_description: C#'ta adım adım kılavuzla görüntüden barkod okuyun. Birden fazla barkodu
  C#'ta nasıl okuyacağınızı, PDF417 sembollerini nasıl çözeceğinizi keşfedin ve tam
  bir C# BarCodeReader örneğini çalıştırın.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: C#'de görüntüden barkod okuyun – BarCodeReader öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: C#'ta Görüntüden Barkod Okuma – BarCodeReader Öğreticisi
url: /tr/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta Görüntüden Barkod Okuma – BarCodeReader Öğreticisi

Bir .NET uygulamasında **görüntüden barkod okuma** ihtiyacınız varsa, bu rehber `BarCodeReader` sınıfı ile bunu tam olarak nasıl yapacağınızı gösterir. Ayrıca **C#'ta birden fazla barkod okuma**, bir PDF417 sembolünü çözme ve projenize kopyalayabileceğiniz tam bir **C# BarCodeReader örneği** elde etme konularını da göreceksiniz.

Bu öğretici, gerekli NuGet paketinin eklenmesinden genişletilmiş PDF417 alanlarının yazdırılmasına kadar her adımı kapsar—böylece çalıştırılabilir bir konsol programı ile bitirirsiniz. Harici bir belgeye ihtiyaç yoktur; tüm kod ve açıklamalar dahil edilmiştir.

## Gereksinimler

Before you start, make sure you have:

* .NET 6.0 SDK veya daha yenisi (kod .NET Core ve .NET Framework ile çalışır)
* Visual Studio 2022 veya herhangi bir C# uyumlu editör
* `Aspose.BarCode` NuGet paketi (veya `BarCodeReader` sağlayan eşdeğer kütüphane)
* Macro PDF417 barkod içeren bir görüntü dosyası (ör. `ExtPDF417Meta.png`)

Bu önkoşullara sahip olmak, örnek kodun ek yapılandırma olmadan derlenmesini sağlar.

## BarCodeReader ile Görüntüden Barkod Okuma

İlk adım, görüntü dosyasını işaret eden ve kütüphaneye hangi barkod tipini araması gerektiğini belirten bir `BarCodeReader` örneği oluşturmaktır.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Neden bu çalışır:**  
`BarCodeReader` görüntüyü açar, belirtilen `DecodeType` için tarama yapar ve bir `BarCodeResult` nesneleri koleksiyonu döndürür. Her sonuç, genel barkod verilerini (`CodeTypeName`, `CodeText`) ve Macro PDF417 için, standartta tanımlanan tüm ek alanları ortaya çıkaran bir `Extended.Pdf417` nesnesini içerir.

## Tek Bir Görüntüde C# ile Birden Fazla Barkod Okuma

Bazen bir görüntü birden fazla barkod içerir (ör. PDF417 yanındaki QR kod). Bu senaryoyu ele almak için, açık `DecodeType` değerini atlayabilir veya `DecodeType.AllSupported` geçebilir ve sonuçlar üzerinde döngü yapabilirsiniz.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Neden buna ihtiyacınız var:**  
`AllSupported` belirtmek, motorun bildiği her barkod formatını denemesini sağlar, bu da görüntüdeki her sembolün yakalanmasını garantiler. Barkod tiplerini önceden tahmin edemediğiniz durumlarda önerilen yaklaşımdır.

## C# Kullanarak PDF417 Barkod Okuma

Sadece klasik PDF417 (macro olmayan) formatıyla ilgileniyorsanız, `DecodeType` değerini `Pdf417` olarak değiştirin. Kodun geri kalanı aynı kalır, ancak genişletilmiş alanlar mevcut olmaz.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Neden bu önemli:**  
Klasik PDF417, macro‑özel özellikleri ortaya çıkarmaz, bu yüzden `Extended.Pdf417` bloğu gereksizdir. Kesin `DecodeType` kullanmak ayrıca taramayı hızlandırır çünkü kütüphane desteklenmeyen algoritmaları atlar.

## Kopyalayabileceğiniz Tam C# BarCodeReader Örneği

Aşağıda, üç senaryoyu tek bir, çalıştırması kolay konsol uygulamasında birleştiren tam program yer almaktadır. `YOUR_DIRECTORY/ExtPDF417Meta.png` ifadesini görüntünüzün gerçek yolu ile değiştirin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Beklenen çıktı

Örnek görüntü bir Macro PDF417 barkod içerdiğinde, konsol aşağıdakine benzer bir şey yazdırır:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Görüntü yalnızca normal bir PDF417 içeriyorsa, “Macro PDF417” bölümü boş olur ve “Classic PDF417” bölümü çözülen metni gösterir.

## Sonuç

Artık `BarCodeReader` kullanarak C#'ta **görüntüden barkod okuma**, tek bir dosyada **C# ile birden fazla barkod okuma** ve **PDF417 barkod okuma**—hem macro hem de klasik varyantlar—için kesin adımları biliyorsunuz. Tam **C# BarCodeReader örneği** herhangi bir .NET projesine yapıştırılmaya hazırdır ve diğer formatları işlemek veya daha büyük bir görüntü‑işleme hattına entegre etmek için genişletebilirsiniz.

**Sonraki adımlar**

* Okuyucu bloğu etrafında `try / catch` gibi hata‑işleme desenlerini keşfedin.  
* `ReaderParameters` nesnesiyle algılama hızını ve doğruluğunu ayarlamak için deneyler yapın.  
* Barkod okuma işlemini görüntü ön işleme kütüphaneleriyle birleştirin (

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Aspose.BarCode ile .NET için DataMatrix Barkodları Nasıl Okunur](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix barkodunu C# ile okuma – DataMatrix Modu (Otomatik) Oluşturma](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Görüntüden Barkod Okuma – Java'da Aspose.BarCode ile Barkod Bölgesi Çıkarma Uzmanlığı](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}