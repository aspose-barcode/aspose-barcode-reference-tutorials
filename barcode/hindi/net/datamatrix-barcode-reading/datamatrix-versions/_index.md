---
date: 2026-01-20
description: Aspose.BarCode का उपयोग करके .NET में डेटामैट्रिक्स त्रुटि सुधार के साथ
  डेटामैट्रिक्स बारकोड बनाना सीखें। जल्दी से बारकोड कैसे बनाएं, जानें।
linktitle: DataMatrix Versions
second_title: Aspose.BarCode .NET API
title: डेटा मैट्रिक्स त्रुटि सुधार के साथ डेटा मैट्रिक्स बारकोड बनाएं
url: /hi/net/datamatrix-barcode-reading/datamatrix-versions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET का उपयोग करके डेटामैट्रिक्स एरर करेक्शन के साथ डेटामैट्रिक्स बारकोड जनरेट करें

यदि आप अपनी .NET एप्लिकेशन में डेटामैट्रिक्स बारकोड जनरेट करने के लिए एक भरोसेमंद समाधान खोज रहे हैं, तो Aspose.BarCode for .NET आपका सही विकल्प है। इस चरण‑दर‑चरण गाइड में, हम आपको **बारकोड कैसे जनरेट करें** को पूरी **डेटामैट्रिक्स एरर करेक्शन** समर्थन के साथ दिखाएंगे, ताकि आप विभिन्न व्यावसायिक परिदृश्यों के लिए मजबूत, स्कैन करने योग्य प्रतीक बना सकें।

## त्वरित उत्तर

- **डेटामैट्रिक्स एरर करेक्शन को कौन सी लाइब्रेरी सपोर्ट करती है?** Aspose.BarCode for .NET
- **कौन सा ECC लेवल सबसे मजबूत सुरक्षा देता है?** Ecc140 (उच्च रिडंडेंसी प्रदान करता है)
- **कोड की कितनी लाइनों की आवश्यकता है?** बेसिक बारकोड के लिए 20 लाइनों से कम
- **क्या मैं पंक्तियों और कॉलम को कस्टमाइज़ कर सकता हूँ?** हाँ – DataMatrix संस्करण को मैन्युअली सेट करें
- **क्या प्रोडक्शन के लिए लाइसेंस आवश्यक है?** हाँ, एक कमर्शियल लाइसेंस चाहिए

## डेटामैट्रिक्स एरर करेक्शन का अवलोकन

डेटामैट्रिक्स एरर करेक्शन (ECC) प्रतीक में अतिरिक्त डेटा जोड़ता है, जिससे स्कैनर बारकोड के किसी हिस्से के क्षतिग्रस्त होने पर भी मूल जानकारी पुनः प्राप्त कर सकते हैं। Aspose.BarCode आपको ECC200, ECC140 और अन्य लेवल्स में से चुनने की सुविधा देता है, जिससे आप प्रतीक के आकार और मजबूती के बीच संतुलन नियंत्रित कर सकते हैं।

## पूर्वापेक्षाएँ

कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- .NET समर्थन वाला विकास पर्यावरण।
- Aspose.BarCode for .NET की एक कॉपी, जिसे आप [इस लिंक](https://releases.aspose.com/barcode/net/) से डाउनलोड कर सकते हैं।
- C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।

अब, चलिए DataMatrix संस्करणों और उन्हें Aspose.BarCode for .NET का उपयोग करके कैसे जनरेट करें, इसे देखें।

## नेमस्पेस इम्पोर्ट करें

किसी भी C# प्रोजेक्ट में, आवश्यक नेमस्पेस इम्पोर्ट करना आवश्यक है। Aspose.BarCode के मामले में, आपको निम्नलिखित को शामिल करना होगा:

```csharp
using Aspose.BarCode.Generation;
```

यह नेमस्पेस `BarcodeGenerator` क्लास तक पहुंच प्रदान करता है, जो बारकोड जनरेट करने के लिए महत्वपूर्ण है।

अब, चलिए उदाहरण को कई चरणों में विभाजित करते हैं।

## चरण 1: अपनी डायरेक्टरी पाथ सेट करें

सबसे पहले उस डायरेक्टरी पाथ को परिभाषित करें जहाँ आप जनरेट किए गए DataMatrix बारकोड सेव करना चाहते हैं।

```csharp
string path = "Your Directory Path";
```

`"Your Directory Path"` को वास्तविक पाथ से बदलें जहाँ आप बारकोड इमेजेज़ सेव करना चाहते हैं।

## चरण 2: बारकोड जेनरेटर को इनिशियलाइज़ करें

`BarcodeGenerator` क्लास की एक इंस्टेंस बनाएं और बारकोड टाइप को `DataMatrix` सेट करें। आप बारकोड के भीतर एन्कोड करने के लिए डेटा भी प्रदान कर सकते हैं।

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Code for generating barcodes goes here
}
```

## चरण 3: डेटामैट्रिक्स एरर करेक्शन के लिए बारकोड प्रॉपर्टीज़ कॉन्फ़िगर करें

आप DataMatrix बारकोड की विभिन्न प्रॉपर्टीज़ जैसे आकार और ECC (Error Correction Code) टाइप को कस्टमाइज़ कर सकते हैं। यहाँ X‑डायमेंशन को 4 पिक्सेल सेट करने और ECC200 चुनने का एक उदाहरण है:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## चरण 4: DataMatrix संस्करण सेट करें और सेव करें

आप पंक्तियों और कॉलम की संख्या सेट करके DataMatrix संस्करण निर्दिष्ट कर सकते हैं। संस्करण कॉन्फ़िगर करने के बाद, बारकोड इमेज को सेव करें।

उदाहरण के लिए, ECC200 का उपयोग करके 22 पंक्तियों और 22 कॉलम के साथ DataMatrix बारकोड बनाने के लिए:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

इसी प्रकार, आप संस्करण और ECC टाइप बदलकर विभिन्न पैरामीटरों के साथ बारकोड जनरेट कर सकते हैं।

## चरण 5: अन्य संस्करणों के लिए दोहराएँ

आप चरण 4 को अन्य DataMatrix संस्करणों के लिए दोहरा सकते हैं। उदाहरण के लिए, ECC200 का उपयोग करके 12 पंक्तियों और 64 कॉलम के साथ बारकोड बनाने के लिए:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## चरण 6: ECC टाइप बदलें

यदि आप ECC टाइप को Ecc140 में बदलना चाहते हैं, तो आप ECC प्रॉपर्टी को अपडेट करके ऐसा कर सकते हैं:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## चरण 7: विभिन्न संस्करणों और ECC के साथ बारकोड जनरेट करें

अन्य DataMatrix संस्करणों और ECC टाइप्स के लिए चरण 4 को दोहराएँ, प्रत्येक बारकोड को एक अनूठे फ़ाइल नाम से सेव करें।

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

अब जब आप Aspose.BarCode for .NET का उपयोग करके DataMatrix बारकोड जनरेट करना सीख चुके हैं, तो आप इस फ़ंक्शनैलिटी को आसानी से अपने .NET एप्लिकेशन में इंटीग्रेट कर सकते हैं।

## निष्कर्ष

Aspose.BarCode for .NET आपके .NET एप्लिकेशन में DataMatrix बारकोड जनरेट करने की प्रक्रिया को सरल बनाता है। इस चरण‑दर‑चरण गाइड के साथ, आप विभिन्न संस्करणों और ECC टाइप्स वाले बारकोड बना सकते हैं, जो आपके विशिष्ट आवश्यकताओं को पूरा करने के लिए लचीलापन और कस्टमाइज़ेशन प्रदान करता है।

यदि आपके कोई प्रश्न हैं या सहायता चाहिए, तो [Aspose.BarCode for .NET दस्तावेज़ीकरण](https://reference.aspose.com/barcode/net/) पर जाएँ या समर्थन के लिए [Aspose.BarCode फ़ोरम](https://forum.aspose.com/c/barcode/13) देखें।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: DataMatrix बारकोड में ECC क्या है?

A1: ECC (Error Correction Code) DataMatrix बारकोड का एक महत्वपूर्ण घटक है जो डेटा की अखंडता सुनिश्चित करने में मदद करता है। विभिन्न ECC लेवल्स विभिन्न स्तर की एरर करेक्शन प्रदान करते हैं।

### प्रश्न 2: क्या मैं Aspose.BarCode for .NET का उपयोग करके कस्टम डाइमेंशन्स के साथ DataMatrix बारकोड जनरेट कर सकता हूँ?

A2: हाँ, आप ट्यूटोरियल में दिखाए अनुसार पंक्तियों और कॉलम की संख्या सेट करके DataMatrix बारकोड के आकार को कस्टमाइज़ कर सकते हैं।

### प्रश्न 3: मैं Aspose.BarCode for .NET कहाँ से डाउनलोड कर सकता हूँ?

A3: आप Aspose.BarCode for .NET को [इस लिंक](https://releases.aspose.com/barcode/net/) से डाउनलोड कर सकते हैं।

### प्रश्न 4: क्या Aspose.BarCode for .NET के लिए कोई फ्री ट्रायल उपलब्ध है?

A4: हाँ, आप Aspose.BarCode for .NET का फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

### प्रश्न 5: मैं Aspose.BarCode for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?

A5: Aspose.BarCode for .NET के लिए अस्थायी लाइसेंस प्राप्त करने के लिए, [इस लिंक](https://purchase.aspose.com/temporary-license/) पर जाएँ।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या लाइब्रेरी .NET Core और .NET 5/6 को सपोर्ट करती है?**  
A: हाँ, Aspose.BarCode for .NET .NET Framework, .NET Core, .NET 5, और .NET 6 के साथ पूरी तरह संगत है।

**Q: अपने उपयोग केस के लिए सही ECC लेवल कैसे चुनें?**  
A: आकार और सुरक्षा के अच्छे संतुलन के लिए ECC200 उपयोग करें; जब आपको क्षति के खिलाफ अधिक लचीलापन चाहिए तो ECC140 पर स्विच करें।

**Q: क्या मैं PNG के अलावा अन्य फ़ॉर्मेट में बारकोड जनरेट कर सकता हूँ?**  
A: बिल्कुल—BarCodeImageFormat JPEG, BMP, GIF, और अन्य फ़ॉर्मेट्स को सपोर्ट करता है।

**Q: यदि मुझे लूप में कई बारकोड जनरेट करने हों तो क्या करें?**  
A: एक `BarcodeGenerator` इंस्टेंस बनाएं, लूप के अंदर डेटा और संस्करण को अपडेट करें, और प्रत्येक इटरेशन के लिए `Save` कॉल करें ताकि प्रदर्शन बेहतर हो।

**अंतिम अपडेट:** 2026-01-20  
**परीक्षित संस्करण:** Aspose.BarCode 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}