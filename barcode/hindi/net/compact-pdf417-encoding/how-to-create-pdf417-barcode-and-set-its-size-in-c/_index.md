---
category: general
date: 2026-09-22
description: C# में PDF417 बारकोड बनाना सीखें, बारकोड का आकार सेट करें, और स्पष्ट
  चरण‑दर‑चरण कोड उदाहरणों के साथ बारकोड इमेज फ़ाइलें जनरेट करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: hi
lastmod: 2026-09-22
og_description: C# में तेज़ी से PDF417 बारकोड बनाएं। यह ट्यूटोरियल दिखाता है कि बारकोड
  का आकार कैसे सेट करें, कॉम्पैक्ट मोड कैसे सक्षम करें, और किसी भी .NET प्रोजेक्ट
  के लिए PNG इमेज कैसे आउटपुट करें।
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: C# में PDF417 बारकोड बनाएं – चरण-दर-चरण मार्गदर्शिका
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: C# में PDF417 बारकोड कैसे बनाएं और उसका आकार सेट करें
url: /hi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में PDF417 बारकोड कैसे बनाएं और उसका आकार सेट करें

यदि आपको C# में **PDF417 बारकोड बनाना** है, तो यह गाइड आपको बारकोड उत्पन्न करने, उसके आयाम नियंत्रित करने, और परिणाम को इमेज फ़ाइल के रूप में सहेजने का तरीका दिखाता है। चाहे आप टिकटिंग सिस्टम, लॉजिस्टिक्स लेबल, या सुरक्षित क्रेडेंशियल बना रहे हों, PDF417 फ़ॉर्मेट में बड़ी मात्रा में डेटा को कॉम्पैक्ट विज़ुअल रूप में एन्कोड करना सीखना आपके लिए फायदेमंद होगा।

इस ट्यूटोरियल में आप सीखेंगे:

* **Aspose.BarCode (या कोई संगत) लाइब्रेरी** का उपयोग करके **PDF417 बारकोड बनाना**।  
* **X‑डायमेंशन और कॉलम काउंट** को समायोजित करके **बारकोड का आकार सेट करना**।  
* C# में **बारकोड इमेज** को PNG, JPEG, या BMP आउटपुट के लिए जनरेट करना।  

उदाहरण में Aspose.BarCode for .NET का फ्री कम्युनिटी एडीशन उपयोग किया गया है, लेकिन समान अवधारणाएँ अन्य लाइब्रेरियों पर भी लागू होती हैं जो समान प्रॉपर्टीज़ प्रदान करती हैं।

## आवश्यकताएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* .NET 6.0 SDK या बाद का संस्करण स्थापित हो।  
* एक C# IDE (Visual Studio, Visual Studio Code, Rider, आदि)।  
* `Aspose.BarCode` NuGet पैकेज (`dotnet add package Aspose.BarCode`)।  

कोई अतिरिक्त कॉन्फ़िगरेशन आवश्यक नहीं है; लाइब्रेरी Windows, Linux, और macOS पर काम करती है।

## चरण 1: बेसिक PDF417 बारकोड बनाएं और उसका आकार सेट करें

पहला कदम `BarcodeGenerator` को `EncodeTypes.Pdf417` एन्नम के साथ इंस्टैंशिएट करना है और वह टेक्स्ट प्रदान करना है जिसे आप एन्कोड करना चाहते हैं। फिर **X‑डायमेंशन** (मॉड्यूल चौड़ाई) और **कॉलम** की संख्या को समायोजित करके कुल आकार नियंत्रित करें।

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**इन सेटिंग्स का महत्व**

* `XDimension.Pixels` सबसे पतली बार की चौड़ाई निर्धारित करता है। छोटे मान बारकोड को अधिक कॉम्पैक्ट बनाते हैं, जबकि बड़े मान कम‑रिज़ॉल्यूशन स्कैनर पर पठनीयता बढ़ाते हैं।  
* `Pdf417.Columns` बारकोड के आस्पेक्ट रेशियो को प्रभावित करता है। कम कॉलम बारकोड को लंबा बनाते हैं; अधिक कॉलम इसे चपटा कर देते हैं। कॉलम को समायोजित करना **बारकोड आकार सेट करने** का मुख्य तरीका है, बिना एन्कोडेड डेटा बदले।

कोड चलाने के बाद, निर्दिष्ट फ़ोल्डर में `Pdf417Basic.png` मिलेगा। इमेज नीचे दिखाए गए स्क्रीनशॉट जैसी होगी:

<img src="images/pdf417-basic.png" alt="बेसिक बारकोड लेआउट दिखाने वाला PDF417 बारकोड उदाहरण">

## चरण 2: समान आकार के साथ कॉम्पैक्ट PDF417 बारकोड (ट्रंकेट मोड) बनाएं

कभी‑कभी सीमित स्थान के कारण आपको छोटा बारकोड चाहिए होता है। PDF417 एक *ट्रंकेट* (कॉम्पैक्ट) मोड प्रदान करता है जो स्टॉप पैटर्न को हटाकर कुल ऊँचाई घटा देता है। इस व्यवहार को `Truncate` प्रॉपर्टी टॉगल करती है।

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true` होने पर क्या बदलता है?**

* बारकोड ऊँचाई में लगभग 15‑20 % तक छोटा हो जाता है, जो छोटे लेबल या मोबाइल स्क्रीन के लिए उपयोगी है।  
* डेटा पूरी तरह से पुनर्प्राप्त योग्य रहता है; अधिकांश आधुनिक स्कैनर ट्रंकेट मोड को स्वचालित रूप से समझते हैं।

परिणामी `CompactPdf417.png` बेसिक बारकोड का एक पतला संस्करण दिखाएगा।

## चरण 3: माइक्रो PDF417 बारकोड बनाएं, कॉलम समायोजित करें, और सहेजें

Micro PDF417 एक नया, हाई‑डेंसिटी वैरिएंट है जो बहुत छोटे स्थानों (जैसे ID कार्ड) के लिए डिज़ाइन किया गया है। यह केवल 1‑4 कॉलम का समर्थन करता है, और लाइब्रेरी आकार नियंत्रण के लिए वही `XDimension` प्रॉपर्टी प्रदान करती है।

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Micro PDF417 के मुख्य बिंदु**

* `EncodeTypes.MicroPdf417` एन्नम स्वचालित रूप से माइक्रो वैरिएंट चुनता है।  
* चूँकि सिम्बॉल अधिक घना है, बारकोड को पठनीय रखने के लिए आपको 300 dpi या उससे अधिक का प्रिंटर चाहिए हो सकता है।  
* कॉलम काउंट समायोजित करना उपलब्ध एकमात्र आकार नियंत्रण है; लाइब्रेरी अभी भी `XDimension` का सम्मान करती है।

## विभिन्न आउटपुट फ़ॉर्मेट्स के लिए बारकोड आकार कैसे सेट करें

ऊपर के उदाहरण PNG का उपयोग करते हैं, लेकिन वही `Save` मेथड JPEG, BMP, या TIFF के साथ भी काम करता है। यदि आपको विशिष्ट इमेज आयाम चाहिए (जैसे 300 × 150 px), तो `XDimension` को `ResolutionX`/ `ResolutionY` के साथ मिलाएँ:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

`ImageResolution` को बढ़ाते हुए `XDimension` को स्केल करने से हाई‑रिज़ॉल्यूशन प्रिंट पर विज़ुअल क्वालिटी बनी रहती है।

## सामान्य समस्याएँ और प्रो टिप्स

| समस्या | क्यों होता है | समाधान |
|--------|--------------|--------|
| स्क्रीन पर बारकोड धुंधला दिखता है | कम DPI के साथ छोटा `XDimension` | `ImageResolution` और/या `XDimension.Pixels` बढ़ाएँ |
| स्कैनर ट्रंकेट मोड नहीं पढ़ पाता | पुराने स्कैनर फ़र्मवेयर में समर्थन नहीं | लेगेसी हार्डवेयर के लिए पूर्ण (नॉन‑ट्रंकेट) मोड उपयोग करें |
| Micro PDF417 पढ़ा नहीं जा रहा | 300 dpi से कम पर प्रिंट किया या कंट्रास्ट पर्याप्त नहीं | मैट पेपर पर 300 dpi या उससे अधिक पर प्रिंट करें, डार्क फ़ोरग्राउंड सुनिश्चित करें |
| आउटपुट फ़ाइल करप्ट है | टार्गेट फ़ोल्डर में लिखने की अनुमति नहीं | `YOUR_DIRECTORY` मौजूद है और लिखने योग्य है, यह जांचें |

**प्रो टिप:** जब आपको आगे की प्रोसेसिंग (जैसे PDFs में एम्बेड) के लिए लॉसलेस क्वालिटी चाहिए, तो हमेशा PNG के रूप में बारकोड जनरेट करें। PNG सटीक पिक्सेल वैल्यू रखता है, जबकि JPEG में कम्प्रेशन आर्टिफैक्ट्स आ सकते हैं जो बारकोड की पठनीयता को प्रभावित कर सकते हैं।

## पूर्ण, चलाने योग्य उदाहरण

नीचे एक पूरा कंसोल एप्लिकेशन है जो एक ही रन में तीनों बारकोड प्रकार दर्शाता है। कोड को नए .NET कंसोल प्रोजेक्ट में कॉपी करें और चलाएँ।

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**अपेक्षित आउटपुट**

प्रोग्राम चलाने पर `Barcodes` फ़ोल्डर के अंदर तीन PNG फ़ाइलें बनेंगी:

* `Pdf417Basic.png` – तीन कॉलम वाला मानक PDF417 बारकोड।  
* `CompactPdf417.png` – वही डेटा ट्रंकेट (कॉम्पैक्ट) मोड में, थोड़ा छोटा।  
* `MicroPdf417.png` – चार कॉलम वाला हाई‑डेंसिटी Micro PDF417 वैरिएंट।

किसी भी इमेज व्यूअर से इमेज खोलें; आपको स्टैक्ड बारकोड का विशिष्ट रूप दिखना चाहिए।

## आगे आप क्या सीखें?

नीचे दिए गए ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ हैं, जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोचेज़ को एक्सप्लोर करने में मदद करेंगे।

- [Aspose.BarCode के साथ कॉम्पैक्ट PDF417 कैसे बनाएं](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [PDF417 बारकोड में एरर लेवल कैसे सेट करें – पूर्ण गाइड](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [C# में PDF417 बारकोड मेटाडाटा बनाएं – पूर्ण चरण‑दर‑चरण गाइड](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}