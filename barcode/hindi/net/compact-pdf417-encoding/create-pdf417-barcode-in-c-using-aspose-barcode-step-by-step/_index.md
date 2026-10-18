---
category: general
date: 2026-10-18
description: Aspose.BarCode के साथ C# में PDF417 बारकोड बनाना सीखें। यह ट्यूटोरियल
  बेसिक, कॉम्पैक्ट, मैक्रो और माइक्रो PDF417 जेनरेशन को पूर्ण कोड के साथ कवर करता
  है।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: hi
lastmod: 2026-10-18
og_description: Aspose.BarCode के साथ C# में PDF417 बारकोड बनाएं। इस गाइड का पालन
  करके बुनियादी, कॉम्पैक्ट, मैक्रो और माइक्रो PDF417 बारकोड चरण‑दर‑चरण उत्पन्न करें।
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: C# में PDF417 बारकोड बनाएं – पूर्ण Aspose.BarCode ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Aspose.BarCode का उपयोग करके C# में PDF417 बारकोड बनाएं – चरण‑दर‑चरण मार्गदर्शिका
url: /hi/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में Aspose.BarCode का उपयोग करके PDF417 बारकोड बनाएं – चरण‑दर‑चरण गाइड

यदि आपको .NET एप्लिकेशन में **PDF417 बारकोड बनाना** है, तो यह ट्यूटोरियल आपको पूरी प्रक्रिया से गुज़राता है। आप देखेंगे कि बेसिक बारकोड कैसे जेनरेट करें, कॉम्पैक्ट मोड सक्षम करें, मैक्रो मेटाडेटा जोड़ें, और माइक्रो वैरिएंट बनाएं—सभी स्पष्ट व्याख्याओं और चलाने योग्य कोड के साथ।

PDF417 बारकोड का निर्माण लॉजिस्टिक्स, टिकटिंग और दस्तावेज़ प्रबंधन में आम है। इस गाइड के अंत तक आप किसी भी C# प्रोजेक्ट में बाहरी टूल्स के बिना बारकोड निर्माण को एकीकृत कर पाएँगे।

## आवश्यकताएँ

* .NET 6.0 या बाद का (कोड .NET Framework 4.7+ के साथ भी काम करता है)
* Visual Studio 2022 या कोई भी C# IDE
* **Aspose.BarCode for .NET** NuGet पैकेज  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* उस फ़ोल्डर में लिखने की अनुमति जहाँ उत्पन्न PNG फ़ाइलें सहेजी जाएँगी

कोई अतिरिक्त कॉन्फ़िगरेशन आवश्यक नहीं है; लाइब्रेरी सभी लो‑लेवल एन्कोडिंग विवरणों को संभालती है।

## चरण 1: बेसिक PDF417 बारकोड बनाएं

पहला चरण कस्टम आकार और कॉलम काउंट के साथ एक नियमित PDF417 बारकोड स्थापित करता है।

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**इन सेटिंग्स का महत्व**

* `XDimension.Pixels` प्रत्येक बारकोड एलिमेंट के भौतिक आकार को नियंत्रित करता है। मान 2 अधिकांश स्क्रीन और प्रिंटर पर स्पष्ट इमेज देता है।
* `Pdf417.Columns` निर्धारित करता है कि बारकोड में कितने डेटा कॉलम होंगे। कम कॉलम चौड़ाई घटाते हैं; अधिक कॉलम डेटा क्षमता बढ़ाते हैं।

कोड चलाने से `Pdf417Basic.png` बनता है, जो तीन डेटा कॉलम और दाएँ ओर एक पूर्ण मेटाडेटा कॉलम वाला सामान्य PDF417 प्रतीक दिखाता है।

## चरण 2: कॉम्पैक्ट (ट्रंकेटेड) मोड सक्षम करें

कॉम्पैक्ट मोड दाएँ‑हाथ मेटाडेटा कॉलम को हटा देता है, जिससे बारकोड संकरी हो जाती है। यह तब उपयोगी है जब जगह सीमित हो लेकिन डेटा शेष पंक्तियों से पुनर्निर्मित किया जा सके।

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**ट्रंकेट क्यों?**  
जब `Truncate` `true` होता है, तो जेनरेटर वैकल्पिक दाएँ‑हाथ कॉलम को छोड़ देता है जो एरर‑करैक्शन और फ़ाइल‑लेवल मेटाडेटा संग्रहीत करता है। परिणामस्वरूप बारकोड कम कॉलम लेती है जबकि अधिकांश PDF417 रीडर्स द्वारा स्कैन योग्य रहती है।

## चरण 3: फ़ाइल‑स्तर मेटाडेटा के साथ मैक्रो PDF417 बारकोड बनाएं

मैक्रो PDF417 मानक फ़ॉर्मेट को सेगमेंट पहचानकर्ताओं के साथ विस्तारित करता है, जिससे बड़े दस्तावेज़ को कई बारकोड में विभाजित किया जा सकता है। यह लंबी स्ट्रिंग्स या मल्टी‑पेज फ़ाइलों को एन्कोड करने में उपयोगी है।

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**मैक्रो फ़ील्ड्स की व्याख्या**

| प्रॉपर्टी | उद्देश्य |
|----------|----------|
| `MacroPdf417FileID` | पूरी फ़ाइल के लिए अद्वितीय पहचानकर्ता; सभी सेगमेंट इस मान को साझा करते हैं। |
| `MacroPdf417SegmentID` | वर्तमान सेगमेंट का इंडेक्स (1 से शुरू)। |
| `MacroPdf417SegmentsCount` | पूर्ण डेटा सेट बनाने वाले कुल सेगमेंट्स की संख्या। |

एक स्कैनर जो मैक्रो PDF417 को समझता है, सभी सेगमेंट पढ़कर और इन पहचानकर्ताओं का उपयोग करके मूल डेटा को पुनः संयोजित कर सकता है।

## चरण 4: छोटे डेटा के लिए माइक्रो PDF417 बारकोड बनाएं

माइक्रो PDF417 एक कॉम्पैक्ट संस्करण है जो छोटे पेलोड (अधिकतम 90 अक्षर) के लिए डिज़ाइन किया गया है। यह कॉलम रेंज को 1‑4 तक सीमित करता है, जिससे बारकोड छोटे लेबल या सीमित डिस्प्ले क्षेत्र वाले डिवाइसों के लिए उपयुक्त बनता है।

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**कब उपयोग करें माइक्रो PDF417**  
इस वैरिएंट का उपयोग तब करें जब डेटा पेलोड छोटा हो और आपको सबसे छोटा संभव बारकोड चाहिए। यह इन्वेंटरी टैग, एक्सेस कार्ड, या किसी भी स्थिति में आदर्श है जहाँ स्क्रीन स्पेस महंगा हो।

## पूर्ण कार्यशील उदाहरण

नीचे एक स्व-निहित कंसोल एप्लिकेशन है जो एक ही रन में चारों बारकोड प्रकार उत्पन्न करता है। कोड को नए C# प्रोजेक्ट में कॉपी करें, `YOUR_DIRECTORY` को मौजूदा फ़ोल्डर पाथ से बदलें, और चलाएँ।

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**अपेक्षित आउटपुट**

प्रोग्राम चलाने से निर्दिष्ट फ़ोल्डर में चार PNG फ़ाइलें बनती हैं:

* `Pdf417Basic.png` – तीन कॉलम वाला मानक बारकोड
* `CompactPdf417.png` – वही डेटा, ट्रंकेटेड दाएँ‑हाथ कॉलम
* `MacroPdf417.png` – सेगमेंट मेटाडेटा वाला मैक्रो बारकोड
* `MicroPdf417.png` – छोटे स्ट्रिंग्स के लिए कॉम्पैक्ट माइक्रो बारकोड

किसी भी इमेज व्यूअर से इमेज खोलें; आपको अलग‑अलग PDF417 पैटर्न दिखेंगे। इन्हें मोबाइल बारकोड रीडर (जैसे ZXing, Scandit) से स्कैन करने पर मूल टेक्स्ट स्ट्रिंग्स मिलेंगी।

## सामान्य प्रश्न और टिप्स

* **बारकोड धुंधला दिखे तो क्या करें?**  
  `XDimension.Pixels` को 3 या 4 तक बढ़ाएँ। बड़े मॉड्यूल साइज उच्च‑रिज़ॉल्यूशन इमेज बनाते हैं, लेकिन फ़ाइल आकार बड़ा हो जाता है।

* **क्या मैं PNG के बजाय SVG आउटपुट कर सकता हूँ?**  
  हाँ। `Save` कॉल्स में `BarCodeImageFormat.Png` को `BarCodeImageFormat.Svg` से बदल दें।

* **क्या मुझे एरर‑करैक्शन लेवल मैन्युअली सेट करना पड़ेगा?**  
  Aspose.BarCode स्वचालित रूप से एक अनुकूल लेवल चुनता है। विशेष उपयोग‑केस के लिए आप `Pdf417.ErrorCorrectionLevel` को समायोजित कर सकते हैं।

* **बारकोड को PDF दस्तावेज़ में कैसे एम्बेड करें?**  
  `Aspose.Pdf` का उपयोग करके उत्पन्न PNG या SVG को PDF पेज पर इमेज एलिमेंट के रूप में जोड़ें।

* **क्या लाइब्रेरी थ्रेड‑सेफ़ है?**  
  प्रत्येक `BarcodeGenerator` इंस्टेंस स्वतंत्र है; आप कई थ्रेड्स पर बिना साझा स्थिति के जेनरेटर बना सकते हैं।

## निष्कर्ष

अब आप Aspose.BarCode का उपयोग करके C# में **PDF417 बारकोड बनाना** जानते हैं, जिसमें बेसिक, कॉम्पैक्ट, मैक्रो और माइक्रो वैरिएंट शामिल हैं।

## अब आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच का पता लगा सकें।

- [C# में pdf417 बारकोड कैसे बनाएं – चरण‑दर‑चरण गाइड](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [C# में कॉम्पैक्ट मोड के साथ PDF417 बारकोड कैसे बनाएं](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [C# में Aspose.BarCode का उपयोग करके मैक्रो PDF417 बारकोड कैसे बनाएं](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}