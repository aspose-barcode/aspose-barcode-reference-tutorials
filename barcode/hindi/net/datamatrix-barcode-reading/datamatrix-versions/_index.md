---
title: .NET के लिए Aspose.BarCode के साथ डेटामैट्रिक्स बारकोड जेनरेट करें
linktitle: डेटामैट्रिक्स संस्करण
second_title: Aspose.BarCode .NET API
description: .NET के लिए Aspose.BarCode का उपयोग करके .NET में DataMatrix बारकोड जेनरेट करना सीखें। कस्टम आयाम, ईसीसी समर्थन, और बहुत कुछ।
weight: 12
url: /hi/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.BarCode के साथ डेटामैट्रिक्स बारकोड जेनरेट करें

यदि आप अपने .NET अनुप्रयोगों में डेटामैट्रिक्स बारकोड उत्पन्न करने के लिए एक विश्वसनीय समाधान की तलाश में हैं, तो .NET के लिए Aspose.BarCode जाने का रास्ता है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको DataMatrix बारकोड बनाने के लिए .NET के लिए Aspose.BarCode का उपयोग करने की प्रक्रिया के बारे में बताएंगे। हम प्रत्येक उदाहरण को कई चरणों में विभाजित करेंगे, यह सुनिश्चित करते हुए कि आप आसानी से अनुसरण कर सकते हैं।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- .NET समर्थन के साथ एक विकास वातावरण।
-  .NET के लिए Aspose.BarCode की एक प्रति, जिसे आप डाउनलोड कर सकते हैं[इस लिंक](https://releases.aspose.com/barcode/net/).
- C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।

अब, आइए DataMatrix संस्करणों का पता लगाएं और .NET के लिए Aspose.BarCode का उपयोग करके उन्हें कैसे उत्पन्न करें।

## नामस्थान आयात करें

किसी भी C# प्रोजेक्ट में, आवश्यक नामस्थान आयात करना आवश्यक है। Aspose.BarCode के मामले में, आपको निम्नलिखित को शामिल करना होगा:

```csharp
using Aspose.BarCode.Generation;
```

 यह नेमस्पेस तक पहुंच प्रदान करता है`BarcodeGenerator` क्लास, जो बारकोड बनाने के लिए महत्वपूर्ण है।

अब, आइए उदाहरण को कई चरणों में विभाजित करें।

## चरण 1: अपना निर्देशिका पथ सेट करें

उस निर्देशिका पथ को परिभाषित करके प्रारंभ करें जहां आप जेनरेट किए गए डेटामैट्रिक्स बारकोड को सहेजना चाहते हैं।

```csharp
string path = "Your Directory Path";
```

 प्रतिस्थापित करें`"Your Directory Path"` वास्तविक पथ के साथ जहां आप बारकोड छवियों को सहेजना चाहते हैं।

## चरण 2: बारकोड जेनरेटर को प्रारंभ करें

 का एक उदाहरण बनाएं`BarcodeGenerator` क्लास बनाएं और बारकोड प्रकार निर्दिष्ट करें`DataMatrix`. आप वह डेटा भी प्रदान कर सकते हैं जिसे आप बारकोड के भीतर एन्कोड करना चाहते हैं।

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // बारकोड जनरेट करने के लिए कोड यहां दिया गया है
}
```

## चरण 3: बारकोड गुणों को कॉन्फ़िगर करें

आप डेटामैट्रिक्स बारकोड के विभिन्न गुणों को अनुकूलित कर सकते हैं, जैसे इसके आयाम और ईसीसी (त्रुटि सुधार कोड) प्रकार। यहां एक्स-आयाम को 4 पिक्सेल पर सेट करने और ECC200 चुनने का एक उदाहरण दिया गया है:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## चरण 4: डेटामैट्रिक्स संस्करण सेट करें और सहेजें

आप पंक्तियों और स्तंभों की संख्या निर्धारित करके डेटामैट्रिक्स संस्करण निर्दिष्ट कर सकते हैं। संस्करण को कॉन्फ़िगर करने के बाद, बारकोड छवि को सहेजें।

उदाहरण के लिए, ECC200 का उपयोग करके 22 पंक्तियों और 22 स्तंभों वाला डेटामैट्रिक्स बारकोड बनाने के लिए:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

इसी तरह, आप आवश्यकतानुसार संस्करण और ईसीसी प्रकार को बदलकर विभिन्न मापदंडों के साथ एक बारकोड उत्पन्न कर सकते हैं।

## चरण 5: अन्य संस्करणों के लिए दोहराएँ

आप अन्य डेटामैट्रिक्स संस्करणों के लिए चरण 4 को दोहरा सकते हैं। उदाहरण के लिए, ECC200 का उपयोग करके 12 पंक्तियों और 64 स्तंभों वाला बारकोड बनाने के लिए:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## चरण 6: ईसीसी प्रकार बदलें

यदि आप ECC प्रकार को Ecc140 में बदलना चाहते हैं, तो आप ECC प्रॉपर्टी को अपडेट करके ऐसा कर सकते हैं:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## चरण 7: विभिन्न संस्करणों और ईसीसी के साथ बारकोड उत्पन्न करें

अन्य डेटामैट्रिक्स संस्करणों और ईसीसी प्रकारों के लिए चरण 4 को दोहराएं, प्रत्येक बारकोड को एक अद्वितीय फ़ाइल नाम के साथ सहेजें।

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

अब जब आपने सीख लिया है कि .NET के लिए Aspose.BarCode का उपयोग करके डेटामैट्रिक्स बारकोड कैसे जनरेट किया जाता है, तो आप इस कार्यक्षमता को आसानी से अपने .NET अनुप्रयोगों में एकीकृत कर सकते हैं।

## निष्कर्ष

.NET के लिए Aspose.BarCode आपके .NET अनुप्रयोगों में डेटामैट्रिक्स बारकोड बनाने की प्रक्रिया को सरल बनाता है। इस चरण-दर-चरण मार्गदर्शिका के साथ, आप विभिन्न संस्करणों और ईसीसी प्रकारों के साथ बारकोड बना सकते हैं, जो आपकी विशिष्ट आवश्यकताओं को पूरा करने के लिए लचीलापन और अनुकूलन प्रदान करते हैं।

 यदि आपके कोई प्रश्न हैं या सहायता की आवश्यकता है, तो यहां आने में संकोच न करें[.NET दस्तावेज़ के लिए Aspose.BarCode](https://reference.aspose.com/barcode/net/) या जाँच करें[Aspose.BarCode फोरम](https://forum.aspose.com/c/barcode/13) समर्थन के लिए।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: डेटामैट्रिक्स बारकोड में ECC क्या है?

A1: ECC (त्रुटि सुधार कोड) डेटामैट्रिक्स बारकोड का एक महत्वपूर्ण घटक है जो डेटा अखंडता सुनिश्चित करने में मदद करता है। विभिन्न ईसीसी स्तर त्रुटि सुधार की अलग-अलग डिग्री प्रदान करते हैं।

### Q2: क्या मैं .NET के लिए Aspose.BarCode का उपयोग करके कस्टम आयामों के साथ DataMatrix बारकोड उत्पन्न कर सकता हूं?

उ2: हां, आप ट्यूटोरियल में दिखाए अनुसार पंक्तियों और स्तंभों की संख्या निर्धारित करके डेटामैट्रिक्स बारकोड के आयामों को अनुकूलित कर सकते हैं।

### Q3: मैं .NET के लिए Aspose.BarCode कहां से डाउनलोड कर सकता हूं?

 A3: आप .NET के लिए Aspose.BarCode डाउनलोड कर सकते हैं[इस लिंक](https://releases.aspose.com/barcode/net/).

### Q4: क्या .NET के लिए Aspose.BarCode का निःशुल्क परीक्षण उपलब्ध है?

 उ4: हां, आप .NET के लिए Aspose.BarCode का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मैं .NET के लिए Aspose.BarCode के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A5: .NET के लिए Aspose.BarCode का अस्थायी लाइसेंस प्राप्त करने के लिए, यहां जाएं[इस लिंक](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
