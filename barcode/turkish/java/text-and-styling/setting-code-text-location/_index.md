---
date: 2025-12-27
description: Aspose.BarCode kullanarak Java'da veri matrisi barkodu oluşturmayı ve
  barkod metin konumunu nasıl ayarlayacağınızı öğrenin. Tam özelleştirme için adım
  adım rehberimizi izleyin.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Java'da veri matrisi barkodu oluştur ve kod metni konumunu ayarla
url: /tr/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da veri matrisi barkodu oluşturma ve kod metni konumunu ayarlama

## Giriş

Barkod oluşturma, envanter, gönderim ve birçok diğer Java tabanlı uygulama için rutin bir gereksinimdir. **Aspose.BarCode for Java** ile **veri matrisi barkodu** hızlı bir şekilde oluşturabilir ve insan tarafından okunabilir metnin nerede görüneceği dahil olmak üzere her görsel unsuru kontrol edebilirsiniz. Bu öğreticide, **veri matrisi barkodu** oluşturmak için tam adımları gösterecek ve **barkod metnini** sembolün **üzerine** nasıl ayarlayacağınızı göstererek tasarım gereksinimlerinize uygun olmasını sağlayacağız.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.BarCode for Java  
- **Hangi barkod türü gösteriliyor?** Data Matrix  
- **Kod metnini nasıl konumlandırırsınız?** `CodeLocation.ABOVE` kullanarak  
- **Üretim için lisans gerekiyor mu?** Evet, ticari bir lisans gereklidir  
- **Kod Java 8+ üzerinde çalışabilir mi?** Kesinlikle, Java 8 ve sonraki sürümleri destekler  

## Data Matrix barkodu nedir?
Data Matrix barkodu, büyük miktarda veriyi kompakt bir kare veya dikdörtgen desen içinde depolayan iki boyutlu (2‑D) bir semboldür. Küçük parçalar, elektronik ve tıbbi cihazların işaretlenmesinde yaygın olarak kullanılır çünkü 2.335 alfanümerik karaktere kadar kodlayabilir.

## Barkod metni konumunu neden ayarlamalısınız?
İnsan tarafından okunabilir metni barkodun **üzerine**, **altına** veya **yanına** yerleştirmek, kullanıcıların kodlanmış veriyi taramadan hızlıca doğrulamasına yardımcı olur. Metin konumunu ayarlamak, UI tutarlılığını artırır ve marka yönergelerine uymayı sağlar.

## Önkoşullar

- Java programlama temellerine sahip olmak.  
- Java Development Kit (JDK) yüklü.  
- Eclipse veya IntelliJ IDEA gibi bir IDE.  
- Aspose.BarCode for Java kütüphanesi ([buradan](https://releases.aspose.com/barcode/java/) indirebilirsiniz).  

## Paketleri İçe Aktarma

İlk olarak, gerekli Aspose.BarCode sınıflarını projenize içe aktarın:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Adım adım kılavuz

### Adım 1: Dizin Yollarını Tanımlama
Dosyaları okuyup/ yazmak istediğiniz yeri belirtin. Yer tutucuları makinenizdeki gerçek yollarla değiştirin.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Adım 2: BarcodeGenerator Örneği Oluşturma
`BarcodeGenerator`'ı **Data Matrix** türüyle örnekleyin ve kodlamak istediğiniz metni sağlayın.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Adım 3: Barkod metni konumunu nasıl ayarlarsınız
İnsan tarafından okunabilir metni taşımak için `CodeLocation` enum'ını kullanın. Bu örnekte metni barkodun **üzerine** yerleştiriyoruz.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Adım 4: Oluşturulan Barkod Görüntüsünü Kaydetme
Son olarak, barkod görüntüsünü diske yazın. Dosya, metnin üstte konumlandırıldığı Data Matrix sembolünü içerecek.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Yaygın Sorunlar ve Çözümler
- **Metin görünmüyor:** `CodeLocation`'ı destekleyen bir Aspose.BarCode sürümü kullandığınızdan emin olun.  
- **Dosya yolu hataları:** `dataDir`'in işletim sisteminize uygun bir dosya ayırıcı (`/` veya `\\`) ile bittiğini doğrulayın.  
- **Desteklenmeyen karakterler:** Data Matrix yalnızca sınırlı bir karakter kümesini kodlayabilir; ISO/IEC 16022 standardında bulunmayan özel sembollerden kaçının.  

## Sıkça Sorulan Sorular (SSS)

### S: Oluşturulan barkodun görünümünü özelleştirebilir miyim?
A: Evet, Aspose.BarCode geniş özelleştirme seçenekleri sunar; renkleri, kenar boşluklarını ve yazı tipi stillerini kontrol etmenizi sağlar.

### S: Aspose.BarCode Java 8 ve sonraki sürümlerle uyumlu mu?
A: Kesinlikle, kütüphane Java 8 ve sonraki tüm sürümlerle çalışır.

### S: Aspose.BarCode'u mevcut Java projemle nasıl entegre edebilirim?
A: Aspose.BarCode JAR dosyalarını projenizin sınıf yoluna ekleyin, gerekli paketleri içe aktarın ve barkod üretmeye hazırsınız.

### S: Aspose.BarCode için bir deneme sürümü mevcut mu?
A: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) alarak Aspose.BarCode'un yeteneklerini keşfedebilirsiniz.

### S: Aspose.BarCode için yardım veya destek nereden alabilirim?
A: Topluluk yardımı ve resmi destek için [Aspose.BarCode forumunu](https://forum.aspose.com/c/barcode/13) ziyaret edin.

## Ek Sıkça Sorulan Sorular

**S: Metni sembolün altında konumlandırarak bir barkod oluşturabilir miyim?**  
C: Evet, aynı `setLocation` metodunda `CodeLocation.BELOW` ayarlayın.

**S: Kütüphane QR Code gibi diğer 2‑D barkodları destekliyor mu?**  
C: Kesinlikle, sadece `EncodeTypes.DATA_MATRIX`'i `EncodeTypes.QR` olarak değiştirin.

**S: Barkod metninin yazı tipi boyutunu nasıl değiştiririm?**  
C: `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)` metodunu kullanın.

## Sonuç

Artık Java'da **veri matrisi barkodu** oluşturmayı ve Aspose.BarCode kullanarak **barkod metninin konumunu** nasıl ayarlayacağınızı tam olarak öğrendiniz. Uygulamanızın tasarım gereksinimlerine uyması için diğer `CodeLocation` değerleri ve stil seçenekleriyle denemeler yapın.

---

**Son Güncelleme:** 2025-12-27  
**Test Edilen Versiyon:** Aspose.BarCode for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}