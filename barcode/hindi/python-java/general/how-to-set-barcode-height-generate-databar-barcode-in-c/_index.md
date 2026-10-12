---
category: general
date: 2026-10-12
description: Aspose.BarCode का उपयोग करके C# में बारकोड की ऊँचाई कैसे सेट करें और
  DataBar बारकोड जेनरेट करें। पूर्ण कोड के साथ चरण‑दर‑चरण गाइड का पालन करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: hi
lastmod: 2026-10-12
og_description: C# में बारकोड की ऊँचाई कैसे सेट करें और Aspose.BarCode के साथ DataBar
  बारकोड जनरेट करें। पूरा कोड जानें, प्रत्येक चरण का महत्व क्यों है, और बारकोड की
  ऊँचाई कैसे बदलें।
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: C# में बारकोड की ऊँचाई कैसे सेट करें और DataBar बारकोड जेनरेट करें
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: बारकोड की ऊँचाई कैसे सेट करें, C# में DataBar बारकोड जेनरेट करें
url: /hi/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बारकोड की ऊँचाई कैसे सेट करें, C# में DataBar बारकोड जनरेट करें

यदि आपको प्रोग्रामेटिकली **how to set barcode** आयाम सेट करने की आवश्यकता है, तो यह गाइड आपको सटीक चरण दिखाएगा। आप सीखेंगे कि DataBar Omni‑directional बारकोड कैसे जनरेट करें, उसकी ऊँचाई कैसे समायोजित करें, और दोनों संस्करण PNG फ़ाइलों के रूप में कैसे सहेजें।

बारकोड की बार ऊँचाई बदलना एक सामान्य आवश्यकता है जब आप बारकोड को रसीदों, उत्पाद लेबलों या मोबाइल स्क्रीन में एकीकृत करते हैं। नीचे दिया गया उदाहरण Aspose.BarCode लाइब्रेरी का उपयोग करता है, जो GS1 DataBar सिम्बोलॉजीज़ की पूरी रेंज को सपोर्ट करती है।

## आप क्या हासिल करेंगे

* **how to set barcode** ऊँचाई DataBar Omni‑directional बारकोड के लिए  
* **generate barcode c#** कोड जो विभिन्न ऊँचाइयों के साथ दो छवियाँ बनाता है  
* **how to create databar** प्रतीकों को समझें और बार ऊँचाई क्यों महत्वपूर्ण है  
* **change barcode height** लॉजिक को जनरेटर को पुनः बनाये बिना लागू करें  

Aspose.BarCode NuGet पैकेज और .NET 6+ रनटाइम के अलावा कोई बाहरी टूल आवश्यक नहीं है।

## पूर्वापेक्षाएँ

* .NET 6 SDK या बाद का स्थापित हो  
* Visual Studio 2022 (या कोई भी C# एडिटर)  
* Aspose.BarCode for .NET – `dotnet add package Aspose.BarCode` के माध्यम से स्थापित करें  

> **Pro tip:** यदि आपके पास व्यावसायिक कुंजी नहीं है तो Aspose की फ्री ट्रायल लाइसेंस का उपयोग करें; API समान तरीके से काम करता है।

## चरण 1: Aspose.BarCode पैकेज स्थापित करें

अपने प्रोजेक्ट फ़ोल्डर में एक टर्मिनल खोलें और चलाएँ:

```bash
dotnet add package Aspose.BarCode
```

यह पैकेज `Aspose.BarCode` नेमस्पेस जोड़ता है, जिसमें `BarcodeGenerator` क्लास शामिल है जिसे हम **generate barcode c#** छवियों के लिए उपयोग करेंगे।

## चरण 2: DataBar बारकोड जनरेटर बनाएं

**how to set barcode** पैरामीटर के लिए पहला ठोस कार्य वांछित सिम्बोलॉजी और डेटा स्ट्रिंग के साथ `BarcodeGenerator` को इंस्टैंशिएट करना है।

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*यह क्यों महत्वपूर्ण है:* `EncodeTypes.DatabarOmniDirectional` एक कॉम्पैक्ट, ऑम्निडायरेक्शनल DataBar उत्पन्न करता है जिसे किसी भी कोण से स्कैन किया जा सकता है—छोटे लेबल्स के लिए आदर्श।

## चरण 3: सामान्य बारकोड पैरामीटर सेट करें (प्रारंभिक बार ऊँचाई सहित)

अब हम **how to set barcode** X‑डायमेंशन और बार ऊँचाई को पहली छवि सहेजने से पहले निर्धारित करेंगे।

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑डायमेंशन प्रत्येक बार की कुल चौड़ाई नियंत्रित करता है; 2‑पिक्सेल सेटिंग अधिकांश स्क्रीन पर पठनीय, तेज़ छवि देती है। बाद में **change barcode height** चरण उसी जनरेटर को पुनः उपयोग करेगा, जिससे समय और मेमोरी बचती है।

## चरण 4: पहली बारकोड छवि सहेजें (30‑पिक्सेल ऊँचाई)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

`DatabarHeight30.png` फ़ाइल अब 30‑पिक्सेल बार ऊँचाई वाला DataBar बारकोड रखती है।

## चरण 5: केवल बार ऊँचाई को 60 पिक्सेल बदलें

**change barcode height** दिखाने के लिए, हम केवल `BarHeight` प्रॉपर्टी को बदलते हैं। सभी अन्य सेटिंग्स अपरिवर्तित रहती हैं, जो एक ही जनरेटर से कई आकार बनाने का सबसे कुशल तरीका है।

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## चरण 6: दूसरी बारकोड छवि सहेजें (60‑पिक्सेल ऊँचाई)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

अब आपके पास दो PNG फ़ाइलें हैं, प्रत्येक की बार ऊँचाई अलग है लेकिन डेटा और X‑डायमेंशन समान हैं।

## पूर्ण, चलाने योग्य उदाहरण

नीचे पूरा प्रोग्राम दिया गया है जिसे आप नई कंसोल एप्लिकेशन (`dotnet new console`) में कॉपी‑पेस्ट कर सकते हैं और तुरंत चला सकते हैं।

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### अपेक्षित आउटपुट

प्रोग्राम चलाने से निष्पादन योग्य की कार्य निर्देशिका में दो फ़ाइलें बनती हैं:

* `DatabarHeight30.png` – 30‑पिक्सेल ऊँचाई वाले बारों के साथ DataBar बारकोड।  
* `DatabarHeight60.png` – वही बारकोड, लेकिन प्रत्येक बार दो गुना ऊँचा है।

दोनों छवियों को किसी भी इमेज व्यूअर में खोला जा सकता है या सीधे PDFs, HTML पेजों, या प्रिंटेड लेबल्स में एम्बेड किया जा सकता है।

## बार ऊँचाई समायोजित करना क्यों महत्वपूर्ण है

* **Scanning reliability:** कुछ स्कैनर कम‑रिज़ॉल्यूशन मीडिया पर बहुत छोटे बारों से जूझते हैं; ऊँचाई बढ़ाने से डिटेक्शन सुधरता है।  
* **Design constraints:** एक मोबाइल ऐप को कॉम्पैक्ट बारकोड (30 px) चाहिए हो सकता है जबकि प्रिंटेड रसीद को बड़ा (60 px) चाहिए।  
* **Regulatory compliance:** कुछ उद्योगों में GS1 DataBar प्रतीकों के लिए न्यूनतम बार ऊँचाई अनिवार्य होती है।  

एक ही `BarcodeGenerator` इंस्टेंस को पुनः उपयोग करके, आप डेटा स्ट्रिंग को पुनः पार्स करने का ओवरहेड बचाते हैं, जो उच्च‑थ्रूपुट वातावरण में विशेष रूप से लाभदायक है।

## सामान्य विविधताएँ और किनारे के मामले

| Situation | Recommended tweak |
|-----------|-------------------|
| विभिन्न X‑डायमेंशन चाहिए | पहले `Save` से पहले `XDimension.Pixels` बदलें। |
| विभिन्न सिम्बोलॉजी चाहिए (जैसे, DataBar Stacked) | `BarcodeGenerator` बनाते समय `EncodeTypes.DatabarStacked` उपयोग करें। |
| बारकोड को PDF में एम्बेड करना आवश्यक है | `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` उपयोग करें और स्ट्रीम को PDF लाइब्रेरी में जोड़ें। |
| .NET Framework 4.6 पर चल रहा है | कोड वही काम करता है; बस उचित Aspose.BarCode असेंबली को रेफ़रेंस करें। |

## विश्वसनीय बारकोड जनरेशन के लिए प्रो टिप्स

* **Cache the generator** का उपयोग करें जब आप समान डेटा लेकिन विभिन्न आकारों के साथ कई बारकोड जनरेट करते हैं।  
* **

## अब आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक कार्यान्वयन दृष्टिकोणों का अन्वेषण करने में मदद करती हैं।

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}