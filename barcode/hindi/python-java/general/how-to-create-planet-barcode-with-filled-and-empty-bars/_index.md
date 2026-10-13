---
category: general
date: 2026-09-29
description: Aspose.Barcode का उपयोग करके C# में भरे और खाली बार दोनों के साथ प्लैनेट
  बारकोड बनाएं – चरण‑दर‑चरण गाइड।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: hi
lastmod: 2026-09-29
og_description: C# में जल्दी से प्लैनेट बारकोड बनाएं। सीखें कैसे भरे हुए बार रेंडर
  करें, खाली बार में स्विच करें, और Aspose.Barcode के साथ X‑डायमेंशन को समायोजित करें।
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: भरे और खाली बारों के साथ ग्रह बारकोड बनाएं – C# ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: भरे और खाली बार के साथ ग्रह बारकोड कैसे बनाएं
url: /hi/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# भरे और खाली बार वाले प्लैनेट बारकोड कैसे बनाएं

यदि आपको C# में **planet barcode** छवियां बनानी हैं, तो यह गाइड आपको दिखाएगा कि कैसे भरे‑बार और खाली‑बार दोनों संस्करण उत्पन्न किए जाएँ। आप देखेंगे कि बार की चौड़ाई (X‑dimension) कैसे सेट करें, `FilledBars` प्रॉपर्टी को कैसे टॉगल करें, और परिणामों को PNG फ़ाइलों के रूप में कैसे सहेजें—सभी Aspose.Barcode लाइब्रेरी के साथ।

पोस्टल बारकोड बनाना शिपिंग सिस्टम, मेलिंग‑लिस्ट एप्लिकेशन और लॉजिस्टिक्स डैशबोर्ड के लिए एक सामान्य आवश्यकता है। इस ट्यूटोरियल के अंत तक आपके पास दो तैयार‑उपयोग PNG फ़ाइलें होंगी जिन्हें आप रिपोर्ट, ईमेल या प्रिंट‑आउट में एम्बेड कर सकते हैं।

## Prerequisites

Before you start, make sure you have:

| आवश्यकता | महत्व क्यों है |
|-------------|----------------|
| .NET 6.0 या बाद का | C# उदाहरण के लिए रनटाइम प्रदान करता है। |
| Visual Studio 2022 (या कोई भी C# IDE) | कोड को कंपाइल और रन करने देता है। |
| **Aspose.Barcode for .NET** NuGet पैकेज | `BarcodeGenerator` क्लास और `EncodeTypes.Planet` प्रदान करता है। इसे `dotnet add package Aspose.Barcode` से इंस्टॉल करें। |
| डिस्क पर किसी फ़ोल्डर में लिखने की अनुमति | `Save` मेथड PNG फ़ाइलें आपके निर्दिष्ट पाथ पर लिखता है। |

## चरण 1: प्रोजेक्ट सेट अप करें और नेमस्पेस इम्पोर्ट करें

एक नया कंसोल प्रोजेक्ट बनाएं (या कोड को मौजूदा प्रोजेक्ट में जोड़ें) और Aspose.Barcode नेमस्पेस को रेफ़रेंस करें।

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

ये `using` निर्देश आपको ट्यूटोरियल में आवश्यक `BarcodeGenerator`, `EncodeTypes` और इमेज‑फ़ॉर्मेट एन्‍युम्स तक पहुँच देते हैं।

## चरण 2: डिफ़ॉल्ट (भरे) बार के साथ Planet बारकोड बनाएं

पहला बारकोड लाइब्रेरी के डिफ़ॉल्ट रेंडरिंग का उपयोग करता है, जो बार को भर देता है।

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**क्यों यह काम करता है:**  
`EncodeTypes.Planet` Aspose.Barcode को **Planet** सिम्बोलॉजी उपयोग करने को बताता है, जो United States Postal Service द्वारा उपयोग किया जाने वाला पोस्टल बारकोड है। `XDimension` प्रॉपर्टी प्रत्येक बार की चौड़ाई नियंत्रित करती है; इसे 4 पिक्सेल पर सेट करने से बारकोड मानक लेबल प्रिंटर पर अच्छी तरह प्रिंट होता है। डिफ़ॉल्ट रूप से, `FilledBars` `true` होता है, इसलिए बार ठोस दिखते हैं।

## चरण 3: खाली बार के साथ Planet बारकोड बनाएं

*खाली* बार के साथ वही डेटा जेनरेट करने के लिए, आपको केवल `FilledBars` फ़्लैग को उलटना है जबकि अन्य सेटिंग्स समान रखें।

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**क्यों यह महत्वपूर्ण है:**  
कुछ मेलिंग सिस्टम में **खाली‑बार** शैली की आवश्यकता होती है ताकि बारकोड को गहरे बैकग्राउंड या कंट्रास्टिंग कलर स्कीम पर प्रिंट करने पर पठनीयता बढ़े। `FilledBars = false` सेट करने से जेनरेटर केवल बार की रूपरेखा बनाता है, अंदरूनी भाग पारदर्शी रहता है।

## Expected output

प्रोग्राम चलाने के बाद, फ़ोल्डर `C:\Barcodes` (या आपका चुना हुआ पाथ) दो PNG फ़ाइलें रखता है:

| फ़ाइल | दृश्य विवरण |
|------|---------------------|
| `PlanetFilledBars.png` | बार काले ठोस आयताकार हैं, पृष्ठभूमि सफेद है। |
| `PlanetEmptyBars.png`  | बार काले रूपरेखा हैं; प्रत्येक बार का अंदरूनी भाग पारदर्शी (पृष्ठभूमि दिखाता है)। |

दोनों छवियां समान संख्यात्मक स्ट्रिंग `"123456"` को एन्कोड करती हैं और 4‑पिक्सेल बार चौड़ाई साझा करती हैं, जिससे केवल भराव शैली में अंतर रहता है।

## Common variations and edge cases

### बार की चौड़ाई बदलना

यदि आपका लेबल प्रिंटर अलग बार चौड़ाई की अपेक्षा करता है, तो `XDimension.Pixels` मान को बदलें। हाई‑रेज़ोल्यूशन प्रिंटर के लिए **2** या **3** पिक्सेल बेहतर हो सकते हैं; लो‑रेज़ोल्यूशन प्रिंटर के लिए **5** या **6** पिक्सेल स्कैन विश्वसनीयता बढ़ा सकते हैं।

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### अलग इमेज फ़ॉर्मेट का उपयोग

Aspose.Barcode PNG, JPEG, BMP, GIF, और TIFF को सपोर्ट करता है। अपने वर्कफ़्लो के अनुसार `BarCodeImageFormat.Png` को किसी अन्य एन्‍युम वैल्यू से बदलें।

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### लूप में कई बारकोड जेनरेट करना

जब आपको Planet बारकोड की बैच चाहिए (जैसे मेलिंग लिस्ट के लिए), तो जेनरेटर लॉजिक को `foreach` लूप में रखें और प्रत्येक इटरेशन में डेटा स्ट्रिंग बदलें।

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### अमान्य इनपुट को संभालना

Planet सिम्बोलॉजी केवल **5‑8** अंकों की संख्यात्मक स्ट्रिंग स्वीकार करती है। अमान्य मान देने पर `ArgumentException` फेंका जाता है। एक सरल वैलिडेशन मेथड से इसे रोकें।

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## प्रो टिप: स्कैनर एमुलेटर से बारकोड सत्यापित करें

Aspose.Barcode में `BarcodeReader` क्लास है जिसे आप जेनरेटेड इमेज को मूल डेटा में डिकोड करने के लिए उपयोग कर सकते हैं।

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

यदि आउटपुट दोनों फ़ाइलों के लिए `"123456"` दिखाता है, तो बारकोड सही तरीके से जेनरेट हुआ है।

## निष्कर्ष

अब आप C# में **planet barcode** छवियां दोनों भरे और खाली बार शैली में बनाना, **Planet barcode XDimension** को नियंत्रित करना, और **Aspose.Barcode** लाइब्रेरी का उपयोग करके PNG फ़ॉर्मेट में सहेजना जानते हैं। बार चौड़ाई समायोजित करें, इमेज फ़ॉर्मेट बदलें, या मानों के संग्रह पर लूप चलाएँ ताकि किसी भी पोस्टल‑कोड वर्कफ़्लो में फिट हो सके।

अगले चरण में, आप देख सकते हैं:

* **बारकोड के नीचे मानव‑पठनीय टेक्स्ट जोड़ना** (`barcodeGenerator.Parameters.Caption.Show = true`)।
* **Aspose.PDF के साथ PDF दस्तावेज़ों में बारकोड एम्बेड करना**।
* **अन्य पोस्टल सिम्बोलॉजीज** जैसे **USPS POSTNET** या **Intelligent Mail** जेनरेट करना।

पैरामीटरों के साथ प्रयोग करने और कोड को अपने शिपिंग या मेलिंग सिस्टम में इंटीग्रेट करने में स्वतंत्र महसूस करें। हैप्पी कोडिंग!

## आगे आप क्या सीखें?

- [C# में Planet Barcode बनाएं – पूर्ण चरण‑दर‑चरण गाइड](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [C# में planet barcode बनाएं – पूर्ण प्रोग्रामिंग गाइड](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – Planet barcode और RM4SCC उदाहरण बनाएं](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}