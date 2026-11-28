---
category: general
date: 2026-11-27
description: Aspose.Barcode kullanarak Python'da QR barkod oluşturun ve barkod görüntüsünü
  hızlıca diske kaydetmeyi öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: tr
lastmod: 2026-11-27
og_description: Aspose.Barcode ile Python’da QR barkod oluşturun ve barkod görüntüsünü
  anında kaydedin. QR kodlarını oluşturmak, özelleştirmek ve depolamak için tam örneği
  izleyin.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Python ile QR barkod oluşturun ve resmi kaydedin – adım adım rehber
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python ile QR barkod oluştur ve resmi kaydet
url: /tr/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python ile QR barkod oluşturma ve resmi kaydetme

Python uygulamanızda **QR barkod oluşturmanız** gerektiğinde, bu kılavuz Aspose.Barcode kütüphanesini kullanarak nasıl yapacağınızı gösterir. Ayrıca **barkod resmini** yerel bir klasöre kaydetmenin doğru yolunu, kütüphane sürüm detaylarını alma ve genişletilmiş kod metni (codetext) segmentlerini yönetmeyi de öğreneceksiniz.

QR kodları oluşturmak, biletleme sistemleri, mobil ödemeler ve ürün takibi için yaygın bir gereksinimdir. Bu öğreticinin sonunda, QR barkod resmi dosyası üreten ve hata ayıklama ya da uyumluluk amaçlı sürüm bilgilerini yazdıran çalıştırmaya hazır bir betiğe sahip olacaksınız.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

* Python 3.8 veya daha yeni bir sürüm.
* `aspose-barcode` paketi. `pip install aspose-barcode` komutuyla kurabilirsiniz.
* Barkod resminin kaydedileceği dizine yazma izni.

Ek bir dış hizmete ihtiyaç yoktur; tüm süreç yerel olarak çalışır.

## Adım 1: `ExtCodetextBuilder` ile genişletilmiş kod metni oluşturma

Genişletilmiş kod metni, tek bir QR kod içinde düz metin ve ECI (Extended Channel Interpretation) segmentlerini karıştırmanıza olanak tanır. Bu, Euro işareti gibi farklı karakter setlerinden karakterler eklemeniz gerektiğinde faydalıdır.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Bu adımın önemi:**  
`ExtCodetextBuilder`, QR kodlayıcının işleyeceği son dizeyi bir araya getirir. Genişletilmiş kod metni oluşturulmazsa, barkod yalnızca düz ASCII karakterler içerir ve yerel‑özel sembolleri temsil edemez.

## Adım 2: Birleştirilmiş genişletilmiş kod metni dizesini alın

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Çıktı şu şekilde görünür:

```
Extended codetext: ABC123[ECI3]€123
```

Köşeli parantez içinde bulunan `[ECI3]` işareti, QR kodlayıcıya sonraki karakterler için belirtilen karakter setine geçmesini söyler.

## Adım 3: Genişletilmiş kod metniyle QR barkodu oluşturma

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Açıklama:**  
`BarcodeGenerator` iki argüman alır: barkod türü (`QR`) ve kodlanacak veri (`extended_codetext`). Üreteç, render için gerekli tüm iç yapılandırmaları hazırlar.

## Adım 4: Oluşturulan barkod resmini kaydetme

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Bu yaklaşımı neden kullanmalısınız:**  
`save` metodunu doğrudan çağırmak, dosya uzantısından çıkarılan formata göre resmi diske yazar. Metod PNG, JPEG, BMP ve TIFF formatlarını destekler; böylece farklı downstream tüketicileri için esneklik sağlar.

### Kaydedilen resmi doğrulama

`output/qr_extended.png` dosyasını herhangi bir görüntüleyicide açın. Tarandığında `ABC123€123` dizesini döndüren bir QR kod görmelisiniz. Çoğu modern mobil QR tarayıcı, ECI segmentini otomatik olarak işler.

## Adım 5: Aspose.BarCode sürüm bilgilerini sorgulama (isteğe bağlı ama faydalı)

Aspose.BarCode kütüphanesinin tam sürümünü bilmek, hata raporlaması yaparken ya da uyumluluğu doğrularken yardımcı olur.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Tipik çıktı:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Tam betik – kopyala, yapıştır ve çalıştır

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Betik çalıştırıldığında QR kod resmi üretilir ve genişletilmiş kod metni ile sürüm detayları konsola yazdırılır.

## Yaygın varyasyonlar ve kenar durumları

| Durum | Önerilen ayarlama |
|-----------|------------------------|
| **Farklı karakter seti** | `add_eci_codetext` metoduna geçirilen ECI tanımlayıcısını değiştirin. UTF‑8 için `5` kullanın. |
| **Daha yüksek hata düzeltme** | `save` çağrısından önce `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` ayarlayın. |
| **Özel görüntü boyutu** | Piksel boyutlarını kontrol etmek için `barcode.parameters.image_width` ve `barcode.parameters.image_height` değerlerini kullanın. |
| **PNG dışı çıktı** | `output_path` içindeki dosya uzantısını `.jpg` veya `.bmp` olarak değiştirin. Kütüphane doğru kodlayıcıyı otomatik seçer. |

## Profesyonel ipuçları

* **Çıktı klasörünü** programlı olarak oluşturun; klasör mevcut olmayabilir:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **QR kodu** oluşturduktan sonra `aspose.barcode.BarcodeReader` ile geri okuyarak doğrulayın. Bu, özellikle ECI segmentleri kullanıldığında kodlanmış verinin beklentilerle eşleştiğinden emin olmanızı sağlar.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Performans ipucu** – bir döngü içinde çok sayıda QR kod üretmeniz gerekiyorsa aynı `BarcodeGenerator` örneğini yeniden kullanın. Her yinelemede yeni bir nesne oluşturmak yerine `code_text` özelliğini sıfırlayın.

## Sonuç

Artık Aspose.Barcode ile Python’da **QR barkod oluşturmayı**, düz ve ECI segmentlerini karıştıran genişletilmiş kod metni oluşturmayı ve **barkod resmini** diske doğru şekilde kaydetmeyi biliyorsunuz. Betik ayrıca sorun giderme için kütüphane sürüm bilgilerini nasıl alacağınızı gösterir.

İleride keşfedebileceğiniz adımlar:

* QR koda logo ekleme veya özel renkler kullanma.
* QR barkodu doğrudan PDF’lere Aspose.PDF ile gömme.
* Büyük veri setleri için toplu üretim otomasyonu.

Farklı veri yükleri, hata‑düzeltme seviyeleri ve görüntü formatlarıyla denemeler yapmaktan çekinmeyin. İyi kodlamalar!


## Bir Sonraki Öğrenmeniz Gerekenler


Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak adım‑adım açıklamalı tam çalışan kod örnekleri içerir.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}