---
date: 2026-10-19
description: Aspose.BarCode for Java kullanarak QR code java oluşturmayı ve tek bir
  görüntüde birden fazla barkod üretmeyi öğrenin. Kurulum, kod ve sorun giderme konularını
  içerir.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Tek bir görüntüde birden fazla barkod oluşturma
og_description: Aspose.BarCode for Java ile QR code java oluşturun ve çeşitli barkod
  türlerini tek bir görüntüde birleştirin. Adım adım kılavuzu izleyin, kod parçacıklarını
  görün ve sorun giderme ipuçlarını öğrenin.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR code java oluşturma – tek bir görüntüde birden fazla barkod oluşturma
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR code java oluşturma – tek bir görüntüde birden fazla barkod oluşturma
url: /tr/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR kodu java oluşturma – tek bir görüntüde birden fazla barkod oluşturma

## Giriş

Bu öğreticide **how to create QR code java** ve **Aspose.BarCode for Java** kullanarak çeşitli barkod tiplerini tek bir tuvalde birleştirmeyi öğreneceksiniz. Kompakt bir QR etiketi, bir ürün barkodu veya 2‑D ve doğrusal sembolojilerin bir karışımına ihtiyacınız olsun, bu kılavuz sizi proje kurulumundan son birleşik görüntünün kaydedilmesine kadar her adımda yönlendirir—böylece barkod üretimini Java uygulamalarınıza hemen entegre etmeye başlayabilirsiniz.

## Hızlı cevaplar
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.BarCode for Java, en kapsamlı semboloji setini sağlar.  
- **Farklı barkod tiplerini birlikte oluşturabilir miyim?** Evet, tek bir tuvalde CODE_39, QR, AZTEC ve daha fazlasını karıştırabilirsiniz.  
- **Geliştirme için bir lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü test için çalışır; üretim için ticari bir lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri tamamen uyumludur.  
- **Çıktı formatı yapılandırılabilir mi?** Birleşik görüntüyü PNG, JPEG, BMP veya TIFF formatında dışa aktarabilirsiniz.  

## create QR code java nedir?

`create QR code java`, bir metin dizesini akıllı telefonlar veya barkod okuyucular tarafından taranabilen iki boyutlu bir matrise dönüştürme sürecine denir. Aspose.BarCode for Java, kodlamayı ve renderlamayı gerçekleştirir, böylece piksel düzeyindeki görüntü işleme yerine iş mantığına odaklanabilirsiniz.

## Java’da barkod oluşturmak için Aspose.BarCode Java neden kullanılmalı?

Aspose.BarCode, **over 50 barcode symbologies**—QR, Data Matrix, Code 128, AZTEC ve geleneksel doğrusal kodlar dahil—destekleyerek en çok yönlü Java barkod kütüphanesi olmasını sağlar. **anti‑aliased images at up to 1200 dpi** render eder, ekranda ve baskıda net taramalar garantiler. API yalnızca JVM gerektirir ve sadece birkaç satır kodla boyut, renk, kenar boşlukları ve hata düzeltmesini özelleştirebileceğiniz akıcı bir yapılandırma modeli sunar.

## Önkoşullar

- Java temellerine sağlam bir hakimiyet.  
- JDK 8 veya daha yenisi kurulu ve PATH içinde yapılandırılmış.  
- Aspose.BarCode for Java JAR (resmi Aspose.BarCode for Java indirme sayfasından indirin).  
- IntelliJ IDEA veya Eclipse gibi bir IDE, örnek kodu düzenlemek ve çalıştırmak için.  

## Ad alanlarını içe aktar

İçe aktarma ifadeleri, `BarcodeGenerator`, `EncodeTypes` ve `BarCodeImageFormat` gibi Aspose.BarCode sınıflarını kapsam içine getirir, böylece tam nitelikli isimler kullanmadan onlara referans verebilirsiniz.  
`BarcodeGenerator`, barkod görüntülerini yapılandırmak ve oluşturmak için kullanılan ana sınıftır.  
`EncodeTypes`, Aspose.BarCode içinde bir enum olup oluşturulacak barkod sembolojisini belirtir.  
`BarCodeImageFormat`, oluşturulan barkodun çıktı görüntü formatını tanımlar.

## Adım 1: kaynak dizinini ayarla

**resource directory**, oluşturulan tüm barkod görüntülerinin yazılacağı dosya sisteminizdeki klasördür. Bir kez tanımlamak projenizi düzenli tutar ve eski dosyaları temizlemeyi kolaylaştırır.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Adım 2: barkod koleksiyonu oluştur

`HashMap<String, EncodeTypes>` her barkodun veri dizesini kullanmak istediğiniz sembolojiyle birlikte depolar. `HashMap`, anahtarları değerlere eşleyen bir Java koleksiyonudur. Bu koleksiyon, ardından gelen üretim döngüsünü yönlendirir. `EncodeTypes`, hangi barkod tipinin oluşturulacağını belirten bir enumdur.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Adım 3: barkod görüntülerini oluştur

Üretim döngüsü `HashMap` üzerinde yineleme yapar, her giriş için bir `BarcodeGenerator` oluşturur ve `generateBarCodeImage()` metodunu çağırarak bir `BufferedImage` elde eder. `generateBarCodeImage()` renderlanmış barkodu içeren bir `BufferedImage` oluşturur. `BufferedImage`, bellekte bir görüntüyü temsil eden bir Java sınıfıdır. Tüm görüntüler daha sonra bir `ArrayList<BufferedImage>` içine eklenir. `ArrayList`, Java’da yeniden boyutlandırılabilir bir liste uygulamasıdır.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Adım 4: birleşik bir görüntü oluştur

İlk olarak, algoritma tüm barkod görüntüleri arasındaki **maximum width** değerini ve isteğe bağlı boşlukla dikey olarak istiflemek için gereken **total height** değerini hesaplar. Ardından bu boyutta bir `BufferedImage` oluşturur ve her barkodu bir `Graphics2D` nesnesi kullanarak tuval üzerine çizer. `Graphics2D`, şekil ve görüntü çizmek için 2D renderleme yetenekleri sağlayan bir Java sınıfıdır.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Adım 5: sonucu kaydet

Son olarak, birleşik görüntü `ImageIO.write` ile diske yazılır, belirttiğiniz format (PNG, JPEG, BMP veya TIFF) kullanılarak. `ImageIO.write`, bir `BufferedImage`'i belirtilen formatta bir dosyaya yazar. Dosya yolu, daha önce tanımlanan kaynak dizinine göredir.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Birden fazla barkod oluşturmanın yaygın kullanım senaryoları

- **Packaging labels** – tek bir etiket üzerinde ürün, parti ve gönderim kodlarını birleştirerek baskı maliyetlerini azaltın.  
- **Event tickets** – mekânda farklı tarama istasyonları için QR, Data Matrix ve Code 128 tanımlayıcılarını gömün.  
- **Inventory management** – hızlı denetim ve izlenebilirlik için SKU, RFID etiket verisi ve seri numaralarını birlikte gösterin.

## Sorun giderme ve ipuçları

- **Image size issues** – barkodlar arasındaki boşluğu artırmak veya azaltmak için `offset` değişkenini ayarlayın.  
- **Unsupported symbology** – Aspose.BarCode sürümünüzün istediğiniz barkod tipini desteklediğini doğrulayın; yeni sürümler ek 2‑D kodlar ekler.  
- **Performance** – döngüde çok sayıda görüntü oluştururken nesne tahsis yükünü azaltmak için tek bir `Graphics2D` nesnesini yeniden kullanın.  

## Sıkça sorulan sorular

**Q: Oluşturulan görüntüdeki tek tek barkodların görünümünü özelleştirebilir miyim?**  
A: Evet. `BarcodeGenerator` özelliklerini, örneğin `setBarColor`, `setBackgroundColor` ve `setXDimension` gibi, her barkodu tuval üzerine eklemeden önce bağımsız olarak stil vermek için kullanın.

**Q: Aspose.BarCode farklı barkod sembolojileriyle uyumlu mu?**  
A: Kesinlikle. Kütüphane, bu öğreticide gösterildiği gibi CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 ve AZTEC dahil 50+ sembolojiyi destekler.

**Q: Aspose.BarCode’u Java projemle nasıl entegre ederim?**  
A: Aspose.BarCode for Java kütüphane indirme sayfasından JAR dosyasını indirin, projenizin sınıf yoluna ekleyin ve “Ad alanlarını içe aktar” bölümünde gösterildiği gibi gerekli ad alanlarını içe aktarın.

**Q: Aspose.BarCode’u ticari uygulamalarda kullanabilir miyim?**  
A: Evet. Deneme sınırlamalarını kaldırmak ve tam üretim desteği almak için Aspose.BarCode lisans satın alma sayfasından bir lisans satın alın.

**Q: Aspose.BarCode için deneme seçenekleri mevcut mu?**  
A: Elbette. Aspose.BarCode ücretsiz deneme indirme sayfasından bir ücretsiz deneme lisansı alabilirsiniz; bu, değerlendirme için tam API erişimi sağlar.

**Q: Baskı için yüksek çözünürlüklü bir QR kodu nasıl oluştururum?**  
A: `generateBarCodeImage()` metodunu çağırmadan önce `BarcodeGenerator` üzerinde `setResolutionDpi` özelliğini ayarlayın, ardından sonucu PNG gibi kayıpsız bir formatta kaydedin.

**Q: Birleşik görüntü kesik görünüyor ise ne yapmalıyım?**  
A: `offset` ve tuval boyutu hesaplamalarının tüm barkod yüksekliklerini doğru şekilde hesaba kattığını doğrulayın; tuval yüksekliğini artırmak veya tek tek barkod boyutlarını küçültmek çoğu kesilme sorununu çözer.

---

**Son Güncelleme:** 2026-10-19  
**Test Edilen Versiyon:** Aspose.BarCode for Java 24.11  
**Yazar:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## İlgili Öğreticiler

- [Java’da Barkod Görüntüsü Oluşturma – Aspose ile Kenarlık Ekleme](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Java’da Barkod Oluşturma: Aspose.BarCode ile Akışlara Kaydetme](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Java’da Barkod Oluşturma ve Aspose ile Barkod Yazdırma](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}