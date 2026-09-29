---
category: general
date: 2026-07-27
description: C#'ta PDF417 barkodunu hızlıca nasıl okuyacağınızı öğrenin. Birden fazla
  barkodu okumayı, görüntüleri çözmeyi ve tam bir C# barkod örneğinde Macro PDF417
  meta verilerini almayı keşfedin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: tr
lastmod: 2026-07-27
og_description: Bu adım adım rehberle C#'ta PDF417 barkodu nasıl okunur. Görüntüleri
  çözün, birden fazla barkodu yönetin ve çalıştırmaya hazır bir örnekte Macro PDF417
  meta verilerini çıkarın.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: C#'ta PDF417 Nasıl Okunur – Tam Barkod Örneği
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: C#'ta PDF417 Nasıl Okunur – Tam Barkod Örneği
url: /tr/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta PDF417 Nasıl Okunur – Tam Barkod Örneği

Hiç **PDF417 barkodunu** bir C# uygulamasında nasıl okuyacağınızı merak ettiniz mi, saçınızı çekmeden? Tek başınıza değilsiniz. İster bir lojistik tarayıcı, bir bilet doğrulayıcı geliştirin, ister PDF417‑kodlu bir kimlik kartından veri çekmeniz gerekse, süreç başlangıçta biraz gizemli görünebilir.  

Bu öğreticide **c# barcode example** üzerinden bir PDF417 görüntüsünü okuyan, **read multiple barcodes** (birden fazla barkod okuma) durumunu yöneten ve ihtiyacınız olabilecek tüm Macro PDF417 meta verilerini çıkaran bir örnek üzerinden ilerleyeceğiz.

## What You’ll Build

Bu kılavuzun sonunda aşağıdaki özelliklere sahip küçük bir konsol programınız olacak:

1. Diskten bir barkod görüntüsü yükler.  
2. **PDF417** (Macro PDF417 dahil) barkodları çözer.  
3. Kod tipi ve metin gibi temel bilgileri yazdırır.  
4. Macro PDF417 alanlarının tam setini (file ID, segment ID, checksum vb.) çıktılar.  

Harici servis yok, sadece tek bir NuGet paketi ve birkaç C# satırı.

## Prerequisites – What You Need Before Starting

- **.NET 6.0** veya daha yeni bir sürüm (kod .NET Framework 4.6+ üzerinde de çalışır).  
- **Aspose.BarCode for .NET** kütüphanesinin güncel bir sürümü – NuGet üzerinden kurun (`Install-Package Aspose.BarCode`).  
- PDF417 barkodu içeren bir görüntü dosyası (demo `ExtPDF417Meta.png` dosyasını kullanıyor).  
- C# konsol uygulamaları hakkında temel bilgi (eğer “Hello World” yazdıysanız yeterli).  

> **Pro tip:** PDF417 örneğiniz yoksa, Aspose demo sitesinden bir tane oluşturabilir ya da akıllı telefon uygulamalarıyla PDF417 etiketleri üretebilirsiniz.

## Step 1: Set Up the Project and Install the Library

İlk olarak yeni bir konsol projesi oluşturun:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Bu, ihtiyacımız olan **c# barcode example** bağımlılıklarını projeye ekler. `Program.cs` dosyasını açın ve varsayılan kodu aşağıdaki iskeletle değiştirin:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Step 2: Initialize the Barcode Reader for PDF417

Çözümün kalbi `BarCodeReader` sınıfıdır. Hangi dosyayı tarayacağını ve hangi barkod tipine odaklanacağını belirtiriz — bu örnekte `DecodeType.Pdf417` ya da makro varyantı `DecodeType.MacroPdf417`. Makro tipini kullanmak, genişletilmiş alanları yakalamamızı sağlar.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Neden `MacroPdf417` kullanıyoruz? Macro PDF417, birçok gerçek dünya uygulamasının ihtiyaç duyduğu ekstra meta verileri (file ID, segment sayısı, zaman damgaları vb.) taşır — örneğin birden fazla sayfaya bölünmüş nakliye manifestoları gibi.

## Step 3: Read All Barcodes Found in the Image

Tek bir görüntü **read multiple barcodes** içerebilir — belki bir QR kod PDF417’nin yanında bulunur. `ReadBarCodes()` metodu, üzerinde dönebileceğimiz bir `IEnumerable<BarCodeResult>` döndürür.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Görüntü sadece bir PDF417 içeriyorsa bile döngü bir kez çalışır, böylece aynı taramadan **read multiple barcodes** ihtiyacı doğabilecek gelecekteki senaryolara kod esnekliği kazanır.

## Step 4: Display Basic Barcode Information

Makro alanlara geçmeden önce barkod tipini ve çözülen metni göstermek faydalıdır. Bu, okuyucunun gerçekten bir PDF417’yi tanıyıp tanımadığını doğrulamanıza yardımcı olur.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` *MacroPdf417* (veya makro bayrağı ayarlanmamışsa *Pdf417*) olarak okunur, `CodeText` ise barkod içinde kodlanmış ham veriyi içerir.

## Step 5: Extract Macro PDF417 Metadata

`Extended` özelliği, PDF417‑özel yapısına derin bir bakış sunar. Aşağıda yazdırdığımız her alan, PDF417 makro spesifikasyonuna doğrudan karşılık gelir.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Her satır makro yükten farklı bir parçayı çeker:

- **FileID** – tüm belge seti için benzersiz bir tanımlayıcı.  
- **SegmentID** – çok parçalı dosyanın hangi bölümünde olduğunuzu gösterir.  
- **SegmentsCount** – beklenen toplam segment sayısı.  
- **FileName, Checksum, FileSize** – aktarılmış dosyanın bütünlüğünü doğrulamak için kullanışlıdır.  
- **TimeStamp, Addressee, Sender** – birçok lojistik sisteminin eklediği isteğe bağlı alanlar.  

Kaynak barkodda bu alanlardan biri eksikse, kütüphane `null` ya da `0` döndürür; bunu ihtiyacınıza göre işleyebilirsiniz.

## Step 6: Run the Complete Example

Hepsini bir araya getirdiğimizde, işte tam, çalıştırmaya hazır program:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Expected Output

Programı geçerli bir `ExtPDF417Meta.png` dosyasıyla çalıştırdığınızda aşağıdakine benzer bir çıktı almanız gerekir:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Eğer görüntü birden fazla barkod içeriyorsa,


## What Should You Learn Next?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, adım adım açıklamalar ve tam çalışan kod örnekleri içerir; böylece ek API özelliklerini ustalaşabilir ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}