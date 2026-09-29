---
category: general
date: 2026-09-29
description: Aspose.BarCode के साथ C# में ओम्निडायरेक्शनल डेटाबार बारकोड बनाना सीखें।
  X‑डायमेंशन को समायोजित करें, अनुपात सेट करें, और PNG इमेजेस को सहेजें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: hi
lastmod: 2026-09-29
og_description: Aspose.BarCode का उपयोग करके C# में ओम्निडायरेक्शनल डेटाबार बारकोड
  बनाएं। X‑डायमेंशन सेट करना, एस्पेक्ट रेशियो समायोजित करना और PNG फ़ाइलें निर्यात
  करना सीखें।
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: C# में ओम्निडायरेक्शनल डेटाबार बारकोड बनाएं – चरण‑दर‑चरण गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: C# में ओम्निडायरेक्शनल डेटाबार बारकोड कैसे बनाएं
url: /hi/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में omnidirectional Databar बारकोड कैसे बनाएं

यदि आपको .NET एप्लिकेशन में **create omnidirectional Databar barcode** बनाना है, तो यह गाइड आपको सटीक चरण दिखाता है। आप देखेंगे कि DataBar stacked omnidirectional बारकोड को कैसे initialise करें, उसका X‑dimension कॉन्फ़िगर करें, aspect ratio बदलें, और Aspose.BarCode के साथ PNG इमेजेज़ जेनरेट करें।

Retail स्कैनर्स के लिए प्रोडक्ट आइडेंटिफ़ायर्स एन्कोड करने की आवश्यकता होने पर **DataBar stacked omnidirectional barcode** बनाना सामान्य है। इस ट्यूटोरियल में आप सीखेंगे कि **set barcode aspect ratio** सेट करें, मॉड्यूल साइज को नियंत्रित करें, और IDE छोड़े बिना परिणाम को एक्सपोर्ट करें।

## आवश्यकताएँ

- .NET 6.0 या बाद का संस्करण स्थापित हो
- Visual Studio 2022 (या कोई भी C#‑compatible IDE)
- **Aspose.BarCode for .NET** NuGet पैकेज (version 23.12 या नया)

आप पैकेज को NuGet Package Manager के माध्यम से जोड़ सकते हैं:

```bash
dotnet add package Aspose.BarCode
```

## चरण 1: omnidirectional Databar बारकोड को initialise करें

पहला चरण है `BarcodeGenerator` इंस्टेंस बनाना जो **DataBar stacked omnidirectional** सिम्बोलॉजी को टार्गेट करता है। कंस्ट्रक्टर एन्कोड टाइप और डेटा स्ट्रिंग लेता है।

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Why this matters:** `EncodeTypes.DatabarStackedOmniDirectional` वैल्यू Aspose.BarCode को यह बताती है कि वह विशिष्ट omnirectional Databar फॉर्मेट रेंडर करे, जो दोनों दिशाओं में स्कैनिंग के लिए आवश्यक है।

## चरण 2: X‑dimension (मॉड्यूल साइज) निर्धारित करें

X‑dimension एक सिंगल बारकोड मॉड्यूल की चौड़ाई को पिक्सेल में नियंत्रित करता है। `2` पिक्सेल का मान ऑन‑स्क्रीन रेंडरिंग और अधिकांश प्रिंटर्स के लिए उपयुक्त है।

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** एक सुसंगत X‑dimension यह सुनिश्चित करता है कि बारकोड रिटेल स्कैनर्स के न्यूनतम आकार स्पेसिफिकेशन को पूरा करे और इमेज फ़ाइल साइज को प्रबंधनीय रखे।

## चरण 3: पहला aspect ratio सेट करें और इमेज सेव करें

**aspect ratio** DataBar की ऊँचाई‑से‑चौड़ाई संबंध निर्धारित करता है। `15` का aspect ratio एक कॉम्पैक्ट, लंबा बारकोड देता है जो संकरी लेबल स्पेस के लिए आदर्श है।

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Why this matters:** aspect ratio को एडजस्ट करने से आप बारकोड को विभिन्न लेबल लेआउट में फिट कर सकते हैं बिना पठनीयता घटाए। सेव किया गया PNG किसी भी इमेज व्यूअर में देखा जा सकता है।

## चरण 4: aspect ratio बदलें और दूसरी इमेज जेनरेट करें

कभी-कभी एक चौड़ा बारकोड आवश्यक होता है—उदाहरण के लिए, जब लेबल में अधिक क्षैतिज स्पेस हो। ratio को `30` करने से एक फ्लैटर लुक बनता है।

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Why this matters:** **set barcode aspect ratio** प्रॉपर्टी को एक्सपोज़ करने से आप एक ही कोड बेस से कई बारकोड वैरिएशन बना सकते हैं, जिससे ऑटोमेटेड लेबल जेनरेशन पाइपलाइन सरल हो जाती है।

## अपेक्षित आउटपुट

प्रोग्राम चलाने पर एप्लिकेशन की आउटपुट फ़ोल्डर में दो PNG फ़ाइलें बनती हैं:

| फ़ाइल नाम                | Aspect Ratio | विज़ुअल विवरण |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | ऊँचा, संकरी बारकोड जो संकरी लेबल्स के लिए उपयुक्त है |
| `DatabarAspectRatio30.png` | 30           | चौड़ा बारकोड जो अधिक क्षैतिज स्पेस को भरता है |

आप इन इमेजेज़ को रिपोर्ट में एम्बेड कर सकते हैं, प्रोडक्ट पैकेजिंग पर प्रिंट कर सकते हैं, या आगे की प्रोसेसिंग के लिए वेब सर्विस को भेज सकते हैं।

![omnidirectional Databar बारकोड उदाहरण बनाएं](databar-example.png "omnidirectional Databar बारकोड उदाहरण बनाएं")

*स्क्रीनशॉट दो जेनरेटेड PNG फ़ाइलों को साइड‑बाय‑साइड दिखाता है।*

## सामान्य प्रश्न और किनारे के केस

### अगर मुझे अलग X‑dimension चाहिए तो?

आप `XDimension.Pixels` को कोई भी इंटीजर वैल्यू असाइन कर सकते हैं। `1` से नीचे के मान इग्नोर हो जाते हैं, और `10` से ऊपर के मान ओवरसाइज़्ड मॉड्यूल बना सकते हैं जो प्रिंटर मार्जिन से बाहर हो जाते हैं। प्रत्येक बदलाव के बाद विज़ुअल आउटपुट का परीक्षण करें।

### मैं अन्य AI‑generated डेटा (जैसे, UPC, EAN) को कैसे एन्कोड करूँ?

`BarcodeGenerator` कंस्ट्रक्टर में डेटा स्ट्रिंग को उपयुक्त Application Identifier (AI) से बदलें। एक UPC‑A कोड के लिए, AI प्रीफ़िक्स के बिना `"012345678905"` उपयोग करें।

### क्या मैं PNG के अलावा अन्य फॉर्मैट्स में एक्सपोर्ट कर सकता हूँ?

हाँ। `Save` मेथड `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, और `BarCodeImageFormat.Bmp` को स्वीकार करता है। वह फॉर्मैट चुनें जो आपके डाउनस्ट्रीम वर्कफ़्लो से मेल खाता हो।

## प्रो टिप: बैच प्रोसेसिंग के लिए जेनरेटर को पुन: उपयोग करें

यदि आपको विभिन्न aspect ratios के साथ दर्जनों बारकोड जेनरेट करने हैं, तो `BarcodeGenerator` इंस्टेंस को जीवित रखें और प्रत्येक `Save` से पहले केवल `DataBar.AspectRatio` को मॉडिफ़ाई करें। इससे हर इमेज के लिए जेनरेटर को फिर से इंस्टैंशिएट करने का ओवरहेड बचता है।

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## निष्कर्ष

अब आप जानते हैं कि Aspose.BarCode का उपयोग करके C# में **create omnidirectional Databar barcode** कैसे **बनाएँ**। `BarcodeGenerator` को initialise करके, X‑dimension सेट करके, **set barcode aspect ratio** को एडजस्ट करके, और PNG फ़ाइलें सेव करके, आप ऐसे बारकोड इमेजेज़ बना सकते हैं जो विभिन्न लेबल आवश्यकताओं को पूरा करें।  

अगला, संबंधित टॉपिक्स जैसे **generate barcode image** के लिए QR कोड्स, **DataBar stacked omnidirectional barcode** वैलिडेशन, या Aspose.PDF के साथ जेनरेटेड PNG को PDF इनवॉइस में इंटीग्रेट करना एक्सप्लोर करें। विभिन्न aspect ratios और मॉड्यूल साइज के साथ प्रयोग करें ताकि अपने विशेष प्रिंटिंग हार्डवेयर के लिए सर्वोत्तम कॉन्फ़िगरेशन मिल सके।

---

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकटतम संबंधित टॉपिक्स को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक रिसोर्स में पूर्ण कार्यशील कोड उदाहरण और चरण-दर-चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करती हैं।

- [C# में बारकोड जेनरेटर का उपयोग करके DataBar Omni‑directional बारकोड कैसे बनाएं](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [C# में databar stacked omnidirectional बारकोड – पूर्ण गाइड](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [C# में बारकोड कैसे जेनरेट करें – DataBar Expanded के साथ बारकोड इमेज बनाएं](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}