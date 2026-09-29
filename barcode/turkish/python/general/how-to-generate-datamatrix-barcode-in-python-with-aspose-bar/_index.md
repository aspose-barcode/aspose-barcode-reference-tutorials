---
category: general
date: 2026-08-22
description: Python'da DataMatrix barkod oluşturmayı ve Aspose.BarCode kullanarak
  Rusça metni kodlamayı öğrenin – adım adım rehber.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: tr
lastmod: 2026-08-22
og_description: Python'da DataMatrix barkod oluşturun ve Aspose.BarCode ile Rusça
  metni kodlayın. Tam örneği izleyin ve hemen çalıştırın.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Python'da DataMatrix barkod oluşturma – eksiksiz Aspose.BarCode öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Python'da Aspose.BarCode ile DataMatrix barkodu nasıl oluşturulur
url: /tr/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python ile Aspose.BarCode kullanarak DataMatrix barkodu nasıl oluşturulur

Python'da **DataMatrix barkodu oluşturmak** ve **Rusça metin kodlamak** istiyorsanız, bu kılavuz size tam adımları gösterir. Tek bir betikte genişletilmiş kod metni oluşturduğunuz, barkodu yapılandırdığınız ve görüntüyü kaydettiğiniz eksiksiz, çalıştırılabilir bir örnek göreceksiniz.

ASCII olmayan karakterler içeren barkodlar oluşturmak genellikle karakter setleri ve veri kodlamasıyla ilgili sorular ortaya çıkarır. Aspose.BarCode’un `ExtCodetextBuilder` sınıfını kullanarak, Cyrillic karakterler gibi UTF‑8 metinleri bir DataMatrix sembolünün içine güvenle gömebilirsiniz. Sonuç, DataMatrix standardını destekleyen herhangi bir tarayıcıyla çalışır.

Bu öğreticide şunları yapacaksınız:

* Gerekli Aspose.BarCode paketini kurun.
* Düz veri ve Rusça metni karıştıran genişletilmiş bir kod metni oluşturun.
* **DataMatrix barkodu** oluşturun ve genişletilmiş dizeyi kullanın.
* Modül boyutu gibi barkod parametrelerini ayarlayın.
* Barkodu PNG dosyası olarak kaydedin.

Harici hizmetlere ihtiyaç yoktur; her şey makinenizde yerel olarak çalışır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

* Python 3.8 veya daha yeni bir sürüm yüklü.
* Aktif bir Aspose.BarCode for Python lisansı (geliştirme için ücretsiz deneme sürümü yeterli).
* Python betikleme konusunda temel bilgi.

Aspose.BarCode kütüphanesini pip aracılığıyla kurabilirsiniz:

```bash
pip install aspose-barcode
```

## Adım 1: Genişletilmiş bir kod metni dizesi oluşturun

İlk görev, hem düz ürün tanımlayıcısını hem de Rusça ifadeyi içeren tek bir dize oluşturmaktır. `ExtCodetextBuilder`, farklı kod metni bölümlerini birleştirmenize ve kodlama bilgilerini korumanıza olanak tanır.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Bu adımın önemi** – DataMatrix sembolleri ham baytları depolar. Alfabeleri karıştırmanız gerektiğinde, kodlayıcıya her segment için hangi karakter setinin geçerli olduğunu söylemeniz gerekir. `add_eci_codetext` yöntemi, Rusça metinden önce bir ECI göstergesi ekleyerek tarayıcıların baytları UTF‑8 olarak yorumlamasını sağlar. ECI olmadan, Cyrillic karakterler bozuk veri olarak görünür.

## Adım 2: Bir DataMatrix barkod üreticisi oluşturun

Genişletilmiş kod metni hazır olduğunda, `EncodeTypes.DATA_MATRIX` tipini belirterek bir `BarcodeGenerator` örneği oluşturun.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Neden DataMatrix?** – DataMatrix, 2.335 alfanümerik karaktere veya 1.556 bayta kadar veri depolayabilen iki boyutlu bir barkoddur. Küçük öğeler, endüstriyel parçalar ve çok dilli metin gömmeniz gereken durumlar için idealdir.

## Adım 3: (İsteğe Bağlı) Barkod parametrelerini yapılandırın

Aspose.BarCode birçok parametre sunar. Çoğu kullanım senaryosu için varsayılan ayarlar okunabilir bir sembol üretir. Ancak, baskı gereksinimlerinize uyacak şekilde her modülün (matristeki en küçük kare) boyutunu kontrol etmek isteyebilirsiniz.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Diğer faydalı parametreler arasında hata düzeltme seviyesi, kenar boşluğu ve arka plan rengi bulunur. Bunları yalnızca hedef tarama ortamınız belirli toleranslar talep ediyorsa ayarlayın.

## Adım 4: Barkod görüntüsünü kaydedin

Son olarak barkodu bir dosyaya yazın. `save` yöntemi PNG, JPEG, BMP ve birkaç vektör formatını destekler.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

`extended_codetext.png` dosyasını açtığınızda net bir DataMatrix sembolü göreceksiniz. Standart bir DataMatrix okuyucu ile taradığınızda iki bölüm geri döner:

1. **ABC123** – düz tanımlayıcı.
2. **Привет** – Rusça selam, UTF‑8 olarak doğru şekilde çözümlenmiş.

## Tam, çalıştırılabilir örnek

Aşağıda `generate_datamatrix.py` adlı bir dosyaya kopyalayıp yapıştırabileceğiniz tam betik yer alıyor. `YOUR_DIRECTORY` ifadesini sisteminizde mevcut bir klasörle değiştirin.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Betik dosyasını komut satırından çalıştırın:

```bash
python generate_datamatrix.py
```

Aşağıdaki gibi bir konsol çıktısı görmelisiniz:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Sonucu doğrulama

Barkodun Rusça ifadeyi doğru kodladığını onaylamak için:

1. PNG dosyasını bir görüntü görüntüleyicide açın.
2. Herhangi bir DataMatrix tarama uygulaması (birçok mobil uygulama destekler) veya bir donanım tarayıcı kullanın.
3. Çözümlenen dize `ABC123Привет` (veya tarayıcı arayüzüne bağlı olarak iki bölüm ayrı ayrı) şeklinde gösterilmelidir.

Rusça karakterler bozuk görünüyorsa, tarayıcının ECI UTF‑8'i desteklediğini tekrar kontrol edin. Çoğu modern okuyucu bunu yapar, ancak eski cihazlar açık bir yapılandırma gerektirebilir.

## Yaygın hatalar ve nasıl önlenir

| Sorun | Neden | Çözüm |
|-------|-------|------|
| Bozuk Cyrillic çıktısı | ECI göstergesi eksik | `add_eci_codetext` ile `eci_encoding=3` kullanın. |
| Barkod yazıcı için çok küçük | Varsayılan modül boyutu düşük DPI için çok ince | `x_dimension` değerini artırın (ör. `3.0` veya `4.0`). |
| Dosya kaydedilmedi | Geçersiz klasör yolu | `YOUR_DIRECTORY` var ve yazılabilir olduğundan emin olun. |
| Tarayıcı okuyamıyor | Aşırı veri yoğunluğu | Kodlanan veri miktarını azaltın veya hata düzeltme seviyesini artırın (`generator.parameters.barcode.error_correction_level`). |

## Örneği genişletme

Bu deseni diğer diller veya veri türleri için uyarlayabilirsiniz:

* **Japonca veya Arapça metin kodlayın** – `eci_encoding` değerini uygun değere değiştirin (ör. ISO‑8859‑5 için 5, ISO‑8859‑7 için 6).  
* **Birden fazla ECI segmenti ekleyin** – `add_eci_codetext` metodunu birden çok kez, her seferinde farklı bir kodlama ile çağırın.  
* **Bunun yerine bir QR kod oluşturun** – `EncodeTypes.DATA_MATRIX` yerine `EncodeTypes.QR` kullanın.  

Diğer tüm adımlar aynı kalır çünkü `ExtCodetextBuilder` düşük seviyeli bayt işleme detaylarını soyutlar.

## Sonuç

Artık Python’da **DataMatrix barkodu oluşturmayı** ve Aspose.BarCode’un genişletilmiş kod metni özelliğiyle **Rusça metin kodlamayı** biliyorsunuz. Tam betik, karakter seti anlaşmasını, barkod oluşturmayı ve görüntü çıktısını sadece birkaç satır kodla halleder.

Sonraki adımda diğer barkod simgelerini (PDF417, Aztec) keşfedebilir veya jeneratörü, talep üzerine PNG görüntüleri dönen bir web hizmetine entegre edebilirsiniz. Aynı prensipler—genişletilmiş bir kod metni oluşturmak ve uygun `EncodeTypes` seçmek—tüm Aspose.BarCode paketinde geçerlidir.

İyi kodlamalar ve çok dilli barkod oluşturmanın gücünün tadını çıkarın!

## Sonraki Öğrenmeniz Gerekenler

Aşağıdaki öğreticiler, bu kılavuzda gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanıza ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmenize yardımcı olacak tam çalışan kod örnekleri ve adım adım açıklamalar içerir.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}