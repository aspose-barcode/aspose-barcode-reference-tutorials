---
category: general
date: 2026-09-29
description: Python'da ürün adını gösterirken, yayın tarihini yazdırın ve barkod kütüphanesinden
  sürüm detaylarını alın.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: tr
lastmod: 2026-09-29
og_description: Python'da ürün adını görüntüleyin ve birkaç satır kodla yayın tarihini
  yazdırmayı, sürümü almayı ve küçük sürümü göstermeyi öğrenin.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Python'da ürün adını ve sürüm bilgilerini göster
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Python'da ürün adını ve sürüm bilgisini göster
url: /tr/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python'da ürün adını ve sürüm bilgilerini gösterme

Bir kütüphaneden **ürün adını** görüntülemeniz gerekiyorsa, bu kılavuz tam olarak nasıl yapılacağını gösterir. Ayrıca **sürüm tarihini** **yazdırmayı**, **sürümü nasıl alacağınızı** ve **küçük sürümü** kısa Python kodu kullanarak öğrenebileceksiniz.

Birçok geliştirici barkod tarama veya oluşturma özelliklerini entegre eder ve kütüphanenin meta verilerini kullanıcılar veya günlükler aracılığıyla göstermek zorundadır. Bu öğretici, bu bilgileri güvenilir bir şekilde alıp sunmak için gereken her şeyi kapsar.

## Öğrenecekleriniz

* `barcode` kütüphanesinden sürüm bilgilerini alın.  
* **Ürün adını** büyük ve küçük sürüm numaralarıyla birlikte gösterin.  
* **Sürüm tarihini** insan tarafından okunabilir bir formatta yazdırın.  
* Eksik öznitelikleri nazikçe ele alın.  

**Önkoşullar**  
* Python 3.8 veya daha yeni bir sürüm.  
* `barcode` paketine erişim (`pip install python-barcode` komutuyla veya `BuildVersionInfo` sağlayan kütüphane ile kurabilirsiniz).  

---

## Python'da ürün adını ve sürüm bilgilerini nasıl gösterilir

İlk adım, kütüphaneyi içe aktarmak ve bir sürüm‑bilgi nesnesi döndüren yöntemi çağırmaktır. Nesne, `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` ve `RELEASE_DATE` gibi öznitelikler içerir.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Neden bu çalışır**  
`BuildVersionInfo()` hafif bir nesne döndürür ve öznitelikleri içe aktarım sırasında doldurulur. Özniteliklere doğrudan erişmek ekstra G/Ç'yi önler ve gösterilen verilerin kodunuzun gerçekten kullandığı kütüphane sürümüyle eşleşmesini garanti eder.

### Beklenen çıktı

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Tam değerler, yüklü barcode kütüphanesinin sürümüne bağlıdır.

---

## Barcode kütüphanesinden sürümü nasıl alırsınız

Sadece sürüm numaralarına ihtiyacınız varsa, ürün adını yazdırmayı atlayabilir ve sayısal alanlara odaklanabilirsiniz.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*`PRODUCT_MAJOR` ve `PRODUCT_MINOR` öznitelikleri anlamsal sürümlemeyi izler, bu da sürümleri programatik olarak karşılaştırmanıza olanak tanır.*

---

## Sürüm tarihini nasıl yazdırırsınız

Sürüm tarihi, `YYYY‑MM‑DD` formatında bir dize olarak saklanır. Farklı bir yerel ayarda sunmak için önce bir `datetime` nesnesine dönüştürün.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**İpucu:** Kütüphane formatını değiştirdiğinde `ValueError` almamak için ayrıştırmadan önce tarih dizesini her zaman doğrulayın.

---

## Küçük sürümü büyük sürümle birlikte gösterme

Bazen uyumluluk uyarılarını kaydederken gibi, küçük sürümü ayrı olarak göstermeniz gerekebilir.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro ipucu:** Özellik bayraklarını tetiklemek için küçük sürümü kullanın:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Eksik özniteliklerin ele alınması (kenar durumlar)

Barcode kütüphanesinin eski sürümleri tüm öznitelikleri ortaya koymayabilir. Öznitelik erişimini mantıklı varsayılanlarla `getattr` içinde sarın.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Bu desen, eksik bir alan nedeniyle betiğinizin hiç çökmemesini sağlar ve birden fazla kütüphane sürümüyle çalışabilecek CI boru hatları için dayanıklı olmasını sağlar.

---

## Tam, çalıştırılabilir örnek

Aşağıda, tüm en iyi uygulamaları birleştiren tam betik yer almaktadır: öznitelik doğrulama, tarih biçimlendirme ve net çıktı.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Bu betiği, barcode kütüphanesi yüklü bir sistemde çalıştırmak, önceki örneğe benzer bir çıktı verir, ancak artık eksik alanlara karşı koruma sağlar ve tarihi güzel bir şekilde biçimler.

---

## Sonuç

Artık **ürün adını** **görüntüleme**, **sürüm tarihini** **yazdırma**, **sürümü nasıl alacağınızı**, **ürünü nasıl yazdıracağınızı** ve **küçük sürümü** basit bir Python iş akışıyla nasıl yapacağınızı biliyorsunuz. Tam örnek, güvenilir öznitelik erişimi, tarih işleme ve sürüm karşılaştırmasını gösterir—bu becerileri meta veri nesneleri sunan herhangi bir üçüncü‑taraf kütüphanede yeniden kullanabilirsiniz.

**Sonraki adımlar**

* Barcode kütüphanesinin `BuildCommitInfo()` gibi diğer meta veri yöntemlerini keşfedin.  
* Çıktıyı bir günlükleme çerçevesine entegre edin (ör. `logging.info`).  
* Sürümleri programatik olarak karşılaştırarak uygulamanızda gereken minimum sürümleri zorlayın.

Farklı çıktı formatlarıyla denemeler yapmaktan veya betiği bilgileri denetim amaçlı bir dosyaya yazacak şekilde genişletmekten çekinmeyin. İyi kodlamalar!  

![Ürün adı ve sürüm detaylarını gösteren terminal çıktısı](image.png "Terminal çıktısı")


## Sonraki Öğrenmeniz Gerekenler


Aşağıdaki öğreticiler, bu rehberde gösterilen tekniklere dayanan ve yakından ilgili konuları kapsar. Her kaynak, adım adım açıklamalarla birlikte tam çalışan kod örnekleri içerir; böylece ek API özelliklerinde uzmanlaşabilir ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [Python barcode kütüphanesini kullanarak ürün adını göster – adım adım rehber](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Aspose.Barcode (Python) Sürümünü Yazdırma](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Aspose.BarCode ile Python'da barkod oluşturma](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}