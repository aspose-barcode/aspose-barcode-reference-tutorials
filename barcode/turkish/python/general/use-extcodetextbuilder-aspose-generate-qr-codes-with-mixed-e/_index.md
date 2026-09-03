---
category: general
date: 2026-07-18
description: extcodetextbuilder aspose'i kullanarak düz ASCII ve UTF‑8 Rusça metni
  birleştiren QR kodları oluşturun. Python'da Aspose.Barcode QR kod üretimini öğrenin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: tr
lastmod: 2026-07-18
og_description: extcodetextbuilder aspose kullanarak bir QR Kodda düz ve UTF‑8 kodlu
  parçaları birleştirebilirsiniz. Python’da Aspose.Barcode için bu adım adım kılavuzu
  izleyin.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: extcodetextbuilder aspose'i kullan – Karışık ECI Metinli QR Kodları Oluştur
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'extcodetextbuilder aspose kullanın: Karışık ECI Metinli QR Kodları Oluşturun'
url: /tr/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# extcodetextbuilder aspose kullan – Karışık ECI Metinli QR Kodları Oluştur

Hiç **extcodetextbuilder aspose**'ı kullanarak hem düz İngilizce hem de Kiril karakterlerini tek bir QR Kodu'na gömmeyi düşündünüz mü? Yalnız değilsiniz. Birçok geliştirici, ASCII ve non‑ASCII verileri karıştırmaları gerektiğinde, özellikle hedef tarayıcının doğru ECI (Extended Channel Interpretation) işaretçilerini beklediğinde bir duvara çarpar.  

Bu öğreticide, “HELLO123” **ve** Rusça kelime “Привет” içeren bir QR Kodu oluşturmak için tam adımları göstereceğiz, hepsi Aspose.Barcode’ın Python API'si ile. Sonunda çalıştırmaya hazır bir betiğiniz olacak, her çağrının neden önemli olduğunu anlayacaksınız ve süreci diğer diller veya veri formatları için nasıl ayarlayacağınızı bileceksiniz.

## Öğrenecekleriniz

- **ExtCodetextBuilder**'ı **initialize** etmeyi ve düz ile ECI‑kodlu parçaları eklemeyi.  
- **ECI encoding** değerinin `3`'ün UTF‑8 ile eşleşmesinin nedeni ve bunun taramayı nasıl etkilediği.  
- Aspose.Barcode ile bir **QR Code generator**'ı kurmak için tam sıralama.  
- Oluşan görüntüyü kaydetme ve karışık içeriği doğrulama.  

**Prerequisites** – Python 3.8+ gerekir, `aspose-barcode` paketi kurulu olmalı (`pip install aspose-barcode`), ve görüntüleri yazabileceğiniz bir klasör. Başka bir şey gerekmez.

---

## extcodetextbuilder aspose kullanarak karışık kod metni oluşturma

İlk ihtiyacımız bir `ExtCodetextBuilder` örneği. Bunu, farklı metin parçalarını birleştiren ve sahne arkasında doğru ECI işaretçilerini otomatik olarak ekleyen bir builder deseni olarak düşünün.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Neden Önemli:**  
- `add_plain_codetext` veriyi olduğu gibi tutar, bu sayılar veya İngiliz harfleri için mükemmeldir.  
- `add_eci_codetext` sağlanan dizgenin önüne bir ECI segmenti (`[ECI:3]`) ekler, uyumlu bir okuyucuya sonraki baytların UTF‑8 olduğunu söyler. Bu olmadan, tarayıcı Kiril baytlarını çöp olarak yorumlar.

> **Pro tip:** Farklı bir karakter setine ihtiyacınız varsa, `eci_encoding` değerini ECI tablosuna göre değiştirin (örneğin, ISO‑8859‑1 için `26`).

---

## Aspose.Barcode ile QR Kodu oluşturmayı Başlatma

Artık düzgün biçimlendirilmiş bir `extended_codetext`'imiz olduğuna göre, bunu QR Kodu oluşturucuya verebiliriz. Aspose.Barcode, düşük seviyeli QR matris oluşturmayı soyutlayarak veriye odaklanmanızı sağlar.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Burada Ne Oluyor?**  
- `BarcodeGenerator()` varsayılan ayarlarla (boyut, çözünürlük vb.) yeni bir oluşturucu nesnesi yaratır.  
- `set_symbology` motoruna, örneğin Code128 yerine bir QR Kodu istediğimizi söyler.  

Daha yüksek bir hata düzeltme seviyesi gerekiyorsa, kod metnini atamadan önce `qr_generator.parameters.barcode.qr_error_level = ...` çağırabilirsiniz.

---

## Genişletilmiş kod metnini QR oluşturucuya atama

Oluşturucu hazır olduğunda, sonraki adım sadece daha önce oluşturduğumuz karışık dizeyi beslemek.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Neden `set_codetext` kullanılmıyor?**  
`set_codetext` girdiyi düz metin olarak ele alır ve tüm ECI işaretçilerini kaldırır. `set_extended_codetext` ham baytları, ECI segmenti dahil, korur ve tarayıcının doğru dil geçişini görmesini sağlar.

---

## QR Kodu görüntüsünü kaydetme ve sonucu doğrulama

Son olarak, QR Kodunu diske yazıyoruz. Aspose.Barcode PNG, JPEG, BMP ve daha fazlasını destekler; PNG kayıpsız veri koruduğu için güvenli bir varsayılandır.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Şimdi belirtilen konumda bir PNG dosyanız olmalı. ECI destekleyen herhangi bir QR tarayıcı uygulamasıyla (çoğu modern akıllı telefon bunu destekler) açın. Bir kez tarayın – “HELLO123” göreceksiniz. Tekrar tarayın (veya ham veriyi gösteren bir tarayıcı kullanın) – “Привет” de alacaksınız. İki parça tek bir yük olarak görünür, tam da oluşturduğumuz gibi.

![extcodetextbuilder aspose QR kod örneği karışık ECI metni gösteriyor](YOUR_DIRECTORY/qr_extended.png)

*Görsel alt metni: extcodetextbuilder aspose QR kod örneği karışık ECI metni gösteriyor*

---

## Tam, Çalıştırmaya Hazır Betik

Her şeyi bir araya getirerek, `qr_mixed_eci.py` adlı bir dosyaya kopyalayıp yapıştırabileceğiniz tam programı aşağıda bulabilirsiniz:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Şu şekilde çalıştırın:

```bash
python qr_mixed_eci.py
```

Kaydetme konumunu onaylayan bir konsol mesajı göreceksiniz ve PNG, belirttiğiniz yere görünecek.

---

## Yaygın Sorular ve Kenar Durumları

### Tarayıcım Kiril kısmını tanımazsa ne olur?

Tarama uygulamasının ECI desteği sunduğundan emin olun. Daha eski donanımlar ECI segmentini görmezden gelebilir ve baytları ISO‑8859‑1 olarak yorumlayarak bozuk karakterler oluşturabilir.

### İki’den fazla parça ekleyebilir miyim?

Kesinlikle. `add_plain_codetext` veya `add_eci_codetext` metodunu ihtiyacınız kadar çağırın. Builder, metodları çağırma sırasına göre parçaları birleştirir.

### QR Kodu boyutunu veya ön plan rengini nasıl değiştiririm?

`qr_generator.parameters` nesnesini kullanın:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Metnin yanına ikili veri (ör. küçük bir dosya) gömmenin bir yolu var mı?

Evet. Bir bayt dizisiyle `add_binary_codetext` kullanın ve ikili veri belirli bir karakter setini temsil ediyorsa uygun bir ECI ile eşleştirin. Builder gerekli mod geçişlerini halleder.

---

## Sonuç

Artık **extcodetextbuilder aspose**'ı kullanarak düz ASCII ve UTF‑8 kodlu Rusça metni sorunsuz bir şekilde birleştiren QR Kodları oluşturmayı biliyorsunuz. `ExtCodetextBuilder`'ı kullanarak, doğru **ECI encoding**'i ayarlayarak ve sonucu bir **Aspose.Barcode QR Code generator**'a vererek, modern tarayıcılarda çalışan tek bir standart‑uyumlu görüntü elde edersiniz.  

Buradan, `eci_encoding=3` değerini diğer dil tanımlayıcılarıyla değiştirerek veya ek düz parçalar ekleyerek çok dilli yükler oluşturmayı deneyin. Vektörel grafiklere ihtiyacınız varsa `BarCodeImageFormat` seçeneklerini inceleyerek SVG veya PDF çıktısı alabilirsiniz.  

Kodlamaktan keyif alın ve herhangi bir sorunla karşılaşırsanız yorum bırakmaktan çekinmeyin—geribildiriminiz bu rehberleri daha da iyileştirmeye yardımcı olur!

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini öğrenmenize ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olmak için adım adım açıklamalar içeren tam çalışan kod örnekleri sunar.

- [Java ile Barkod Oluşturma - Aspose.BarCode kullanarak Kod Metnini Ayarlama](/barcode/english/java/text-and-styling/setting-code-text/)
- [aspose .net ile barkod oluşturma - DataMatrix Kod Metnini yapılandırma](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [.NET için Aspose.BarCode ile Aztec Kod Metni Kodlaması](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}