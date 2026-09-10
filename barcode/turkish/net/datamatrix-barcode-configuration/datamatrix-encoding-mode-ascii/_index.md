---
date: 2026-06-09
description: Aspose.BarCode for .NET kullanarak ASCII modunda DataMatrix barkodu oluşturmayı
  öğrenin. Bu rehber, C# ile barkodu hızlı bir şekilde üretmeyi gösterir.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix Kodlama Modu (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET ile ASCII modunda DataMatrix barkodu oluşturun
url: /tr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ASCII modunda Aspose.BarCode for .NET ile DataMatrix barkodu oluşturma

## Giriş

Verimli ASCII kodlamasını kullanan **DataMatrix barkodu** görüntüleri oluşturmaya hazır mısınız? Bu öğreticide, Aspose.BarCode for .NET kullanarak ASCII modunda bir DataMatrix barkodu nasıl oluşturacağınızı öğreneceksiniz. Projeyi kurmaktan son görüntüyü kaydetmeye kadar her adımı adım adım göstereceğiz; böylece C# uygulamalarınıza dakikalar içinde barkod üretimini ekleyebilirsiniz.

## Hızlı Yanıtlar
- **DataMatrix için .NET'te en iyi kütüphane hangisidir?** Aspose.BarCode for .NET  
- **Kaç satır kod gerekir?** Temel bir ASCII barkod için yaklaşık 5‑7 satır  
- **Lisans gerekiyor mu?** Geliştirme için ücretsiz deneme çalışır; üretim için lisans gereklidir  
- **Desteklenen platformlar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Boyutu veya renkleri değiştirebilir miyim?** Evet, Aspose.BarCode boyutlar ve ön/arka plan renkleri için özellikler sunar  

## DataMatrix barkodu nedir?
DataMatrix, metin ve ikili verileri kompakt kare bir desen içinde depolayan iki‑boyutlu bir barkoddur.  
DataMatrix barkodu, bilgiyi siyah ve beyaz modüllerden oluşan bir ızgara içinde kodlar ve tek bir sembolde 2.335 alfanümerik karaktere kadar depolanabilir. Üretim, lojistik ve sağlık sektörlerinde yaygın olarak kullanılır çünkü çok küçük boyutlarda bile yüksek tarama başarısı sağlar.

## ASCII modunda DataMatrix barkodu nasıl oluşturulur?
Aspose.BarCode ad alanını yükleyin, bir `BarcodeGenerator` örneği oluşturun, `EncodeMode` değerini **EncodeMode.ASCII** olarak ayarlayın, veri dizesini atayın ve görüntüyü dosyaya yazmak için `Save` metodunu çağırın. Bu yaklaşım, sadece birkaç C# satırıyla ASCII‑only kodlamalı tamamen uyumlu bir DataMatrix barkodu üretir.

## DataMatrix için ASCII kodlaması neden kullanılır?
ASCII modu, düz metin verileri için varsayılan ve en verimli kodlamadır; alfanümerik dizeler için mümkün olan en küçük sembol boyutunu sağlar. 128 ASCII karakterinin tamamını destekler, genişletilmiş modlardan daha hızlı veri işler ve standart ASCII sembollerini bekleyen eski tarayıcılarla maksimum uyumluluk garantiler.

## Önkoşullar

1. **Geliştirme Ortamı** – Visual Studio, Rider veya herhangi bir C#‑uyumlu IDE.  
2. **Aspose.BarCode for .NET** – En son paketi [buradan](https://releases.aspose.com/barcode/net/) indirin.  
   - Documentation: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Community help: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Temel C# bilgisi** – .NET proje yapısına aşina olmak adımları hızlı takip etmenize yardımcı olur.  
4. **Diğer Aspose ürünleri** [burada](https://releases.aspose.com/) bulunabilir.  

## Ad Alanlarını İçe Aktarma

Başlamak için C# dosyanızın en üstüne gerekli `using` yönergelerini ekleyin:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Bu ad alanları, `BarcodeGenerator` sınıfına ve çıktıyı kaydetmek için gereken görüntü‑ile ilgili türlere erişim sağlar.

## Adım 1: Bir Dizin Oluşturun

Oluşturulan barkod görüntülerinin saklanacağı bir klasör seçin. `"Your Directory Path"` ifadesini makinenizde mevcut olan mutlak ya da göreli bir yol ile değiştirin.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Kod, dosya yazma girişiminde bulunmadan önce dizinin var olduğundan emin olur ve çalışma zamanı hatalarını önler.

## Adım 2: Veriyi ASCII Modunda Kodlamak

`BarcodeGenerator` sınıfı barkod görüntülerini oluşturur ve yapılandırır. `DataMatrixEncodeMode` enum’u, DataMatrix sembolleri için kullanılan kodlama algoritmasını seçer.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Kodu çalıştırdıktan sonra, belirttiğiniz klasörde `datamatrix_ascii.png` dosyasını bulacaksınız. Görüntü, `"1234567890"` dizesini kompakt ASCII modunda kodlayan bir DataMatrix barkodu içerir.

## Yaygın sorunlar ve çözümler

- **Dosya erişim hataları** – Uygulamanın hedef klasöre yazma izni olduğundan emin olun. Visual Studio'yu Yönetici olarak çalıştırmak Windows'ta izin sorunlarını çözebilir.  
- **Yanlış sembol boyutu** – Barkod çok büyük ya da küçük görünüyorsa `generator.Parameters.Image.Width` ve `Height` değerlerini ayarlayın veya bu özellikleri atlayarak Aspose'un optimal boyutu otomatik hesaplamasına izin verin.  
- **Desteklenmeyen karakterler** – ASCII modu yalnızca 0‑127 aralığındaki karakterleri kabul eder. Unicode veri için `DataMatrixEncodeMode.Base256` veya başka uygun bir moda geçin.  

## Sıkça Sorulan Sorular

**S: Bunu ticari bir uygulamada kullanabilir miyim?**  
**C:** Evet, üretim kullanımı için geçerli bir Aspose lisansı gereklidir; değerlendirme için ücretsiz deneme mevcuttur.

**S: Kütüphane .NET Core ile çalışıyor mu?**  
**C:** Kesinlikle – Aspose.BarCode .NET Core 3.1+, .NET 5, .NET 6 ve sonraki sürümleri tam olarak destekler.

**S: ASCII modunda kaç karakter kodlayabilirim?**  
**C:** ASCII kodlaması kullanıldığında tek bir DataMatrix sembolüne 2.335 alfanümerik karakter sığabilir.

**S: Barkodun ön plan veya arka plan rengini değiştirebilir miyim?**  
**C:** Evet, `generator.Parameters.Image.ForeColor` ve `BackColor` değerlerini istediğiniz `System.Drawing.Color` ile ayarlayabilirsiniz.

**S: Daha gelişmiş örnekleri nerede bulabilirim?**  
**C:** Resmi dokümantasyon, özel boyutlar, renkler ve hata‑düzeltme seviyeleriyle ilgili onlarca örnek içerir.

## SSS

### S1: Aspose.BarCode for .NET'i C# dışındaki diğer programlama dilleriyle kullanabilir miyim?

**C1:** Aspose.BarCode birden fazla programlama dilini destekler, ancak bu öğreticide C# odaklanılmıştır.

### S2: DataMatrix barkodlarında hangi kodlama modları mevcuttur?

**C2:** DataMatrix barkodları ASCII, C40, Text ve Base256 dahil olmak üzere çeşitli kodlama modlarını destekler. Her mod farklı veri tipleri için uygundur.

### S3: Oluşturulan barkodun boyutu ve rengi gibi görünümünü özelleştirebilir miyim?

**C3:** Evet, Aspose.BarCode barkod görünümünü özelleştirmek için boyut, renk ve daha fazlasını kapsayan geniş bir parametre yelpazesi sunar.

### S4: Aspose.BarCode for .NET'in ücretsiz deneme sürümü mevcut mu?

**C4:** Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) keşfedebilirsiniz.

### S5: Aspose.BarCode for .NET için lisansı nereden satın alabilirim?

**C5:** Lisansı Aspose web sitesinden [burada](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2026-06-09  
**Test Edilen Versiyon:** Aspose.BarCode 24.11 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [DataMatrix Encoding in Bytes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}