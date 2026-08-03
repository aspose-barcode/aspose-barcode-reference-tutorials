---
category: general
date: 2026-08-03
description: C# BarCodeReader kullanarak bir görüntüden PDF417 barkodu okuyun – birden
  fazla barkodu nasıl okuyacağınızı da gösteren eksiksiz bir barkod okuyucu örneği.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: tr
lastmod: 2026-08-03
og_description: C# BarCodeReader örneğiyle PDF417 barkodunu hızlıca okuyun. Makro
  PDF417'i çözmek ve bir görüntüden birden fazla barkodu okumak için bu adım adım
  rehberi izleyin.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C#'ta PDF417 barkodu okuyun – tam barkod okuyucu örneği
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: C#'ta PDF417 barkodu oku – barkod okuyucu örneği
url: /tr/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta PDF417 barkodunu okuyun – barkod okuyucu örneği

Bir görüntüden PDF417 barkod verilerini okumanız gerekiyorsa, bu kılavuz C#'ta **BarCodeReader** sınıfını kullanarak nasıl yapacağınızı gösterir. Macro PDF417'ı da işleyen ve tek bir görüntüde birden fazla barkodu okuyabilen bir barkod okuyucu örneği öğreneceksiniz.

Barkodlarla çalışmak genellikle farklı görüntü kaynakları, değişken aydınlatma koşulları ve bazen macro PDF417 segmentleri gibi birleşik verilerle uğraşmayı gerektirir. Bu öğreticide PDF417 barkodunu çözmek, genişletilmiş alanlarını çıkarmak ve aynı resimdeki birkaç barkodu işlemek için ihtiyacınız olan her şeyi bulacaksınız. Sonunda, bir görüntü dosyasından barkodları okuyup ayrıntılı bilgileri konsola yazdıran çalıştırılabilir bir konsol programına sahip olacaksınız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

* .NET 6.0 SDK veya daha yeni bir sürüm yüklü  
* `BarCodeReader` ve `DecodeType.MacroPdf417` sağlayan **Aspose.BarCode for .NET** NuGet paketinin (veya uyumlu bir kütüphanenin) güncel bir sürümü  
* PDF417 veya macro PDF417 barkodu içeren bir görüntü dosyası (örnek `ExtPDF417Meta.png` kullanır)  
* Visual Studio 2022 gibi bir kod editörü veya IDE  

Ek hizmetler veya dış API'ler gerekmez.

## Barkod okuma projesini kurma

1. **Yeni bir konsol projesi oluşturun**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Barkod kütüphanesini ekleyin**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Barkod görüntüsünü kopyalayın**  

   `ExtPDF417Meta.png` dosyasını (veya PDF417 barkodu içeren herhangi bir görüntüyü) proje klasörüne yerleştirin.  
   Bu öğreticide dosyanın `YOUR_DIRECTORY/ExtPDF417Meta.png` konumunda olduğunu varsayıyoruz.

Proje artık barkod okuyucu örneğini derleyip çalıştırmaya hazır.

## BarCodeReader ile PDF417 barkodu nasıl okunur

Çözümün çekirdeği, bir `BarCodeReader` örneği oluşturan, `DecodeType.MacroPdf417` belirten ve tespit edilen her barkodu döngüyle işleyen bir `using` bloğudur. Aşağıdaki kod, `Program.cs` dosyasına yapıştırabileceğiniz tam, bağımsız bir programdır.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Neden çalışır**:  

* `DecodeType.MacroPdf417` okuyucuya PDF417'nın macro uzantısını aramasını söyler; bu uzantı dosya kimliği, segment sayısı ve zaman damgaları gibi ek meta verileri taşır.  
* `using` ifadesi, yönetilmeyen kaynakların (dosya tutamaçları, yerel çözüm tamponları) hızlı bir şekilde serbest bırakılmasını garanti eder.  
* `foreach` döngüsü, görüntünün içerdiği **tüm** barkodları otomatik olarak işler ve *birden fazla barkodu okuma* gereksinimini karşılar.  

Programı (`dotnet run`) çalıştırdığınızda aşağıdakine benzer bir çıktı görmelisiniz:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Görüntü birden fazla PDF417 barkodu içeriyorsa, döngü her barkod için ayrı bir blok yazdırır; böylece tek bir resimden **birden fazla barkodu okuma** gösterilmiş olur.

## Tek bir görüntüden birden fazla barkod okuma

Aynı `BarCodeReader` örneği birden fazla barkod tipini aynı anda çözebilir. Kapsamı yalnızca macro PDF417'dan tüm PDF417'lara (ve hatta QR, Code128 vb.) genişletmek için `DecodeType` bayrağını şu şekilde ayarlayın:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* bir bitmask'tir, bu yüzden desteklenen istediğiniz sayıda formatı birleştirebilirsiniz. Bu esneklik, ürün etiketleri, biletler veya kimlik kartları gibi çeşitli kullanım senaryoları için çalışan bir **barkod okuyucu örneği** oluşturur.

## Macro PDF417 alanlarına güvenli erişim

Macro PDF417, zengin bir genişletilmiş özellik kümesi ekler. Ancak, her barkod bu alanların tümünü içermez. Eksik bir özelliğe erişmek `NullReferenceException` fırlatabilir. En güvenli yol, her özelliği yazdırmadan önce doğrulamaktır:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Neden önemli*: Gerçek dünya dağıtımlarında macro verisi içermeyen düz PDF417 barkodları alabilirsiniz. Savunmacı kontrol, uygulamanızın çökmeden çalışmaya devam etmesini sağlar.

## Yaygın hatalar ve en iyi uygulamalar

| Sorun | Neden ortaya çıkar | Önerilen çözüm |
|-------|--------------------|----------------|
| Görüntü yolu hatalı | `BarCodeReader` dosya bulunamadı hatası verir, çözüm başlamaz | `Path.Combine` kullanın ve `File.Exists` ile dosyanın varlığını doğrulayın |
| Düşük çözünürlüklü görüntü | Çözücü barkod kenarlarını bulamaz, tespit sıfır olur | Güvenilir sonuçlar için minimum 300 dpi çözünürlük sağlayın |
| Barkod 45°'den fazla döndürülmüş | Birçok kütüphane dik konumu varsayar | `reader.RecognitionOptions.RotateImage = true` özelliğini etkinleştirin eğer |

## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, adım adım açıklamalarla tam çalışan kod örnekleri içerir; böylece ek API özelliklerini ustalaşabilir ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}