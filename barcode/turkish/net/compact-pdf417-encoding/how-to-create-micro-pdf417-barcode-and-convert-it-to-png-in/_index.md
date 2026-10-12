---
category: general
date: 2026-10-12
description: C# kullanarak mikro PDF417 barkod oluşturmayı ve barkodu PNG'ye dönüştürmeyi
  öğrenin. Tam kod ve ipuçlarıyla adım adım rehber.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: tr
lastmod: 2026-10-12
og_description: C# ile mikro PDF417 barkod oluşturun ve barkodu PNG’ye dönüştürün.
  Hem standart hem de GS1 sürümlerini oluşturmak için bu kapsamlı rehberi izleyin.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Mikro PDF417 barkod oluştur ve PNG'ye dönüştür – C# öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: C# ile mikro PDF417 barkod oluşturma ve PNG'ye dönüştürme
url: /tr/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta micro PDF417 barkod oluşturma ve PNG'ye dönüştürme

Bir .NET uygulamasında **micro PDF417 barkod oluşturmanız** gerekiyorsa, bu öğretici size tam olarak nasıl yapılacağını gösterir. Hem standart Micro PDF417 barkodu hem de GS1‑uyumlu bir sürüm üreten eksiksiz, çalıştırılabilir bir örnek göreceksiniz ve ardından **barkodu PNG'ye dönüştürerek** baskı veya web gösterimi gibi sonraki kullanım için hazır hale getireceksiniz.

Barkod oluşturmak yalnızca tek bir yöntemi çağırmaktan daha fazlasıdır—doğru modül boyutunu, sütun sayısını ve kodlama formatını seçmek tarama güvenilirliğini belirler. Bu rehberin sonunda her ayarın neden önemli olduğunu ve kendi projelerinizde nasıl ayarlayabileceğinizi anlayacaksınız.

## Önkoşullar

| Gereksinim | Sebep |
|-------------|--------|
| .NET 6.0 SDK or later | C# konsol uygulaması için çalışma zamanını sağlar |
| Visual Studio 2022 (or any C# IDE) | Düzenleme ve hata ayıklamayı kolaylaştırır |
| **Aspose.BarCode for .NET** NuGet package | `BarcodeGenerator`, `EncodeTypes` ve `BarCodeImageFormat` sınıflarını sağlar |
| Write permission to the output folder | PNG dosyaları oluşturan `Save` çağrıları için gereklidir |

Aspose.BarCode paketini CLI üzerinden ekleyebilirsiniz:

```bash
dotnet add package Aspose.BarCode
```

## Adım 1: Minimum bir konsol projesi kurun

Yeni bir konsol projesi oluşturun ve barkod kütüphanesini referans gösterin. Aşağıdaki `Program.cs` ihtiyacınız olan tüm kodu içerir; harici dosya gerekmez.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Her satırın önemi

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – İlk olan basit bir Micro PDF417 barkod oluşturur, ikincisi ise GS1 standartlarını izleyerek Uygulama Tanımlayıcılarını (AIs) gömer. Alt sisteminizin GS1 verisi bekleyip beklemediğine göre seçim yapın.
* **`XDimension.Pixels = 2`** – Modül genişliğini kontrol eder. Daha küçük değerler daha yoğun bir görüntü oluşturur ancak düşük çözünürlüklü tarayıcılarda okunamaz hale gelebilir. Çoğu etiket yazıcısı için iki piksel güvenli bir varsayılandır.
* **`Pdf417.Columns = 4`** – Micro PDF417, sütun sayısını sınırlamanıza izin verir, böylece toplam genişlik azalır. Dört sütun, kısa veri yükleri için veri kapasitesinden ödün vermeden barkodu kompakt tutar.
* **`BarCodeImageFormat.Png`** – PNG, kayıpsız kaliteyi korur, barkod netliği için gereklidir. Bu yüzden **barkodu PNG'ye dönüştürüyoruz** JPEG yerine.

## Adım 2: Programı çalıştırın ve çıktıyı doğrulayın

1. Projeyi derleyin: `dotnet build`.
2. Çalıştırın: `dotnet run`.

Aşağıdaki gibi konsol mesajları görmelisiniz:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Oluşturulan PNG dosyalarını herhangi bir görüntüleyici ile açın. Her iki görüntü de taramaya hazır, net ve yüksek kontrastlı bir barkod gösterir.

### Beklenen görsel sonuç

| Barkod türü | Görünüm |
|--------------|------------|
| **Micro PDF417** | 4 sütunlu küçük dikdörtgen desen, çoğu 2‑D barkod tarayıcısı tarafından okunabilir. |
| **GS1 Micro PDF417** | Aynı boyutta ancak GS1 AIs kodlar; GS1'i anlayan bir tarayıcı GTIN ve seri numarasını döndürür. |

Eğer bir tarayıcı görüntüyü okuyamazsa, `XDimension.Pixels` değerini **3** veya **4** olarak artırmayı, ya da standart Micro PDF417 için sütun sayısını azaltmayı deneyin.

## Yaygın tuzaklar ve nasıl önlenir

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| Baskı sonrası bulanık barkod | Düşük DPI yazıcı ayarları | PNG'yi 300 dpi veya daha yüksek bir çözünürlükte dışa aktarın, ya da ölçeklemeyi yazıcı sürücüsüne bırakın. |
| Tarayıcı “geçersiz veri” döndürüyor | Eksik veya hatalı biçimlendirilmiş GS1 AI formatı | Her AI'nın parantez içinde olduğundan ve GS1 spesifikasyonuna (ör. `(01)` GTIN‑14 için) uygun olduğundan emin olun. |
| Görüntü dosyası oluşturulmadı | Çıktı klasöründe yazma izni yok | Programı yükseltilmiş yetkilerle çalıştırın veya `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` gibi bir klasör seçin. |
| Barkod etiket için çok büyük | Varsayılan sütun sayısı çok yüksek | `Pdf417.Columns` değerini azaltın (ör. **3**) veya `XDimension`'ı artırarak toplam boyutu küçültün. |

## Örneği genişletmek

* **Different image formats** – İş akışınız gerektiriyorsa `BarCodeImageFormat.Png` yerine `Jpeg` veya `Bmp` kullanın. PNG, kayıpsız kalite için en iyi seçim olmaya devam eder.
* **Dynamic data** – Kullanıcı girişi veya veritabanı değerlerini `BarcodeGenerator` yapıcısına geçirerek barkodları anında oluşturun.
* **Batch generation** – Oluşturma mantığını bir döngü içinde sarın; CSV dosyasından satırları okuyup her barkodu benzersiz bir dosya adıyla kaydedin.

## Sonuç

Artık C#'ta **micro PDF417 barkod oluşturmayı** ve hem standart hem de GS1‑uyumlu senaryolar için **barkodu PNG'ye dönüştürmeyi** biliyorsunuz. Eksiksiz, çalıştırılabilir kod, temel ayarları—X boyutu, sütun sayısı ve kodlama türü—gösteriyor, böylece çözümü kompakt, yüksek kalite 2‑D barkodlara ihtiyaç duyan herhangi bir .NET projesine uyarlayabilirsiniz.

*Sonraki adımlar*: Aspose.BarCode tarafından desteklenen diğer sembolojileri keşfedin (ör. QR, DataMatrix), yüksek çözünürlüklü baskı için farklı `XDimension` değerleriyle deney yapın veya oluşturulan PNG'leri talep üzerine barkod hizmeti veren bir web API'ye entegre edin.

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, adım adım açıklamalarla eksiksiz çalışan kod örnekleri içerir ve ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olur.

- [C#'ta micro pdf417 barkod oluşturma ve PNG olarak kaydetme](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [C#'ta barkod PNG oluşturma – GS1 Micro PDF417 tam rehberi](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [C#'ta Micro PDF417 Barkod Oluşturma – Tam Kılavuz](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}