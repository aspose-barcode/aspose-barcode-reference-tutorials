---
category: general
date: 2026-09-29
description: C# का उपयोग करके GS1 DataBar Omni‑Directional बारकोड की चौड़ाई कैसे सेट
  करें और ऊँचाई कैसे बदलें। पूर्ण कोड के साथ चरण‑दर‑चरण गाइड का पालन करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: hi
lastmod: 2026-09-29
og_description: C# में GS1 DataBar Omni‑Directional बारकोड की चौड़ाई कैसे सेट करें
  और ऊँचाई कैसे बदलें। सटीक API कॉल्स सीखें और एक पूर्ण चलाने योग्य उदाहरण देखें।
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: GS1 DataBar बारकोड की चौड़ाई कैसे सेट करें – C# गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: C# में GS1 DataBar Omni‑Directional बारकोड की चौड़ाई सेट करने और ऊँचाई समायोजित
  करने का तरीका
url: /hi/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में GS1 DataBar Omni‑Directional बारकोड की चौड़ाई सेट करने और ऊँचाई समायोजित करने का तरीका

GS1 DataBar Omni‑Directional बारकोड की चौड़ाई सेट करना एक सामान्य कार्य है जब आपको स्कैनिंग उपकरणों के लिए सटीक आकार चाहिए। इस ट्यूटोरियल में आप **ऊँचाई कैसे बदलें** यह भी सीखेंगे ताकि बारकोड आपके लेआउट में पूरी तरह फिट हो सके। यह गाइड प्रोजेक्ट सेटअप से लेकर पूरी तरह चलने वाले कोड सैंपल तक की पूरी प्रक्रिया को दर्शाता है।

हम कवर करेंगे:

* आवश्यक NuGet पैकेज और .NET संस्करण।
* बारकोड पठनीयता के लिए X‑dimension (मॉड्यूल चौड़ाई) क्यों महत्वपूर्ण है।
* **चौड़ाई कैसे सेट करें** और **ऊँचाई कैसे बदलें** के सटीक API कॉल।
* न्यूनतम मॉड्यूल चौड़ाई और हाई‑रेज़ोल्यूशन रेंडरिंग जैसे एज‑केस हैंडलिंग।
* एक पूर्ण, कॉपी‑एंड‑पेस्ट उदाहरण जो दो PNG फ़ाइलें विभिन्न बार ऊँचाइयों के साथ बनाता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

| आवश्यकता | कारण |
|------------|--------|
| .NET 6.0 SDK या बाद का संस्करण | उदाहरण आधुनिक C# फीचर्स का उपयोग करता है और Windows, Linux, या macOS पर चलता है। |
| Visual Studio 2022 (या कोई भी C# IDE) | Aspose.Barcode API के लिए IntelliSense प्रदान करता है। |
| **Aspose.Barcode for .NET** NuGet पैकेज | `BarcodeGenerator`, `EncodeTypes`, और इमेज फ़ॉर्मेट सपोर्ट शामिल है। `dotnet add package Aspose.Barcode` से इंस्टॉल करें। |
| वह फ़ोल्डर जहाँ PNG फ़ाइलें सहेजी जाएँगी, उसमें लिखने की अनुमति | जेनरेटर आउटपुट इमेज को डिस्क पर लिखता है। |

## बारकोड की चौड़ाई कैसे सेट करें

**चौड़ाई कैसे सेट करें** चरण `XDimension` प्रॉपर्टी को कॉन्फ़िगर करके किया जाता है। `XDimension` मॉड्यूल चौड़ाई (सबसे छोटा बार या स्पेस) को पिक्सेल, पॉइंट या मिलीमीटर में दर्शाता है। इसे सही ढंग से सेट करने से बारकोड स्कैनर स्पेसिफिकेशन को पूरा करता है।

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### X‑dimension क्यों महत्वपूर्ण है

* **स्कैनर सहनशीलता** – अधिकांश स्कैनर न्यूनतम मॉड्यूल चौड़ाई की अपेक्षा करते हैं; बहुत छोटा मान पढ़ने में त्रुटि पैदा कर सकता है।
* **प्रिंट रिज़ॉल्यूशन** – 300 dpi पर प्रिंट करने पर 2 px मॉड्यूल लगभग 0.17 mm बनता है, जो GS1 DataBar के अनुशंसित रेंज में आता है।
* **इमेज आकार** – बड़ी X‑dimension मान कुल बारकोड की चौड़ाई बढ़ाते हैं, जिससे लेआउट प्रतिबंध प्रभावित हो सकते हैं।

### विश्वसनीय चौड़ाई सेटिंग के लिए टिप्स

* **XDimension को 1 px से नीचे कभी न रखें** – लाइब्रेरी मान को क्लैंप कर देगी, लेकिन resulting बारकोड पढ़ने योग्य नहीं रह सकता।
* **लक्षित DPI से मिलाएँ** – यदि आप हाई‑रेज़ोल्यूशन फ़ॉर्मेट (जैसे TIFF @ 600 dpi) में रेंडर कर रहे हैं, तो XDimension को अनुपातिक रूप से बढ़ाएँ।
* **वास्तविक स्कैनर से टेस्ट करें** – चौड़ाई बदलने के बाद, उस डिवाइस पर बारकोड को वैलिडेट करें जो इसे पढ़ेगा।

## बारकोड की ऊँचाई कैसे बदलें

एक बार चौड़ाई निर्धारित हो जाने के बाद, आप `BarHeight` प्रॉपर्टी से वर्टिकल साइज को नियंत्रित कर सकते हैं। नीचे दिया गया कोड **ऊँचाई को 30 px से 60 px तक बदलने** और दो अलग‑अलग इमेज सेव करने का प्रदर्शन करता है।

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### बार ऊँचाई को समझना

* **विज़ुअल बैलेंस** – ऊँचे बार कम‑कॉन्ट्रास्ट बैकग्राउंड पर पठनीयता बढ़ाते हैं, लेकिन इमेज की वर्टिकल फुटप्रिंट भी बढ़ाते हैं।
* **नियामक सीमाएँ** – कुछ मानक (जैसे रिटेल लेबलिंग) अधिकतम बार ऊँचाई निर्धारित करते हैं; उसी अनुसार समायोजित करें।
* **अस्पेक्ट रेशियो** – ऊँचाई बदलने से मॉड्यूल चौड़ाई प्रभावित नहीं होती; आप दोनों को स्वतंत्र रूप से ट्यून कर सकते हैं।

### ऊँचाई समायोजन के लिए एज‑केस हैंडलिंग

| स्थिति | अनुशंसित तरीका |
|-----------|----------------------|
| ऊँचाई < 10 px | कम से कम 10 px तक बढ़ाएँ; बहुत छोटी बार स्कैनर द्वारा अनदेखी हो सकती हैं। |
| बहुत ऊँचे बार (≥ 100 px) | सुनिश्चित करें कि आउटपुट माध्यम (कागज, लेबल) अतिरिक्त स्पेस को समायोजित कर सके। |
| अनुपातिक स्केलिंग चाहिए | `BarHeight = XDimension * desiredRatio` गणना करें ताकि विज़ुअल कंसिस्टेंसी बनी रहे। |

## पूर्ण, चलने योग्य उदाहरण

नीचे पूरा प्रोग्राम है जो **चौड़ाई कैसे सेट करें** और **ऊँचाई कैसे बदलें** दोनों चरणों को मिलाता है। कोड को नई कंसोल प्रोजेक्ट में कॉपी करें, Aspose.Barcode NuGet पैकेज रिस्टोर करें, और चलाएँ। दो PNG फ़ाइलें `bin/Debug/net6.0` फ़ोल्डर में बनेंगी।

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**अपेक्षित आउटपुट**

प्रोग्राम चलाने पर दो PNG फ़ाइलें बनेंगी:

* `DatabarBarHeight30Pixels.png` – 30 px ऊँचा बारकोड, 2 px चौड़े मॉड्यूल।
* `DatabarBarHeight60Pixels.png` – वही बारकोड, लेकिन ऊँचाई दोगुनी।

किसी भी व्यूअर में इमेज खोलें; आपको एक साफ़ GS1 DataBar Omni‑Directional सिंबल दिखाई देगा जो स्कैनिंग के लिए तैयार है।

## सामान्य प्रश्नों के उत्तर

| प्रश्न | उत्तर |
|----------|--------|
| *क्या मैं पिक्सेल के बजाय मिलीमीटर उपयोग कर सकता हूँ?* | हाँ। `generator.Parameters.Barcode.XDimension.Millimeters` और `BarHeight.Millimeters` सेट करें। लाइब्रेरी इमेज के DPI के आधार पर डिवाइस पिक्सेल में बदल देती है। |
| *यदि मुझे अलग बारकोड प्रकार चाहिए तो?* | `EncodeTypes.DatabarOmniDirectional` को किसी अन्य `EncodeTypes` वैल्यू (जैसे `EncodeTypes.QR`) से बदलें। चौड़ाई और ऊँचाई प्रॉपर्टी समान रूप से काम करती हैं। |
| *क्या PNG के बजाय SVG जनरेट कर सकते हैं?* | `Save` कॉल में `BarCodeImageFormat.Svg` उपयोग करें। चौड़ाई/ऊँचाई सेटिंग्स वही रहती हैं। |
| *क्या मुझे `generator.Dispose()` कॉल करना चाहिए?* | `BarcodeGenerator` `IDisposable` को इम्प्लीमेंट करता है। कंसोल ऐप में आप इसे `using` ब्लॉक में रख सकते हैं, लेकिन छोटे उदाहरणों में वैकल्पिक है। |

## निष्कर्ष

अब आप Aspose.Barcode API का उपयोग करके C# में GS1 DataBar Omni‑Directional बारकोड की **चौड़ाई कैसे सेट करें** और **ऊँचाई कैसे बदलें** दोनों जानते हैं। पूरा उदाहरण जेनरेटर बनाना, `XDimension` और `BarHeight` कॉन्फ़िगर करना, और विभिन्न वर्टिकल साइज वाली PNG फ़ाइलें सेव करना दर्शाता है।

अब आप कर सकते हैं:

* अन्य `EncodeTypes` (जैसे QR, Code128) के साथ प्रयोग करें।
* प्रिंटिंग के लिए TIFF जैसे हाई‑रेज़ोल्यूशन फ़ॉर्मेट में रेंडर करें।
* जेनरेटर को वेब API में इंटीग्रेट करें जो बारकोड ऑन‑द‑फ़्लाई रिटर्न करता है।

हैप्पी कोडिंग, और आपके बारकोड हमेशा साफ़ स्कैन हों!

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में महारत हासिल कर सकें और अपने प्रोजेक्ट में वैकल्पिक इम्प्लीमेंटेशन एप्रोच का अन्वेषण कर सकें।

- [C# में बारकोड ऊँचाई बदलने का पूरा गाइड](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [C# में बारकोड जेनरेटर उदाहरण – चौड़ाई और ऊँचाई सेट करें](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [C# में बारकोड जेनरेटर का उपयोग करके DataBar Omni‑directional बारकोड बनाना](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}