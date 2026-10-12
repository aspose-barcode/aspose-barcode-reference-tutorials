---
category: general
date: 2026-09-29
description: C#'ta GS1 barkod oluşturun ve BarcodeGenerator kullanarak barkod PNG
  görüntüleri üretin. Barkod görüntüsünü verimli bir şekilde dışa aktarmak için adım
  adım kılavuzu izleyin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: tr
lastmod: 2026-09-29
og_description: C#'ta GS1 barkod oluşturun ve BarcodeGenerator ile barkod PNG dosyaları
  üretin. Barkod görüntüsünü hızlıca dışa aktarmak için bu kapsamlı rehberi izleyin.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: C#'ta GS1 barkod oluşturun – dakikalar içinde PNG olarak dışa aktarın
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: C#'ta GS1 barkodu oluştur ve PNG olarak dışa aktar
url: /tr/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta GS1 barkod oluşturma ve PNG olarak dışa aktarma

Bir .NET uygulamasında **GS1 barkod oluşturmanız** gerekiyorsa, bu kılavuz tam olarak nasıl yapılacağını gösterir. Aspose.BarCode `BarcodeGenerator` sınıfı ile bir barkod PNG görüntüsü oluşturan ve barkod görüntüsünü diske dışa aktaran özlü bir çözüm göreceksiniz.

GS1 barkod oluşturma, envanter, nakliye ve satış noktası sistemleri için yaygın bir gereksinimdir. Bu öğreticinin sonunda, GS1 uyumlu bir MicroPDF417 barkodu oluşturan ve yüksek kaliteli bir PNG dosyası olarak kaydeden küçük bir C# programı yazabilecek olacaksınız.

## Önkoşullar

* **.NET 6** (veya daha yeni bir .NET sürümü) yüklü.
* **Visual Studio 2022** veya C# destekleyen herhangi bir IDE.
* **Aspose.BarCode for .NET** NuGet paketi (`Aspose.BarCode`) – örneklerde kullanılan `BarcodeGenerator` API'sini sağlar.
* C# sözdizimi hakkında temel bilgi.

> **Pro ipucu:** Deneme yaparken Aspose.BarCode'un ücretsiz topluluk sürümünü kullanın; tam sürüm değerlendirme filigranlarını kaldırır.

## Adım 1 – BarcodeGenerator ile GS1 barkod oluşturma

İlk olarak, *MicroPDF417* formatı için `BarcodeGenerator` örneğini oluşturmalı ve ona bir GS1 veri dizesi vermelisiniz. GS1 Uygulama Tanımlayıcıları (AI'lar) parantez içinde sarılır, örneğin GTIN‑14 için `(01)` ve seri numarası için `(21)`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Neden önemli:**  
`EncodeTypes.MicroPdf417`, dize geçerli AI'lar içerdiğinde girişi otomatik olarak GS1 verisi olarak işler. Bu, ek yapılandırma gerektirmeden oluşturulan barkodun GS1 spesifikasyonuna uygun olmasını sağlar.

## Adım 2 – Optimum boyut için barkod boyutlarını ayarlama

Bir barkodun görsel boyutu **X‑dimension** (tek bir modülün genişliği) ile kontrol edilir. `XDimension.Pixels` değerini ayarlamak, okunabilirliği korurken son görüntü boyutunu ince ayar yapmanızı sağlar.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Barkod PNG oluşturma** – X‑dimension, kodlanan veriyi etkilemez; yalnızca oluşturulan görüntünün fiziksel boyutlarını değiştirir. Yüksek çözünürlüklü baskı için daha büyük bir barkod gerekiyorsa, bu değeri artırın (ör. `3` veya `4`).

## Adım 3 – Barkod PNG oluşturma ve barkod görüntüsünü dışa aktarma

Artık barkodu render edebilir ve bir PNG dosyasına yazabilirsiniz. `Save` yöntemi hedef yolu ve istenen görüntü formatını alır.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Arka planda neler oluyor:**  
`BarcodeGenerator.Save`, barkodu bir bitmap'e rasterleştirir, önceki adımda ayarladığınız X‑dimension'ı uygular ve bitmap'i PNG dosyası olarak kodlar. Ortaya çıkan dosya doğrudan web sayfalarında kullanılabilir, etiketlere basılabilir veya PDF'lere gömülebilir.

## Tam kaynak kodu örneği

Aşağıda, kopyalayıp yapıştırıp çalıştırabileceğiniz tam ve bağımsız bir konsol uygulaması bulunmaktadır. **Barkod PNG dosyalarının nasıl oluşturulacağını**, **barkod görüntüsünün nasıl dışa aktarılacağını** gösterir ve temel hata yönetimini içerir.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Beklenen çıktı

Programı çalıştırdığınızda şu çıktıyı görmelisiniz:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

PNG dosyasını açtığınızda, GTIN‑14 `12345678901234` ve seri numarası `ABC123` kodlayan net bir **GS1 MicroPDF417** barkodu görüntülenir. Herhangi bir GS1 uyumlu tarayıcıyla tarandığında orijinal veri dizesi dönecektir.

## Yaygın tuzaklar ve en iyi uygulamalar

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Yanlış AI formatı** | Parantezlerin eksik olması veya yanlış sırada olması barkodun GS1 olmamasına neden olur. | Her AI'yi her zaman parantez içinde sarın, ör. `(01)`. |
| **Çok küçük X‑dimension** | Barkod düşük çözünürlüklü cihazlarda okunamaz hale gelir. | Çoğu yazıcı için `XDimension.Pixels` değerini ≥ 2 tutun; yüksek DPI çıktısı için artırın. |
| **Çıktı klasörü mevcut değil** | `Save`, `DirectoryNotFoundException` hatası verir. | `Save` çağırmadan önce `Directory.CreateDirectory` kullanın. |
| **Yanlış EncodeType kullanımı** | Bazı tipler (ör. `Code128`) GS1 verisini doğrudan desteklemez. | `EncodeTypes.MicroPdf417` veya herhangi bir GS1 uyumlu tip seçin. |
| **NuGet referansı eksik** | `The type or namespace name 'Aspose' could not be found` gibi derleme zamanı hataları. | NuGet üzerinden `Aspose.BarCode` paketini kurun. |

## Örneği genişletme

* **Farklı görüntü formatları** – Başka bir formata ihtiyacınız varsa `BarCodeImageFormat.Png` yerine `Jpeg`, `Gif` veya `Bmp` kullanın.
* **Yüksek çözünürlüklü çıktı** – Kaydetmeden önce `generator.Parameters.ImageResolution.DpiX` ve `DpiY` değerlerini ayarlayın.
* **PDF'ye gömme** – PNG'yi bir PDF faturası veya etikete yerleştirmek için `Aspose.Pdf` kullanın.

## Sonuç

Artık Aspose.BarCode `BarcodeGenerator` kullanarak C#'ta **GS1 barkod oluşturmayı**, **barkod PNG oluşturmayı** ve **barkod görüntüsünü** dosya sistemine **dışa aktarmayı** biliyorsunuz. Kılavuz, GS1 verisiyle jeneratörü başlatmadan, X‑dimension ayarlamaya, son PNG dosyasını kaydetmeye kadar tüm adımları kapsadı; yaygın hataları ele aldı ve genişletme fikirleri sundu.

Diğer GS1 Uygulama Tanımlayıcıları, farklı barkod sembolojileri veya daha yüksek çözünürlüklü görüntülerle denemeler yapmaktan çekinmeyin. Bu temelleri kavradığınızda, envanter, nakliye veya perakende için uyumlu barkodlar oluşturmak .NET araç kutunuzun rutin bir parçası haline gelir.

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}