---
title: Aspose.BarCode ile Java'da Tek Görüntü Üzerinde Çoklu Barkod Oluşturma
linktitle: Tek Bir Görüntü Üzerinde Çoklu Barkod Oluşturma
second_title: Aspose.BarCode Java API'si
description: Aspose.BarCode for Java'yı kullanarak tek bir görüntü üzerinde zahmetsizce birden fazla barkod oluşturun. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
type: docs
weight: 19
url: /tr/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## giriiş

Java programlamanın dinamik dünyasında, barkodları verimli bir şekilde oluşturmak ve yönetmek, çeşitli uygulamalar için çok önemlidir. Aspose.BarCode for Java bu süreci basitleştirerek geliştiricilerin tek bir görüntü üzerinde birden fazla barkodu sorunsuz bir şekilde oluşturmasına olanak tanır. Bu eğitim, Aspose.BarCode'u Java ortamında kullanarak bunu başarmanıza yönelik adımlar konusunda size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Java programlamanın temel anlayışı.
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.BarCode for Java kütüphanesi indirildi ve kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/barcode/java/).
- Eclipse veya IntelliJ IDEA gibi entegre bir geliştirme ortamı (IDE).

## Ad Alanlarını İçe Aktar

Aspose.BarCode işlevselliğine erişmek için Java projenizde gerekli ad alanlarını içe aktarın. Aşağıdaki import ifadelerini Java sınıfınızın başına ekleyin:

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

## 1. Adım: Kaynak Dizinini Ayarlayın

Oluşturulan barkodların kaydedileceği kaynak dizininin yolunu tanımlayın. Bu dizin, barkod görsellerinizi düzenlemek ve yönetmek için çok önemlidir.

```java
// Kaynak dizininin yolu.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Adım 2: Barkod Koleksiyonu Oluşturun

Barkod verilerini depolamak için bir HashMap başlatın. Koleksiyondaki her giriş, ilgili kodlama türüne sahip bir barkodu temsil eder.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 3. Adım: Barkod Görüntüleri Oluşturun

Koleksiyonu yineleyin ve Aspose.BarCode kütüphanesini kullanarak barkod görüntüleri oluşturun. Daha ileri işlemler için görüntüleri bir ArrayList'te saklayın.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 4. Adım: Birleştirilmiş Bir Görüntü Oluşturun

Barkod görüntülerinin maksimum genişliğini ve toplam yüksekliğini belirleyin. Bireysel barkod görüntülerini tek bir çıktı görüntüsünde birleştirmek için BufferedImage oluşturun.

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
## Adım 5: Sonucu Kaydet

Son birleştirilmiş görüntüyü belirtilen dosya konumuna kaydedin.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Çözüm

Tebrikler! Aspose.BarCode for Java'yı kullanarak tek bir görüntü üzerinde birden fazla barkodu başarıyla oluşturdunuz. Bu güçlü kitaplık, barkod kullanımını basitleştirerek onu Java geliştiricileri için paha biçilmez bir araç haline getirir.

## SSS'ler

### S1: Oluşturulan görüntüdeki barkodların görünümünü ayrı ayrı özelleştirebilir miyim?

C1: Evet, Aspose.BarCode, barkod görünümü için kapsamlı özelleştirme seçenekleri sunarak her barkodun stilini tercihlerinize göre uyarlamanıza olanak tanır.

### S2: Aspose.BarCode farklı barkod sembolojileriyle uyumlu mudur?

A2: Kesinlikle! Aspose.BarCode, bu eğitimde gösterildiği gibi CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 ve AZTEC dahil olmak üzere çok çeşitli sembolojileri destekler.

### S3: Aspose.BarCode'u Java projeme nasıl entegre edebilirim?

 Cevap3: Aspose.BarCode for Java kütüphanesini şuradan indirmeniz yeterli:[Burada](https://releases.aspose.com/barcode/java/) ve belgelerde verilen kurulum talimatlarını izleyin.

### S4: Aspose.BarCode'u ticari uygulamalar için kullanabilir miyim?

 Cevap4: Evet, adresinden lisans alabilirsiniz.[Burada](https://purchase.aspose.com/buy) Aspose.BarCode'u ticari amaçlarla kullanmak.

### S5: Aspose.BarCode için herhangi bir deneme seçeneği mevcut mu?

 A5: Kesinlikle! Ücretsiz deneme lisansı alarak Aspose.BarCode'un özelliklerini keşfedebilirsiniz.[Burada](https://releases.aspose.com/).