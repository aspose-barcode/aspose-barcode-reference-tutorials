---
category: general
date: 2026-09-13
description: C# में बारकोड बनाना सीखें, बारकोड का आकार कस्टमाइज़ करें, और Aspose.BarCode
  का उपयोग करके बारकोड इमेज को PNG के रूप में सहेजें। पूर्ण चरण‑दर‑चरण गाइड।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: hi
lastmod: 2026-09-13
og_description: C# में कस्टम बारकोड आकार के साथ बारकोड कैसे जेनरेट करें और बारकोड
  इमेज को PNG के रूप में सेव करें। Aspose.BarCode के लिए इस पूर्ण गाइड का पालन करें।
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: C# में बारकोड कैसे जनरेट करें, कस्टम आकार सेट करें, और इमेज सहेजें
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: C# में बारकोड सेट को कस्टम आकार में जेनरेट कैसे करें और इमेज सहेजें
url: /hi/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में बारकोड सेट कस्टम साइज कैसे जेनरेट करें और इमेज सहेजें

यदि आपको .NET एप्लिकेशन में **बारकोड जेनरेट करने का तरीका** चाहिए, तो यह ट्यूटोरियल आपको एक पूर्ण समाधान दिखाता है। आप देखेंगे कि कैसे **कस्टम बारकोड साइज** को समायोजित किया जाए और **बारकोड इमेज** फ़ाइलों को कुछ ही C# कोड लाइनों से सहेजा जाए।

बारकोड जेनरेट करना इन्वेंटरी सिस्टम, शिपिंग लेबल और पॉइंट‑ऑफ़‑सेल एप्लिकेशन के लिए एक सामान्य आवश्यकता है। इस गाइड के अंत तक आपके पास एक चलाने योग्य प्रोग्राम होगा जो दो DataBar‑Stacked‑Omnidirectional बारकोड बनाता है, प्रत्येक का अलग aspect ratio होता है, और उन्हें डिस्क पर PNG फ़ाइलों के रूप में लिखता है।

**आवश्यकताएँ**

- .NET 6.0 या बाद का (कोड .NET Framework 4.7+ के साथ भी काम करता है)
- Visual Studio 2022 या कोई भी C# IDE
- Aspose.BarCode for .NET (फ्री ट्रायल या लाइसेंस्ड NuGet पैकेज)

---

## Aspose.BarCode के साथ बारकोड कैसे जेनरेट करें

Aspose.BarCode लाइब्रेरी बारकोड मानकों के लो‑लेवल विवरणों को एब्स्ट्रैक्ट करती है, जिससे आप उस डेटा पर ध्यान केंद्रित कर सकते हैं जिसे आप एन्कोड करना चाहते हैं और आवश्यक विज़ुअल अपीयरेंस पर।

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### प्रत्येक पंक्ति क्यों महत्वपूर्ण है

| चरण | व्याख्या |
|------|-------------|
| **1️⃣ जेनरेटर बनाएं** | `EncodeTypes.DatabarStackedOmniDirectional` enum Aspose को बताता है कि कौन सा बारकोड सिम्बोलॉजी उपयोग करना है। स्ट्रिंग `"(01)12345678901231"` GS1‑128 डेटा फ़ॉर्मेट का पालन करती है, जहाँ `(01)` GTIN के लिए Application Identifier है। |
| **2️⃣ X‑dimension सेट करें** | `XDimension.Pixels` एक सिंगल बारकोड मॉड्यूल (सबसे छोटा बार) की चौड़ाई को परिभाषित करता है। इस मान को बदलना **कस्टम बारकोड साइज** प्राप्त करने का मुख्य तरीका है, बिना एन्कोडेड डेटा को बदले। |
| **3️⃣ aspect ratio सेट करें और सहेजें** | `DataBar.AspectRatio` DataBar सिंबल्स के height‑to‑width ratio को नियंत्रित करता है। 15 का aspect ratio अपेक्षाकृत छोटा, चौड़ा बारकोड बनाता है, जबकि 30 इसे लंबा बनाता है। `Save` विज़ुअल प्रतिनिधित्व को PNG फ़ाइल में लिखता है, जिससे **बारकोड इमेज सहेजें** की आवश्यकता पूरी होती है। |
| **4️⃣ aspect ratio बदलें और फिर से सहेजें** | एक ही जेनरेटर इंस्टेंस को पुनः उपयोग करने से आप विभिन्न विज़ुअल विशेषताओं वाले कई इमेज बना सकते हैं, जबकि डेटा स्थिर रहता है। |

---

## X‑dimension से आगे कस्टम बारकोड साइज को समायोजित करना

`XDimension.Pixels` मॉड्यूल की चौड़ाई सेट करता है, आप दो प्रॉपर्टीज़ को मिलाकर बारकोड के कुल आयामों को भी फाइन‑ट्यून कर सकते हैं:

1. **`BarHeight`** – पिक्सेल में स्पष्ट ऊँचाई।  
2. **`BarWidth`** – पिक्सेल में स्पष्ट चौड़ाई (X‑dimension को ओवरराइड करता है)।

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** बारकोड प्रिंट करते समय हमेशा जेनरेटेड इमेज को अंतिम प्रिंट साइज पर टेस्ट करें। 2 px की मॉड्यूल चौड़ाई स्क्रीन पर दिखाने के लिए काम करती है, लेकिन प्रिंटेड लेबल्स को स्कैन योग्य रहने के लिए अक्सर कम से कम 4 px चाहिए।

---

## बारकोड इमेज सहेजने के लिए सही इमेज फ़ॉर्मेट चुनना

Aspose.BarCode PNG, JPEG, BMP, GIF, और TIFF को सपोर्ट करता है। PNG लॉसलेस है और तेज़ किनारों को बनाए रखता है, जिससे यह अधिकांश एप्लिकेशन के लिए सबसे सुरक्षित विकल्प बनता है। यदि आपको वेब उपयोग के लिए छोटी फ़ाइल चाहिए, तो 90 क्वालिटी सेटिंग वाला JPEG अच्छा काम करता है, लेकिन ध्यान रखें कि कम्प्रेशन आर्टिफैक्ट्स स्कैन विश्वसनीयता को प्रभावित कर सकते हैं।

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## पूर्ण, चलाने योग्य उदाहरण

नीचे एक स्व-निहित कंसोल एप्लिकेशन है जिसे आप कॉपी, पेस्ट और रन कर सकते हैं। यह **बारकोड जेनरेट करने का तरीका**, **कस्टम बारकोड साइज** को संशोधित करना, और दो अलग-अलग फ़ॉर्मेट में **बारकोड इमेज सहेजना** दर्शाता है।

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**कंसोल पर अपेक्षित आउटपुट**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

चार इमेज फ़ाइलें प्रोग्राम में दिखाई देंगी

## अब आप आगे क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑बद्ध व्याख्याएँ शामिल हैं, जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करेंगे।

- [Aspose.BarCode for .NET का उपयोग करके DataMatrix बारकोड कैसे जेनरेट करें – चरण‑बद्ध गाइड](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose के साथ PDF417 बारकोड कैसे जेनरेट करें – पूर्ण गाइड](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Aspose.BarCode for .NET का उपयोग करके कस्टम aspect ratio के साथ Aztec बारकोड कैसे जेनरेट करें](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}