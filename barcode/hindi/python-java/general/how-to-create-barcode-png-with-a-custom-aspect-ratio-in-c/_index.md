---
category: general
date: 2026-10-05
description: C# में बारकोड PNG बनाएं और स्टैक्ड DataBar ओम्निडायरेक्शनल बारकोड्स के
  लिए एस्पेक्ट रेशियो 15 सेट करना सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: hi
lastmod: 2026-10-05
og_description: C# में बारकोड PNG बनाएं और कुछ चरणों में स्टैक्ड DataBar ओम्निडायरेक्शनल
  बारकोड्स के लिए एस्पेक्ट रेशियो 15 सेट करना जानें।
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: C# में बारकोड PNG बनाएं – अस्पेक्ट रेशियो 15 सेट करने का ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: C# में कस्टम अनुपात के साथ बारकोड PNG कैसे बनाएं
url: /hi/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में कस्टम एस्पेक्ट रेशियो के साथ बारकोड PNG कैसे बनाएं

यदि आपको C# में **create barcode PNG** बनाना है, तो यह गाइड आपको **how to set aspect ratio** 15 को सेट करने का तरीका दिखाता है एक स्टैक्ड DataBar ओम्निडायरेक्शनल बारकोड के लिए। हम प्रत्येक API कॉल को समझेंगे, बताएँगे कि एस्पेक्ट रेशियो क्यों महत्वपूर्ण है, और आपको एक पूर्ण, चलाने योग्य उदाहरण देंगे जिसे आप किसी भी .NET प्रोजेक्ट में डाल सकते हैं।

बारकोड इमेज बनाना इन्वेंटरी सिस्टम, शिपिंग लेबल, और रिटेल पॉइंट‑ऑफ़‑सेल एप्लिकेशन के लिए एक सामान्य आवश्यकता है। इस ट्यूटोरियल के अंत तक आपके पास एक PNG फ़ाइल होगी जो आपके बिजनेस पार्टनर द्वारा आवश्यक सटीक विज़ुअल स्पेसिफिकेशन को पूरा करती है। कोई बाहरी टूल नहीं, कोई मैन्युअल इमेज एडिटिंग नहीं—सिर्फ कोड।

## आवश्यकताएँ

* .NET 6.0 या बाद का (उदाहरण .NET 6 का उपयोग करता है लेकिन .NET 5+ के साथ भी काम करता है)
* Visual Studio 2022 (या कोई भी IDE जो .NET को सपोर्ट करता है)
* The **Aspose.BarCode for .NET** NuGet पैकेज  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* उस फ़ोल्डर में लिखने की अनुमति जहाँ आप PNG फ़ाइल सहेजना चाहते हैं

ये आवश्यकताएँ न्यूनतम हैं; वही कोड .NET Core, .NET Framework, या एक कंसोल एप्लिकेशन में काम करता है।

## Aspose.BarCode के साथ बारकोड PNG बनाएं

पहला कदम सही बारकोड प्रकार के साथ `BarcodeGenerator` क्लास का इंस्टैंस बनाना है। इस केस में हम `EncodeTypes.DatabarStackedOmniDirectional` का उपयोग करते हैं, जो एक स्टैक्ड DataBar बनाता है जिसे किसी भी दिशा से पढ़ा जा सकता है।

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*यह क्यों महत्वपूर्ण है:* The constructor takes two arguments—**the barcode symbology** and **the data string**. The DataBar format expects a GS1 application identifier, which is why the sample data starts with `(01)`.

## स्टैक्ड DataBar के लिए एस्पेक्ट रेशियो कैसे सेट करें

DataBar की विज़ुअल चौड़ाई **aspect ratio** प्रॉपर्टी द्वारा नियंत्रित होती है। उच्च रेशियो बार को चौड़ा बनाता है, जिससे लो‑रेज़ोल्यूशन प्रिंटर पर स्कैन विश्वसनीयता बढ़ सकती है।

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` एक सिंगल मॉड्यूल (सबसे छोटा बार या स्पेस) का आकार निर्धारित करता है। इसे 2 px पर रखने से एक स्पष्ट, हाई‑डेंसिटी इमेज मिलती है जो अधिकांश लेबल प्रिंटर के लिए उपयुक्त है।

## एस्पेक्ट रेशियो 15 सेट करें – कोड walkthrough

अब हम **set aspect ratio 15** की आवश्यकता लागू करते हैं। यह ट्यूटोरियल का मुख्य भाग है और वह सटीक API कॉल दिखाता है जिसकी आपको जरूरत है।

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*क्यों 15?* स्टैक्ड DataBar के लिए डिफ़ॉल्ट एस्पेक्ट रेशियो 12 है। इसे 15 तक बढ़ाने से प्रत्येक बार की चौड़ाई 25 % बढ़ जाती है, जो अक्सर लॉजिस्टिक्स प्रोवाइडर्स की स्पेसिफिकेशन से मेल खाती है जो तेज़ स्कैनिंग के लिए व्यापक बारकोड चाहते हैं।

## बारकोड को PNG के रूप में सहेजें

जनरेटर को कॉन्फ़िगर करने के बाद, अंतिम कदम इमेज को डिस्क पर लिखना है। `Save` मेथड एक फ़ाइल पाथ और एक इमेज फॉर्मेट एनेम को स्वीकार करता है।

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG फॉर्मेट लॉसलेस क्वालिटी को बरकरार रखता है, जिससे बारकोड किसी भी डिस्प्ले या प्रिंटर पर ठीक वैसा ही रेंडर होता है जैसा डिज़ाइन किया गया है।

## पूरा उदाहरण और अपेक्षित आउटपुट

नीचे पूरा प्रोग्राम है जिसे आप कंसोल ऐप के `Main` मेथड में कॉपी कर सकते हैं। इसमें ऊपर वर्णित सभी चरण शामिल हैं, साथ ही एक छोटा वेरिफिकेशन मैसेज भी है।

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**अपेक्षित आउटपुट**

प्रोग्राम चलाने से `DatabarAspectRatio15.png` नाम की फ़ाइल बनती है जिसमें एक स्पष्ट, चौड़ा स्टैक्ड DataBar बारकोड होता है। जब आप PNG खोलेंगे, तो आपको एक क्षैतिज रूप से विस्तारित बारकोड दिखेगा जो अभी भी GS1 DataBar स्पेसिफिकेशन के अनुरूप है।

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*छवि वैकल्पिक पाठ:* **एक स्टैक्ड DataBar के साथ एस्पेक्ट रेशियो 15 दिखाते हुए बारकोड PNG बनाएं**

### टिप्स और सामान्य समस्याएँ

| स्थिति | सिफारिश |
|-----------|----------------|
| **छवि धुंधली दिख रही है** | `XDimension.Pixels` को 3 px या उससे अधिक बढ़ाएँ, लेकिन कुल इमेज साइज को 500 px से नीचे रखें ताकि बड़े फ़ाइलों से बचा जा सके। |
| **स्कैनर कोड नहीं पढ़ पा रहा है** | डेटा स्ट्रिंग को GS1 फॉर्मेट (`(01)` प्रीफ़िक्स) के अनुसार सत्यापित करें। साथ ही, प्रिंटर रेज़ोल्यूशन कम से कम 300 dpi हो, यह सुनिश्चित करें। |
| **विभिन्न फ़ाइल फ़ॉर्मेट चाहिए** | `BarCodeImageFormat.Png` को `Jpeg`, `Bmp`, या `Gif` से बदलें—API सभी प्रमुख रास्टर फ़ॉर्मेट को सपोर्ट करता है। |
| **वेब एप्लिकेशन में चलाना** | `generator.Save(Stream, BarCodeImageFormat.Png)` का उपयोग करके सीधे HTTP रिस्पॉन्स में लिखें, फ़ाइल सिस्टम को छुए बिना। |

### उदाहरण का विस्तार

* **एक इमेज में कई बारकोड:** अतिरिक्त `BarcodeGenerator` इंस्टैंस बनाएं और उन्हें `Graphics` का उपयोग करके एक ही `Bitmap` पर ड्रॉ करें।  
* **ह्यूमन‑रीडेबल टेक्स्ट जोड़ना:** `generator.Parameters.Caption.Visible = true` सेट करें और फ़ॉन्ट को `generator.Parameters.Caption.Font` के माध्यम से कस्टमाइज़ करें।  
* **डायनामिक एस्पेक्ट रेशियो:** कॉन्फ़िगरेशन फ़ाइल या डेटाबेस से रेशियो वैल्यू प्राप्त करें ताकि बारकोड को ऑन‑द‑फ़्लाई विभिन्न चौड़ाइयों के साथ जेनरेट किया जा सके।

## निष्कर्ष

इस ट्यूटोरियल में आपने C# में **create barcode PNG** करना और स्टैक्ड DataBar ओम्निडायरेक्शनल बारकोड के लिए सटीक **set aspect ratio** 15 सेट करना सीखा। पूर्ण, चलाने योग्य कोड प्रत्येक आवश्यक API कॉल को दर्शाता है, बताता है कि प्रत्येक सेटिंग क्यों महत्वपूर्ण है, और वास्तविक दुनिया में डिप्लॉयमेंट के लिए व्यावहारिक टिप्स प्रदान करता है।  

अगला, आप अन्य बारकोड प्रकारों (जैसे QR Code या Code 128) के लिए **how to set aspect ratio** का पता लगा सकते हैं या जनरेटर को ASP .NET Core सर्विस में इंटीग्रेट कर सकते हैं जो मांग पर बारकोड इमेज रिटर्न करता है। कोडिंग का आनंद लें!

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन करीबी संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर करने में मदद करती हैं।

- [C# और Aspose.Barcode के साथ databar PNG इमेज कैसे बनाएं](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [C# में Aspose.Barcode के साथ databar stacked barcode कैसे बनाएं](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [.NET में databar stacked omnidirectional Aspect Ratio को कस्टमाइज़ करें](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}