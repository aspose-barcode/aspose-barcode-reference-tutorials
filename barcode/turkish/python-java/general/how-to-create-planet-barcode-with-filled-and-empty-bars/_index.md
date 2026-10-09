---
category: general
date: 2026-09-29
description: C#'ta dolu ve boş çubukları olan gezegen barkodu oluşturma – Aspose.Barcode
  ile adım adım rehber.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: tr
lastmod: 2026-09-29
og_description: C#'ta planet barkodunu hızlı bir şekilde oluşturun. Dolu çubukları
  nasıl oluşturacağınızı, boş çubuklara nasıl geçeceğinizi ve Aspose.Barcode ile X
  boyutunu nasıl ayarlayacağınızı öğrenin.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Dolu ve boş çubuklarla gezegen barkodu oluşturma – C# öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Dolu ve boş çubuklarla gezegen barkodu nasıl oluşturulur
url: /tr/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planet barkodunu dolu ve boş çubuklarla nasıl oluşturulur

C#'ta **planet barkodu** görüntüleri oluşturmanız gerekiyorsa, bu kılavuz dolu‑çubuk ve boş‑çubuk sürümlerini nasıl oluşturacağınızı tam olarak gösterir. Çubuk genişliğini (X‑dimension) nasıl ayarlayacağınızı, `FilledBars` özelliğini nasıl değiştireceğinizi ve sonuçları PNG dosyaları olarak nasıl kaydedeceğinizi—tüm bunları Aspose.Barcode kütüphanesi ile göreceksiniz.

Posta barkodları oluşturmak, gönderi sistemleri, posta listesi uygulamaları ve lojistik panoları için yaygın bir gereksinimdir. Bu öğreticinin sonunda raporlar, e‑mailler veya çıktılar içinde gömebileceğiniz iki kullanıma hazır PNG dosyanız olacak.

## Önkoşullar

| Gereksinim | Neden Önemli |
|-------------|----------------|
| .NET 6.0 veya üzeri | C# örneği için çalışma zamanını sağlar. |
| Visual Studio 2022 (veya herhangi bir C# IDE) | Kodu derlemenizi ve çalıştırmanızı sağlar. |
| **Aspose.Barcode for .NET** NuGet paketi | `BarcodeGenerator` sınıfı ve `EncodeTypes.Planet` sağlar. `dotnet add package Aspose.Barcode` komutuyla kurun. |
| Diskte bir klasöre yazma izni | `Save` yöntemi belirtilen yola PNG dosyaları yazar. |

## Adım 1: Projeyi kurun ve ad alanlarını içe aktarın

Yeni bir konsol projesi oluşturun (veya kodu mevcut bir projeye ekleyin) ve Aspose.Barcode ad alanına referans verin.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Bu `using` yönergeleri, öğreticide ihtiyaç duyulan `BarcodeGenerator`, `EncodeTypes` ve görüntü‑formatı enum'larına erişmenizi sağlar.

## Adım 2: Varsayılan (dolu) çubuklarla Planet barkodu oluşturun

İlk barkod, çubukları dolduran kütüphanenin varsayılan render'ını kullanır.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Neden bu çalışır:**  
`EncodeTypes.Planet`, Aspose.Barcode'a **Planet** sembolünü kullanmasını söyler; bu, United States Postal Service tarafından kullanılan bir posta barkodudur. `XDimension` özelliği her bir çubuğun genişliğini kontrol eder; 4 piksel olarak ayarlandığında standart etiket yazıcılarında iyi bir baskı elde edilir. Varsayılan olarak `FilledBars` **true** olduğundan çubuklar katı görünür.

## Adım 3: Boş çubuklarla Planet barkodu oluşturun

Aynı veriyi *boş* çubuklarla üretmek için diğer ayarları aynı tutarken sadece `FilledBars` bayrağını tersine çevirmeniz yeterlidir.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Neden bu önemli:**  
Bazı posta sistemleri, barkodun koyu arka planlarda veya zıt renk şemalarında daha okunabilir olmasını sağlamak için **boş‑çubuk** stilini ister. `FilledBars = false` ayarlandığında jeneratör yalnızca çubukların dış hatlarını çizer, iç kısımları şeffaf bırakır.

## Beklenen çıktı

Programı çalıştırdıktan sonra `C:\Barcodes` klasörü (veya seçtiğiniz yol) iki PNG dosyası içerir:

| Dosya | Görsel açıklama |
|------|---------------------|
| `PlanetFilledBars.png` | Çubuklar beyaz bir arka planda katı siyah dikdörtgenlerdir. |
| `PlanetEmptyBars.png`  | Çubuklar siyah dış hatlara sahiptir; her bir çubuğun iç kısmı şeffaftır (arka planı gösterir). |

Her iki görüntü de aynı `"123456"` sayısal dizesini kodlar ve 4 piksel çubuk genişliğini paylaşır; dolgu stilinin dışındaki tüm görünümler tutarlıdır.

## Yaygın varyasyonlar ve kenar durumları

### Çubuk genişliğini değiştirme

Etiket yazıcınız farklı bir çubuk genişliği bekliyorsa `XDimension.Pixels` değerini değiştirin. Yüksek çözünürlüklü yazıcılar için **2** veya **3** piksel, düşük çözünürlüklü yazıcılar için **5** veya **6** piksel tercih edilebilir; bu, tarama güvenilirliğini artırabilir.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Farklı bir görüntü formatı kullanma

Aspose.Barcode PNG, JPEG, BMP, GIF ve TIFF formatlarını destekler. İş akışınıza uygun olması için `BarCodeImageFormat.Png` ifadesini başka bir enum değeriyle değiştirin.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Döngü içinde birden fazla barkod oluşturma

Bir posta listesi gibi birden çok Planet barkoduna ihtiyacınız olduğunda, jeneratör mantığını bir `foreach` döngüsü içinde sarın ve her yinelemede veri dizesini değiştirin.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Geçersiz girdi işleme

Planet sembolü yalnızca **5‑8** basamaklı sayısal dizeleri kabul eder. Geçersiz bir değer sağlandığında `ArgumentException` fırlatılır. Bunu basit bir doğrulama yöntemiyle önleyin.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Pro ipucu: Barkodu bir tarayıcı emülatörü ile doğrulayın

Aspose.Barcode, oluşturulan görüntünün orijinal veriye geri çözüldüğünü doğrulamak için kullanabileceğiniz bir `BarcodeReader` sınıfı içerir.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Çıktı her iki dosya için de `"123456"` gösteriyorsa barkod doğru şekilde oluşturulmuştur.

## Sonuç

Artık C#'ta **planet barkodu** görüntülerini hem dolu hem de boş çubuk stilleriyle nasıl oluşturacağınızı, **Planet barkodu XDimension** değerini nasıl kontrol edeceğinizi ve **Aspose.Barcode** kütüphanesiyle PNG formatında nasıl kaydedeceğinizi biliyorsunuz. Çubuk genişliğini ayarlayın, görüntü formatını değiştirin veya herhangi bir posta‑kodu iş akışına uyması için değer koleksiyonları üzerinde döngü kurun.

Sonraki adımda şunları keşfedebilirsiniz:

* **Barkodun altına insan tarafından okunabilir metin ekleme** (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Barkodları PDF belgelerine gömme** Aspose.PDF ile.
* **USPS POSTNET** veya **Intelligent Mail** gibi diğer posta sembolojilerini oluşturma.

Parametrelerle deney yapmaktan ve kodu gönderi ya da posta sisteminize entegre etmekten çekinmeyin. İyi kodlamalar!

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak tam çalışan kod örnekleri ve adım‑adım açıklamalar içerir.

- [C#'ta Planet Barkodu Oluşturma – Tam Adım‑Adım Kılavuz](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [C#'ta planet barkodu oluşturma – tam programlama kılavuzu](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [C# Barkod Üreteci – Planet barkodu ve RM4SCC örneği](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}