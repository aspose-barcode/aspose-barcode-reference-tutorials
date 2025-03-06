---
title: Aspose.BarCode for .NET ile Ek Barkod Verileri Oluşturma
linktitle: Ek Barkod Veri Yapılandırması
second_title: Aspose.BarCode .NET API'si
description: Aspose.BarCode for .NET ile ek barkod verileri oluşturun. EAN-2 ve EAN-5 barkodlarını zahmetsizce özelleştirin. .NET geliştiricileri için adım adım kılavuz.
weight: 10
url: /tr/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET ile Ek Barkod Verileri Oluşturma


Barkod oluşturma ve özelleştirme dünyasında Aspose.BarCode for .NET güçlü ve çok yönlü bir araç olarak öne çıkıyor. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz Aspose.BarCode for .NET'i kullanarak tamamlayıcı barkod verilerini yapılandırma sürecinde size yol gösterecektir. 

## Önkoşullar

Tamamlayıcı barkod verileri dünyasına dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya başka herhangi bir .NET geliştirme aracıyla kurulmuş bir geliştirme ortamı.
-  Aspose.BarCode for .NET'in bir kopyası. Henüz yapmadıysanız indirebilirsiniz[Burada](https://releases.aspose.com/barcode/net/).
- Temel C# programlama bilgisi.
- Oluşturulan barkod görsellerini kaydedebileceğiniz dizin.

## Ad Alanlarını İçe Aktarma

Öncelikle Aspose.BarCode for .NET ile çalışmak için C# kodunuzda gerekli ad alanlarının bulunduğundan emin olun. Gerekli ad alanlarını C# dosyanızın başlangıcında içe aktarın:

```csharp
using Aspose.BarCode.Generation;
```

Şimdi ek barkod verilerini yapılandırma sürecini birden fazla adıma ayıralım.

## Adım 1: Dizin Yolunu Ayarlama

 C# kodunuzda, oluşturulan barkod görüntülerini kaydetmek istediğiniz dizinin yolunu tanımlayın. Yer değiştirmek`"Your Directory Path"` gerçek dizin yolunuzla.

```csharp
string path = "Your Directory Path";
```

## Adım 2: Barkod Oluşturucu Oluşturma

 Bir örneğini oluşturun`BarcodeGenerator` Barkod tipini ve kodlamak istediğiniz veriyi belirterek. Bu örnekte "1234567890128" verisine sahip bir EAN-13 barkodu kullanıyoruz.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## 3. Adım: Barkod Boyutlarını Özelleştirme

X boyutu (barkoddaki en küçük öğenin genişliği) ve ek alan gibi barkodun boyutlarını ayarlayın. Bu örnekte X boyutunu 2 piksele ve ek alanı 20 piksele ayarladık.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Adım 4: EAN-2 Ekini Yapılandırma

EAN-2 ek barkodunu yapılandırmak için ek verileri istenen değere ayarlayın. Bu durumda onu "12" olarak ayarladık. 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Adım 5: Barkod Görüntüsünü Kaydetme

Oluşturulan barkod görüntüsünü anlamlı bir adla belirttiğiniz dizine kaydedin. Bu örnekte EAN-2 ek barkodunu "SupplementEAN2.png" olarak kaydediyoruz.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Adım 6: EAN-5 Ekini Yapılandırma

 EAN-5 ek barkodunu yapılandırmak için yalnızca`SupplementData` istediğiniz değere Burada "12345" olarak ayarladık.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Adım 7: Barkod Görüntüsünün Kaydedilmesi (EAN-5)

Son olarak, EAN-5 ek barkod görüntüsünü belirttiğiniz dizine kaydedin. Bu durumda "SupplementEAN5.png" olarak kaydediyoruz.

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Artık Aspose.BarCode for .NET'i kullanarak ek barkod verilerini başarıyla yapılandırıp oluşturdunuz. Bu yaklaşımı, değişen ek verilere sahip çok çeşitli barkod türleri oluşturmak için kullanabilirsiniz.

## Çözüm

Aspose.BarCode for .NET, barkod oluşturma ve özelleştirme için güçlü bir araçtır. Bu kılavuzda, ek barkod verilerini yapılandırma ve oluşturma sürecini adım adım anlattık. Doğru ön koşullar ve biraz kodlamayla barkod verileriyle verimli bir şekilde çalışabilir ve özel ihtiyaçlarınızı karşılayabilirsiniz.

 Daha fazla bilgi ve gelişmiş kullanım için bkz.[Aspose.BarCode for .NET belgeleri](https://reference.aspose.com/barcode/net/).

## Sıkça Sorulan Sorular

### Aspose.BarCode for .NET'i .NET Core projemde kullanabilir miyim?
Evet, Aspose.BarCode for .NET, .NET Core ile uyumludur.

### Aspose.BarCode for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ziyaret ederek ücretsiz olarak deneyebilirsiniz[bu bağlantı](https://releases.aspose.com/).

### Aspose.BarCode for .NET için nereden geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode çok çeşitli barkod türlerini destekliyor mu?
Evet, EAN-13, QR Code, Code 128 ve daha fazlası dahil olmak üzere çeşitli barkod türlerini destekler.

### Oluşturulan barkodların görünümünü özelleştirebilir miyim?
Kesinlikle gereksinimlerinizi karşılamak için barkodların boyutlarını, renklerini ve diğer yönlerini özelleştirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
