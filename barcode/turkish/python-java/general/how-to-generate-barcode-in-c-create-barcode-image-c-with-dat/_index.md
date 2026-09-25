---
category: general
date: 2026-08-22
description: Aspose.BarCode kullanarak C#'ta barkod nasıl oluşturulur. Barkod görüntüsü
  oluşturmayı adım adım öğrenin, 2‑D bileşeni devre dışı bırakın ve PNG dosyalarını
  kaydedin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: tr
lastmod: 2026-08-22
og_description: C# ile Aspose.BarCode kullanarak barkod nasıl oluşturulur. Bu öğreticide
  DataBar Expanded kullanarak, 2‑D bileşenini etkinleştirerek barkod görüntüsü nasıl
  oluşturulur ve PNG dosyaları nasıl kaydedilir gösterilmektedir.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: C#'ta barkod nasıl oluşturulur – barkod resmi oluşturma için tam rehber
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: C#'ta barkod nasıl oluşturulur – DataBar Expanded ile barkod resmi oluşturma
url: /tr/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C#'ta barkod nasıl oluşturulur – DataBar Expanded ile barkod görüntüsü c# oluşturma

C#'ta barkod oluşturmak, uygulamalarınıza makine tarafından okunabilir veri yerleştirmeniz gerektiğinde sık karşılaşılan bir gereksinimdir. Bu kılavuz, Aspose.BarCode kütüphanesini kullanarak barkod görüntüsü c# oluşturmayı, 2‑D birleşik bileşeni devre dışı bırakmayı ve sonucu PNG dosyaları olarak kaydetmeyi gösterir.

Tam, çalıştırılabilir bir program, her yapılandırma seçeneğinin açıklaması ve çıktıyı özelleştirme ipuçlarını göreceksiniz. Harici bir belgeye gerek yok—sadece aşağıdaki kod ve bir .NET geliştirme ortamı.

## Önkoşullar

* .NET 6.0 SDK veya daha yeni bir sürüm yüklü  
* Visual Studio 2022 (veya .NET'i destekleyen herhangi bir IDE)  
* Aspose.BarCode for .NET NuGet paketi (`Aspose.BarCode`)  

Paketi aşağıdaki komutla ekleyebilirsiniz:

```bash
dotnet add package Aspose.BarCode
```

Kütüphane, bu öğreticide tüm boyunca kullanılan `BarcodeGenerator` sınıfını sağlar.

## Adım 1: Projeyi kurun ve ad alanlarını içe aktarın

Yeni bir konsol uygulaması oluşturun ve gerekli ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` ad alanı, barkodları yapılandırmak ve oluşturmak için gereken tüm sınıfları içerir.

## Adım 2: DataBar Expanded barkod üretecini başlatın

İlk işlevsel satır, **DataBar Expanded** sembolojisi için bir `BarcodeGenerator` oluşturur ve ham veri dizesini sağlar. Veri dizesi, `(01)12345678901231` şeklindeki GS1 Uygulama Tanımlayıcısı formatını izler.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Üreteci oluşturmak, dahili bitmap tuvalini ayırır, böylece oluşturma işleminden önce boyutu ve görünümü ayarlayabilirsiniz.

## Adım 3: Modül genişliğini (X‑dimension) tanımlayın

X‑dimension, en küçük barkod öğesinin genişliğini kontrol eder. Piksel cinsinden ayarlamak, son görüntü boyutu üzerinde hassas kontrol sağlar.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` piksel değeri ekran görüntüsü için iyidir; daha yüksek çözünürlüklü baskılar için artırın.

## Adım 4: 2‑D birleşik bileşeni devre dışı bırakın

DataBar Expanded, isteğe bağlı olarak ek bilgi taşıyan bir 2‑D bileşen içerebilir. Bu bileşen **olmadan** bir barkod oluşturmak için bayrağı `false` olarak ayarlayın.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Bileşeni devre dışı bırakmak görsel karmaşıklığı azaltır ve daha küçük bir PNG dosyası üretir.

## Adım 5: 2‑D bileşeni olmadan barkod görüntüsünü kaydedin

Bir çıktı dizini seçin ve görüntüyü diske yazın. `BarCodeImageFormat.Png` enumu, kayıpsız bir PNG dosyası sağlar.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Bu çağrıdan sonra, `Databar2DComponentDisabled.png` temiz bir DataBar Expanded barkodu içerir.

## Adım 6: 2‑D birleşik bileşeni etkinleştirin

Ek veri katmanına ihtiyacınız varsa, bayrağı yeniden etkinleştirin. Aynı üreteç örneği yeniden kullanılabilir, bu da ikinci bir nesne oluşturmayı önler.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Adım 7: 2‑D bileşeni etkinleştirilmiş barkod görüntüsünü kaydedin

2‑D bayrağı dışındaki aynı ayarları kullanarak ikinci görüntüyü oluşturun.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Şimdi `Databar2DComponentEnabled.png` ek 2‑D desenli barkodu gösterir.

## Tam kaynak kodu

Aşağıdaki tüm kod parçacığını `Program.cs` dosyasına kopyalayın ve projeyi çalıştırın. Program, belirttiğiniz klasörde her iki PNG dosyasını da oluşturur.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Beklenen çıktı

Programı çalıştırmak şu çıktıyı verir:

```
Barcode images generated successfully.
```

ve iki dosya oluşturur:

* `Databar2DComponentDisabled.png` – 2‑D bileşeni olmadan barkod  
* `Databar2DComponentEnabled.png` – 2‑D bileşeniyle barkod  

Görsel farkı doğrulamak için PNG'leri herhangi bir görüntüleyicide açın.

## Yaygın varyasyonlar ve uç durumlar

| Durum | Ayar |
|-----------|------------|
| **Farklı semboloji** | `EncodeTypes.DatabarExpanded` ifadesini başka bir değerle, örneğin `EncodeTypes.Code128` ile değiştirin. |
| **Daha yüksek çözünürlük** | `XDimension.Pixels` değerini 4 veya 5'e artırın, ya da `barcodeGenerator.Parameters.Image` içinde `Resolution` ayarlayın. |
| **Diğer görüntü formatları** | `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` veya `BarCodeImageFormat.Svg` kullanın. |
| **Web uygulamasında çalıştırma** | Görüntü baytlarını diske kaydetmek yerine doğrudan HTTP yanıtına akıtın. |
| **Bellek yönetimi** | .NET Framework hedefliyorsanız, yönetilmeyen kaynakların serbest bırakılmasını sağlamak için üreteci bir `using` bloğu içinde sarın. |

## Profesyonel ipuçları

* **Üreteci yeniden kullanın** – Sadece 2‑D bayrağını değiştirerek nesneyi yeniden örneklemeyi önlersiniz, bu da CPU döngülerini tasarruf ettirir.  
* **Veriyi doğrulayın** – GS1 verileri tam uzunluk ve kontrol toplamı kurallarına uymalıdır; geçersiz giriş `ArgumentException` fırlatır.  
* **Toplu işleme** – Veri dizesi koleksiyonu üzerinde döngü yapın, gerektiğinde 2‑D bayrağını değiştirin ve her görüntüyü benzersiz bir dosya adıyla kaydedin.  

## Sonuç

Artık C#'ta barkod nasıl oluşturulur ve 2‑D birleşik bileşen üzerinde tam kontrol sağlayarak barkod görüntüsü c# nasıl oluşturulur biliyorsunuz. Örnek, üreteci başlatmayı, X‑dimension'ı yapılandırmayı, bileşeni açıp kapamayı ve PNG dosyalarını kaydetmeyi gösterir. Buradan diğer sembolojileri keşfedebilir, görüntüleri PDF'lere gömebilir veya barkod oluşturmayı ASP.NET Core hizmetlerine entegre edebilirsiniz.

--- 

*Sonraki adımlar*: QR kodları oluşturmaya çalışın, farklı görüntü çözünürlükleriyle deney yapın veya oluşturulan PNG'leri Aspose.PDF kullanarak bir PDF'ye gömün. Bu uzantılar aynı `BarcodeGenerator` API'si üzerine inşa edilir ve iş akışınızı tutarlı tutar.

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Aspose.BarCode for .NET Kullanarak DataMatrix Barkodları Nasıl Oluşturulur – Adım Adım Kılavuz](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET Kullanarak Tek Boyutlu Databar İçin Barkod Yüksekliği Nasıl Oluşturulur ve Ayarlanır](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Aspose.BarCode for .NET Kullanarak Özel En‑Boy Oranı ile Aztec Barkod Nasıl Oluşturulur](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}