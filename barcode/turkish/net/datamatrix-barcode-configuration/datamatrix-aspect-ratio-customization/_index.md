---
date: 2026-05-30
description: Aspose.BarCode for .NET kullanarak özel bir DataMatrix en-boy oranı ile
  barkod PNG oluşturmayı öğrenin. Barkod üretimi ve boyut özelleştirmesi için adım
  adım rehber.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: DataMatrix En-Boy Oranı Özelleştirme
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Barkod PNG Oluştur – DataMatrix En-Boy Oranı – Aspose.BarCode
url: /tr/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG Oluştur – DataMatrix En‑Boy Oranı – Aspose.BarCode

DataMatrix en‑boy oranı özelleştirilmiş bir **barcode PNG** oluşturmak, belirli düzen kısıtlamalarına uyan **barcode PNG** dosyaları oluşturmanız gerektiğinde yaygın bir gereksinimdir. Bu öğreticide Aspose.BarCode for .NET kullanarak **barcode PNG** dosyaları oluşturma adımlarını, en‑boy oranını neden ayarlamak isteyebileceğinizi ve çıktıyı uygulamanıza göre nasıl ince ayar yapacağınızı göstereceğiz.

## Hızlı Yanıtlar
- **“aspect ratio” neyi kontrol eder?** DataMatrix modüllerinin genişlik‑yükseklik oranını tanımlar.  
- **PNG, JPEG veya SVG çıktı alabilir miyim?** Evet – `Save` yöntemi PNG, JPEG, BMP, GIF, TIFF, SVG ve PDF'yi destekler.  
- **Bu özellik için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Kaç farklı en‑boy oranı değeri geçerlidir?** Herhangi bir pozitif ondalık; tipik değerler 0.5 – 2.0.

## DataMatrix barkod nedir ve neden en‑boy oranını ayarlamalısınız?
DataMatrix barkod, büyük miktarda veriyi kompakt bir kare içinde depolayan iki‑boyutlu bir matris kodudur. **En‑boy oranını** ayarlamak, modülleri yatay olarak uzatmanıza veya sıkıştırmanıza olanak tanır; bu, barkodu dar sütunlara veya geniş etiketlere, tarama güvenilirliğinden ödün vermeden sığdırmanız gerektiğinde faydalıdır.

## Neden Aspose.BarCode ile barcode PNG oluşturmalısınız?
Aspose.BarCode **7 görüntü formatını** — PNG, JPEG, BMP, GIF, TIFF, SVG ve PDF — destekler ve bellekte **50+ giriş ve çıkış formatını** işleyebilir, tüm dosyayı yüklemeden çok sayfalı belgeleri yönetir. Kütüphane, tek bir kod satırıyla DataMatrix barkod oluşturmanıza olanak tanıyan akıcı bir API sunar, piksel‑tam render garantisi verir ve tam .NET uyumluluğu sağlar.

## Önkoşullar

1. **Visual Studio** – herhangi bir yeni sürüm yeterlidir.  
2. **Aspose.BarCode for .NET** – bunu [buradan](https://releases.aspose.com/barcode/net/) indirin.  
3. Diğer Aspose ürün sürümlerini de [buradan](https://releases.aspose.com/) keşfedebilirsiniz.  
4. **.NET Framework / .NET Core** – projeniz desteklenen bir sürümü hedeflemelidir.

## Ad Alanlarını İçe Aktarın

İlk olarak, C# projenizde gerekli ad alanını içe aktarmanız gerekir:

`using Aspose.BarCode.Generation;` imports the namespace that contains the barcode generation classes.  

```csharp
using Aspose.BarCode.Generation;
```

**İpucu:** Bu `using` ifadesini dosyanızın en üstünde tutun, böylece `BarcodeGenerator` sınıfı her zaman kullanılabilir.

## Özel en‑boy oranı ile barcode PNG nasıl oluşturulur?

`BarcodeGenerator`'ı yükleyin, DataMatrix tipini ayarlayın, `AspectRatio` özelliğini düzenleyin ve `Save`'i çağırın. Bu tek‑satır desen, belirttiğiniz oranı koruyan bir barcode PNG oluşturur ve kütüphane otomatik olarak modül ölçeklendirmesini ve sessiz bölgeleri yönetir.

`BarcodeGenerator` creates a barcode image from the specified symbology and data.

### Adım 1: Projenizi Kurun
Visual Studio'da yeni bir konsol veya Windows Forms projesi oluşturun ve Aspose.BarCode DLL'ine referans ekleyin.

### Adım 2: Bir Barcode Generator Başlatın
DataMatrix sembolojisi ve kodlamak istediğiniz veriyle örnekleyin:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

Bu satır, örnek metni içeren bir DataMatrix barkodu üretmeye hazır bir jeneratör oluşturur.

### Adım 3: En‑boy Oranını Özelleştir ve PNG Dosyalarını Kaydet
Artık **en‑boy oranını** değiştirebilir ve her sürümü bir PNG görüntüsü olarak kaydedebilirsiniz:

`AspectRatio`, DataMatrix modüllerinin genişlik‑yükseklik oranını ayarlar.  
`Save`, oluşturulan barkod görüntüsünü seçilen formatta bir dosyaya yazar.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- İlk çağrı kare‑orantılı bir barkod oluşturur (`AspectRatio = 1`).  
- İkinci çağrı barkodu yatay olarak sıkıştırır (`AspectRatio = 0.5`), daha geniş bir görünüm üretir.

Artık raporlar, etiketler veya UI öğelerinde kullanıma hazır, farklı en‑boy oranlarına sahip iki **barcode PNG** dosyanız var.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Oluşturulan görüntü bulanık** | Kaydetmeden önce `Resolution` parametresini artırın (`gen.Parameters.ImageResolution = 300`). |
| **Barkod taranmıyor** | En‑boy oranının 0.5 – 2.0 arasında kalmasını ve yeterli sessiz bölgeyi (`gen.Parameters.Barcode.CodeTextParameters.Margin`) koruyun. |
| **Dosya yolu hataları** | Çıktı yolunu oluşturmak için `Path.Combine` kullanın ve klasörün var olduğunu doğrulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.BarCode for .NET kullanarak diğer barkod türlerinin en‑boy oranını özelleştirebilir miyim?**  
C: Evet, birçok 2‑D barkod (ör. QR, PDF417) belirli parametre nesneleri aracılığıyla en‑boy oranı ayarlamalarını destekler.

**S: Aspose.BarCode for .NET için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, Aspose.BarCode for .NET'in ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.BarCode for .NET için lisansı nereden satın alabilirim?**  
C: Aspose web sitesinden [buradan](https://purchase.aspose.com/buy) lisans satın alabilirsiniz.

**S: Aspose.BarCode for .NET farklı .NET Framework sürümleriyle uyumlu mu?**  
C: Evet, .NET Framework 4.x, .NET Core 3.1+ ve en yeni .NET sürümleriyle çalışır.

**S: Aspose.BarCode for .NET ile farklı formatlarda barkod üretebilir miyim?**  
C: Kesinlikle – PNG, JPEG, BMP, GIF, TIFF, SVG ve PDF doğrudan desteklenir.

## Sonuç

DataMatrix barkodunun **en‑boy oranını** özelleştirmek ve **barcode PNG** dosyaları oluşturmak, Aspose.BarCode for .NET ile oldukça basittir. Yukarıdaki adımları izleyerek projenizin tam düzen gereksinimlerini karşılayan mükemmel boyutlu barkodlar üretebilirsiniz. Çıktıyı daha da özelleştirmek için `Resolution`, `Margin` ve `Color` gibi ek parametreleri keşfedin ve Visual Studio'da taramaya uygun uygulamalar geliştirirken `generate datamatrix barcode` yeteneklerini göz önünde bulundurun.

Daha derin bir keşif için resmi [belgelere](https://reference.aspose.com/barcode/net/) göz atın veya [Aspose.BarCode forumunda](https://forum.aspose.com/c/barcode/13) topluluğa katılın.

---

**Son Güncelleme:** 2026-05-30  
**Test Edilen Versiyon:** Aspose.BarCode 24.12 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [DataMatrix Barkod Oluştur – Aspose.BarCode ile Pro Kılavuz](/barcode/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET ile DataMatrix Barkodları (ECC 200) Nasıl Oluşturulur](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET ile ASCII'de DataMatrix Kodlamasını Ustalaştırma](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}