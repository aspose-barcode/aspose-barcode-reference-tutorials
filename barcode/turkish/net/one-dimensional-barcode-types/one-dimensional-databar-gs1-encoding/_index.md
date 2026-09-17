---
date: 2026-03-07
description: Aspose.BarCode kullanarak .NET’te tek boyutlu databar GS1 kodlu barkodların
  nasıl oluşturulacağını öğrenin. Bu kılavuz, GS1’i nasıl ayarlayacağınızı, barkod
  oluşturucuyu nasıl yapılandıracağınızı ve barkodları hızlı bir şekilde nasıl üreteceğinizi
  gösterir.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode ile Tek Boyutlu Databar GS1 Kodlaması Oluştur
url: /tr/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode ile Tek Boyutlu Databar GS1 Kodlaması Oluşturma

Bu öğreticide, .NET için Aspose.BarCode kütüphanesini kullanarak GS1 standardına uygun **tek boyutlu databar** barkodları oluşturacaksınız. Katı GS1 doğrulaması mı yoksa daha esnek bir barkod mu ihtiyacınız var, kütüphaneyi kurmaktan kodlama istisnalarını ele almaya kadar her adımı birlikte inceleyeceğiz; böylece kendi uygulamalarınızda güvenilir barkodlar üretebileceksiniz.

## Hızlı Yanıtlar
- **“tek boyutlu databar oluşturma” ne anlama geliyor?** Databar ailesine ait doğrusal (1‑D) bir barkod üretmek demektir; perakende ve lojistikte sıkça kullanılır.  
- **GS1 doğrulamasını nasıl ayarlarım?** `DataBar` parametrelerinde `IsAllowOnlyGS1Encoding` özelliğini `true` olarak ayarlayın.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kütüphaneyi nereden indirebilirim?** Resmi Aspose sürüm sayfasından (gereksinimlere bakın).

## “tek boyutlu databar oluşturma” nedir?
Tek boyutlu Databar (RSS olarak da bilinir), sayısal veri, tarih veya AI (Application Identifier) dizgileri kodlayabilen kompakt bir doğrusal barkoddur. GS1 kodlamasıyla birleştirildiğinde, barkod küresel olarak tanınan bir veri yapısına uyar; bu da perakende, sağlık ve tedarik zinciri senaryoları için idealdir.

## Neden .NET için Aspose.BarCode kullanmalı?
Aspose.BarCode akıcı bir API, tam GS1 desteği ve barkodun her görsel unsurunu ince ayar yapma imkanı sunar. Düşük seviyeli kodlamanın belirsizliklerini ortadan kaldırır ve iş mantığınıza odaklanmanızı sağlar.

## Önkoşullar

1. **Aspose.BarCode for .NET** – [buradan](https://releases.aspose.com/barcode/net/) indirip kurun.  
2. **Dizin Yolunuz** – örneklerdeki `"Your Directory Path"` ifadesini yazma izniniz olan bir klasörle değiştirin.

## Ad Alanlarını İçe Aktarma

C# dosyanızın en üstüne gerekli `using` ifadelerini ekleyin:

```csharp
using Aspose.BarCode;
using System;
```

## Adım 1: Barkod Üreteci Başlatma

`BarcodeGenerator` örneği oluşturun ve Databar Expanded sembolojisini belirtin:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Adım 2: GS1 Ayarlama – Katı GS1 doğrulamalı barkod oluşturma

GS1‑only kodlamayı etkinleştirin, GS1‑uyumlu bir kod metni atayın ve görüntüyü kaydedin:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Adım 3: Aspose ile Barkod Oluşturma – Değişken kodlama (GS1 kontrolü yok)

GS1 kurallarını **zorlamayan** bir barkod istiyorsanız kontrolü kapatın:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Adım 4: Barkod Üreteci GS1 kontrolü – İstisna yakalama

`IsAllowOnlyGS1Encoding` `true` iken kod metni GS1‑uyumlu değilse Aspose bir istisna fırlatır. Aşağıdaki örnek, bu istisnanın nasıl yakalanıp kaydedileceğini gösterir:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Yaygın Tuzaklar ve İpuçları
- **Tuzak:** GS1 kontrolü açıkken GS1 dışı bir dize sağlamak barkod oluşturmayı durdurur.  
- **Profesyonel ipucu:** `CodeText`e atamadan önce AI dizgilerinizi doğrulayarak çalışma zamanı hatalarını önleyin.  
- **İpucu:** Dosya adlarını platformlar arasında güvenli bir şekilde oluşturmak için mutlak yollar veya `Path.Combine` kullanın.

## Sonuç

Artık **tek boyutlu databar** barkodlarını GS1 kodlamasıyla nasıl oluşturacağınızı, GS1 kontrolünü nasıl açıp kapatacağınızı ve ilgili istisnaları nasıl yöneteceğinizi biliyorsunuz — tüm bunlar .NET için Aspose.BarCode kullanılarak yapılmaktadır. `Parameters.Barcode` nesnesi aracılığıyla barkod boyutu, rengi ve kenar boşlukları gibi ek stil seçeneklerini keşfetmekten çekinmeyin.

Herhangi bir sorunla karşılaşırsanız resmi dokümantasyon ve topluluk forumu mükemmel kaynaklardır:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Sık Sorulan Sorular

### 1. Barkodlarda GS1 kodlaması nedir?
GS1 kodlaması, bir barkod içinde (ör. ürün tanımlayıcıları) verileri standart bir biçimde yapılandırarak perakendeciler, üreticiler ve lojistik sağlayıcıları arasında birlikte çalışabilirliği sağlar.

### 2. Oluşturulan barkodların görünümünü özelleştirebilir miyim?
Evet. Aspose.BarCode, `Parameters.Barcode` ayarlarıyla boyut, renk, kenar boşlukları ve hatta insan tarafından okunabilir metin ekleme gibi seçenekleri ayarlamanıza olanak tanır.

### 3. Aspose.BarCode için ek kaynaklar ve dokümantasyon nerede bulunur?
Kapsamlı dokümantasyon ve örnekleri [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) adresinde bulabilirsiniz. Öğrenme ve sorun giderme için değerli bir kaynaktır.

### 4. Aspose.BarCode için deneme sürümü mevcut mu?
Evet, [buradan](https://releases.aspose.com/) .NET için ücretsiz deneme sürümünü edinebilirsiniz.

### 5. Aspose.BarCode for .NET lisansı nasıl satın alınır?
Aspose web sitesindeki [satın alma sayfasını](https://purchase.aspose.com/buy) ziyaret ederek Aspose.BarCode for .NET lisansı satın alabilirsiniz.

---

**Son Güncelleme:** 2026-03-07  
**Test Edilen Versiyon:** Aspose.BarCode 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}