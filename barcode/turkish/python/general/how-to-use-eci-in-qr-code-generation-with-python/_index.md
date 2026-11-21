---
category: general
date: 2026-11-20
description: ECI'yi nasıl kullanacağınızı, metinden QR oluşturmayı, oluşturucuyu temizlemeyi
  ve Python barkod kütüphanesini kullanarak QR görüntüsünü kaydetmeyi öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: tr
lastmod: 2026-11-20
og_description: ECI'yi kullanarak metinden QR oluşturma, QR oluşturucuyu temizleme
  ve QR görüntüsünü kaydetme – adım adım eksiksiz bir rehber.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Python ile QR kod oluştururken ECI nasıl kullanılır
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Python ile QR kod oluştururken ECI nasıl kullanılır
url: /tr/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python ile QR kod oluştururken ECI nasıl kullanılır

QR kodları oluştururken **ECI nasıl kullanılır**'a ihtiyacınız varsa, bu rehber tam adımları gösterir. Metinden QR nasıl oluşturulur, builder nasıl temizlenir ve sonunda QR resmi nasıl kaydedilir—hepsini birkaç Python satırıyla göreceksiniz.

Çok dilli veri içeren QR kodları genellikle tarayıcının hangi karakter setini uygulayacağını bilmesi için bir Genişletilmiş Kanal Yorumlaması (ECI) segmenti gerektirir. Bu öğretici, genişletilmiş kod metni oluşturmayı, builder'ı yeniden kullanırken temizlemeyi ve sonucu PNG dosyası olarak kaydetmeyi adım adım gösterir.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

- Python 3.8+ yüklü.
- Aspose.BarCode for Python via .NET paketi (veya `ExtCodetextBuilder` ve `BarcodeGenerator` sağlayan herhangi bir uyumlu `barcode` kütüphanesi).
- QR kod kavramları hakkında temel bilgi.

Kütüphaneyi pip ile kurun:

```bash
pip install aspose-barcode
```

> **Pro tip:** Sürüm çakışmalarını önlemek için bir sanal ortam kullanın.

## Adım 1: Gerekli sınıfları içe aktarın

İşleyeceğiniz temel sınıflar, genişletilmiş kod metni oluşturmak için `ExtCodetextBuilder` ve QR kodu oluşturmak için `BarcodeGenerator`'dır.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Bu içe aktarmalar, builder metodlarına (`add_plain_codetext`, `add_eci_codetext` vb.) ve jeneratörün `set_code_text`, `set_symbology` ve `save` fonksiyonlarına erişim sağlar.

## Adım 2: ExtCodetextBuilder'ı oluşturun ve yapılandırın

Yeni bir builder örneği oluşturmak, **ECI nasıl kullanılır** konusundaki ilk somut örnektir. Daha sonra yeniden kullanmanız gerekirse builder'ı temizleyebilirsiniz.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

`clear()` çağrısı, builder'ın temiz bir durumla başlamasını sağlar; bu, bir döngü içinde birden fazla QR kodu üretirken çok önemlidir.

## Adım 3: Düz (ECI olmayan) kod metni ekleyin

Düz metin bir ECI segmentine ihtiyaç duymaz. ASCII uyumlu dizeler için `add_plain_codetext` kullanın.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Builder şimdi `"HelloWorld"` düz segmentini tutuyor.

## Adım 4: ECI kodlu bir segment ekleyin

İşte **ECI nasıl kullanılır**'ın özü: ECI değerini (UTF‑8 için 26) belirtiyor ve kodlamak istediğiniz Unicode dizesini sağlıyorsunuz. Bu, QR kodunun varsayılan ISO‑8859‑1 seti tarafından kapsanmayan Rusça, Çince veya başka bir dili taşımasını sağlar.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Neden önemli:** ECI göstergesi olmadan bir tarayıcı, baytları varsayılan karakter setiyle yorumlar ve ASCII dışı metin için bozuk karakterler gösterir.

## Adım 5: Birleştirilmiş genişletilmiş kod metni dizesini alın

Tüm gerekli segmentleri ekledikten sonra, QR jeneratörüne verilecek son dizeyi alın.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Yazdırılan değer şu şekilde görünebilir:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Tam format kütüphaneye bağlıdır, ancak önemli kısım ECI işaretleyicisinin (`[ECI26]`) UTF‑8 yükünden önce gelmesidir.

## Adım 6: Birleştirilmiş metni kullanarak QR kodu oluşturun

Şimdi **metinden QR oluştur**arak genişletilmiş kod metnini `BarcodeGenerator`'a geçirebilirsiniz.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

`qr_extended.png` dosyasını açtığınızda, hem düz İngilizce dizesini hem de Rusça selamlamayı kodlayan bir QR kodu görürsünüz. Modern bir QR tarayıcıyla tarandığında “HelloWorld” ve “Привет” doğru şekilde görüntülenir.

### Builder'ı yeniden kullanmadan önce `clear()` çağırmanızın nedeni

Bir döngü içinde birden fazla QR kodu üretirseniz, builder'ı temizlemeyi unutmak eski segmentleri yeniyle birleştirerek geçersiz bir kod üretir. İşte hızlı bir örnek:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Bu snippet **builder'ı nasıl temizleyeceğinizi** ve **metinden QR nasıl oluşturulacağını** tekrar tekrar gösterir.

## Kenar durumları ve yaygın tuzaklar

| Durum | Dikkat edilmesi gereken | Nasıl ele alınır |
|-----------|-------------------|---------------|
| **Desteklenmeyen ECI değeri** | Kütüphane `InvalidArgumentException` hatası verir. | Sadece spesifikasyonda listelenen ECI değerlerini kullanın (ör. UTF‑8 için 26, Shift‑JIS için 20). |
| **Çok uzun birleştirilmiş metin** | QR sürümü maksimum kapasiteyi aşabilir. | QR sürümünü otomatik olarak artırın (`qr_generator.set_qr_version(QRVersion.AUTO)`) veya veriyi birden fazla QR koda bölün. |
| **Dosya sistemi izin hataları** | `save` işlemi `IOError` ile başarısız olur. | Hedef dizinin mevcut olduğundan ve işlemin yazma iznine sahip olduğundan emin olun. |
| **Yanlış karakter seti gösterimi** | Tarayıcı bozuk karakterler gösterir. | Doğru ECI değerinin, dizenin gerçek kodlamasıyla eşleştiğini doğrulayın. |

## Tam çalıştırılabilir örnek

Aşağıda, tüm içe aktarmaları, hata yönetimini ve açıklamaları içeren, kopyalayıp yapıştırıp çalıştırabileceğiniz bağımsız bir betik bulabilirsiniz.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Bu betiği çalıştırdığınızda `output/qr_extended.png` oluşturulur; hem İngilizce hem de Rusça metni doğru şekilde kodlayan bir QR kodudur.

## Sonuç

Artık **ECI nasıl kullanılır** konusunda, **QR builder'ı temizleme**, **metinden QR oluşturma** ve **QR resmi kaydetme** adımlarını Python ile biliyorsunuz. Yukarıdaki deseni izleyerek, builder durumunu öngörülebilir tutarken herhangi bir Unicode dizesini QR koduna gömebilirsiniz.

### Sıradaki adımlar?

- Çince gibi diller için diğer ECI değerlerini keşfedin (ECI 20) veya ISO‑8859‑5.
- Tarama güvenilirliğini artırmak için hata düzeltme seviyelerini (`qr_generator.set_error_correction_level`) ayarlayın.
- Karışık‑dilli mesajlar için tek bir QR içinde birden fazla ECI segmenti birleştirin.

Kodlamaktan keyif alın ve çok dilli QR kodlar oluşturmanın tadını çıkarın!

## Sonra Ne Öğrenmelisiniz?


Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanız ve projelerinizde alternatif uygulama yaklaşımlarını keşfetmeniz için adım adım açıklamalı tam çalışan kod örnekleri içerir.

- [Aspose.Barcode Python ile ECI kullanarak barkod oluşturma](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Aspose.Barcode ile Python'da QR Kod Görüntüsü Oluşturma – Tam Kılavuz](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Python'da barkod oluşturma – tam adım adım rehber](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}