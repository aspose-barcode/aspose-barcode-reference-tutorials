---
category: general
date: 2026-11-27
description: DataBar Omni‑Directional barkod üreteçinde barkod çubuğu yüksekliğini
  nasıl ayarlayacağınızı öğrenin. Adım adım kod, yüksekliği 30 px ve 60 px olarak
  ayarlamayı gösterir.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: tr
lastmod: 2026-11-27
og_description: Python ile DataBar Omni‑Directional barkod üreteçte barkod çubuğu
  yüksekliğini ayarlayın. Yükseklikleri, X‑boyutunu belirlemek ve PNG görüntülerini
  kaydetmek için tam kılavuzu izleyin.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: DataBar Omni‑Yönlü oluşturucusunda barkod çubuğu yüksekliğini ayarlayın
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: DataBar Omni‑Directional jeneratöründe barkod çubuğu yüksekliğini nasıl ayarlarsınız
url: /tr/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar Omni‑Directional jeneratöründe barkod çubuk yüksekliğini ayarlama

DataBar Omni‑Directional barkod için **barkod çubuk yüksekliğini ayarlamanız** gerekiyorsa, bu kılavuz tam olarak nasıl yapılacağını gösterir. X‑dimension ve görüntü formatını aynı tutarken çubuk yüksekliğini 30 px'den 60 px'e değiştiren tam, çalıştırılabilir bir Python örneği göreceksiniz.

Barkodun görsel boyutlarını değiştirmek, barkodun belirli bir etiket boyutuna veya tasarım kılavuzuna uyması gerektiğinde yaygın bir gereksinimdir. Çubuk yüksekliğine ek olarak **X‑dimension** (modül boyutu) ayarlamak veya PNG ya da JPEG gibi farklı bir **barcode image format** seçmek isteyebilirsiniz.

Bu öğreticide şunları yapacaksınız:

* Gerekli kütüphaneyi (GroupDocs.Barcode for Python) kurun
* Bir DataBar Omni‑Directional barkod jeneratörü oluşturun
* `XDimension` ile modül boyutunu ayarlayın
* Çubuk yüksekliği özelliğini iki kez değiştirin
* Sonuçta oluşan görüntüleri istediğiniz **BarCodeImageFormat** ile kaydedin

GroupDocs API'siyle ilgili önceden bir deneyime ihtiyacınız yok—sadece temel Python bilgisi yeterli.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

* Python 3.8 veya daha yeni bir sürüm
* `groupdocs.barcode` paketi (`pip install groupdocs-barcode`)  
* PNG dosyalarının kaydedileceği klasöre yazma izni

**DataBar Omni‑Directional barkod** hakkında bilginiz yoksa, 14 haneli bir GTIN kodlar ve perakendede her yönden taramaya izin verdiği için yaygın olarak kullanılır.

## Adım 1: DataBar Omni‑Directional barkod jeneratörünü kurun

İlk olarak gerekli sınıfları içe aktarın ve kodlamak istediğiniz GTIN verisiyle jeneratörü örnekleyin.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Neden önemli:* `EncodeTypes.DatabarOmniDirectional` sabiti, kütüphaneye Omni‑Directional sembolojisini üretmesini söyler. Veri dizesi, GTIN‑14 değerini işaretleyen `(01)` AI kodunu içerir.

## Adım 2: X‑dimension (modül boyutu) tanımlayın

X‑dimension, en dar çubuğun genişliğini kontrol eder. Ekranda görüntüleme için yaygın bir değer **modül başına 2 px**'dir.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Tutarlı bir **set XDimension** kullanmak, barkodun farklı yazıcı ve tarayıcılarda doğru ölçeklenmesini sağlar.

## Adım 3: Çubuk yüksekliğini 30 px yapın ve görüntüyü kaydedin

Şimdi çubuk yüksekliği özelliğini değiştiriyoruz. İlk olarak kullanacağımız yükseklik **30 px**'dir; bu, küçük etiketler için uygundur.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` sabiti, **barcode image format** olarak PNG'yi seçer; bu da kayıpsız kaliteyi korur.

### Beklenen sonuç

`DatabarBarHeight30Pixels.png` dosyası, çubukları 30 px yüksekliğinde bir DataBar Omni‑Directional barkod içerir. Aşağıda bir yer tutucu ön izleme yer almaktadır:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **İpucu:** PNG'yi bir görüntü düzenleyicide açarsanız, tam çubuk yüksekliğini görebilirsiniz. Dar çubuklar, daha önce tanımlanan 2 px genişliğindedir.

## Adım 4: Daha uzun bir barkod için çubuk yüksekliğini 60 px yapın

Freight etiketi gibi daha büyük bir görsel alan gerektiren uygulamalar için çubuk yüksekliğini **60 px**'e çıkarabilirsiniz.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Sadece `BarHeight` özelliği değişir; X‑dimension ve kodlama aynı kalır, böylece barkod taranabilirliğini korur.

## Adım 5: Güncellenmiş barkod görüntüsünü kaydedin

Son olarak, daha uzun barkodu ikinci bir PNG dosyasına yazın.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Beklenen sonuç

`DatabarBarHeight60Pixels.png` aynı veriyi kodlar, ancak her çubuk artık 60 px yüksekliğindedir. Görsel fark aşağıda gösterilmiştir:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Tam, çalıştırılabilir örnek

Her şeyi bir araya getirdiğimizde, `adjust_barcode_height.py` adlı bir dosyaya kopyalayıp doğrudan çalıştırabileceğiniz tam betik aşağıdadır.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Betik çalıştırın:

```bash
python adjust_barcode_height.py
```

`output` klasöründe iki PNG dosyası görmelisiniz; her biri ayarladığınız çubuk yüksekliğini yansıtır.

## Yaygın sorular ve kenar durumları

| Question | Answer |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is lossy, so prefer PNG for precise scanning. |
| **What if I need a bar height that isn’t a multiple of 10?** | The `BarHeight.Pixels` property accepts any integer value. Just assign the desired pixel count (e.g., `45`). |
| **Does changing the bar height affect the encoded data?** | No. Only the visual representation changes; the underlying data string remains identical. |
| **How do I change the X‑dimension after saving the first image?** | You can modify `gen.parameters.barcode.x_dimension.pixels` at any time before calling `save()`. The change will apply to subsequent images. |
| **Is the generator thread‑safe?** | The `BarcodeGenerator` instance is not guaranteed to be thread‑safe. Create a separate instance per thread if you generate barcodes concurrently. |

## Sonuç

Python kullanarak bir DataBar Omni‑Directional barkod jeneratöründe **barkod çubuk yüksekliğini ayarlamayı** artık biliyorsunuz. Öğreticide jeneratör oluşturma, **X‑dimension** ayarlama, **barcode bar height** özelliğini değiştirme ve istenen **barcode image format** ile görüntüleri kaydetme konuları ele alındı.

Buradan itibaren farklı yükseklikler, farklı modül boyutları deneyebilir ya da JPEG veya BMP gibi alternatif görüntü formatlarına geçebilirsiniz. Ayrıca **barcode generator python** özellikleri arasında insan‑okunabilir metin ekleme veya renk şemalarını değiştirme gibi ek işlevleri keşfedebilirsiniz.

İyi kodlamalar, barkodlarınız her zaman net ve mükemmel boyutta olsun!

## Bir Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanarak ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanız ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmeniz için adım‑adım açıklamalı tam çalışan kod örnekleri içerir.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}