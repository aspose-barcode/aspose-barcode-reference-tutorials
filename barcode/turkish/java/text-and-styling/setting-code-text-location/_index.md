---
date: 2026-05-04
description: Java barkod kütüphanesi kullanarak bir Data Matrix barkodu oluşturmayı
  ve Aspose.BarCode ile barkod metni konumunu sembolün üzerine ayarlamayı öğrenin.
  Adım adım barkod oluşturma örneğimizi izleyin.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Kod Metni Konumunu Ayarlama
second_title: Aspose.BarCode Java API
title: Java Barkod Kütüphanesi ile Data Matrix Barkodu Oluşturun ve Kod Metni Konumunu
  Ayarlayın
url: /tr/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Barcode Kütüphanesi ile Data Matrix Barkod Oluşturma ve Kod Metni Konumunu Ayarlama

## Giriş

Java’da bir envanter, nakliye veya izleme sistemi geliştiriyorsanız, güvenilir bir **java barcode library**'nin ne kadar önemli olduğunu çabucak fark edeceksiniz. **Aspose.BarCode for Java** ile sadece birkaç satır kod yazarak bir **Data Matrix barkod** oluşturabilir ve insan‑okunur metnin nerede görüneceği dahil olmak üzere görsel düzeni tam olarak kontrol edebilirsiniz. Bu öğreticide, eksiksiz bir **barcode generation example** üzerinden ilerleyecek, **barcode text** yerleşimini nasıl **özelleştireceğinizi** gösterecek ve metni sembolün üzerine konumlandırmanın kullanılabilirliği nasıl artırdığını açıklayacağız.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.BarCode for Java  
- **Hangi barkod türü gösteriliyor?** Data Matrix  
- **Kod metni nasıl konumlandırılır?** `CodeLocation.ABOVE` kullanarak (aynı zamanda `BELOW` da kullanılabilir)  
- **Üretim için lisans gerekiyor mu?** Evet, ticari bir lisans gereklidir  
- **Kod Java 8+ üzerinde çalışabilir mi?** Kesinlikle, Java 8 ve sonraki sürümleri destekler  

## Java barcode kütüphanesi nedir?
Bir **java barcode library**, geliştiricilere Java uygulamalarından doğrudan 1‑D ve 2‑D barkodları oluşturma, okuma ve stil verme imkanı sağlayan hazır API'ler sunar. Karmaşık kodlama kurallarını soyutlar ve düşük seviyeli görüntü işleme yerine iş mantığına odaklanmanızı sağlar.

## Barcode oluşturma örneği için neden bir Java barcode kütüphanesi kullanılmalı?
- **Hız:** Milisaniyeler içinde yüksek kaliteli barkodlar üretir.  
- **Güvenilirlik:** ISO/IEC standartlarına yerleşik uyumluluk.  
- **Esneklik:** Boyut, renk, kenar boşlukları ve **barcode text** yerleşimi üzerinde tam kontrol.  
- **Çapraz platform:** Masaüstü uygulamalardan bulut hizmetlerine kadar herhangi bir JVM‑tabanlı ortamda çalışır.  

## Data Matrix barkodu nedir?
Data Matrix barkodu, büyük miktarda veriyi kompakt bir kare veya dikdörtgen desen içinde depolayan iki‑boyutlu (2‑D) bir semboldür. Küçük parçalar, elektronik bileşenler ve tıbbi cihazların işaretlenmesinde yaygın olarak kullanılır; çünkü 2.335 alfanümerik karaktere kadar kodlayabilir.

## Neden barkod metni konumu ayarlanmalı?
İnsan‑okunur metni **üstte**, **altta** veya **yanında** konumlandırmak, kullanıcıların taramadan önce kodlanmış veriyi hızlıca doğrulamasını sağlar. Metin konumunu ayarlamak UI tutarlılığını artırır, marka yönergelerine uyar ve manuel veri girişindeki hataları azaltabilir.

## Önkoşullar

- Java programlama temelleri.  
- Java Development Kit (JDK) yüklü.  
- Eclipse veya IntelliJ IDEA gibi bir IDE.  
- Aspose.BarCode for Java kütüphanesi (buradan indirin: [here](https://releases.aspose.com/barcode/java/)).  

## Paketleri İçe Aktarma

İlk olarak, projenize gerekli Aspose.BarCode sınıflarını içe aktarın:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Bu import'lar, barkod üreticisine ve metin konumunu kontrol eden enum'a erişmenizi sağlar.

## Adım adım kılavuz

### Adım 1: Dizin Yollarını Tanımlama
Dosyaları okuyup yazmak istediğiniz konumu belirtin. Yer tutucuları makinenizdeki gerçek yollarla değiştirin.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Adım 2: BarcodeGenerator Örneği Oluşturma
**Data Matrix** türüyle bir `BarcodeGenerator` nesnesi oluşturun ve kodlamak istediğiniz metni sağlayın.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Adım 3: Barkod metni konumunu ayarla (barkod metnini özelleştir)
İnsan‑okunur metni taşımak için `CodeLocation` enum'ını kullanın. Bu örnekte metni barkodun **üstüne** yerleştiriyoruz.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro tip:** Metni **simgeden aşağı** konumlandırmak için `CodeLocation.ABOVE` yerine `CodeLocation.BELOW` yazmanız yeterlidir.

### Adım 4: Oluşturulan Barkod Görüntüsünü Kaydet
Son olarak barkod görüntüsünü diske yazın. Dosya, metni üstte gösteren Data Matrix sembolünü içerecek.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Yaygın Sorunlar ve Çözümler
- **Metin görünmüyor:** `CodeLocation`'ı destekleyen bir Aspose.BarCode sürümü kullandığınızdan emin olun.  
- **Dosya yolu hataları:** `dataDir`'in işletim sisteminize uygun bir dosya ayırıcı (`/` veya `\\`) ile bittiğini kontrol edin.  
- **Desteklenmeyen karakterler:** Data Matrix yalnızca sınırlı bir karakter seti kodlayabilir; ISO/IEC 16022 standardında yer almayan özel sembollerden kaçının.  

## Sık Sorulan Sorular (SSS)

### S: Oluşturulan barkodun görünümünü özelleştirebilir miyim?
C: Evet, Aspose.BarCode renkler, kenar boşlukları ve yazı tipi stilleri gibi geniş özelleştirme seçenekleri sunar.

### S: Aspose.BarCode Java 8 ve sonraki sürümlerle uyumlu mu?
C: Kesinlikle, kütüphane Java 8 ve sonraki tüm sürümlerle çalışır.

### S: Aspose.BarCode'u mevcut Java projemle nasıl entegre ederim?
C: Aspose.BarCode JAR dosyalarını projenizin sınıf yoluna ekleyin, gerekli paketleri içe aktarın ve barkod üretmeye hazırsınız.

### S: Aspose.BarCode için deneme sürümü mevcut mu?
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

### S: Aspose.BarCode için yardım veya destek nereden alınır?
C: Topluluk yardımı ve resmi destek için [Aspose.BarCode forumunu](https://forum.aspose.com/c/barcode/13) ziyaret edin.

## Ek Sık Sorulan Sorular

**S: Metin sembolün altında olacak şekilde bir barkod oluşturabilir miyim?**  
C: Evet, aynı `setLocation` metodunda `CodeLocation.BELOW` ayarlamanız yeterlidir.

**S: Kütüphane QR Code gibi diğer 2‑D barkodları destekliyor mu?**  
C: Kesinlikle, sadece `EncodeTypes.DATA_MATRIX` yerine `EncodeTypes.QR` kullanmanız yeterlidir.

**S: Barkod metninin yazı tipi boyutunu nasıl değiştiririm?**  
C: `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)` metodunu kullanın.

## Sonuç

Artık **java barcode library** kullanarak Java’da bir **Data Matrix barkod** oluşturmayı ve Aspose.BarCode ile **barkod metni konumunu** tam olarak nasıl ayarlayacağınızı öğrendiniz. Uygulamanızın tasarım gereksinimlerine uygun olarak farklı `CodeLocation` değerlerini, yazı tipi ayarlarını ve renk seçeneklerini deneyin.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}