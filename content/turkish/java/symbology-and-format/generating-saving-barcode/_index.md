---
title: Java'da Barkod Oluşturma ve Kaydetme
linktitle: Barkod Oluşturma ve Kaydetme
second_title: Aspose.BarCode Java API'si
description: Aspose.BarCode ile Java'da zahmetsizce barkod oluşturun ve kaydedin. Sorunsuz bir şekilde entegre edin, görünümü özelleştirin ve kapsamlı barkod desteğinin keyfini çıkarın.
type: docs
weight: 12
url: /tr/java/symbology-and-format/generating-saving-barcode/
---

## giriiş

Barkod oluşturmayı Java uygulamanıza sorunsuz bir şekilde entegre etmek mi istiyorsunuz? Başka yerde arama! Bu adım adım kılavuzda, barkodları verimli bir şekilde oluşturmak ve kaydetmek için Aspose.BarCode for Java'yı kullanma sürecinde size yol göstereceğiz. Aspose.BarCode, barkod oluşturmayı ve işlemeyi kolaylaştıran, uygulamalarınızı barkod işlevselliğiyle geliştirmek için gereken araçları sağlayan güçlü bir Java kütüphanesidir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı: Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.

- Aspose.BarCode Kütüphanesi: Aspose.BarCode kütüphanesini indirip yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/barcode/java/).

- MySQL Veritabanı: Barkodla ilgili bilgileri saklamayı planladığınız bir MySQL veritabanı kurun.

- Veritabanı Bağlantısı: MySQL veritabanıyla etkileşim kurmak için gerekli kimlik bilgilerine ve bağlantıya sahip olduğunuzdan emin olun.

## Paketleri İçe Aktar

Aspose.BarCode ve MySQL bağlantısı için gerekli paketleri Java projenize aktarın.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## 1. Adım: Barkod Oluşturun ve Kaydedin

```java
// Adım 1 - Barkod oluşturun ve geçici olarak bir dosyaya kaydedin
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

Açıklama: Bu adım, Aspose.BarCode ile bir barkod oluşturmayı, kod metnini ayarlamayı ve barkod görüntüsünü belirtilen konuma kaydetmeyi içerir.

## Adım 2: MySQL Veritabanına Kayıt Ekleme

```java
// Adım 2 - MySQL DB'ye yeni bir kayıt ekleyin
Connection con = null;

// Bağlantıyı aç
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Açıklamayı hazırla
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Ürün numarasını ve ürün adını ayarlayın
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 3. sütun barkod görüntüsü içindir. DB türü BLOB'dur
// Resmi kaydetmek için resim dosyasından bir akış oluşturmamız gerekiyor
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// İfadeyi yürüt
pre.executeUpdate();
System.out.println("Insertion successful.");

// Yakın bağlantı
pre.close();
con.close();
```

Açıklama: Bu adım, MySQL veritabanına bağlanmayı ve ürün bilgileri ve ilgili barkod görüntüsünü içeren yeni bir kayıt eklemeyi içerir.

## Çözüm

Tebrikler! Barkod oluşturmak ve kaydetmek için Aspose.BarCode for Java'yı uygulamanıza başarıyla entegre ettiniz. Bu güçlü kütüphane süreci basitleştirerek barkod uygulamasını kolaylaştırır.

## Sıkça Sorulan Sorular

### S: Aspose.BarCode farklı barkod türleriyle uyumlu mudur?
C: Evet, Aspose.BarCode CODE_39_STANDARD, CODE_128, QR ve daha fazlası dahil olmak üzere çeşitli barkod türlerini destekler.

### S: Oluşturulan barkodların görünümünü özelleştirebilir miyim?
C: Kesinlikle! Aspose.BarCode, barkod görünümü için kapsamlı özelleştirme seçenekleri sunarak, barkodu özel ihtiyaçlarınıza göre uyarlamanıza olanak tanır.

### S: Aspose.BarCode'un ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S: Aspose.BarCode için ayrıntılı belgeleri nerede bulabilirim?
 C: Belgelere bakın[Burada](https://reference.aspose.com/barcode/java/).

### S: Aspose.BarCode için nasıl destek alabilirim?
 C: Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/barcode/13) herhangi bir yardım veya sorularınız için.