---
date: 2026-09-28
description: Aspose.BarCode for .NET ile GS1 kuponları için barcode özel boşluğunu
  nasıl oluşturacağınızı öğrenin ve barcode okunabilirliğini artırın. Adım adım rehberimizi
  izleyin.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 Coupon Supplement Boşluk Yapılandırması
og_description: Aspose.BarCode for .NET ile GS1 kuponları için barcode özel boşluğunu
  nasıl oluşturacağınızı öğrenin ve barcode okunabilirliğini artırın. Adım adım kod
  ve ipuçları dahil.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: GS1 coupon supplement için barcode özel boşluğu oluşturun – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: GS1 kupon supplementi için barcode özel boşluğu nasıl oluşturulur
url: /tr/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 kupon ek alanı yapılandırması

Bu öğreticide Aspose.BarCode for .NET kullanarak **GS1 Kupon Ek Alanı** için barkod özel alanı **oluşturacaksınız**. Ek alanı ayarlamak, düşük çözünürlüklü tarayıcılarda barkod okunabilirliğini **artırmak** veya perakendeci tarafından belirlenen marjlara uymak gerektiğinde önemlidir. Bu kılavuzun sonunda ek alanının neden önemli olduğunu, programlı olarak nasıl ayarlanacağını ve farklı piksel değerleriyle nasıl görüntü oluşturulacağını anlayacaksınız.

## Hızlı cevaplar
- **Ek alan neyi kontrol eder?** Kupon verisi ile barkodun geri kalan kısmı arasındaki boş alanı (piksel cinsinden) tanımlar.  
- **Hangi barkod türü kullanılıyor?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Alan boyutunu değiştirebilir miyim?** Evet – `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` değerini istediğiniz tam sayı değere ayarlayın.  
- **Bu özellik için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans çalışır; üretim için tam lisans gereklidir.  
- **Hangi çıktı formatları destekleniyor?** PNG, JPEG, BMP, GIF, TIFF ve daha fazlası `BarCodeImageFormat` aracılığıyla.

## GS1 kupon ek alanı nedir?
GS1 Kupon Ek Alanı, GS1‑Databar kupon barkodlarında görülen tanımlı boş bir bölgedir. Perakende sistemleri, bu alanı tarama güvenilirliğini artırmak ve ek veri etrafında minimum bir marj gerektiren sektör spesifikasyonlarına uymak için kullanır.

## Neden ek alanı yapılandırmalısınız?
Ek alan doğrudan **barkod okunabilirliğini artırır** ve katı perakende yönergelerini karşılamanıza yardımcı olur. Ek piksel ekleyerek düşük çözünürlüklü tarayıcılarda hatalı okuma olasılığını azaltır, farklı etiket boyutlarında tutarlı tarama sağlar ve baskı düzeninde barkodu dengelemek için görsel esneklik sunar.

## Önkoşullar

Aspose.BarCode for .NET ile GS1 Kupon Ek Alanı yapılandırmasına başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Visual Studio** – .NET geliştirme için birincil IDE.  
2. **Aspose.BarCode for .NET** – Kütüphaneyi [Aspose.BarCode for .NET belgeleri](https://reference.aspose.com/barcode/net/) adresinden indirin.  
3. **.NET Framework veya .NET 5+** – C# ve .NET çalışma zamanı hakkında temel bilgi gereklidir.

Ortam hazır olduğuna göre, uygulamaya geçelim.

## Ad alanlarını içe aktar

`Aspose.BarCode.Generation` ad alanı, `BarcodeGenerator` sınıfını ve ilgili ayarları içerir.

```csharp
using Aspose.BarCode;
```

## Adım 1: yolu tanımlayın

Oluşturulan görüntülerin kaydedileceği klasörü seçin. Yol, işletim sisteminize uygun dizin ayırıcıyla (\\ veya /) sonlanmalıdır.

```csharp
string path = "Your Directory Path";
```

## Adım 2: GS1 kupon ek alanı yapılandırmasını oluşturun

Aşağıdaki kod parçacığı bir barkod oluşturur, X‑boyutunu ayarlar ve ek alanı düzenler.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

Bu örnekte:

1. **Create** `BarcodeGenerator` örneğini `UpcaGs1DatabarCoupon` türü için oluştururuz.  
2. **Set** X‑boyutunu 2 piksel olarak ayarlar, bu en dar çubuk genişliğini belirler.  
3. **Adjust** `SupplementSpace.Pixels` özelliğini 30 px olarak ayarlar, bir görüntü üretir, ardından 50 px ile tekrar eder.  

Baskı iş akışınıza uyacak şekilde diğer piksel değerleriyle denemeler yapabilirsiniz.

## Yaygın sorunlar ve ipuçları

- **Geçersiz yol** – `path` değişkeninin işletim sisteminize uygun bir son eğik çizgi (`\` veya `/`) ile bittiğinden emin olun.  
- **Yetersiz izinler** – Visual Studio'yu Yönetici olarak çalıştırın veya uygulamanın yazma iznine sahip bir klasör seçin.  
- **Yanlış veri formatı** – Veri dizesi GS1 sözdizimini (`(8110)` ek tanımlayıcıyı gösterir) izlemelidir.  

## Bunun işiniz için önemi nedir

Aspose.BarCode **60’tan fazla barkod sembolünü** destekler ve **10.000 × 10.000 piksel** boyutuna kadar görüntü oluşturabilir, bellek tükenmeden. Büyük ölçekli perakende dağıtımları için bu, tipik sunucu donanımında bir görüntü başına bir saniyenin altında işlem süresiyle yüksek çözünürlüklü GS1 kuponlarını toplu olarak oluşturabileceğiniz anlamına gelir.

## Sıkça Sorulan Sorular

**S: Barkodlarda GS1 Kupon Ek Alanının amacı nedir?**  
C: Ek veri etrafında zorunlu bir boş marj ekleyerek tarayıcı güvenilirliğini artırır ve perakendeci tarafından belirlenen minimum genişlik gereksinimlerini karşılar.

**S: Aspose.BarCode for .NET ile GS1 Kupon Ek Alanının genişliğini özelleştirebilir miyim?**  
C: Evet, `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` değerini istediğiniz tam sayıya ayarlayın; kütüphane değişikliği anında oluşturulan görüntüye uygular.

**S: Aspose.BarCode for .NET için ek belgeler ve destek nereden bulunur?**  
C: [Aspose.BarCode for .NET belgeleri](https://reference.aspose.com/barcode/net/) adresine bakın ve topluluk yardımı için [Aspose.BarCode forumunu](https://forum.aspose.com/c/barcode/13) ziyaret edin.

**S: Aspose.BarCode for .NET hem yeni başlayanlar hem de deneyimli geliştiriciler için uygun mu?**  
C: Kesinlikle. API, hızlı görevler için basit yöntemler ve ince ayarlı barkod üretimi için gelişmiş seçenekler sunar.

**S: Özelliklerini değerlendirmek için Aspose.BarCode for .NET için geçici bir lisans alabilir miyim?**  
C: Evet, [Aspose geçici lisans web sitesinden](https://purchase.aspose.com/temporary-license/) bir deneme lisansı talep edebilirsiniz.

## Sonuç

Yukarıdaki adımları izleyerek **GS1 Kupon Ek Alanı** için **barkod özel alanı oluşturmayı** öğrendiniz; bu, **barkod okunabilirliğini artırmak** ve perakende standartlarını karşılamak için kritik bir tekniktir. Kodu mevcut tarama çözümlerinizle bütünleştirin, farklı piksel değerleriyle deney yapın ve Aspose.BarCode for .NET tarafından sunulan diğer barkod türlerini keşfedin.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## İlgili Eğitimler

- [Aspose.BarCode Databar barkodu .NET API kullanarak oluşturma – Satır ve Sütun Yapılandırması](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Aspose.BarCode for .NET kullanarak DataMatrix Barkodları Nasıl Oluşturulur – Adım Adım Kılavuz](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}