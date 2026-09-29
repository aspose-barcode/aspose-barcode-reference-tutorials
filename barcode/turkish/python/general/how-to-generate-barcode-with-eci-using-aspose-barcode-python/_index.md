---
category: general
date: 2026-08-19
description: Aspose.Barcode for Python kullanarak ECI ile barkod nasıl oluşturulur.
  ECI verisini eklemeyi, düz metni karıştırmayı ve resmi kaydetmeyi tek bir net rehberde
  öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: tr
lastmod: 2026-08-19
og_description: Aspose.Barcode for Python kullanarak ECI ile barkod nasıl oluşturulur.
  Bu öğreticiyi izleyerek eci verisi eklemeyi, görünümü özelleştirmeyi ve sonucu kaydetmeyi
  öğrenin.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Aspose.Barcode Python ile ECI kullanarak barkod nasıl oluşturulur – adım
  adım
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Aspose.Barcode Python kullanarak ECI ile barkod nasıl oluşturulur
url: /tr/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ECI kullanarak Aspose.Barcode Python ile barkod oluşturma

Düz metin karakterleri ve ECI‑kodlu verileri içeren **barkod nasıl oluşturulur** bilmeniz gerekiyorsa, bu kılavuz tam süreci gösterir. **eci nasıl eklenir** bölümlerini, boyutu ayarlamayı ve tek bir çalıştırılabilir betikle görüntüyü diske kaydetmeyi göreceksiniz.

The tutorial covers:

* Aspose.Barcode kütüphane sürümünü alma (isteğe bağlı ancak hata ayıklama için faydalı).  
* Düz ve ECI‑kodlu karakterleri karıştıran genişletilmiş kod metni dizesi oluşturma.  
* Genişletilmiş kod metnini destekleyen bir semboloji için barkod oluşturucu oluşturma.  
* Barkod boyutlarını özelleştirme ve son PNG dosyasını kaydetme.

Harici bir dokümantasyona gerek yok; kodu kopyalayın, çalıştırın ve ECI 26 (UTF‑8) ile kodlanmış Çince karakterleri içeren bir barkod görüntüsü elde edeceksiniz.

## Önkoşullar

Before you start, make sure you have:

* Python 3.8 veya daha yeni bir sürüm yüklü.  
* `aspose-barcode` paketi yüklü (`pip install aspose-barcode`).  
* PNG dosyasını kaydetmek istediğiniz klasöre yazma izni.

Bir sanal ortam kullanıyorsanız, bağımlılıkları izole tutmak için önce onu etkinleştirin.

## Adım 1: Aspose.Barcode sürümünü doğrula (isteğe bağlı)

Knowing the exact library version helps when you need to report bugs or compare features across releases.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Neden önemli*: Sürüm çıktısı, çalıştırma ortamının takip ettiğiniz dokümantasyonla eşleştiğini doğrular. Farklı sürümler farklı ECI değerlerini destekleyebilir, bu yüzden hızlı bir kontrol sağlar.

## Adım 2: Düz ve ECI‑kodlu bölümlerle genişletilmiş kod metni oluşturma

Aspose.Barcode, düz veri ve ECI‑kodlu segmentleri birleştirmek için `ExtCodetextBuilder` sağlar. Bu örnekte sayısal bir dizeyi Çince karakterlerle karıştırıyoruz.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Açıklama*:  
* `add_plain_codetext` barkod sembolojisinin normal karakterler olarak yorumladığı veriyi ekler.  
* `add_eci_codetext` jeneratöre, sağlanan metinden önce bir ECI göstergesi (burada **26**, UTF‑8’e karşılık gelir) eklemesini söyler. Bu, bir barkoda **eci nasıl eklenir** verisinin tam olarak eklenmesidir.

`add_eci_codetext` metodunu birden fazla kez çağırarak çeşitli dil bloklarını gömebilirsiniz. Builder gerekli kaçış dizilerini otomatik olarak yönetir.

## Adım 3: Genişletilmiş kod metnini destekleyen bir semboloji seçin

Not every barcode type can store ECI segments. Code 128, QR, and Data Matrix are common choices. The example uses Code 128 because it is widely supported and works well for mixed alphanumeric data.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Neden Code 128?*: Builder tarafından üretilen tam ASCII aralığını ve ECI kaçış dizilerini kabul eder, bu da düz ve kodlanmış metni karıştıran “barkod nasıl oluşturulur” senaryosu için idealdir.

## Adım 4: Barkod görünümünü ayarla

You can control size, height, margins, and many other visual aspects via the `parameters` object.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*İpucu*: Barkodu yazdırmayı planlıyorsanız, hedef DPI’da okunabilirliği korumak için `x_dimension` ve `bar_height` değerlerini orantılı olarak artırın.

## Adım 5: Barkod görüntüsünü kaydet

Finally, write the generated image to a file. Aspose.Barcode supports PNG, JPEG, BMP, and many other formats.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

`save` metodunu çağırmadan önce `output` klasörünün var olduğundan emin olun veya `os.makedirs("output", exist_ok=True)` ile oluşturun.

### Beklenen sonuç

When you open `extended_codetext.png`, you should see a Code 128 barcode that encodes the numeric string `1234567890` followed by the Chinese characters “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return the original mixed string.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode oluşturma örneği ile oluşturulan barkod"}

## Yaygın sorular ve uç durumlar

### Farklı bir karakter setine ihtiyacım olsaydı ne olur?

Choose the appropriate ECI value from the ISO/IEC 18004 table. For example, ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext` accordingly.

### Birden fazla ECI bloğu gömebilir miyim?

Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary ECI switch codes between blocks, preserving the order you add them.

### Jeneratör QR kodlarını ECI ile destekliyor mu?

Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR` and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Çok uzun veri dizelerini nasıl yönetirim?

For linear barcodes like Code 128, the maximum length is about 80 characters when using extended codetext. If you exceed that, consider switching to a two‑dimensional symbology such as QR or Data Matrix, which can store thousands of characters.

## Tam, çalıştırılabilir betik

Below is the complete program you can copy‑paste into a file named `generate_extended_barcode.py` and run directly.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Sonra Ne Öğrenmelisiniz?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Aspose.BarCode ile Ekstra Boşluk Özelleştirmesi Kullanarak Barkod Görüntüsü Oluşturma](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Aspose.BarCode ile Java’da Barkod Görüntüsü Oluşturma](/barcode/english/java/barcode-rendering-techniques/)
- [.NET için Aspose.BarCode ile DataMatrix barkodu oluşturma](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}