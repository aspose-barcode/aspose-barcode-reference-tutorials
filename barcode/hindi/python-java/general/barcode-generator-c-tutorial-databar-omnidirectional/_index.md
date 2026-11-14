---
category: general
date: 2026-11-14
description: बारकोड जेनरेटर C# ट्यूटोरियल जो दिखाता है कि DataBar Omnidirectional
  बारकोड कैसे बनाएं, X‑डायमेंशन सेट करें, और पिक्सेल में बार की ऊँचाई समायोजित करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: hi
lastmod: 2026-11-14
og_description: बारकोड जेनरेटर C# ट्यूटोरियल चरण-दर-चरण बताता है कि कैसे DataBar Omnidirectional
  बारकोड बनाएं, पिक्सेल में XDimension निर्धारित करें, और PNG आउटपुट के लिए बार की
  ऊँचाई बदलें।
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: बारकोड जेनरेटर C# ट्यूटोरियल – DataBar बारकोड बनाएं
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'बारकोड जेनरेटर C# ट्यूटोरियल: डेटा बार सर्वदिशात्मक'
url: /hi/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बारकोड जेनरेटर C# ट्यूटोरियल – DataBar Omnidirectional बारकोड बनाएं

यदि आप **बारकोड जेनरेटर C# ट्यूटोरियल** की तलाश में हैं, तो आप सही जगह पर आए हैं। यह गाइड आपको DataBar Omnidirectional बारकोड बनाने, पिक्सेल में XDimension सेट करने, और बार की ऊँचाई को समायोजित करके PNG इमेज बनाने की प्रक्रिया दिखाता है।

आप एक पूर्ण, चलाने योग्य उदाहरण देखेंगे जिसमें जेनरेटर को इनिशियलाइज़ करने से लेकर विभिन्न बार ऊँचाइयों के साथ कई इमेज सेव करने तक सब कुछ शामिल है। कोई बाहरी दस्तावेज़ीकरण आवश्यक नहीं—कोड को कॉपी करें, चलाएँ, और आपके पास उपयोग के लिए दो बारकोड फ़ाइलें तैयार होंगी।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* .NET 6.0 या बाद का संस्करण स्थापित हो  
* वह बारकोड लाइब्रेरी जिसका रेफ़रेंस `BarcodeGenerator`, `EncodeTypes`, और `BarCodeImageFormat` प्रदान करती है (उदाहरण के लिए, Aspose.BarCode for .NET)  
* C# सिंटैक्स और Visual Studio या आपके पसंदीदा IDE की बुनियादी समझ  

> **प्रो टिप:** यदि आप Aspose.BarCode उपयोग कर रहे हैं, तो अपने प्रोजेक्ट में NuGet पैकेज `Aspose.BarCode` जोड़ें।

## बारकोड जेनरेटर C# ट्यूटोरियल – चरण 1: जेनरेटर बनाएं

पहला चरण है `DatabarOmniDirectional` एन्कोड टाइप और आप जो डेटा एन्कोड करना चाहते हैं, उसके साथ `BarcodeGenerator` का एक इंस्टेंस बनाना।

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*यह क्यों महत्वपूर्ण है:* `EncodeTypes.DatabarOmniDirectional` लाइब्रेरी को बताता है कि वह ऐसा बारकोड उत्पन्न करे जिसे किसी भी दिशा से पढ़ा जा सके, जो रिटेल पैकेजिंग और लॉजिस्टिक्स के लिए आदर्श है।

## बारकोड के लिए XDimension पिक्सेल सेट करें

X‑डायमेंशन बारकोड में सबसे छोटे मॉड्यूल (अर्थात “पिक्सेल”) की चौड़ाई निर्धारित करता है। इसे पिक्सेल में सेट करने से आपको बारकोड की दृश्य घनत्व पर सटीक नियंत्रण मिलता है।

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*व्याख्या:* `2` पिक्सेल का मान अधिकांश स्कैनरों के लिए पर्याप्त तेज़ बारकोड देता है, जबकि इमेज फ़ाइल आकार को मध्यम रखता है।

## बार की ऊँचाई समायोजित करें और इमेज सेव करें

बार की ऊँचाई निर्धारित करती है कि बार कितने ऊँचे दिखेंगे। आप `BarHeight.Pixels` प्रॉपर्टी को बदलकर और फिर `Save` कॉल करके विभिन्न ऊँचाइयों के साथ कई इमेज बना सकते हैं।

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` एन्‍उम वैल्यू सुनिश्चित करती है कि आउटपुट एक लॉस‑लेस PNG फ़ाइल हो, जो बारकोड ग्राफ़िक्स के लिए अनुशंसित फ़ॉर्मेट है क्योंकि यह सटीक आयामों को बरकरार रखता है।

## कई इमेज बनाने के लिए बार ऊँचाई बदलें

अक्सर आपको एक ही बारकोड विभिन्न आकारों में चाहिए—जैसे एक छोटा लेबल और दूसरा बड़ा पोस्टर। बार ऊँचाई बदलें और उसी जेनरेटर इंस्टेंस का पुनः उपयोग करें:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*एज केस:* यदि बार ऊँचाई बहुत कम सेट की जाती है (उदाहरण के लिए, 10 px से कम), तो कुछ स्कैनर को कोड पढ़ने में दिक्कत हो सकती है। हमेशा अपने लक्ष्य स्कैनर हार्डवेयर के साथ उत्पन्न इमेज का परीक्षण करें।

## पूर्ण स्रोत कोड

नीचे पूरा प्रोग्राम दिया गया है जिसे आप नई कंसोल प्रोजेक्ट में कॉपी‑पेस्ट कर सकते हैं। इसमें सभी आवश्यक `using` निर्देश शामिल हैं और बार‑ऊँचाई के दो वैरिएशन दर्शाए गए हैं।

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

प्रोग्राम चलाएँ, `YOUR_DIRECTORY` को वैध फ़ोल्डर पाथ से बदलें, और आपको दो PNG फ़ाइलें मिलेंगी:

* `DatabarBarHeight30Pixels.png` – 30 px ऊँचे बार  
* `DatabarBarHeight60Pixels.png` – 60 px ऊँचे बार  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## सामान्य प्रश्न

| प्रश्न | उत्तर |
|----------|--------|
| **क्या मैं इमेज फ़ॉर्मेट बदल सकता हूँ?** | हाँ। `BarCodeImageFormat.Png` को अपनी आवश्यकता अनुसार `Jpeg`, `Bmp`, या `Gif` से बदलें। PNG लॉसलेस क्वालिटी के लिए पसंदीदा है। |
| **यदि मुझे अलग XDimension चाहिए तो?** | `generator.Parameters.Barcode.XDimension.Pixels` को किसी भी पूर्णांक मान पर सेट करें। बड़े मान कुल बारकोड की चौड़ाई बढ़ाते हैं। |
| **क्या DataBar Omnidirectional मोबाइल स्कैनिंग के लिए उपयुक्त है?** | हाँ, बशर्ते प्रिंटेड आकार स्कैनर के न्यूनतम मॉड्यूल आकार (आमतौर पर 0.33 mm) को पूरा करता हो। पिक्सेल‑आधारित XDimension इस आवश्यकता को पूरा करने में मदद करता है। |
| **बारकोड को PDF में कैसे एम्बेड करूँ?** | PNG सेव करने के बाद, किसी PDF लाइब्रेरी (जैसे iTextSharp) का उपयोग करके इमेज को PDF पेज में डालें। |

## निष्कर्ष

इस **बारकोड जेनरेटर C# ट्यूटोरियल** में हमने दिखाया कि कैसे DataBar Omnidirectional बारकोड बनाएं, XDimension पिक्सेल में सेट करें, और विभिन्न बार ऊँचाइयों के साथ PNG फ़ाइलें जनरेट करें। अब आपके पास एक पुन: उपयोग योग्य कोड स्निपेट है जिसे आप किसी भी C# प्रोजेक्ट में बारकोड निर्माण के लिए अनुकूलित कर सकते हैं।

### आगे क्या करें?

* `EncodeTypes` जैसे `Code128` या `QR` को एक्सप्लोर करें ताकि आपका बारकोड ज्ञान विस्तृत हो।  
* जनरेट किए गए PNG को PDF जेनरेशन लाइब्रेरी के साथ मिलाकर प्रिंटेबल इनवॉइस बनाएं।  
* `generator.Parameters.Barcode.Color` के साथ कस्टम रंगों का प्रयोग करें, जबकि स्कैनर स्पेसिफिकेशन में रहें।

उदाहरण को संशोधित करने, अतिरिक्त बार ऊँचाइयों को आज़माने, या आउटपुट फ़ॉर्मेट बदलने में संकोच न करें। हैप्पी कोडिंग!

## अगला क्या सीखें?

नीचे दिए गए ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर कर सकें।

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}