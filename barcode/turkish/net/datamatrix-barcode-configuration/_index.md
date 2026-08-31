---
date: 2026-06-09
description: Aspose.BarCode for .NET ile datamatrix barkod oluşturmayı öğrenin, aspect
  ratios, ECC modları ve verimli barkod oluşturma için datamatrix c40 encoding'i özelleştirin.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix Barkod Yapılandırması
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrix Barkod Oluşturma – Aspose.BarCode ile Profesyonel Kılavuz
url: /tr/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix Barkod Oluşturma – Aspose.BarCode ile Pro Rehber

Aspose.BarCode for .NET kullanarak **DataMatrix barkodu oluşturma** konusundaki kapsamlı öğretici serimize hoş geldiniz. İster barkod çıktısını ince ayar yapan deneyimli bir geliştirici olun, ister temelleri öğrenmek isteyen yeni bir kullanıcı olun, bu rehber size temel yapılandırmadan gelişmiş kodlama tekniklerine kadar her adımı gösterir—böylece herhangi bir .NET uygulamasında güvenilir, taramaya hazır barkodlar oluşturabilirsiniz.

## Hızlı Yanıtlar
- **Ana amaç nedir?** DataMatrix barkodlarını programlı olarak oluşturmak ve özelleştirmek.  
- **Hangi kütüphane kullanılıyor?** Aspose.BarCode for .NET.  
- **Lisans gerekli mi?** Ücretsiz deneme mevcuttur; üretim için ticari lisans gereklidir.  
- **Desteklenen .NET sürümleri?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **En boy oranını özelleştirebilir miyim?** Evet – “DataMatrix en‑boy oranını nasıl özelleştirirsiniz” bölümüne bakın.

## DataMatrix barkodu oluşturma nedir?
DataMatrix barkodu, 2 300 alfanümerik karaktere kadar depolayabilen siyah ve beyaz hücrelerden oluşan iki boyutlu bir matristir. Aspose.BarCode kullanarak **DataMatrix barkodu** görüntüleri, PDF'ler veya SVG'ler oluşturabilir, boyut, hata düzeltme seviyesi ve kodlama modunu doğrudan .NET kodunuzdan kontrol ederek herhangi bir endüstri standardını karşılayabilirsiniz.

## DataMatrix için Aspose.BarCode neden kullanılmalı?
Aspose.BarCode, DataMatrix sembollerini **600 dpi**'ye kadar pikselleşme olmadan render eder ve yüksek çözünürlüklü yazıcılarda net taramaları garanti eder. **50+ ECC ve makro modunun tamamını** destekler—ECC 000‑140, ECC 200 ve Macro 05/06 dahil—böylece veri boyutunuza en uygun hata düzeltme seviyesini seçebilirsiniz. API, **ASCII, C40, Text, X12 ve Bytes** kodlama seçenekleri sunarak veriyi verimli bir şekilde paketlemenizi sağlar. Entegrasyon sadece tek bir NuGet paketi gerektirir ve harici yerel kütüphanelere ihtiyaç duymaz.

## DataMatrix en‑boy oranını nasıl özelleştirirsiniz
`BarCodeGenerator` sınıfının `AspectRatio` özelliği, oluşturulan DataMatrix sembolünün genişlik‑yükseklik oranını kontrol eder. `BarCodeGenerator`, Aspose.BarCode içinde barkod görüntüleri oluşturmak için kullanılan ana sınıftır.  

**Doğrudan cevap:** `GenerateBarCodeImage()` metodunu çağırmadan önce `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (veya 0.5 ile 2.0 arasında herhangi bir değer) olarak ayarlayın. Kütüphane, istenen oranı korurken tarama güvenilirliğini sağlamak için modül boyutunu otomatik olarak yeniden hesaplar.

### Adım‑adım
1. **Örnekleyin** `BarCodeGenerator`'ı `EncodeTypes.DataMatrix` ile.  
2. **Ayarlayın** `AspectRatio`'yu istediğiniz değere.  
3. **Oluşturun** görüntüyü ve bir tarayıcı ya da Aspose'un yerleşik okuyucusuyla doğrulayın.

## DataMatrix ECC 000‑140 barkodları nasıl oluşturulur
ECC 000‑140, kompakt bir sembolün gerektiği kısa veri dizileri için idealdir ve 140 hata‑düzeltme kod kelimesine kadar sunar. `DataMatrixEccMode.Ecc000140`, DataMatrix için ECC 000‑140 hata‑düzeltme şemasını seçer.  

**Doğrudan cevap:** Render etmeden önce `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` kullanın. Bu, kodlayıcıyı ECC 000‑140 algoritmasına geçirir ve verilen veri için mümkün olan en küçük matrisi üretirken hâlâ güçlü hata düzeltmesi sağlar.

### Pratik ipucu
20 karakterin altında sayısal veri kodlarken, ECC 000‑140 genellikle 10 × 10 bir matris üretir ve bu da değerli etiket alanını tasarruf ettirir.

## DataMatrix ECC 200 barkodları nasıl oluşturulur
ECC 200, en yaygın kullanılan DataMatrix modudur, 2 335 alfanümerik karaktere kadar destekler ve üstün hata düzeltme sunar. `DataMatrixEccMode.Ecc200`, DataMatrix için ECC 200 hata‑düzeltme şemasını seçer.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` olarak ayarlayın ve yükünüzü `CodeText` ile sağlayın. Kütüphane ardından otomatik olarak optimal matris boyutunu seçer.

### ECC 200 ne zaman tercih edilmeli
Daha uzun dizeler, karışık tip veriler veya hasara karşı en yüksek dayanıklılığı gerektiğinde ECC 200 kullanın—sembolün **%30**'una kadar geri getirilebilir.

## DataMatrix kodlamasını ASCII'de nasıl ustalaşırsınız
ASCII modu, karakterleri karakter başına tek bayt kullanarak kodlar ve bu da düz metin için en alan‑verimli yöntemdir. `DataMatrixEncodeMode.Ascii`, jeneratöre DataMatrix sembolü için ASCII kodlamasını kullanmasını söyler.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` atayın ve `CodeText`'i ASCII dizenize ayarlayın. Motor, ekstra yük olmadan veriyi paketler ve saf ASCII içeriği için mümkün olan en küçük matrisi üretir.

### Örnek senaryo
Büyük harfler ve rakamlardan oluşan bir depo SKU'su (ör. “AB1234”) ASCII modunda mükemmel uyum sağlar ve genellikle 12 × 12 bir matrisle sonuçlanır.

## DataMatrix Modu (Auto) nasıl oluşturulur
Auto modu, Aspose.BarCode'un girişi analiz etmesine ve en verimli kodlamayı (ASCII, C40, Text, X12 veya Bytes) otomatik olarak seçmesine olanak tanır. `DataMatrixEncodeMode.Auto` bu otomatik seçim özelliğini etkinleştirir.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto` olarak ayarlayın. Kütüphane, yükü değerlendirir, optimal modu seçer ve barkodu tek adımda render eder.

### Avantajlar
Auto modu, geliştirme çabasını azaltır ve karışık tip veriler için mümkün olan en küçük sembolü garanti eder, tarama hızını artırır.

## DataMatrix kodlama modu (Bytes) nasıl kullanılır
Bytes modu, şifrelenmiş yükler veya sıkıştırılmış dosyalar gibi ikili veriler için tasarlanmıştır. `DataMatrixEncodeMode.Bytes`, jeneratöre her baytı ham veri olarak ele almasını söyler.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` kullanın ve `CodeText` olarak Base64‑kodlu bir dize sağlayın. Kodlayıcı, her baytı ham veri olarak ele alır ve tam ikili temsili korur.

### Kullanım durumu
128‑bit bir GUID'i veya küçük bir şifreli token'ı doğrudan bir DataMatrix sembolüne gömmek.

## DataMatrix kodlama modu (C40) nasıl ustalaşılır
C40 modu, büyük harf alfanümerik verileri sıkıştırır ve ASCII'ye kıyasla **%40**'a kadar boyut azaltımı sağlar. `DataMatrixEncodeMode.C40` bu sıkıştırma algoritmasını etkinleştirir.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` olarak ayarlayın ve büyük harfli bir dize (ör. “HELLO WORLD”) sağlayın. Motor, üç karakteri iki kod sözcüğüne paketleyerek son matrisi küçültür.

### Pro ipucu
C40, yükün çoğunlukla büyük harfli harfler, sayılar ve boşluklardan oluştuğu durumlarda en iyi çalışır. Karışık durumlar için Auto modu düşünün.

## DataMatrix kod metnini nasıl yapılandırırsınız
`CodeText` özelliği, barkodda saklanan tam veriyi tanımlar. Düz metin, sayısal dizeler veya hatta XML yükleri içerebilir. `CodeText`, `BarCodeGenerator`'ın barkod yükünü tutan birincil dize özelliğidir.  

**Doğrudan cevap:** Render etmeden önce `generator.Parameters.Barcode.CodeText = "YourDataHere"` atayın. Bu özellik, seçilen ECC modunun desteklediği maksimum uzunluğa kadar herhangi bir UTF‑8 dizesini kabul eder.

### İleri düzey ipucu
`CodeText`'i `ExtendedDataMatrix` ile birleştirerek görünür matris boyutunu artırmadan ek meta verileri gömebilirsiniz.

## DataMatrix makro yapılandırmasını nasıl ustalaşırsınız
Macro modları (Macro 05 ve Macro 06), birincil sembolün içine ikincil bir DataMatrix sembolü gömmenizi sağlar; dış veri kaynaklarına bağlanmak için faydalıdır. `DataMatrixMacroMode.Macro05` ve `DataMatrixMacroMode.Macro06` bu makro özelliklerini etkinleştirir.  

**Doğrudan cevap:** `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (veya `Macro06`) ile makro modunu etkinleştirin ve ikincil yük için `MacroPdf417` özelliklerini ayarlayın. Jeneratör, tarayıcıların iki bağlı kod olarak yorumlayabileceği birleşik bir sembol oluşturur.

### Gerçek‑dünya örneği
Ürün tanımlayıcılarını birincil matrisde tutarken, makro kısmına bir URL gömmek, sorunsuz web‑to‑barkod entegrasyonu sağlar.

*Using Aspose.BarCode For .NET Tutorials Listing*

## DataMatrix Barkod Yapılandırma Öğreticileri
### [DataMatrix En‑Boy Oranını Özelleştirme](./datamatrix-aspect-ratio-customization/)
DataMatrix barkod en‑boy oranlarını Aspose.BarCode for .NET kullanarak nasıl özelleştireceğinizi öğrenin. Barkod oluşturma için adım‑adım rehber.
### [DataMatrix ECC 000-140 Barkodları Oluşturma](./datamatrix-ecc-000-140-configuration/)
Aspose.BarCode for .NET ile DataMatrix ECC 000-140 barkodları kolayca oluşturun. Envanter yönetiminde ve daha fazlasında verimliliği artırın.
### [DataMatrix ECC 200 Barkodları Oluşturma](./datamatrix-ecc-200-configuration/)
Aspose.BarCode for .NET kullanarak .NET içinde DataMatrix ECC 200 barkodları nasıl oluşturulur öğrenin. Verimli barkod oluşturma ile operasyonları basitleştirin.
### [ASCII'de DataMatrix Kodlamasını Ustalaşma](./datamatrix-encoding-mode-ascii/)
Aspose.BarCode for .NET ile ASCII modunda DataMatrix barkodları nasıl oluşturulur öğrenin. Geliştiriciler için adım‑adım rehber.
### [DataMatrix Modu (Auto) Oluşturma](./datamatrix-encoding-mode-auto/)
Aspose.BarCode for .NET ile DataMatrix Modu (Auto) nasıl oluşturulur öğrenin. Bu adım‑adım rehber, ön koşullardan barkod okuma aşamasına kadar her şeyi kapsar.
### [DataMatrix Kodlama Modu (Bytes)](./datamatrix-encoding-mode-bytes/)
Aspose.BarCode for .NET ile Bytes modunda DataMatrix formatında veri nasıl kodlanır öğrenin. Barkod oluşturma ve tanıma için adım‑adım rehberimizi izleyin.
### [DataMatrix Kodlama Modu (C40) Ustalaşma](./datamatrix-encoding-mode-c40/)
Aspose.BarCode for .NET ile DataMatrix Kodlama Modu (C40) öğrenin. Özel barkodları verimli bir şekilde oluşturun. Adım‑adım rehberi keşfedin.
### [DataMatrix Kod Metnini Yapılandırma](./datamatrix-extended-code-text-configuration/)
Aspose.BarCode for .NET kullanarak DataMatrix genişletilmiş kod metnini nasıl yapılandıracağınızı öğrenin. .NET uygulamalarınızda barkodları oluşturun, tanıyın ve entegre edin.
### [DataMatrix Makro Yapılandırmasını Ustalaşma](./datamatrix-macro-configuration/)
Aspose.BarCode for .NET ile DataMatrix Makro barkodlarını nasıl yapılandıracağınızı öğrenin. .NET uygulamalarınızda DataMatrix barkodlarını oluşturun, özelleştirin ve tanıyın.

## Sıkça Sorulan Sorular

**S: Hangi ECC modunu kullanmalıyım?**  
**C:** Küçük veri setleri ve sınırlı hata düzeltme için ECC 000‑140, daha büyük veri ve daha yüksek güvenilirlik için ECC 200 seçin. Makro modu, bağlama için ekstra bir veri katmanı ekler.

**S: DataMatrix barkoduna özel metin gömebilir miyim?**  
**C:** Evet, `CodeText` özelliğini özel dizeye ayarlayın, ardından boyutu kontrol etmek için uygun kodlama modunu (ASCII, C40, vb.) seçin.

**S: En iyi kodlama modunu otomatik olarak seçmenin bir yolu var mı?**  
**C:** `EncodeMode`'u `Auto` olarak ayarlayın; Aspose.BarCode, yükü değerlendirir ve otomatik olarak en alan‑verimli modu seçer.

**S: Büyük barkod partileri için performans hususları nelerdir?**  
**C:** Tek bir `BarCodeGenerator` örneğini yeniden kullanın, çoklu iş parçacığını etkinleştirin ve kayıpsız kalite için PNG, daha küçük dosya boyutu için JPEG görüntüleri oluşturun. 10 000 sembolün işlenmesi, standart bir 8‑çekirdekli sunucuda genellikle 30 saniyenin altında tamamlanır.

**S: Aspose.BarCode .NET Core ve .NET 5/6'yı destekliyor mu?**  
**C:** Kesinlikle – kütüphane .NET Framework, .NET Core ve en yeni .NET sürümleriyle tam uyumludur ve tüm platformlarda aynı özellik setini sunar.

**Son Güncelleme:** 2026-06-09  
**Test Edilen Versiyon:** Aspose.BarCode 24.12 for .NET  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.BarCode for .NET ile DataMatrix Barkodları (ECC 200) Nasıl Oluşturulur](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET ile ASCII'de DataMatrix Kodlamasını Ustalaşma](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Barkod PNG Oluştur – DataMatrix En‑Boy Oranı – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}