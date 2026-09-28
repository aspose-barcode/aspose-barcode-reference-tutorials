---
date: 2026-09-28
description: Aspose.BarCode for .NET ile 2d matrix barcode oluşturmayı öğrenin – DotCode
  barkodlarını genişletilmiş kod metniyle oluşturmak için adım adım bir rehber.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode Genişletilmiş Kod Metni Yapılandırması
og_description: Aspose.BarCode for .NET kullanarak 2d matrix barcode oluşturmayı öğrenin.
  Bu rehber, DotCode barkodlarını genişletilmiş kod metniyle oluşturmanın adım adım
  nasıl yapılacağını gösterir.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Aspose.BarCode for .NET ile 2d matrix barcode oluşturun
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Aspose.BarCode for .NET ile 2d matrix barcode nasıl oluşturulur
url: /tr/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET ile 2d matris barkodu nasıl oluşturulur

## Giriş

Barkod oluşturma ve yönetimi alanında, Aspose.BarCode for .NET, **50+ giriş ve çıkış formatı** destekleyen ve tüm dosyayı belleğe yüklemeden çok sayfalı belgeleri işleyebilen çok yönlü bir çözüm olarak öne çıkar. Ürün takibi, envanter kontrolü veya veri yoğun uygulamalar için barkodlara ihtiyacınız olsun, DotCode gibi **2d matris barkodu** oluşturmak ve genişletilmiş kod metni kullanmak, hem metinsel hem de ikili yükleri kompakt bir kare sembolde gömmenizi sağlar. Bu öğretici, genişletilmiş kod metnini adım adım oluşturmanızı ve son görüntüyü oluşturmanızı gösterir.

## Hızlı cevaplar
- **“dotcode extended codetext oluşturma” ne anlama geliyor?** Bu, FNC1, ECICodetext, düz metin ve sembol ayırıcılarını tek bir genişletilmiş yük içinde içeren bir DotCode barkodu oluşturmak anlamına gelir.  
- **Hangi kütüphane gereklidir?** Aspose.BarCode for .NET.  
- **Bir lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans çalışır; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.

## dotcode extended codetext nasıl oluşturulur

Projenizi yükleyin, dizini ayarlayın, genişletilmiş kod metnini oluşturun ve görüntüyü oluşturun – tümü on bir satırdan az bir kodla. Aşağıdaki doğrudan cevap tüm süreci özetler:

`BarcodeGenerator`'ı `EncodeTypes.DotCode` ile yükleyin, `DotCodeExtendedCodetextBuilder` kullanarak genişletilmiş kod metnini oluşturun (FNC1, ECICodetext, düz metin ve FNC3 ayırıcıları ekleyerek), ardından PNG dosyası yazmak için `Save` metodunu çağırın. Bu sıralama, tek bir çağrıda tam uyumlu bir 2d matris barkodu oluşturur.

## dotcode extended codetext nedir?

**dotcode extended codetext**, FNC1 tanımlayıcıları, ECICodetext, düz metin ve FNC3 ayırıcıları gibi birden çok veri segmentini birleştirerek DotCode'un çözebileceği tek bir yük oluşturan birleşik bir dizedir. Tek bir 2d matris barkodu içinde çok dilli metin, ikili veri ve yapılandırılmış veri kodlamayı mümkün kılar; bu da tedarik zinciri, sağlık ve IoT senaryoları için idealdir.

## Bu görev için Aspose.BarCode neden kullanılmalı?

Aspose.BarCode, tipik sunucu donanımında **saniyede 500 sayfaya kadar** işleyebilir ve DotCode dahil **30'dan fazla barkod sembolojisini** destekler. `GetExtendedCodetext` API'si kontrol karakterlerinin doğru yerleştirilmesini garanti eder, manuel dize birleştirme hatalarını ortadan kaldırır ve ISO/IEC 24724 uyumluluğunu sağlar. Ayrıca, yerleşik hata düzeltme ve otomatik sessiz bölge (quiet‑zone) yönetimi sunarak manuel ayarlamaya olan ihtiyacı azaltır.

## Önkoşullar

- **Aspose.BarCode for .NET** – [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) adresinden indirin.  
- .NET geliştirme ortamı (Visual Studio 2022 veya daha yeni sürüm önerilir).  
- İsteğe bağlı: değerlendirme için geçici bir lisans dosyası.

## Ad alanlarını içe aktar

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Bu ad alanları örnek için gerekli olan `BarcodeGenerator` sınıfını ve `DotCodeExtendedCodetextBuilder` yardımcı sınıfını ortaya çıkarır.

```csharp
using Aspose.BarCode.Generation;
```

Artık önkoşulları ele aldığımıza göre, DotCode Extended Code Text oluşturma sürecini adım adım bir kılavuza ayıralım.

## Adım 1: dizin yolunu tanımla

Oluşturulan PNG'nin nereye kaydedileceğini belirtin. Uygulamanızın yazabileceği mutlak veya göreli bir yol kullanın.

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` ifadesini sisteminizdeki gerçek yol ile değiştirin.

## Adım 2: dotcode extended codetext oluştur

`DotCodeExtendedCodetextBuilder` sınıfı çeşitli segmentleri tek bir genişletilmiş kod metni dizesine birleştirir.

DotCode Extended Code Text oluşturmak için şu alt adımları izleyin:

### 2.1 fnc1 format tanımlayıcısını ekle

FNC1 format tanımlayıcısı yeni bir veri alanının başlangıcını işaret eder. GS1 uyumlu DotCode sembolleri için gereklidir.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ecicodetext ekle

ECICodetext özel karakterleri ve uluslararası metni kodlar. Bu örnekte `"犬Right狗"` ifadesini UTF‑8 kullanarak kodluyoruz.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 düz kod metni ekle

DotCode Extended Code Text'e düz metin de ekleyebilirsiniz. Burada `"Plain text"` ekliyoruz.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 fnc3 sembol ayırıcı ekle

FNC3 sembol ayırıcı, kodun farklı bölümlerini ayırır ve tarayıcıların okunabilirliğini artırır.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 fnc3 okuyucu başlatma ekle

Bu adım, tarayıcıya sonraki verileri nasıl yorumlayacağını söyleyen FNC3 Okuyucu Başlatma bilgisini ekler.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 kod metnini oluştur

Şimdi `textBuilder` nesnesi üzerinde `GetExtendedCodetext` metodunu çağırarak DotCode Extended Codetext'i oluşturun.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Adım 3: dotcode görüntüsü oluştur

Genişletilmiş kod metninden barkod görüntüsünü oluşturun.

#### 3.1 barkod oluşturucuyu başlat

`BarcodeGenerator` sınıfı, Aspose.BarCode'un herhangi bir barkod oluşturmak için temel nesnesidir. İstediğiniz semboloji (`EncodeTypes.DotCode`) ve az önce oluşturduğunuz genişletilmiş kod metni ile örnekleyebilirsiniz.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Son olarak, PNG dosyasını diske yazmak için `Save` metodunu çağırın. Görüntü raporlara, mobil uygulamalara veya basılı etiketlere eklenmeye hazır.

## Yaygın sorunlar ve çözümler

- **Yanlış kodlama** – Çok dilli metin eklerken `ECIEncodings.UTF8` kullandığınızdan emin olun; aksi takdirde karakterler bozuk görünebilir.  
- **Dosya erişim hataları** – Uygulamanın hedef dizine yazma izni olduğundan emin olun.  
- **Sessiz bölge eksik** – Tarayıcılar sembolün etrafında ekstra boşluk gerektiriyorsa `gen.Parameters.Barcode.Margin` ayarlayın.

## Sıkça Sorulan Sorular

**S: Oluşturulan barkodu bir mobil uygulamada kullanabilir miyim?**  
C: Evet. Üreteç tarafından oluşturulan PNG görüntüsü iOS, Android veya herhangi bir çapraz platform mobil uygulamaya gömülebilir.

**S: Metin yerine ikili veri kodlamam gerekirse ne yapmalıyım?**  
C: İkili yükleri gömmek için uygun `ECIEncodings` (ör. `ECIEncodings.Base64`) ile `AddECICodetext` metodunu kullanın.

**S: Barkod boyutunu okunabilirliği etkilemeden nasıl değiştiririm?**  
C: `XDimension.Pixels` özelliğini ayarlayın; daha yüksek değerler modül boyutunu artırır, daha düşük değerler barkodu daha kompakt yapar.

**S: Barkodun etrafına bir sessiz bölge eklemenin bir yolu var mı?**  
C: Evet. İstenen sessiz bölgeyi piksel olarak tanımlamak için `gen.Parameters.Barcode.Margin` ayarlayın.

**S: Kütüphane .NET 8'i destekliyor mu?**  
C: En son Aspose.BarCode sürümleri .NET 8 ile uyumludur; sadece uygun NuGet paket sürümüne referans verin.

Daha fazla rehberliğe ihtiyacınız varsa veya sorularınız varsa, [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) adresini ziyaret etmekten veya [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) topluluğuna katılmaktan çekinmeyin.

---

**Son Güncelleme:** 2026-09-28  
**Test Edilen:** Aspose.BarCode 24.12 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Create DotCode Barcode .NET (Auto Mode) with Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/net/datamatrix-barcode-configuration/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}