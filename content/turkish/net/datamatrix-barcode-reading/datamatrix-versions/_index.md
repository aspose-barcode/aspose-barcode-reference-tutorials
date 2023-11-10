---
title: Aspose.BarCode for .NET ile DataMatrix Barkodları Oluşturun
linktitle: DataMatrix Sürümleri
second_title: Aspose.BarCode .NET API'si
description: Aspose.BarCode for .NET'i kullanarak .NET'te DataMatrix barkodlarını nasıl oluşturacağınızı öğrenin. Özel boyutlar, ECC desteği ve daha fazlası.
type: docs
weight: 12
url: /tr/net/datamatrix-barcode-reading/datamatrix-versions/
---
.NET uygulamalarınızda DataMatrix barkodları oluşturmak için güvenilir bir çözüm arıyorsanız Aspose.BarCode for .NET doğru yoldur. Bu adım adım kılavuzda, DataMatrix barkodları oluşturmak için Aspose.BarCode for .NET'i kullanma sürecinde size yol göstereceğiz. Kolayca takip edebilmenizi sağlamak için her örneği birden fazla adıma ayıracağız.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- .NET desteğine sahip bir geliştirme ortamı.
- Aspose.BarCode for .NET'in bir kopyasını şu adresten indirebilirsiniz:[bu bağlantı](https://releases.aspose.com/barcode/net/).
- C# ve .NET çerçevesi hakkında temel bilgi.

Şimdi DataMatrix sürümlerini ve bunların Aspose.BarCode for .NET kullanılarak nasıl oluşturulacağını inceleyelim.

## Ad Alanlarını İçe Aktar

Herhangi bir C# projesinde gerekli ad alanlarının içe aktarılması önemlidir. Aspose.BarCode durumunda aşağıdakileri eklemeniz gerekir:

```csharp
using Aspose.BarCode.Generation;
```

 Bu ad alanı aşağıdakilere erişim sağlar:`BarcodeGenerator` Barkod oluşturmak için çok önemli olan sınıf.

Şimdi örneği birden çok adıma ayıralım.

## 1. Adım: Dizin Yolunuzu Ayarlayın

Oluşturulan DataMatrix barkodlarını kaydetmek istediğiniz dizin yolunu tanımlayarak başlayın.

```csharp
string path = "Your Directory Path";
```

 Yer değiştirmek`"Your Directory Path"` barkod görüntülerini kaydetmek istediğiniz gerçek yolla.

## Adım 2: Barkod Oluşturucuyu Başlatın

 Bir örneğini oluşturun`BarcodeGenerator` sınıfını seçin ve barkod türünü şu şekilde belirtin:`DataMatrix`. Barkod içerisinde kodlamak istediğiniz verileri de sağlayabilirsiniz.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Barkod oluşturma kodu buraya gelecek
}
```

## 3. Adım: Barkod Özelliklerini Yapılandırın

DataMatrix barkodunun boyutları ve ECC (Hata Düzeltme Kodu) türü gibi çeşitli özelliklerini özelleştirebilirsiniz. Burada X boyutunun 4 piksele ayarlanmasına ve ECC200'ün seçilmesine ilişkin bir örnek verilmiştir:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Adım 4: DataMatrix Sürümünü Ayarlayın ve Kaydedin

Satır ve sütun sayısını ayarlayarak DataMatrix versiyonunu belirleyebilirsiniz. Sürümü yapılandırdıktan sonra barkod görüntüsünü kaydedin.

Örneğin ECC200 kullanarak 22 satır ve 22 sütunlu bir DataMatrix barkodu oluşturmak için:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Benzer şekilde ihtiyacınıza göre versiyonu ve ECC tipini değiştirerek farklı parametrelere sahip bir barkod oluşturabilirsiniz.

## Adım 5: Diğer Sürümler için Tekrarlayın

Diğer DataMatrix versiyonları için 4. Adımı tekrarlayabilirsiniz. Örneğin ECC200'ü kullanarak 12 satır ve 64 sütundan oluşan bir barkod oluşturmak için:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Adım 6: ECC Türlerini Değiştirin

ECC tipini Ecc140 olarak değiştirmek istiyorsanız bunu ECC özelliğini güncelleyerek yapabilirsiniz:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Adım 7: Farklı Sürümlere ve ECC'ye Sahip Barkodlar Oluşturun

Diğer DataMatrix sürümleri ve ECC türleri için 4. Adımı tekrarlayın ve her barkodu benzersiz bir dosya adıyla kaydedin.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Artık Aspose.BarCode for .NET'i kullanarak DataMatrix barkodlarını nasıl oluşturacağınızı öğrendiğinize göre, bu işlevselliği .NET uygulamalarınıza kolayca entegre edebilirsiniz.

## Çözüm

Aspose.BarCode for .NET, .NET uygulamalarınızda DataMatrix barkodları oluşturma sürecini basitleştirir. Bu adım adım kılavuzla, farklı versiyonlara ve ECC türlerine sahip barkodlar oluşturarak özel ihtiyaçlarınızı karşılayacak esneklik ve özelleştirme sunabilirsiniz.

 Herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa, ziyaret etmekten çekinmeyin.[Aspose.BarCode for .NET belgeleri](https://reference.aspose.com/barcode/net/) veya şuraya göz atın[Aspose.BarCode forumu](https://forum.aspose.com/c/barcode/13) destek için.

## SSS'ler

### S1: DataMatrix barkodlarında ECC nedir?

Cevap1: ECC (Hata Düzeltme Kodu), DataMatrix barkodlarının veri bütünlüğünün sağlanmasına yardımcı olan hayati bir bileşenidir. Farklı ECC seviyeleri, değişen derecelerde hata düzeltme sağlar.

### S2: Aspose.BarCode for .NET'i kullanarak özel boyutlu DataMatrix barkodları oluşturabilir miyim?

Cevap2: Evet, eğitimde gösterildiği gibi satır ve sütun sayısını ayarlayarak DataMatrix barkodlarının boyutlarını özelleştirebilirsiniz.

### S3: Aspose.BarCode for .NET'i nereden indirebilirim?

 Cevap3: Aspose.BarCode for .NET'i şu adresten indirebilirsiniz:[bu bağlantı](https://releases.aspose.com/barcode/net/).

### S4: Aspose.BarCode for .NET'in ücretsiz deneme sürümü mevcut mu?

 Cevap4: Evet, Aspose.BarCode for .NET'in ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).

### S5: Aspose.BarCode for .NET için nasıl geçici lisans alabilirim?

 Cevap5: Aspose.BarCode for .NET için geçici bir lisans almak için şu adresi ziyaret edin:[bu bağlantı](https://purchase.aspose.com/temporary-license/).