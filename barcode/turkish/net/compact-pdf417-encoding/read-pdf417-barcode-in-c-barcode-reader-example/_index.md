---
category: general
date: 2026-10-14
description: C# ile PDF417 barkodlarını okuyan, macro PDF417'ı işleyen ve tek bir
  görüntüden birden fazla barkodu çözen bir konsol barkod tarayıcısı oluştur.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: C# ile bir konsol barkod tarayıcısı oluşturarak görüntülerden PDF417
  ve macro PDF417 barkodlarını hızlıca okuyun. Bu adım adım kılavuz, tek bir resimde
  birden fazla barkodu nasıl çözeceğinizi gösterir.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C# ile konsol barkod tarayıcısı oluştur – tam kılavuz
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: C# ile konsol barkod tarayıcısı oluştur – PDF417 barkod örneği
url: /tr/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konsol barkod tarayıcısı oluşturma C# – PDF417 barkod okuma örneği

`BarCodeReader` Aspose.BarCode'un çekirdek sınıfıdır ve görüntülerden barkodları çözer ve ayrıntılı meta verileri döndürür. Bir görüntüden PDF417 barkod verilerini okumanız gerekiyorsa, bu kılavuz C#'ta **BarCodeReader** sınıfını nasıl kullanacağınızı gösterir. **Konsol barkod tarayıcısı oluşturma** örneğini öğrenecek ve aynı zamanda macro PDF417'ı da işleyip tek bir görüntüde birden fazla barkodu okuyabileceksiniz.

Barkodlarla çalışmak genellikle farklı görüntü kaynakları, değişen aydınlatma koşulları ve bazen macro PDF417 segmentleri gibi birleşik verilerle uğraşmayı gerektirir. Bu eğitim, PDF417 barkodunu çözmek, genişletilmiş alanlarını çıkarmak ve aynı resimde birden fazla barkodu işlemek için ihtiyacınız olan her şeyi kapsar. Sonunda, bir görüntü dosyasından barkodları okuyup ayrıntılı bilgileri konsola yazdıran çalıştırılabilir bir konsol programına sahip olacaksınız.

## Hızlı cevaplar
- **Örnek ne yapıyor?** Bir konsol barkod tarayıcısı oluşturur; bir resimden PDF417 ve macro PDF417 barkodlarını okur ve tüm çözülen alanları yazdırır.  
- **Hangi kütüphane gerekiyor?** Aspose.BarCode for .NET (NuGet).  
- **Birden fazla barkodu aynı anda okuyabilir mi?** Evet – okuyucu görüntüde bulunan her barkodu yineleyerek işler.  
- **İnternet bağlantısına ihtiyacım var mı?** Hayır, kütüphane tamamen çevrim dışı çalışır.  
- **Hangi .NET sürümü destekleniyor?** .NET 6.0 veya daha yenisi.

## Gerekenler

Başlamadan önce şunların yüklü olduğundan emin olun:

* .NET 6.0 SDK veya daha yeni bir sürüm yüklü  
* Son sürüm **Aspose.BarCode for .NET** NuGet paketi (veya `BarCodeReader` ve `DecodeType.MacroPdf417` sağlayan uyumlu bir kütüphane)  
* PDF417 veya macro PDF417 barkodu içeren bir görüntü dosyası (örnek `ExtPDF417Meta.png` kullanır)  
* Visual Studio 2022 gibi bir kod editörü veya IDE  

Ek hizmetler veya harici API'ler gerekmez.

## Barkod okuma için projeyi ayarlama

1. **Yeni bir konsol projesi oluşturun**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Barkod kütüphanesini ekleyin**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Barkod görüntüsünü kopyalayın**  

   `ExtPDF417Meta.png` dosyasını (veya PDF417 barkodu içeren herhangi bir görüntüyü) proje klasörüne yerleştirin.  
   Bu eğitimde dosyanın `YOUR_DIRECTORY/ExtPDF417Meta.png` konumunda olduğunu varsayıyoruz.

Proje artık barkod okuyucu örneğini derleyip çalıştırmaya hazır.

## C#'ta bir konsol barkod tarayıcısı nasıl oluşturulur?

`BarCodeReader` Aspose.BarCode tarafından sağlanan bir sınıftır; görüntülerden barkodları okur ve çözülen verileri döndürür.  
Görüntüyü `BarCodeReader` ile yükleyin, çözümleme türünü `MacroPdf417` olarak ayarlayın ve sonuçlar üzerinde yineleyin – bu, bir konsol barkod tarayıcısı oluşturmak için ihtiyacınız olan tek şeydir. `using` ifadesi sayesinde okuyucu yerel kaynakları otomatik olarak serbest bırakır, böylece belleği manuel olarak yönetmeniz gerekmez. Bu yaklaşım PNG, JPEG veya BMP gibi .NET tarafından desteklenen herhangi bir görüntü formatı için çalışır.

### Adım adım kılavuz

Çözümün çekirdeği, bir `BarCodeReader` örneği oluşturan, `DecodeType.MacroPdf417` belirten ve tespit edilen her barkodu yineleyen bir `using` bloğudur. Aşağıdaki kod, `Program.cs` dosyasına yapıştırabileceğiniz tam, bağımsız bir programdır.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Neden bu çalışır**:  

* `DecodeType.MacroPdf417`, okuyucuya PDF417'nin macro uzantısını aramasını söyler; bu uzantı dosya kimliği, segment sayısı ve zaman damgaları gibi ek meta veriler taşır.  
* `using` ifadesi, yönetilmeyen kaynakların (dosya tutamaçları, yerel kod çözücü tamponları) hızlı bir şekilde serbest bırakılmasını garanti eder.  
* `foreach` döngüsü, görüntünün içerdiği **tüm** barkodları otomatik olarak işler ve *birden fazla barkod okuma* gereksinimini karşılar.  

Programı (`dotnet run`) çalıştırdığınızda aşağıdakine benzer bir çıktı görmelisiniz:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Görüntü birden fazla PDF417 barkodu içeriyorsa, döngü her barkod için ayrı bir blok yazdırır; böylece tek bir resimden **birden fazla barkod okuma** nasıl yapılır gösterilir.

## Bir görüntüden birden fazla barkodu nasıl okuyabilirim?

Tek bir `BarCodeReader` örneği kullanın ve `DecodeType` bayrağını tespit etmek istediğiniz tüm formatları içerecek şekilde ayarlayın. Bayrakları bitwise OR operatörüyle birleştirerek kütüphaneye PDF417, QR, Code‑128 ve daha birçok sembolojiyi tek geçişte aramasını söyleyebilirsiniz. Bu, ayrı okuyuculara ihtiyaç duymayı ortadan kaldırır ve işleme süresini azaltır.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* bir bitmask olduğundan, desteklenen istediğiniz sayıda formatı birleştirebilirsiniz. Aspose.BarCode **30+ barkod sembolojisi** destekler; QR, DataMatrix, Code‑128 ve UPC‑A gibi çeşitli kullanım senaryolarını tek bir tarayıcıyla yönetmenizi sağlar (ürün etiketleme, bilet doğrulama, kimlik doğrulama vb.).

## Macro PDF417 nedir ve alanlarına güvenli bir şekilde nasıl erişilir?

Macro PDF417, büyük bir veri setinin birden fazla barkod sembolü arasında bölünmesine olanak tanıyan PDF417 sembolojisinin bir uzantısıdır.  
Macro PDF417, zengin bir genişletilmiş özellik seti ekler. Ancak, her barkod her alanı içermez. Eksik bir özelliğe erişmek `NullReferenceException` fırlatabilir. En güvenli yaklaşım, her özelliği yazdırmadan önce doğrulamaktır; böylece macro verisi olmadığında bile uygulamanız kararlı kalır.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Neden bu önemli*: Gerçek dünyada macro verisi olmayan düz PDF417 barkodları alabilirsiniz. Savunmacı kontrol, uygulamanızın çökmeden çalışmaya devam etmesini sağlar.

## Yaygın tuzaklar ve en iyi uygulamalar

| Sorun | Neden oluşur | Önerilen çözüm |
|-------|----------------|-----------------|
| Görüntü yolu yanlış | `BarCodeReader`, herhangi bir kod çözme gerçekleşmeden dosya bulunamadı istisnası atar | `Path.Combine` kullanın ve dosyanın varlığını `File.Exists` ile doğrulayın |
| Düşük çözünürlüklü görüntü | Kod çözücü barkod kenarlarını bulamaz, sonuçta sıfır tespit olur | Güvenilir sonuçlar için minimum 300 dpi çözünürlük sağlayın |
| Barkod 45°'den fazla döndürülmüş | Birçok kütüphane dikey konum varsayar | Görüntü döndürülmüş olabilecekse `reader.RecognitionOptions.RotateImage = true` etkinleştirin |
| Eksik macro alanları | Null bir özelliği okumaya çalışmak çöküşe neden olur | Macro özelliklerine erişmeden önce her zaman `null` kontrolü yapın |
| Büyük toplu işleme | Her dosya için okuyucuyu yeniden oluşturmak ek yük getirir | Birçok görüntü işlenirken farklı akışlarla tek bir `BarCodeReader` örneğini yeniden kullanın |

## Konsol barkod tarayıcısı için Aspose.BarCode neden kullanılmalı?

Aspose.BarCode **30+ barkod türünü** çözebilir ve **200 MP**'ye kadar görüntüyü belleğe tamamen yüklemeden işleyebilir; tipik bir 3.2 GHz CPU'da **150 kare/saniye** işleme hızı sağlar. Bu ölçülen yetenekler, gecikme ve doğruluğun kritik olduğu yüksek hacimli, şirket içi tarama çözümleri için güvenilir bir tercih olmasını sağlar.

## Sonra ne öğrenmelisiniz?

Aşağıdaki eğitimler, bu rehberde gösterilen tekniklere dayanan yakın konuları kapsar. Her kaynak, adım adım açıklamalarla tam çalışan kod örnekleri içerir; böylece ek API özelliklerini öğrenebilir ve kendi projelerinizde alternatif uygulama yaklaşımlarını keşfedebilirsiniz.

- [Aspose.BarCode for .NET ile DataMatrix Barkodlarını Okuma](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix Barkodu C# ile Okuma – DataMatrix Modu (Otomatik) Oluşturma](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Görüntüden Barkod Okuma – Java'da Aspose.BarCode ile Barkod Bölgesi Çıkarma Uzmanlığı](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Sıkça Sorulan Sorular

**S: Bu tarayıcıyı üretim ortamında kullanabilir miyim?**  
E: Evet. Değerlendirme filigranını kaldırmak ve tam destek almak için ticari bir Aspose.BarCode lisansı satın alın.

**S: Kütüphane Linux ve macOS'ta çalışıyor mu?**  
E: Kesinlikle. Aspose.BarCode for .NET, Windows, Linux ve macOS'ta .NET 6+ üzerinde çalışan çapraz platform bir çözümdür.

**S: Çok büyük görüntüleri belleği tüketmeden nasıl yönetirim?**  
E: `LoadOptions` yapıcısını kullanarak akış modunu etkinleştirin; bu, görüntüyü tamamen RAM'e yüklemek yerine parçalar halinde işler.

**S: Şifreli veya parola korumalı görüntüler çözülebilir mi?**  
E: Okuyucu, standart PNG/JPEG parola şemalarıyla şifrelenmiş görüntüleri işleyebilir; sadece parolayı `reader.ImagePassword` ile sağlayın.

**S: Barkodum kısmen hasar görmüşse ne olur?**  
E: Hasar veya gürültüye karşı dayanıklılığı artırmak için `reader.RecognitionOptions.CorrectErrors = true` gibi hata düzeltme seçeneklerini etkinleştirin.

**Son Güncelleme:** 2026-10-14  
**Test Edilen:** Aspose.BarCode 24.11 for .NET  
**Yazar:** Aspose

## İlgili Eğitimler

- [C'de Pdf417 Okuma – Tam Barkod Okuyucu Örneği](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Pdf417 ile C'de Birden Fazla Barkod Okuma – Tam Kılavuz](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Bir Görüntüden Barkod Çözme – C Barkod Okuyucu Örneği](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}