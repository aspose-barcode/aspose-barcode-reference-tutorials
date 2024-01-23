---
title: .NET के लिए Aspose.BarCode के साथ पूरक बारकोड डेटा बनाना
linktitle: पूरक बारकोड डेटा कॉन्फ़िगरेशन
second_title: Aspose.BarCode .NET API
description: .NET के लिए Aspose.BarCode के साथ पूरक बारकोड डेटा जेनरेट करें। EAN-2 और EAN-5 बारकोड को सहजता से अनुकूलित करें। .NET डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

बारकोड निर्माण और अनुकूलन की दुनिया में, .NET के लिए Aspose.BarCode एक शक्तिशाली और बहुमुखी उपकरण के रूप में सामने आता है। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको .NET के लिए Aspose.BarCode का उपयोग करके पूरक बारकोड डेटा को कॉन्फ़िगर करने की प्रक्रिया के बारे में बताएगी। 

## आवश्यक शर्तें

इससे पहले कि हम पूरक बारकोड डेटा की दुनिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- विज़ुअल स्टूडियो या किसी अन्य .NET विकास उपकरण के साथ स्थापित एक विकास वातावरण।
-  .NET के लिए Aspose.BarCode की एक प्रति। यदि आपने पहले से नहीं किया है, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/barcode/net/).
- सी# प्रोग्रामिंग का बुनियादी ज्ञान।
- एक निर्देशिका जहां आप जेनरेट की गई बारकोड छवियों को सहेज सकते हैं।

## नामस्थान आयात करना

सबसे पहले, सुनिश्चित करें कि .NET के लिए Aspose.BarCode के साथ काम करने के लिए आपके C# कोड में आवश्यक नेमस्पेस शामिल हैं। अपनी C# फ़ाइल की शुरुआत में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.BarCode.Generation;
```

अब, आइए पूरक बारकोड डेटा को कॉन्फ़िगर करने की प्रक्रिया को कई चरणों में विभाजित करें।

## चरण 1: निर्देशिका पथ की स्थापना

 अपने C# कोड में, उस निर्देशिका का पथ परिभाषित करें जहाँ आप जेनरेट की गई बारकोड छवियों को सहेजना चाहते हैं। प्रतिस्थापित करें`"Your Directory Path"` आपके वास्तविक निर्देशिका पथ के साथ।

```csharp
string path = "Your Directory Path";
```

## चरण 2: बारकोड जेनरेटर बनाना

 का एक उदाहरण बनाएं`BarcodeGenerator` बारकोड प्रकार और वह डेटा निर्दिष्ट करके जिसे आप एन्कोड करना चाहते हैं। इस उदाहरण में, हम "1234567890128" डेटा के साथ EAN-13 बारकोड का उपयोग कर रहे हैं।

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## चरण 3: बारकोड आयामों को अनुकूलित करना

बारकोड के आयाम सेट करें, जैसे कि एक्स आयाम (बारकोड में सबसे छोटे तत्व की चौड़ाई) और पूरक स्थान। इस उदाहरण में, हमने X आयाम को 2 पिक्सेल और पूरक स्थान को 20 पिक्सेल पर सेट किया है।

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## चरण 4: EAN-2 अनुपूरक को कॉन्फ़िगर करना

EAN-2 पूरक बारकोड को कॉन्फ़िगर करने के लिए, पूरक डेटा को वांछित मान पर सेट करें। इस स्थिति में, हम इसे "12" पर सेट करते हैं। 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## चरण 5: बारकोड छवि को सहेजना

उत्पन्न बारकोड छवि को एक सार्थक नाम के साथ अपनी निर्दिष्ट निर्देशिका में सहेजें। इस उदाहरण में, हम EAN-2 पूरक बारकोड को "SupplementEAN2.png" के रूप में सहेजते हैं।

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## चरण 6: ईएएन-5 अनुपूरक को कॉन्फ़िगर करना

 EAN-5 पूरक बारकोड को कॉन्फ़िगर करने के लिए, बस इसे बदलें`SupplementData` आपके इच्छित मूल्य पर. यहां, हमने इसे "12345" पर सेट किया है।

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## चरण 7: बारकोड छवि सहेजना (ईएएन-5)

अंत में, EAN-5 पूरक बारकोड छवि को अपनी निर्दिष्ट निर्देशिका में सहेजें। इस स्थिति में, हम इसे "SupplementEAN5.png" के रूप में सहेजते हैं।

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

अब, आपने .NET के लिए Aspose.BarCode का उपयोग करके पूरक बारकोड डेटा को सफलतापूर्वक कॉन्फ़िगर और जेनरेट कर लिया है। आप अलग-अलग पूरक डेटा के साथ बारकोड प्रकारों की एक विस्तृत श्रृंखला बनाने के लिए इस दृष्टिकोण का उपयोग कर सकते हैं।

## निष्कर्ष

.NET के लिए Aspose.BarCode बारकोड निर्माण और अनुकूलन के लिए एक शक्तिशाली उपकरण है। इस गाइड में, हमने चरण दर चरण पूरक बारकोड डेटा को कॉन्फ़िगर करने और उत्पन्न करने की प्रक्रिया के बारे में बताया। सही पूर्वावश्यकताओं और थोड़ी सी कोडिंग के साथ, आप बारकोड डेटा के साथ कुशलतापूर्वक काम कर सकते हैं और अपनी विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।

 अधिक जानकारी और उन्नत उपयोग के लिए, देखें[.NET दस्तावेज़ के लिए Aspose.BarCode](https://reference.aspose.com/barcode/net/).

## अक्सर पूछे जाने वाले प्रश्नों

### क्या मैं अपने .NET कोर प्रोजेक्ट में .NET के लिए Aspose.BarCode का उपयोग कर सकता हूँ?
हाँ, .NET के लिए Aspose.BarCode .NET कोर के साथ संगत है।

### क्या .NET के लिए Aspose.BarCode का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप विजिट करके इसे निःशुल्क आज़मा सकते हैं[इस लिंक](https://releases.aspose.com/).

### मुझे .NET के लिए Aspose.BarCode का अस्थायी लाइसेंस कहां मिल सकता है?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### क्या Aspose.BarCode बारकोड प्रकारों की एक विस्तृत श्रृंखला का समर्थन करता है?
हां, यह EAN-13, QR कोड, कोड 128 और अन्य सहित विभिन्न बारकोड प्रकारों का समर्थन करता है।

### क्या मैं जेनरेट किए गए बारकोड के स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल, आप अपनी आवश्यकताओं को पूरा करने के लिए बारकोड के आयाम, रंग और अन्य पहलुओं को अनुकूलित कर सकते हैं।