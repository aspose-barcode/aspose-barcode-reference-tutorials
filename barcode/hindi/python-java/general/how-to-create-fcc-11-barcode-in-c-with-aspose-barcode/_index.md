---
category: general
date: 2026-08-22
description: Aspose.BarCode का उपयोग करके C# में FCC 11 बारकोड बनाएं। चरण‑दर‑चरण कोड
  सीखें, आयाम कॉन्फ़िगर करें, और ऑस्ट्रेलिया पोस्ट के लिए PNG छवियां उत्पन्न करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: hi
lastmod: 2026-08-22
og_description: Aspose.BarCode के साथ C# में FCC 11 बारकोड बनाएं। ऑस्ट्रेलिया पोस्ट
  के लिए PNG बारकोड उत्पन्न करने हेतु इस संक्षिप्त ट्यूटोरियल का पालन करें, जिसमें
  FCC 59 और FCC 62 वैरिएंट शामिल हैं।
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: C# में FCC 11 बारकोड बनाएं – पूर्ण Aspose.BarCode गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: C# में Aspose.BarCode के साथ FCC 11 बारकोड कैसे बनाएं
url: /hi/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में Aspose.BarCode के साथ FCC 11 बारकोड कैसे बनाएं

यदि आपको .NET एप्लिकेशन में **FCC 11 बारकोड बनाना** है, तो यह गाइड आपको आवश्यक सटीक कोड दिखाता है। आप देखेंगे कि बारकोड के आयाम कैसे कॉन्फ़िगर करें, उचित एन्कोडिंग टेबल चुनें, और परिणाम को PNG फ़ाइल के रूप में सहेजें।

ऑस्ट्रेलिया पोस्ट बारकोड बनाना लॉजिस्टिक्स, मेलिंग सिस्टम और इन्वेंटरी ट्रैकिंग के लिए एक सामान्य आवश्यकता है। यह ट्यूटोरियल FCC 11 फ़ॉर्मेट को कवर करता है और यह भी दर्शाता है कि विभिन्न एन्कोडिंग टेबल्स के साथ FCC 59 और FCC 62 बारकोड कैसे बनाएं, ताकि आप उसी पैटर्न को अन्य पोस्टल सेवाओं के लिए पुन: उपयोग कर सकें।

## आपको क्या चाहिए

* .NET 6.0 SDK या बाद का संस्करण स्थापित हो  
* Visual Studio 2022 (या कोई भी C#‑compatible IDE)  
* **Aspose.BarCode for .NET** का वैध लाइसेंस – कम्युनिटी एडिशन मूल्यांकन के लिए काम करता है  
* उस फ़ोल्डर में लिखने की अनुमति जहाँ PNG फ़ाइलें सहेजी जाएँगी  

ये पूर्वापेक्षाएँ सुनिश्चित करती हैं कि कोड बिना अतिरिक्त कॉन्फ़िगरेशन के संकलित और चलाया जा सके।

## चरण 1: Aspose.BarCode NuGet पैकेज स्थापित करें

प्रोजेक्ट फ़ोल्डर में एक टर्मिनल खोलें और चलाएँ:

```bash
dotnet add package Aspose.BarCode
```

## चरण 2: आउटपुट फ़ोल्डर निर्धारित करें

एक फ़ोल्डर बनाएँ जहाँ उत्पन्न छवियों को संग्रहीत किया जाएगा। पथ पूर्ण (absolute) या executable के सापेक्ष (relative) हो सकता है।

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` फ़ोल्डर की मौजूदगी सुनिश्चित करता है, जिससे `Save` मेथड द्वारा फ़ाइल लिखते समय रन‑टाइम त्रुटियों से बचा जा सके।

## चरण 3: FCC 11 बारकोड उत्पन्न करें

FCC 11 फ़ॉर्मेट ऑस्ट्रेलिया पोस्ट के पोस्टल बारकोड के लिए डिफ़ॉल्ट एन्कोडिंग है। नीचे दिया गया कोड एक बारकोड बनाता है जो संख्यात्मक स्ट्रिंग `1101234567` को एन्कोड करता है।

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**क्यों यह काम करता है:**  
* `EncodeTypes.AustraliaPost` लाइब्रेरी को ऑस्ट्रेलिया पोस्ट एन्कोडिंग नियम लागू करने के लिए बताता है।  
* डेटा स्ट्रिंग `1101234567` FCC 11 विनिर्देश का पालन करती है: पहले दो अंक (`11`) फ़ॉर्मेट को पहचानते हैं, उसके बाद 7‑अंकीय ग्राहक संदर्भ आता है।  
* `XDimension` और `BarHeight` प्रिंटेड बारकोड के आकार को नियंत्रित करते हैं, जो स्कैनर की पठनीयता के लिए महत्वपूर्ण है।  

प्रोग्राम चलाने के बाद, आपको `Barcodes` फ़ोल्डर में `PostalAustraliaPostFCC11.png` मिलेगा। छवि इस प्रकार दिखती है:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## चरण 4: अतिरिक्त ऑस्ट्रेलिया पोस्ट बारकोड बनाएं (वैकल्पिक)

जबकि मुख्य लक्ष्य **FCC 11 बारकोड बनाना** है, विभिन्न मेल क्लासों के लिए अक्सर आपको FCC 59 या FCC 62 बारकोड की आवश्यकता होती है। नीचे दिया गया कोड वही `BarcodeGenerator` इंस्टेंस पुनः उपयोग करता है, केवल डेटा स्ट्रिंग और वैकल्पिक एन्कोडिंग टेबल को बदलता है।

### 4.1 N‑Table एन्कोडिंग के साथ FCC 59

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 N‑Table एन्कोडिंग के साथ FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 C‑Table एन्कोडिंग के साथ FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 अन्य एन्कोडिंग के साथ FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

सभी चार छवियों को एक ही फ़ोल्डर में साइड‑बाय‑साइड सहेजा जाता है, जिससे दृश्य अंतर की तुलना आसान हो जाती है।

## चरण 5: एन्कोडिंग टेबल्स को समझें

ऑस्ट्रेलिया पोस्ट तीन एन्कोडिंग टेबल्स परिभाषित करता है:

* **N‑Table** – संख्यात्मक ग्राहक जानकारी को व्याख्या करता है। जब पेलोड में केवल अंक हों तो इसका उपयोग करें।  
* **C‑Table** – अल्फ़ान्यूमेरिक अक्षरों का समर्थन करता है, उन रेफ़रेंस नंबरों के लिए उपयोगी है जिनमें अक्षर भी होते हैं।  
* **Other** – कस्टम या विस्तारित डेटा फ़ॉर्मेट के लिए एक फॉलबैक।  

सही टेबल चुनने से यह सुनिश्चित होता है कि बारकोड स्कैनर जानकारी को ठीक उसी तरह डिकोड करे जैसा इच्छित है। यदि आप `AustralianPostEncodingTable` प्रॉपर्टी को छोड़ देते हैं, तो लाइब्रेरी डिफ़ॉल्ट रूप से N‑Table का उपयोग करती है, जिससे गैर‑संख्यात्मक अक्षर कट सकते हैं।

## टिप्स, किनारे के मामले, और सामान्य कठिनाइयाँ

| स्थिति | अनुशंसित उपाय |
|-----------|----------------------|
| डेटा स्ट्रिंग की लंबाई आवश्यक से छोटी है | FCC विनिर्देश को पूरा करने के लिए संख्यात्मक भाग को अग्रणी शून्य (leading zeros) से पैड करें। |
| बारकोड प्रिंट करने पर धुंधला दिखता है | `XDimension` को 5 या 6 पिक्सेल तक बढ़ाएँ और प्रिंटर की DPI सेटिंग्स की जाँच करें। |
| स्कैनर “अमान्य फ़ॉर्मेट” लौटाता है | सुनिश्चित करें कि सही एन्कोडिंग टेबल (N‑Table, C‑Table, Other) डेटा पेलोड से मेल खाती है। |
| Linux पर बिना GUI के चलाना | `System.Drawing.Common` पैकेज का संदर्भ सुनिश्चित करें, या `Save` मेथड को `BarCodeImageFormat.Png` के साथ उपयोग करें जो डिस्प्ले कॉन्टेक्स्ट की आवश्यकता नहीं रखता। |
| विभिन्न इमेज फ़ॉर्मेट की आवश्यकता | आवश्यकतानुसार `BarCodeImageFormat.Png` को `BarCodeImageFormat.Jpeg` या `BarCodeImageFormat.Tiff` से बदलें। |

ये व्यावहारिक टिप्स पोस्टल बारकोड समाधान के वास्तविक उपयोग मामलों से निकली हैं।

## पूर्ण चलाने योग्य उदाहरण

नीचे एक स्व-निहित प्रोग्राम दिया गया है जिसे आप नई कंसोल प्रोजेक्ट (`dotnet new console`) में कॉपी कर सकते हैं और बिना किसी संशोधन के चला सकते हैं।



## अब आपको क्या सीखना चाहिए?

निम्नलिखित ट्यूटोरियल्स उन निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण-दर-चरण व्याख्याएँ शामिल हैं, जो आपको अतिरिक्त API सुविधाओं में निपुण बनने और अपने प्रोजेक्ट्स में वैकल्पिक कार्यान्वयन दृष्टिकोणों का अन्वेषण करने में मदद करती हैं।

- [जावा में बारकोड कैसे जनरेट करें – ऑस्ट्रेलिया पोस्ट बारकोड Aspose के साथ](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Aspose.BarCode के साथ एक-आयामी डेटाबार GS1 एन्कोडिंग बनाएं](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Aspose.BarCode का उपयोग करके .NET में Code 16K के लिए बारकोड क्वाइट ज़ोन कैसे बनाएं](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}