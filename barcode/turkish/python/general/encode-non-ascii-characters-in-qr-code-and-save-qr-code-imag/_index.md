---
category: general
date: 2026-09-10
description: QR kodunda ASCII dışı karakterleri kodlayın ve basit bir Python oluşturucu
  ile QR kodu görüntüsünü kaydedin. ExtCodetextBuilder ve BarcodeGenerator kullanarak
  adım adım bir kılavuzu izleyin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: tr
lastmod: 2026-09-10
og_description: Python kullanarak bir QR kodunda ASCII olmayan karakterleri kodlayın
  ve QR kodu görüntüsünü kaydedin. Bu öğreticide genişletilmiş kod metni nasıl oluşturulur,
  QR kodu nasıl üretilir ve görüntü nasıl saklanır gösterilmektedir.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: QR kodda ASCII olmayan karakterleri kodlayın ve QR kod görüntüsünü kaydedin
  – adım adım Python rehberi
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: QR kodda ASCII olmayan karakterleri kodlayın ve QR kod görüntüsünü kaydedin
url: /tr/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR kodunda ASCII olmayan karakterleri kodlayın ve QR kodu görüntüsünü kaydedin

Eğer bir QR kodunda **ASCII olmayan karakterleri kodlamanız** gerekiyorsa, bu kılavuz tam olarak nasıl yapılacağını ve ardından **QR kodu görüntüsünü** diske **kaydetmeyi** gösterir. Rusça, Çince veya emoji verileriyle çalışıyor olun, ExtCodetextBuilder size düz metin ve ECI‑kodlu segmentleri manuel bayt işlemesi yapmadan karıştırma imkanı sağlar.

Bu eğitimde, genişletilmiş bir codetext dizesi oluşturmayı, bu dizeyi anlayan bir QR kodu üretmeyi ve son olarak barkod görüntüsünü bir dosyaya yazmayı öğreneceksiniz. Eğitim, temel Python bilgisi ve `barcode` SDK'sının kurulu olduğunu varsayar.

## Gereksinimler

Başlamadan önce şunların yüklü olduğundan emin olun:

* Python 3.8+ kurulmuş.
* `ExtCodetextBuilder`, `CodetextEncodingType` ve `BarcodeGenerator` sağlayan `barcode` Python paketi (veya uygun SDK).
* **QR kodu görüntüsünü** kaydetmek istediğiniz dizine yazma izni.

SDK'yı pip ile kurabilirsiniz (`barcode-sdk` kısmını gerçek paket adıyla değiştirin):

```bash
pip install barcode-sdk
```

## Adım 1: Genişletilmiş codetext oluşturucu oluşturun

İlk adım `ExtCodetextBuilder` örneğini oluşturmaktır. Bu nesne birden fazla metin segmentini toplar ve QR kodu sembolojisinin yorumlayabileceği tek bir dize üretir.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Neden önemli*: QR kodları **genişletilmiş codetext**'i destekler; bu, bir barkod içinde birden fazla kodlama modunu (düz, ECI vb.) gömebileceğiniz anlamına gelir. Oluşturucu, QR spesifikasyonu tarafından gerektiren düşük‑seviye biçimlendirmeyi soyutlar.

## Adım 2: Düz‑metin segmenti ekleyin

Düz metin varsayılan moddur ve ASCII karakterler için çalışır. Bunu ilk eklemek, ECI'yi görmezden gelen tarayıcılar için okunabilir bir geri dönüş sağlar.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Bu adımı atlamış olsaydınız, QR kodu yalnızca ECI segmentini içerirdi ve bazı eski okuyucular bunu doğru şekilde çözemeyebilirdi.

## Adım 3: ASCII dışı karakterler için ECI‑kodlu bir segment ekleyin

ASCII aralığının dışındaki karakterleri—örneğin Kiril, Çince veya emoji—kapsamak için bir ECI (Extended Channel Interpretation) kodlaması belirtmeniz gerekir. Burada Rusça “Привет” kelimesi için UTF‑8 kullanıyoruz.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Neden çalışır*: QR spesifikasyonu, tarayıcıya hangi karakter kümesinin uygulanacağını söyleyen ECI değerlerini tanımlar. ECI işareti olmadan, ham baytlar ISO‑8859‑1 olarak yorumlanır ve bozuk çıktı ortaya çıkar.

## Adım 4: Birleştirilmiş genişletilmiş codetext dizesini alın

İstenen tüm segmentleri ekledikten sonra, barkod üreticisinin beklediği son dizeyi elde etmek için `get_extended_codetext()` çağırın.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Yazdırılan değer, bir dizi kontrol karakteri ve ardından gerçek metin gibi görünür, ancak bunu manuel olarak ayrıştırmanız gerekmez.

## Adım 5: Genişletilmiş codetext ile bir QR kodu oluşturun

Şimdi bir `BarcodeGenerator` oluşturun, sembolojiyi QR olarak ayarlayın (genişletilmiş codetext'i destekleyen tek yaygın 2‑D semboloji) ve birleştirilmiş dizeyi besleyin.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*İpucu*: Aynı süreci Code‑128 veya DataMatrix ile denerseniz, SDK bu formatların ECI işaretlerini yorumlayamadığını belirten bir istisna fırlatır.

## Adım 6: QR kodu görüntüsünü kaydedin

Son olarak barkodu bir PNG dosyasına yazın. İşte **QR kodu görüntüsünü** daha sonra kullanmak üzere kaydettiğiniz adım.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`save` metodunu çağırmadan önce `output` klasörünün var olduğundan emin olun veya `os.makedirs('output', exist_ok=True)` ile oluşturun.

### Tam çalıştırılabilir örnek

Tüm adımları bir araya getiren, hemen çalıştırabileceğiniz bağımsız bir betik:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Beklenen çıktı** (konsol):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

`qr_extended.png` dosyasını herhangi bir QR tarayıcıyla açtığınızda `HelloWorldПривет` görüntülenecektir. ECI'yi anlayan tarayıcılar Kiril karakterlerini doğru gösterirken, diğerleri yalnızca ASCII kısmını gösterecektir.

## Sık sorulan sorular & kenar durumları

| Soru | Cevap |
|----------|--------|
| *Shift‑JIS gibi başka kodlamalar kullanabilir miyim?* | Evet. `CodetextEncodingType.UTF_8` yerine `CodetextEncodingType.SHIFT_JIS` kullanın ve uygun metni sağlayın. |
| *Birleştirilmiş veri QR kapasitesini aşarsa ne olur?* | QR kodlarının sürüm limitleri vardır (en fazla 177 × 177 modül). Oluşturucu bir boyut istisnası fırlatırsa, hata‑düzeltme seviyesini artırın veya veriyi birden fazla QR koduna bölün. |
| *Belirli bir QR sürümü ayarlamam gerekiyor mu?* | SDK, veriye uyan en küçük sürümü otomatik seçer. Gerekirse `qr_generator.set_qr_version(10)` ile bir sürüm zorlayabilirsiniz. |
| *Görüntü şeffaf olacak mı?* | Varsayılan olarak SDK, beyaz arka planlı bir PNG yazar. Şeffaflık gerekiyorsa `qr_generator.set_background_color(Color.Transparent)` metodunu `save` öncesinde kullanın. |

## Sonuç

Bu eğitimde, `ExtCodetextBuilder` kullanarak bir QR kodunda **ASCII olmayan karakterleri kodlamayı** ve ardından `BarcodeGenerator` ile **QR kodu görüntüsünü kaydetmeyi** öğrendiniz. Süreç, genişletilmiş bir codetext dizesi oluşturmayı, hem düz hem de ECI‑kodlu segmentler eklemeyi, QR sembolojisini üretmeyi ve son olarak görüntü dosyasını yazmayı içerir.

Bundan sonra keşfedebilecekleriniz:

* Daha fazla ECI segmenti eklemek (farklı diller veya emoji).
* Daha yüksek güvenilirlik için QR hata‑düzeltme seviyelerini ayarlamak.
* Oluşturulan PNG'yi PDF'lere veya web sayfalarına gömmek.

İyi kodlamalar ve çok dilli QR kodları oluşturmanın tadını çıkarın!


## Bir Sonraki Öğrenmeniz Gerekenler


Aşağıdaki eğitimler, bu kılavuzda gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanız ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmeniz için adım‑adım açıklamalı tam çalışan kod örnekleri içerir.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}