---
category: general
date: 2026-10-28
description: ExtCodetextBuilder kullanarak Python’da genişletilmiş kod metni oluşturmayı
  öğrenin. Düz ve ECI‑kodlu verileri, adım adım kod örneklerini ve en iyi uygulama
  ipuçlarını içerir.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: tr
lastmod: 2026-10-28
og_description: ExtCodetextBuilder ile Python’da genişletilmiş kod metni oluşturun.
  Bu öğreticide düz ve ECI‑kodlu veri işleme, tam çalıştırılabilir kod ve yaygın hatalar
  gösterilmektedir.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Python'da Genişletilmiş Kod Metni Oluşturma – Tam Kılavuz
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: ExtCodetextBuilder ile Python’da genişletilmiş kod metni nasıl oluşturulur
url: /tr/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python'da ExtCodetextBuilder ile genişletilmiş kod metni oluşturma

Eğer barkod veya data‑matrix uygulamaları için **genişletilmiş kod metni oluşturmanız** gerekiyorsa, bu rehber Python'da bunu nasıl yapacağınızı tam olarak gösterir. Düz metni nasıl birleştireceğinizi, Unicode karakterler için ECI (Extended Channel Interpretation) bölümleri eklemeyi ve kodlamaya hazır tek, doğru biçimlendirilmiş bir dize almayı göreceksiniz.

Bu öğretici, gerekli kütüphanenin kurulmasından desteklenmeyen ECI değerleri gibi uç durumların ele alınmasına kadar her şeyi kapsar. Sonunda, **genişletilmiş kod metni oluşturmak** isteyen herhangi bir projeye ekleyebileceğiniz yeniden kullanılabilir bir desen elde edeceksiniz.

## Öğrenecekleriniz

* `ExtCodetextBuilder`'ın karışık kodlamalı dizeler oluşturmadaki rolü.  
* Tek bir builder örneğinde **düz kod metni ekleme** ve **ECI kod metni ekleme** nasıl yapılır.  
* Son çıktıyı nasıl doğrular ve yaygın hataları nasıl giderirsiniz.  
* Diğer karakter setleri için varyasyonlar (ör. ISO‑8859‑1, Shift‑JIS).  

### Önkoşullar

* Python 3.8 ve üzeri.  
* `extcodetext` paketi (veya `ExtCodetextBuilder` sağlayan benzer bir kütüphane). Şu komutla kurun:

```bash
pip install extcodetext
```

* Unicode ve ECI değerlerine temel aşinalık – ECI 3 UTF‑8, ECI 4 ISO‑8859‑1 vb. eşleşir.

> **Pro tip:** ECI numaralarının bir referans tablosunu elinizin altında bulundurun. Bu, bildirilen kodlama ile gerçek bayt dizisi arasındaki tesadüfi uyumsuzlukları önler.

## ExtCodetextBuilder'ı Anlamak

`ExtCodetextBuilder`, birden çok metin parçasını otomatik olarak gerekli ECI işaretçilerini ekleyerek birleştiren küçük bir yardımcı programdır. ECI işaretçisi, aşağı akış barkod kodlayıcıya sonraki baytlar için hangi karakter setinin kullanılacağını söyler. İşaretçi olmadan, ASCII dışı karakterler hatalı yorumlanır.

Builder üç basit aşamada çalışır:

1. **Create** (oluştur) builder örneğini.  
2. **Append** (ekle) düz veya ECI‑kodlu parçaları.  
3. **Retrieve** (al) birleştirilmiş genişletilmiş‑kodmetni dizesini.

Aşağıda her aşamayı somut kodlarla gösteriyoruz.

## Adım 1: ExtCodetextBuilder örneği oluşturma

İlk satır, tüm parçaları tutacak nesneyi oluşturur. Bu noktada herhangi bir yapılandırma gerekmez.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Bu neden önemlidir*: Builder'ı örneklemek, dahili bir tampon tahsis eder. Sonraki tüm `add_*` çağrıları bu tampon üzerinde çalışır ve belirttiğiniz sırayı garanti eder.

## Adım 2: Düz (kodlanmamış) veri ekleme

Düz veri, varsayılan karakter setine (genellikle ASCII) ait karakterlerden oluşur. Bu tür parçalar için `add_plain_codetext` kullanın.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Açıklama*: `"ABC123"` dizesi yalnızca ASCII karakterler içerdiği için ECI işaretçisine gerek yoktur. Metot, ham baytları doğrudan dahili tamponun sonuna ekler.

## Adım 3: ECI ile önceden eklenmesi gereken veriyi ekleme

Unicode karakterler—ör. Kiril, Japonca veya emoji—gömmeniz gerektiğinde, kodlayıcıya hangi karakter setinin kullanılacağını söylemeniz gerekir. Bu, `add_eci_codetext(eci, text)` ile yapılır. İlk argüman sayısal ECI değeridir; ikincisi gerçek metindir.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*ECI 3 neden?*: ISO/IEC 18004 spesifikasyonuna göre, ECI 3 UTF‑8'e karşılık gelir. Bu işaretçi eklendiğinde, barkod okuyucu sonraki baytları UTF‑8 olarak çözer ve Kiril karakterlerini korur.

### Diğer kodlamaları işleme

ISO‑8859‑1 (Batı Avrupa) gerekiyorsa `add_eci_codetext(4, "¡Hola!")` kullanırsınız. Shift‑JIS (Japonca) için ECI değeri 20’dir:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Seçilen ECI değerinin hedef barkod kütüphanesi tarafından desteklendiğini her zaman doğrulayın; desteklenmeyen ECIs kodlama hatalarına yol açar.

## Adım 4: Birleştirilmiş genişletilmiş‑kodmetni dizesini al

Tüm parçalar eklendikten sonra, `get_extended_codetext()` çağırarak son dizeyi elde edin. Bu dize, gerekli ECI kaçış dizilerini içerir.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Beklenen çıktı** (açıklık için Python `repr` olarak gösterilmiştir):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Parçalama*:

* `ABC123` – düz ASCII bölümü.  
* `\x1B\x1D\x03` – UTF‑8 için ECI kaçış dizisi (ESC GS 0x03).  
* `Привет` – UTF‑8 kodlu Kiril kelimesi.

Kaçış baytları kütüphane uygulamasına göre değişebilir, ancak mantıksal sıralama her zaman *düz → ECI işaretçisi → Unicode metni* olacaktır.

## Tam çalıştırılabilir örnek

Her şeyi bir araya getirerek, `create_extended_codetext.py` adlı bir dosyaya kopyalayıp hemen çalıştırabileceğiniz bağımsız bir betik aşağıdadır.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Betik çalıştırıldığında, birleşik dizeyi yazdırır; bu dize, genişletilmiş‑kodmetni girişi kabul eden herhangi bir barkod kodlayıcı için hazırdır.

## Yaygın tuzaklar ve nasıl önlenir

| Belirti | Muhtemel neden | Çözüm |
|---|---|---|
| `UnicodeEncodeError` `add_eci_codetext` çağrılırken | Seçilen ECI içinde temsil edilemeyen karakterler içeren bir dize sağlanması | ECI'nin dizeyle gerçek kodlamasını doğrulayın (ör. tüm UTF‑8 metinler için ECI 3 kullanın). |
| Son çıktıda ECI işaretçisi eksik | ASCII dışı veri için yanlışlıkla `add_plain_codetext` kullanılması | ASCII dışı herhangi bir karakter için `add_eci_codetext`'e geçin. |
| Barkod tarayıcı bozuk karakter gösteriyor | Tarayıcının seçilen ECI değerini desteklememesi | Evrensel olarak desteklenen bir ECI seçin (UTF‑8 yaygın olarak desteklenir) veya hedef dil izin veriyorsa ISO‑8859‑1'e geri dönün. |
| `get_extended_codetext` boş dize döndürüyor | Metodu çağırmadan önce hiç parça eklenmemiş olması | En az bir `add_*` çağrısının yürütüldüğünden emin olun. |

### Kenar durumu: Boş dizeler

`add_plain_codetext("")` veya `add_eci_codetext(3, "")` çağrısı zararsızdır; builder boş parçayı görmezden gelir. Ancak, tekrarlanan boş çağrılar gereksiz ECI işaretçilerine yol açabilir. Boş eklemelerden kaçınmak için dize uzunluğunu kontrol edin.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Dinamik veri için deseni genişletme

Gerçek dünyada, genişletilmiş kodmetni genellikle kullanıcı girişi veya bir veritabanı kaydından oluşturursunuz. Aşağıdaki kod, `type` değeri `"plain"` ya da `"eci"` olan `(type, value)` çiftleri listesini işleyen bir döngüyü gösterir.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Bu yaklaşım ölçeklenebilir: Parça tanımlarını JSON, CSV veya bir API'den okuyabilir, temel oluşturma mantığını değiştirmeden kullanabilirsiniz.

## Çıktıyı test etme

Builder'ın beklendiği gibi davrandığını doğrulamak için hızlı bir birim testi ekleyin. `pytest` kullanarak:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

`pytest` çalıştırıldığında geçmelidir; bu, ECI işaretçisinin tam olarak gerektiği yerde göründüğünü onaylar.

## Sonraki keşfedebileceğiniz ilgili kavramlar

* **Barkod kodlama kütüphaneleri** – ör. `python-barcode`, `zxing` bağlayıcıları, genişletilmiş kodmetni dizesini doğrudan kabul eder.  
* **ECI tablo referansı** – sayısal ECI değerlerinin tam listesi ISO/IEC 18004 tarafından yayınlanır ve Python sözlüğü olarak saklanabilir.  
* **Hata düzeltme seviyeleri** – QR kod üretirken, genişletilmiş kodmetni uygun hata düzeltme seviyesi (L, M, Q, H) ile birleştirerek taramayı güçlendirebilirsiniz.  

## Sonuç

Artık Python'da `ExtCodetextBuilder` kullanarak **genişletilmiş kod metni oluşturmayı** biliyorsunuz. Süreç basittir:

1. Builder'ı örnekleyin.  
2. Gerekli olduğunda düz ve ECI‑kodlu parçaları ekleyin.  
3. Son dizeyi alın ve barkod üreticinizle besleyin.

Yukarıdaki deseni izleyerek ASCII ve Unicode verisinin herhangi bir karışımını yönetebilir, yaygın kodlama hatalarından kaçınabilir ve çeşitli tarayıcılarda çalışan barkod‑hazır dizeler üretebilirsiniz. Farklı ECIs ile deney yapın, builder'ı veri akışınıza entegre edin ve genişletilmiş‑kodmetni ihtiyaçlarınız için sağlam bir temel oluşturun.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}