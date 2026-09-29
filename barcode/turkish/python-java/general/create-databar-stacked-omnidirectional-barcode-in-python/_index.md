---
category: general
date: 2026-07-30
description: Python'da Databar Stacked Omnidirectional barkod oluşturun. Aspect ratio
  ve XDimension'ı yapılandırmak ve bir Python barkod üreteci kullanarak PNG dışa aktarmak
  için bu adım adım rehberi izleyin.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: tr
lastmod: 2026-07-30
og_description: Python'da Databar Stacked Omnidirectional barkod oluşturun. Bu öğreticide
  XDimension ayarlama, DataBar en‑boy oranını ince ayar yapma ve BarCodeImageFormat
  ile PNG olarak kaydetme gösterilmektedir.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Databar Yığılmış Çok Yönlü Barkod Oluşturma – Python Öğreticisi
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Python'da Databar Yığılmış Çok Yönlü Barkod Oluştur
url: /tr/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python'da Databar Yığılmış Çok Yönlü Barkod Oluşturma

Python'da **databar stacked omnidirectional** barkod oluşturmanız gerektiğinde nereden başlayacağınızı bilemediniz mi? Yalnız değilsiniz—birçok geliştirici `BarcodeGenerator` sınıfıyla ilk kez çalıştıklarında aynı engelle karşılaşıyor. İyi haber şu ki, temel özellikleri anladığınızda tüm süreç oldukça basit.

Bu rehberde, **python barcode generator** kullanarak XDimension'ı ayarlayan, DataBar en‑boy oranını ince ayar yapan ve sonunda iki PNG dosyası dışa aktaran tam, çalıştırılabilir bir örnek üzerinden adım adım ilerleyeceğiz. Sonuna geldiğinizde, herhangi bir envanter veya lojistik projesi için yüksek kaliteli yığılmış çok yönlü semboller üretmeyi sağlam bir şekilde kavrayacaksınız.

## Öğrenecekleriniz

- GTIN‑14 yüküyle bir **databar stacked omnidirectional** üreticisini nasıl örnekleyebileceğinizi.  
- **XDimension piksel boyutunun** tarama güvenilirliği açısından neden önemli olduğunu.  
- **DataBar en‑boy oranının** satır genişliği ve yüksekliği üzerindeki etkisini.  
- Sonucu **BarCodeImageFormat PNG** dosyası olarak nasıl kaydedeceğinizi.  
- Aynı üretici nesnesini tekrar kullanarak ekstra bellek yükü olmadan birden fazla varyant üretme ipuçları.

### Önkoşullar

- Python 3.8+ (kullandığımız kütüphane saf‑Python, derlenmiş tekerlek (wheel) gerektirmez).  
- `barcode-generator` paketi (`pip install barcode-generator` ile kurulur).  
- Yazma izniniz olan bir klasör – script iki PNG görüntüsünü oraya dökecek.

Temel Python içe aktarmaları ve nesne‑yönelimli kodlamada rahat iseniz, hazırsınız.

## Databar Yığılmış Çok Yönlü Barkod Oluşturma – Adım Özeti

Aşağıda iş akışını altı küçük adıma bölüyoruz. Her adım, bir REPL ya da script dosyasına kopyalayıp yapıştırabileceğiniz bağımsız bir kod bloğu. Denemekten çekinmeyin—en‑boy oranını ya da XDimension'ı değiştirerek anında farklı bir görsel stil elde edersiniz.

---

## Adım 1: Databar Yığılmış Çok Yönlü Üreticiyi Oluşturma

İlk yaptığımız şey, uygun `EncodeTypes` enum'ını ve veri dizesini geçirerek **databar stacked omnidirectional** üretici örneği **oluşturmaktır**.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Neden önemli:** `EncodeTypes.DatabarStackedOmniDirectional` bayrağı, kütüphaneye yığılmış çok yönlü bir sembol üretmesini söyler; bu, 14 haneye kadar kodlayabilen ve her açıdan okunabilir tek DataBar çeşididir.

---

## XDimension Piksel Boyutunu Yapılandırma

**XDimension piksel boyutu**, en küçük modülü (en ince siyah çubuğu) kontrol eder. `2` piksel değeri, çoğu ekran görüntüsü senaryosu için iyi çalışır.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro ipucu:** Barkodu yüksek DPI'da yazdırmayı planlıyorsanız, bulanık kenarlardan kaçınmak için bu değeri 3 veya 4'e yükseltin.

---

## DataBar En‑Boy Oranını (15) Ayarlama

**DataBar en‑boy oranı**, her satırın yüksekliğine göre ne kadar geniş olduğunu belirler. `15` en‑boy oranı, daha geniş satırlar üretir; bu, birçok tarayıcının hızlı hareket yakalamasını tercih eder.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Neden 15?** Resmi GS1 spesifikasyonu, yığılmış çok yönlü semboller için 10 ile 20 arasında bir oran önerir. Biz dengeli bir varsayılan olarak `15` seçtik.

---

## Barkodu BarCodeImageFormat Kullanarak PNG Olarak Dışa Aktarma

Üretici yapılandırıldıktan sonra, görüntüyü kalıcı hâle getiriyoruz. `BarCodeImageFormat.Png` enum'u kayıpsız çıktı sağlar, sonraki işlemler için mükemmeldir.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Ne göreceksiniz:** Oluşan PNG'yi açtığınızda, nispeten geniş satırlara sahip temiz, yüksek kontrastlı bir barkod fark edeceksiniz.

---

## DataBar En‑Boy Oranını 30'a Değiştirme

Bazen daha dar bir etiket için geniş satırlar yerine daha yüksek satırlar gerekir. **DataBar en‑boy oranını** `30`'a ayarlamak her satırı daha yüksek yapar.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Köşe durumu:** Çok yüksek oranlar (ör. >40) barkodun tipik etiket yüksekliğini aşmasına neden olabilir; bu yüzden gerçek bir yazıcıda test edin.

---

## Yeni En‑Boy Oranı ile Barkodu Tekrar Dışa Aktarma

Son olarak, aynı `barcode_generator` nesnesini yeniden kullanarak ikinci bir PNG yazıyoruz. Üreticiyi yeniden oluşturmanıza gerek yok—sadece özelliği değiştirin ve `Save` metodunu tekrar çağırın.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Sonuç:** Artık iki PNG dosyanız var—biri geniş satırlarla (`AR15`), diğeri yüksek satırlarla (`AR30`). Yan yana karşılaştırarak tarayıcınız için hangisinin daha iyi çalıştığını belirleyin.

---

## Tam Çalışan Örnek

Hepsini bir araya getirerek, anında çalıştırabileceğiniz tam script burada. `YOUR_DIRECTORY` kısmını makinenizdeki mutlak bir yol ile değiştirin.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Beklenen çıktı** (konsolunuzda):

```
✅ Two PNG files created – AR15 and AR30
```

Ve iki görüntü dosyası hedef klasörde ortaya çıkar, tarama testlerine hazır.

---

## Sonuç

Python'da **databar stacked omnidirectional** barkodları oluşturduk, **XDimension piksel boyutunu** ayarladık, iki farklı **DataBar en‑boy oranı** ayarıyla deneme yaptık ve sonuçları **BarCodeImageFormat PNG** dosyaları olarak dışa aktardık. Tüm iş akışı birkaç satırda sığar, ancak tarayıcılar için en önemli görsel özellikler üzerinde tam kontrol sağlar.

Sırada ne var? Yükü farklı bir GTIN ile değiştirin, PNG'yi palet‑tabanlı bir görüntüye dönüştürerek renklerle oynayın veya her iki PNG'yi yan yana gömülü bir PDF raporu oluşturun. `BarcodeGenerator` sınıfı bu senaryoların tümünü yönetebilecek kadar esnektir, bu yüzden denemekten çekinmeyin.

Belirli bir kullanım durumu hakkında sorunuz mu var ya da bir hatayla mı karşılaştınız? Aşağıya yorum bırakın, yardımcı olmaktan memnuniyet duyarım. İyi kodlamalar!

## Sonra Ne Öğrenmelisiniz?

Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanarak yakından ilgili konuları kapsar. Her kaynak, ek API özelliklerini ustalaşmanız ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfetmeniz için adım adım açıklamalarla tam çalışan kod örnekleri içerir.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}