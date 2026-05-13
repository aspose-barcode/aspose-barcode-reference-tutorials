---
date: 2026-01-12
description: Aspose.BarCode for .NET kullanarak özel bir DataMatrix en‑boy oranı ile
  barkod PNG'si oluşturmayı öğrenin. Barkod oluşturma ve boyut özelleştirme için adım
  adım rehber.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Barkod PNG Oluştur – DataMatrix En‑Boy Oranı – Aspose.BarCode
url: /tr/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG Oluşturma – DataMatrix En‑Boy Oranı – Aspose.BarCode

Özel bir DataMatrix en‑boy oranı ile **barcode PNG** oluşturmak, barkodun belirli düzen kısıtlamalarına uyması gerektiğinde yaygın bir gereksinimdir. Bu öğreticide, Aspose.BarCode for .NET kullanarak **barcode PNG** dosyalarını nasıl **oluşturacağınızı** adım adım gösterecek, en‑boy oranını neden ayarlamanız gerektiğini açıklayacak ve çıktıyı uygulamanıza göre nasıl ince ayar yapacağınızı anlatacağız.

## Hızlı Yanıtlar
- **“En‑boy oranı” neyi kontrol eder?** DataMatrix modüllerinin genişlik‑yükseklik oranını tanımlar.  
- **PNG, JPEG veya SVG olarak çıktı alabilir miyim?** Evet – `Save` yöntemi PNG, JPEG, BMP, GIF ve daha fazlasını destekler.  
- **Bu özellik için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Kaç en‑boy oranı değeri geçerlidir?** Pozitif bir float; tipik değerler 0.5 – 2.0 arasındadır.

## DataMatrix barkodu nedir ve neden en‑boy oranını ayarlamalıyız?
DataMatrix, büyük miktarda veriyi küçük bir alanda saklayan iki‑boyutlu bir matris barkodudur. **En‑boy oranını** ayarlamak, modülleri yatay olarak gerip sıkıştırmanıza olanak tanır; bu da barkodu dar sütunlara ya da geniş etiketlere, okunabilirliği kaybetmeden sığdırmak için faydalıdır.

## Ön Koşullar

DataMatrix en‑boy oranlarını özelleştirmeye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:

1. **Visual Studio** – herhangi bir yeni sürüm yeterlidir.  
2. **Aspose.BarCode for .NET** – indirmek için [burada](https://releases.aspose.com/barcode/net/) tıklayın.  
3. **.NET Framework / .NET Core** – projeniz desteklenen bir sürümü hedeflemelidir.

## Ad Alanlarını İçe Aktarma

C# projenizde gerekli ad alanını içe aktarmanız gerekir:

```csharp
using Aspose.BarCode.Generation;
```

> **İpucu:** Bu `using` ifadesini dosyanızın en üstünde tutun; böylece `BarcodeGenerator` sınıfı her zaman kullanılabilir olur.

## Adım‑Adım Kılavuz

### Adım 1: Projenizi Kurun
Visual Studio’da yeni bir console ya da Windows Forms projesi oluşturun ve Aspose.BarCode DLL’ine referans ekleyin.

### Adım 2: Barcode Generator’ı Başlatın
DataMatrix türü ve kodlamak istediğiniz veriyi kullanarak bir `BarcodeGenerator` örneği oluşturun:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Bu satır, örnek metni içeren bir DataMatrix barkodu üretmeye hazır bir jeneratör oluşturur.

### Adım 3: En‑boy Oranını Özelleştirip PNG Dosyalarını Kaydedin
Şimdi **en‑boy oranını** değiştirebilir ve her bir versiyonu PNG olarak kaydedebilirsiniz:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- İlk çağrı kare‑orantılı bir barkod oluşturur (`AspectRatio = 1`).  
- İkinci çağrı barkodu yatay olarak sıkıştırır (`AspectRatio = 0.5`), daha geniş bir görünüm elde edilir.

Artık raporlar, etiketler veya UI öğeleri için farklı en‑boy oranlarına sahip iki **barcode PNG** dosyanız hazır.

## Yaygın Sorunlar & Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Oluşturulan görüntü bulanık** | Kaydetmeden önce `Resolution` parametresini artırın (`gen.Parameters.ImageResolution = 300`). |
| **Barkod taranmıyor** | En‑boy oranının 0.5 – 2.0 arasında kalmasını ve yeterli sessiz bölge (`gen.Parameters.Barcode.CodeTextParameters.Margin`) bırakılmasını sağlayın. |
| **Dosya yolu hataları** | Çıktı yolunu oluşturmak için `Path.Combine` kullanın ve klasörün var olduğunu doğrulayın. |

## Sık Sorulan Sorular

**S: Aspose.BarCode for .NET kullanarak diğer barkod türlerinin en‑boy oranını da özelleştirebilir miyim?**  
C: Evet, birçok 2‑D barkod (ör. QR, PDF417) kendi parametre nesneleri aracılığıyla en‑boy oranı ayarlarını destekler.

**S: Aspose.BarCode for .NET için ücretsiz bir deneme mevcut mu?**  
C: Evet, Aspose.BarCode for .NET için ücretsiz deneme sürümüne [burada](https://releases.aspose.com/) ulaşabilirsiniz.

**S: Aspose.BarCode for .NET lisansını nereden satın alabilirim?**  
C: Lisansı Aspose web sitesinden [burada](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Aspose.BarCode for .NET farklı .NET Framework sürümleriyle uyumlu mu?**  
C: Evet, .NET Framework 4.x, .NET Core 3.1+ ve en yeni .NET sürümleriyle çalışır.

**S: Aspose.BarCode for .NET ile barkodları farklı formatlarda üretebilir miyim?**  
C: Kesinlikle – PNG, JPEG, BMP, GIF, TIFF, SVG ve PDF doğrudan desteklenir.

## Sonuç

DataMatrix barkodunun **en‑boy oranını** özelleştirmek ve **barcode PNG** dosyaları oluşturmak, Aspose.BarCode for .NET ile oldukça basittir. Yukarıdaki adımları izleyerek projenizin tam düzen gereksinimlerini karşılayan mükemmel boyutta barkodlar üretebilirsiniz. Çıktıyı daha da özelleştirmek için `Resolution`, `Margin` ve `Color` gibi diğer parametrelere de göz atın.

Daha derin bir keşif için resmi [belgeler](https://reference.aspose.com/barcode/net/) sayfasına bakabilir veya [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) topluluğuna katılabilirsiniz.

---

**Son Güncelleme:** 2026-01-12  
**Test Edilen Versiyon:** Aspose.BarCode 24.12 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}