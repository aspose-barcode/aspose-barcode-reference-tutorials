---
category: general
date: 2026-09-23
description: c# बारकोड जेनरेटर ट्यूटोरियल दिखाता है कि कैसे Aspose.BarCode लाइब्रेरी
  का उपयोग करके कस्टम एस्पेक्ट रेशियो के साथ बारकोड इमेजेज जनरेट करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: hi
lastmod: 2026-09-23
og_description: C# बारकोड जेनरेटर गाइड आपको बताता है कि कैसे बारकोड इमेज बनाएं, एस्पेक्ट
  रेशियो को समायोजित करें, और Aspose.BarCode का उपयोग करके PNG फ़ाइलें निर्यात करें।
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: C# बारकोड जेनरेटर के साथ उच्च‑गुणवत्ता वाले बारकोड बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: DataBar कोड के लिए C# बारकोड जेनरेटर का उपयोग कैसे करें
url: /hi/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar कोड के लिए C# बारकोड जेनरेटर का उपयोग कैसे करें

यदि आपको एक **c# barcode generator** चाहिए जो DataBar stacked Omni‑Directional प्रतीक बना सके, तो यह गाइड आपको एक पूर्ण, तुरंत चलाने योग्य समाधान देता है। आप देखेंगे कि कैसे बारकोड छवियों को जनरेट करें, X‑dimension को नियंत्रित करें, और IDE छोड़े बिना aspect ratio बदलें।

बारकोड बनाना इन्वेंटरी सिस्टम, शिपिंग लेबल और पॉइंट‑ऑफ़‑सेल एप्लिकेशन्स के लिए एक सामान्य आवश्यकता है। इस ट्यूटोरियल के अंत तक आप अपनी पसंद के किसी भी aspect ratio के साथ PNG फ़ाइलें बना सकते हैं, और आप समझेंगे कि कोड को अन्य बारकोड प्रकारों के लिए कैसे अनुकूलित किया जाए।

## पूर्वापेक्षाएँ

* .NET 6.0 SDK या बाद का संस्करण स्थापित हो  
* Visual Studio 2022 (या कोई भी C# एडिटर जो आप पसंद करते हैं)  
* एक NuGet रेफ़रेंस **Aspose.BarCode** – वह लाइब्रेरी जो `BarcodeGenerator` क्लास को शक्ति देती है  

आपको अलग ग्राफ़िक्स लाइब्रेरी की आवश्यकता नहीं है; Aspose.BarCode आंतरिक रूप से इमेज एन्कोडिंग संभालता है।

## चरण 1: Aspose.BarCode NuGet पैकेज स्थापित करें

अपने प्रोजेक्ट फ़ोल्डर में एक टर्मिनल खोलें और चलाएँ:

```bash
dotnet add package Aspose.BarCode
```

## चरण 2: आउटपुट फ़ोल्डर निर्धारित करें

एक फ़ोल्डर चुनें जहाँ उत्पन्न PNG फ़ाइलें सहेजी जाएँगी। एक absolute या relative पाथ का उपयोग करना समान रूप से काम करता है, लेकिन relative पाथ प्रोजेक्ट को पोर्टेबल रखता है।

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

डायरेक्टरी को प्रोग्रामेटिकली बनाना रनटाइम त्रुटियों से बचाता है यदि फ़ोल्डर मौजूद नहीं है।

## चरण 3: नमूना डेटा के साथ C# बारकोड जेनरेटर को इंस्टैंशिएट करें

`BarcodeGenerator` कन्स्ट्रक्टर को दो आर्ग्यूमेंट चाहिए: बारकोड प्रकार और डेटा स्ट्रिंग। DataBar stacked Omni‑Directional प्रतीक के लिए आप `EncodeTypes.DatabarStackedOmniDirectional` का उपयोग करते हैं।

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

डेटा स्ट्रिंग GS1 Application Identifier फ़ॉर्मेट का पालन करती है। `EncodeTypes` एन्‍युम में 150 से अधिक बारकोड मानक हैं; आप एन्‍युम वैल्यू बदलकर किसी अन्य प्रकार में स्विच कर सकते हैं।

## चरण 4: बारकोड के लिए X‑dimension (पिक्सेल आकार) सेट करें

X‑dimension सबसे पतली बार की चौड़ाई नियंत्रित करता है। पिक्सेल वैल्यू 2 रखने से एक स्पष्ट, हाई‑रेज़ोल्यूशन इमेज मिलती है जो अधिकांश स्क्रीन के लिए उपयुक्त है।

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

X‑dimension को समायोजित करना वैकल्पिक है, लेकिन यह आपको बारकोड की विज़ुअल डेंसिटी पर सूक्ष्म नियंत्रण देता है।

## चरण 5: aspect ratio 15 के साथ बारकोड जनरेट करें और PNG के रूप में सहेजें

`AspectRatio` प्रॉपर्टी `DataBar` सब‑ऑब्जेक्ट की है। इस वैल्यू को बदलने से बारकोड वर्टिकली स्ट्रेच या कॉम्प्रेस होता है जबकि एन्कोडेड डेटा बना रहता है।

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` मेथड बारकोड को निर्दिष्ट फ़ाइल पाथ पर लिखता है। `BarCodeImageFormat.Png` एन्‍युम लॉसलेस कम्प्रेशन सुनिश्चित करता है।

![c# barcode generator output example](generated_barcode_example.png)

*छवि: aspect ratio 15 के साथ जनरेट किया गया बारकोड.*

## चरण 6: aspect ratio को 30 करें और दूसरी इमेज जनरेट करें

एक ही `BarcodeGenerator` इंस्टेंस को पुन: उपयोग करने से नया ऑब्जेक्ट अलोकेट नहीं करना पड़ता। बस `AspectRatio` को अपडेट करें और फिर से `Save` कॉल करें।

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

अब आपके पास दो PNG फ़ाइलें हैं जो केवल वर्टिकल स्केलिंग में अलग हैं। यह तकनीक तब उपयोगी होती है जब आपको एक ही डेटा विभिन्न लेबल साइज के लिए रेंडर करना हो।

## सामान्य विविधताएँ और किनारे के केस

### किसी अन्य बारकोड प्रकार में स्विच करना

यदि आपको QR कोड, Code 128, या PDF417 चाहिए, तो कन्स्ट्रक्टर में एन्‍युम वैल्यू को बदलें:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

बाकी सभी कॉन्फ़िगरेशन स्टेप्स (X‑dimension, सेविंग) समान रहते हैं।

### असमर्थित कैरेक्टर्स को संभालना

`BarcodeGenerator` इनपुट स्ट्रिंग को चयनित सिम्बोलॉजी के विरुद्ध वैलिडेट करता है। अवैध कैरेक्टर देने पर `ArgumentException` फेंका जाता है। फ्रेंडली एरर मैसेज देने के लिए निर्माण को try‑catch ब्लॉक में रैप करें:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### अन्य इमेज फ़ॉर्मेट में एक्सपोर्ट करना

Aspose.BarCode BMP, JPEG, TIFF, और SVG को सपोर्ट करता है। `Save` के दूसरे आर्ग्यूमेंट को उसी अनुसार बदलें:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### प्रिंटिंग के लिए हाई‑रेज़ोल्यूशन आउटपुट

हाई‑DPI प्रिंटर पर प्रिंट करते समय, X‑dimension बढ़ाएँ और वैकल्पिक रूप से `Resolution` प्रॉपर्टी सेट करें:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

इन सेटिंग्स से फ़ाइलें बड़ी बनती हैं लेकिन फिजिकल मीडिया पर स्पष्ट किनारे बनाए रखती हैं।

## अपेक्षित आउटपुट

पूरा प्रोग्राम चलाने से `GeneratedBarcodes/` के अंदर निम्न फ़ाइलें बनती हैं:

* `DatabarAspectRatio15.png` – एक standard‑height DataBar कोड  
* `DatabarAspectRatio30.png` – एक vertically stretched संस्करण  

दोनों इमेज में वही एन्कोडेड GS1 डेटा है, और आप उन्हें किसी भी बारकोड स्कैनर ऐप से वेरिफ़ाई कर सकते हैं।

## पूर्ण स्रोत कोड

नीचे दिया गया कोड एक नए कंसोल प्रोजेक्ट (`dotnet new console`) में कॉपी करें और चलाएँ। प्रोग्राम कंसोल पर स्टेटस मैसेज प्रिंट करता है और PNG फ़ाइलें डिस्क पर लिखता है।

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

प्रोग्राम चलाने पर कंसोल आउटपुट इस प्रकार दिखेगा:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## निष्कर्ष

अब आपके पास एक **c# barcode generator** है जो DataBar stacked Omni‑Directional प्रतीक बना सकता है, X‑dimension को समायोजित कर सकता है, और कस्टम aspect ratios के साथ PNG फ़ाइलें एक्सपोर्ट कर सकता है। वही पैटर्न Aspose.BarCode द्वारा सपोर्ट किए गए किसी भी अन्य बारकोड सिम्बोलॉजी के लिए काम करता है, जिससे इन्वेंटरी, शिपिंग, या पॉइंट‑ऑफ़‑सेल समाधान में बारकोड निर्माण को एकीकृत करना आसान हो जाता है।

यदि आप आगे अन्वेषण करना चाहते हैं, तो कोशिश करें:

* QR कोड या PDF417 प्रतीक जनरेट करना (`how to generate barcode` for mobile apps)  
* स्केलेबल वेब ग्राफ़िक्स के लिए SVG में एक्सपोर्ट करना  
* जनरेट की गई इमेज को सीधे PDF इनवॉइस में एम्बेड करना Aspose.PDF का उपयोग करके  

विभिन्न `AspectRatio` वैल्यू, X‑dimension साइज़, और आउटपुट फ़ॉर्मेट के साथ प्रयोग करें ताकि सटीक मिल सके

## अब आपको आगे क्या सीखना चाहिए?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करती हैं।

- [Aspose.BarCode for .NET का उपयोग करके कस्टम aspect ratio के साथ Aztec बारकोड कैसे जनरेट करें](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aspose.BarCode for .NET के साथ Codablock F Aspect Ratio को कैसे एडजस्ट करें – बारकोड साइज](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Aspose.BarCode for .NET का उपयोग करके वन‑डायमेंशनल Databar के लिए बारकोड ऊँचाई कैसे जनरेट और एडजस्ट करें](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}