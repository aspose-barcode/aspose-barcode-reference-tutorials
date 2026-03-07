---
date: 2026-03-07
description: Aspose.BarCode for .NET kullanarak C# ile ek veri içeren EAN‑13 barkod
  oluşturmayı öğrenin – barkodu PNG olarak hızlıca üretin.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Ek Veriyle EAN-13 Barkod Oluşturma – Aspose.BarCode
url: /tr/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EAN-13 Barkodunu Ek Veri ile Oluşturma – Aspose.BarCode for .NET

Bu uygulamalı öğreticide **EAN-13 barkod** oluşturacaksınız ve bu barkod, ek EAN‑2 veya EAN‑5 verilerini içerecek; ayrıca sadece birkaç C# satırıyla **barcode PNG** dosyaları nasıl **oluşturulur** göreceksiniz. Perakende ödeme sistemi, lojistik uygulaması ya da basit bir envanter aracı geliştiriyor olun, ek bilgi ekleme yeteneği barkodlarınızı çok daha kullanışlı hâle getirir.

## Hızlı Yanıtlar
- **“Supplemental data” ne anlama geliyor?** Ana barkodun yanına basılan ekstra rakamlar (EAN‑2/EAN‑5), genellikle fiyat veya sayı numaraları için kullanılır.  
- **Hangi barkod türü kullanılıyor?** Birincil sembol olarak EAN‑13, isteğe bağlı EAN‑2 veya EAN‑5 ekleriyle.  
- **PNG görüntüleri çıkartabilir miyim?** Evet – `Save` yöntemi doğrudan PNG olarak dışa aktarmanızı sağlar.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Bu .NET Core / .NET 6 ile uyumlu mu?** Kesinlikle – Aspose.BarCode tüm modern .NET çalışma zamanlarını destekler.

## Önkoşullar

Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio (veya herhangi bir .NET‑uyumlu IDE).  
- Aspose.BarCode for .NET kopyası – **[buradan](https://releases.aspose.com/barcode/net/)** indirebilirsiniz.  
- Temel C# bilgisi.  
- Oluşturulan PNG dosyalarının kaydedileceği yazılabilir bir klasör.

## Ad Alanlarını İçe Aktarma

İlk olarak, jeneratör sınıflarına erişebilmek için Aspose.BarCode ad alanını ekleyin:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro ipucu:** .NET Core kullanıyorsanız, DLL'yi manuel olarak referanslamak yerine projenize `Aspose.BarCode` NuGet paketini ekleyin.

## Ek Barkod Nedir?

Ek barkod, ana barkodun yanına basılan yardımcı bir sayısal dizidir.  
- **EAN‑2** – iki basamaklı ek, genellikle dergi sayı numaraları için kullanılır.  
- **EAN‑5** – beş basamaklı ek, perakende ürünlerde fiyat uzantıları için yaygın olarak kullanılır.

Bu ekleri eklemek, birincil EAN‑13 verisini değiştirmez; sadece tarayıcıların okuyabileceği ekstra bağlam sağlar.

## Neden Aspose.BarCode ile Ek Veri Kullanmalı?

- **Tek satır API** – ana barkodu ve ekini tek bir nesnede yapılandırın.  
- **Boyutlar üzerinde tam kontrol** – X‑dimension, ek boşluğu ve görüntü formatını ayarlayın.  
- **Çapraz platform** – .NET Framework, .NET Core ve .NET 5/6+ üzerinde çalışır.

## Adım Adım Kılavuz

### Adım 1: Çıktı Dizini Ayarlama

PNG dosyalarının nerede saklanacağını tanımlayın. Yer tutucuyu makinenizdeki gerçek bir yol ile değiştirin.

```csharp
string path = "Your Directory Path";
```

### Adım 2: Barkod Jeneratörünü Başlatma (Barcode Generator C#)

`BarcodeGenerator` örneği oluşturun, ana tip olarak **EAN‑13** belirleyin ve 13 basamaklı veriyi sağlayın.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Adım 3: Barkod Boyutlarını Ayarlama

Barkodun görsel boyutunu ve ek için ayrılan boşluğu hassas bir şekilde ayarlayın.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Adım 4: EAN‑2 Eki Ekleyin

Ek veriyi iki basamaklı bir değere (ör. “12”) ayarlayın. Bu, ana barkodun sağında görünecek.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Adım 5: EAN‑2 Barkodu PNG Olarak Kaydedin

Görüntüyü dışa aktarın. `BarCodeImageFormat.Png` argümanı yüksek kalite bir PNG dosyası sağlar.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Adım 6: EAN‑5 Ekine Geçiş Yapın

Fiyat uzantıları için `SupplementData` değerini beş basamaklı bir dizeye değiştirin.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Adım 7: EAN‑5 Barkodu PNG Olarak Kaydedin

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Neden bu çalışıyor:** Aynı `BarcodeGenerator` örneği yeniden kullanılır, bu yüzden her `Save` çağrısından önce sadece `SupplementData` özelliğini değiştirmeniz yeterlidir. Bu, kodu özlü tutar ve gereksiz nesne oluşturmayı önler.

## Yaygın Sorunlar ve İpuçları

- **Geçersiz dizin yolu** – klasörün var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun.  
- **Yanlış ek uzunluğu** – EAN‑2 tam 2 rakam, EAN‑5 ise 5 rakam bekler; aksi takdirde bir istisna fırlatılır.  
- **Görüntü görünmüyor** – `BarCodeImageFormat.Png` kullanıldığını doğrulayın; diğer formatlar (ör. JPEG) tarayıcı okunurluğunu etkileyebilecek sıkıştırma artefaktları ekleyebilir.  

## Sıkça Sorulan Sorular

### Aspose.BarCode for .NET'i .NET Core projemde kullanabilir miyim?
Evet, Aspose.BarCode for .NET .NET Core, .NET 5 ve .NET 6 ile tamamen uyumludur.

### Aspose.BarCode for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, **[bu linki](https://releases.aspose.com/)** ziyaret ederek ücretsiz deneyebilirsiniz.

### Aspose.BarCode for .NET için geçici lisansı nereden alabilirim?
Geçici bir lisansı **[bu linkten](https://purchase.aspose.com/temporary-license/)** alabilirsiniz.

### Aspose.BarCode geniş bir barkod tipi yelpazesini destekliyor mu?
Kesinlikle – EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 ve daha birçok barkod tipini destekler.

### Oluşturulan barkodların görünümünü özelleştirebilir miyim?
Evet, renkleri, yazı tiplerini, kenar boşluklarını değiştirebilir ve hatta kapsamlı `Parameters` API'siyle arka plan resimleri ekleyebilirsiniz.

## Sonuç

Artık **EAN-13 barkod** oluşturmayı, ek EAN‑2 veya EAN‑5 verileri eklemeyi ve Aspose.BarCode for .NET kullanarak **barcode PNG** dosyaları üretmeyi biliyorsunuz. Bu yaklaşım, barkod boyutları, ek boşluğu ve çıktı formatı üzerinde tam kontrol sağlar; perakende, lojistik ve ekstra sayısal bilgi gerektiren her senaryo için idealdir.

Daha derin bir keşif için tam referans kılavuzuna göz atın: **[Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)**.

---

**Son Güncelleme:** 2026-03-07  
**Test Edilen Versiyon:** Aspose.BarCode 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}