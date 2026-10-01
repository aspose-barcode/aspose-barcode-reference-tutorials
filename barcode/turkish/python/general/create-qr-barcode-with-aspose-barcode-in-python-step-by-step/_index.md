---
category: general
date: 2026-08-09
description: Aspose.BarCode kullanarak Python'da QR barkod oluşturun. Genişletilmiş
  kod metnini nasıl oluşturacağınızı, görünümünü nasıl ayarlayacağınızı ve görüntüyü
  nasıl kaydedeceğinizi öğrenin—hepsi tek bir öğreticide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: tr
lastmod: 2026-08-09
og_description: Python ile Aspose.BarCode kullanarak QR barkod oluşturun. Bu kılavuz,
  genişletilmiş kod metnini nasıl oluşturacağınızı, görsel parametreleri nasıl ayarlayacağınızı
  ve görüntüyü nasıl dışa aktaracağınızı gösterir.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Python'da Aspose.BarCode ile QR barkod oluşturma – tam kod örneği
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python'da Aspose.BarCode ile QR barkod oluşturma – adım adım rehber
url: /tr/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python'da Aspose.BarCode ile QR barkod oluşturma – adım adım rehber

Python'da **QR barkod oluşturmanız** gerekiyorsa, bu öğretici Aspose.BarCode kütüphanesini kullanarak tüm süreci adım adım gösterir. Ürün kimliklerini, çok dilli metinleri veya özel verileri kodluyor olsanız da, genişletilmiş kod metni nasıl oluşturulur, görsel ayarlar nasıl ayarlanır ve son görüntünün tek bir çalıştırılabilir betikte nasıl kaydedileceğini göreceksiniz.

Örnek ayrıca kütüphane sürümünün nasıl görüntüleneceğini gösterir; bu, uyumlu bir sürüm kullandığınızı doğrulamanıza yardımcı olur. Bu rehberin sonunda, kullanıma hazır bir QR barkod görüntüsüne ve her yapılandırma seçeneğinin net bir anlayışına sahip olacaksınız.

## Önkoşullar

- Python 3.8+ yüklü.
- `aspose-barcode` paketi (kurulum: `pip install aspose-barcode`).
- Python sözdizimi hakkında temel bilgi.
- PNG dosyasının kaydedileceği çıktı dizinine yazma izni.

> **Pro ipucu:** Diğer projelerle sürüm çakışmalarını önlemek için bir sanal ortam kullanın.

## 1. Adım: Aspose.BarCode kütüphane sürümünü doğrulama

Kütüphane sürümünü görüntülemek, genişletilmiş kod metni ve QR kodlamasını destekleyen bir sürüm kullandığınızı garanti eder.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Neden önemli:**  
Eski sürümlerde, düz ve ECI segmentlerinin karışımını desteklemek için gereken `ExtCodetextBuilder` sınıfı bulunmayabilir. Sürümü doğrulamak, iş akışının ilerleyen aşamalarında çalışma zamanı hatalarını önler.

## 2. Adım: Genişletilmiş kod metni dizesi oluşturma

Genişletilmiş bir kod metni, düz ASCII verisini Unicode (ECI) segmentleriyle birleştirmenizi sağlar; bu, çok dilli QR kodları için gereklidir.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Neden önemli:**  
`add_plain_codetext` yöntemi veriyi standart ASCII olarak saklarken, `add_eci_codetext` Unicode bloğunu uygun ECI tanımlayıcısı ile önekler. Bu yaklaşım, QR tarayıcıların Japonca metni doğru yorumlamasını sağlar ve bozuk karakterlerin ortaya çıkmasını engeller.

### Yaygın varyasyonlar

- **Birden fazla ECI segmenti:** Birden çok dili karıştırmak için `add_eci_codetext` metodunu birden fazla kez çağırın.
- **Farklı ECI tanımlayıcıları:** Hedef kodlamanıza bağlı olarak ISO‑8859‑1 için `27`, ISO‑8859‑2 için `28` vb. kullanın.

## 3. Adım: Genişletilmiş kod metni ile QR barkod oluşturma

Artık doğru biçimlendirilmiş bir dizeye sahip olduğumuza göre, QR kodunu oluşturabiliriz.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Neden önemli:**  
`EncodeTypes.QR`, Aspose.BarCode'e QR sembolünü kullanmasını söyler. `extended_codetext`'i doğrudan geçirmek, karışık veriyi QR matrisine bağlar ve hem düz hem de Unicode bölümlerinin korunmasını sağlar.

## 4. Adım: Görsel görünümü ayarlama (isteğe bağlı ancak önerilir)

Barkodun görsel parametrelerini ince ayar yapmak, tarama güvenilirliğini artırır ve marka yönergelerine uyum sağlar.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Neden önemli:**  
- **`x_dimension`** her QR modülünün boyutunu kontrol eder; çok küçük olması düşük çözünürlüklü cihazlarda okuma hatalarına yol açabilir.  
- **`border_width`** sessiz bir bölge ekler. Bazı tarayıcılar en az 4 modül sessiz bölge ister; kütüphane bunu otomatik ekler, ancak ekstra güvenlik için artırabilirsiniz.

### Kenar durumları yönetimi

- **Yüksek yoğunluklu veri:** Kodlanan veri büyükse, `x_dimension` değerini artırmanız veya daha yüksek bir hata düzeltme seviyesi seçmeniz ( `qr_generator.parameters.qr.error_correction_level` aracılığıyla) gerekebilir.  
- **Şeffaf arka plan:** Alfa kanallı PNG'ler için `qr_generator.parameters.barcode.bg_color = Color.Transparent` ayarlayın.

## 5. Adım: QR barkod görüntüsünü kaydetme

Son olarak, görüntüyü tercih ettiğiniz formatta diske yazın.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Neden önemli:**  
PNG olarak kaydetmek kayıpsız kaliteyi korur; bu, keskin kenarlara ihtiyaç duyan QR kodları için idealdir. Web uygulaması için farklı bir formata ihtiyacınız varsa, sadece `BarCodeImageFormat` enum'ını değiştirin.

### Sonucu doğrulama

Kaydedilen dosyayı herhangi bir görüntüleyicide açın. Tarandığında birleşik dizeyi döndüren bir QR kodu görmelisiniz:

```
ABC12345
こんにちは
```

Çoğu modern QR tarayıcı uygulaması önce düz segmenti gösterir ve ardından Japonca selamlamayı doğru şekilde render eder.

---

## Tam çalıştırılabilir betik

Aşağıdaki tüm bloğu `create_qr_barcode.py` adlı bir dosyaya kopyalayın ve `python create_qr_barcode.py` ile çalıştırın. `YOUR_DIRECTORY` değerini makinenizde yazılabilir bir klasöre göre ayarlayın.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Bu betiği çalıştırdığınızda sürüm, genişletilmiş kod metni ve PNG dosyasının oluşturulduğuna dair bir onay mesajı yazdırılır.

---

## Sonuç

Artık Python'da Aspose.BarCode kullanarak **QR barkod** görüntüleri oluşturmayı biliyorsunuz. Öğreticide şunlar ele alındı:

1. Kütüphane sürümünün doğrulanması.  
2. Düz ve ECI (Unicode) segmentleriyle genişletilmiş kod metni oluşturma.  
3. QR kodunun oluşturulması.  
4. Modül boyutu ve kenar genişliği gibi görsel parametrelerin özelleştirilmesi.  
5. Son görüntünün PNG formatında kaydedilmesi.

Bundan sonra şunları keşfedebilirsiniz:

- Hata düzeltme seviyelerini değiştirme (`qr_generator.parameters.qr.error_correction_level`).  
- Logo veya arka plan resmi ekleme (`qr_generator.parameters.qr.logo`).  
- SVG gibi ölçeklenebilir web grafikleri için diğer formatlara dışa aktarma.  
- Flask veya Django uç noktasına entegre ederek anlık QR oluşturma.

Uygulamanızın marka kimliğine ve tarama gereksinimlerine uygun farklı veri yükleri ve görsel ayarlarla deneyler yapın. Kodlamanın tadını çıkarın!

## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Aspose.BarCode ile .NET için dotcode genişletilmiş kod metni oluşturma](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose .NET ile barkod oluşturma – DataMatrix kod metnini yapılandırma](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode ile .NET için ITF-14 Barkod Sessiz Bölgesi Oluşturma](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}