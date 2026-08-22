---
category: general
date: 2026-08-22
description: Aspose.BarCode ile C#’ta PDF417 barkod oluşturmayı, barkod boyutunu ayarlamayı,
  sütunları düzenlemeyi ve kompakt modu etkinleştirmeyi öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: tr
lastmod: 2026-08-22
og_description: C# ile Aspose.BarCode kullanarak PDF417 barkod oluşturun. Bu kılavuz,
  barkod boyutunu ayarlamayı, sütunları kontrol etmeyi ve daha küçük bir görüntü için
  kompakt modu etkinleştirmeyi gösterir.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: C#'ta PDF417 barkod oluşturma – boyut, sütun ve kompakt modu ayarlama
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: C#'ta PDF417 barkodu nasıl oluşturulur ve barkod boyutu nasıl ayarlanır
url: /tr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta PDF417 barkodu nasıl oluşturulur ve barkod boyutu nasıl ayarlanır

Bir .NET uygulamasında **PDF417 barkodu oluşturmanız** gerekiyorsa, bu kılavuz size sürecin tamamını gösterir. Aspose.BarCode ile **PDF417 nasıl oluşturulur**, **barkod boyutu nasıl ayarlanır** ve raporlara ya da mobil uygulamalara gömülebilecek kompakt bir PNG nasıl üretilir, adım adım göreceksiniz.

Barkod oluşturmak ayrı bir grafik editörü gerektirmez. Bu öğreticinin sonunda, ihtiyacınız olan tam boyutlarda bir PDF417 resmi üreten, aşağı akışta kullanılmaya hazır tam işlevsel bir C# yönteminize sahip olacaksınız.

## Öğrenecekleriniz

* Aspose.BarCode kütüphanesini kurma ve referans ekleme.
* PDF417 barkod üreticisi oluşturma ve kodlanacak metni belirleme.
* X‑dimension ve sütun sayısını yapılandırarak **barkod boyutunu ayarlama**.
* Sembolü küçültmek için kompakt (kısaltılmış) modu etkinleştirme.
* Sonucu PNG dosyası olarak kaydetme.
* Okunamayan kodlar ve aşırı büyük görüntüler gibi yaygın sorunları giderme.

### Önkoşullar

* .NET 6.0 veya üzeri (API, .NET Framework 4.6+ ile de çalışır).
* C# ve Visual Studio (veya herhangi bir C# IDE) hakkında temel bilgi.
* Geçerli bir Aspose.BarCode lisansı (ücretsiz değerlendirme sürümü test için yeterlidir).

> **Pro tip:** Bir döngü içinde birden çok barkod oluşturacaksanız, tek bir `BarcodeGenerator` örneğini yeniden kullanın ve yalnızca `CodeText` özelliğini değiştirin. Bu, bellek tahsislerini azaltır.

## Aspose.BarCode ile PDF417 barkodu oluşturma

İlk adım, PDF417 sembolü için `BarcodeGenerator` nesnesini başlatmaktır. Bu nesne, tüm barkod işlemleri için giriş noktasıdır.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Neden önemli*: `EncodeTypes.Pdf417` kütüphaneye PDF417 standardını kullanmasını söyler; bu standart büyük veri hacimleri ve hata düzeltme desteği sunar. Yapıcı ayrıca kodlamak istediğiniz veriyi de alır, böylece daha sonra ayrı bir `CodeText` atamasına gerek kalmaz.

## Barkod boyutu ve sütun sayısını ayarlama

PDF417 sembolleri, küçük dikdörtgen modüllerden oluşan satır ve sütunlardan meydana gelir. Modül genişliğini (X‑dimension) ve sütun sayısını kontrol ederek genel boyutları hassas bir şekilde ayarlayabilirsiniz.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Açıklama*:  
* **X‑dimension** (`Pixels`) her bir modülün ne kadar geniş olacağını belirler. Daha küçük değerler daha sıkı bir barkod üretirken, daha büyük değerler düşük çözünürlüklü tarayıcılarda okunabilirliği artırır.  
* **Columns** yatay yerleşimi kontrol eder. Daha az sütun barkodu daha uzun, daha çok sütun ise daha geniş yapar. Bu iki ayarı birlikte değiştirerek ihtiyacınız olan **barkod boyutunu ayarlamış** olursunuz.

## Daha küçük bir barkod için kompakt modu etkinleştirme

PDF417, gereksiz boşlukları kaldıran ve genel alanı azaltan bir “compact” (veya truncated) modu içerir. Bu, ekran alanı sınırlı olduğunda özellikle faydalıdır.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Neden kısaltma etkinleştirilmeli?*  
`Truncate` `true` olduğunda, üretici durdurma desenini ve çoğu tarama senaryosu için gerekli olmayan bazı hata‑düzeltme kod kelimelerini atlar. Ortaya çıkan görüntü, veri bütünlüğünden ödün vermeden yaklaşık %15‑20 daha küçüktür.

## Barkodu PNG olarak kaydetme

Boyut ve modu yapılandırdıktan sonra barkodu diske yazın. PNG kayıpsızdır, böylece modül kenarları keskin kalır.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

`CompactPdf417.png` dosyası, önceki adımlarda belirlediğiniz boyutlara uyan net bir PDF417 sembolü içerecektir.

### Beklenen çıktı

Kaydedilen PNG’yi açtığınızda, her bir modül 2 px genişliğinde olmak üzere üç sütunlu, dikey yönlendirilmiş bir PDF417 barkodu görmelisiniz; toplam boyut yaklaşık **120 × 240 px** (genişlik × yükseklik) olacaktır. Görüntüyü herhangi bir standart PDF417 okuyucu ile taradığınızda, “Sample text for PDF417” metni geri dönecektir.

## Yaygın tuzaklar ve nasıl önlenir

| Belirti | Muhtemel neden | Çözüm |
|---------|----------------|------|
| Barkod okunamıyor | Tarayıcı için X‑dimension çok küçük | `XDimension.Pixels` değerini 3 veya 4 yapın |
| Görüntü UI’da çok geniş | Çok fazla sütun ayarlanmış | `Pdf417.Columns` değerini azaltın veya `Truncate` etkinleştirin |
| `ArgumentOutOfRangeException` hatası | Sütun sayısı negatif ya da sıfır | `Columns` değerinin pozitif bir tam sayı (minimum 1) olduğundan emin olun |
| PNG dosyası boş | Çıktı yolu yok ya da yazma izni eksik | Dizin var mı kontrol edin ve uygulamanın yazma izni olduğundan emin olun |

> **Pro tip:** `Save()` çağırmadan önce `barcodeGenerator.ValidateParameters()` kullanarak yapılandırma hatalarını erken yakalayabilirsiniz.

## Tam, çalıştırılabilir örnek

Aşağıda, yukarıdaki tüm adımları içeren bağımsız bir konsol programı yer alıyor. Yeni bir C# projesine kopyalayın, Aspose.BarCode NuGet paketini restore edin ve sonucu görmek için çalıştırın.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Programı çalıştırmak**, çalıştırılabilirin çalışma dizininde `CompactPdf417.png` oluşturur. Görüntüyü bir mobil uygulama (ör. “Barcode Scanner”) ile tarayarak kodlanmış metnin kaynak dizeyle aynı olduğunu doğrulayın.

## Sonraki adımlar ve ilgili konular

* **Hata düzeltme seviyesini artırma** – gürültülü taramalarda `Pdf417.ErrorLevel` ayarını değiştirin.  
* **Yönlendirmeyi değiştirme** – yatay bir düzen gerekiyorsa `Pdf417.Rotate` değerini `RotationAngle.Rotate90` yapın.  
* **Barkodu bir PDF’e gömme** – Aspose.PDF ile Aspose.BarCode’u birleştirerek resmi doğrudan belgeye yerleştirin.  
* **Diğer 2‑D barkodları oluşturma** – aynı `BarcodeGenerator` sınıfı DataMatrix, QR ve Aztec kodlarını da destekler; sadece `EncodeTypes.Pdf417` yerine istediğiniz sembolü kullanın.

**PDF417 barkodu oluşturma** tekniklerini ustalaşarak, biletleme, envanter etiketleme ve güvenli veri iletimi gibi geniş bir .NET uygulama yelpazesinde otomasyonu sağlayabilirsiniz.

## Sonuç

Artık C#’ta **PDF417 barkodu nasıl oluşturulur**, **barkod boyutu nasıl tam olarak ayarlanır**, sütunlar nasıl yapılandırılır, kompakt mod nasıl etkinleştirilir ve sonuç PNG olarak nasıl kaydedilir, biliyorsunuz. Bu ayarları herhangi bir UI kısıtlamasına veya tarama gereksinimine uyacak şekilde uygulayın ve gerektiğinde diğer barkod formatlarına da genişletin. Kodlamanın tadını çıkarın!

## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak tam çalışan kod örnekleri ve adım adım açıklamalar içerir.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}