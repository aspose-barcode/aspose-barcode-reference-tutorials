---
category: general
date: 2026-07-15
description: Aspose.BarCode के साथ C# में तेज़ी से ओम्नी‑डायरेक्शनल बारकोड बनाएं –
  सीखें कि कैसे समायोज्य बार ऊँचाई और X‑डायमेंशन के साथ C# में बारकोड जेनरेट करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: hi
lastmod: 2026-07-15
og_description: Aspose.BarCode के साथ C# में ओम्नी-डायरेक्शनल बारकोड बनाएं। XDimension
  और BarHeight को समायोजित करके C# में बारकोड जनरेट करने की कला में निपुण बनें और
  परिपूर्ण परिणाम प्राप्त करें।
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: C# में सर्वदिशात्मक बारकोड बनाएं – पूर्ण प्रोग्रामिंग मार्गदर्शिका
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: C# में सर्वदिशात्मक बारकोड बनाएं – स्टेप बाय स्टेप गाइड
url: /hi/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में ओम्नी-डायरेक्शनल बारकोड बनाना – चरण‑दर‑चरण गाइड

क्या आप कभी सोचते रहे हैं कि C# में ऐसा बारकोड कैसे जेनरेट करें जो GS1 DataBar Omni‑Directional सिम्बोलॉजी के अनुरूप हो? आप अकेले नहीं हैं। इस ट्यूटोरियल में हम **ओम्नी-डायरेक्शनल बारकोड** इमेजेज़ को शून्य से बनाएँगे, X‑डायमेंशन को समायोजित करेंगे, और बार की ऊँचाई के साथ प्रयोग करेंगे—सभी Aspose.BarCode लाइब्रेरी का उपयोग करके।

हम एक वास्तविक परिदृश्य से गुजरेंगे: आपको रिटेल लेबल के लिए एक कॉम्पैक्ट, हाई‑डेंसिटी बारकोड चाहिए, और आप उसके विज़ुअल आकार पर पूर्ण नियंत्रण चाहते हैं। अंत तक आपके पास दो PNG फ़ाइलें होंगी—एक 30 px बार ऊँचाई के साथ और दूसरी 60 px के साथ—जो किसी भी प्रिंटिंग वर्कफ़्लो में आसानी से डाली जा सकती हैं।

## आवश्यकताएँ

- .NET 6 (या कोई भी हालिया .NET रनटाइम) आपके मशीन पर स्थापित हो।  
- Visual Studio 2022 या VS Code—आपका पसंदीदा IDE चलेगा।  
- एक मुफ्त Aspose.BarCode for .NET NuGet पैकेज (`Aspose.BarCode`)।

कोई अन्य निर्भरताएँ आवश्यक नहीं हैं। यदि आपने पहले कभी NuGet नहीं छुआ है, तो सिर्फ Package Manager Console खोलें और चलाएँ:

```powershell
Install-Package Aspose.BarCode
```

## ओम्नी-डायरेक्शनल बारकोड बनाना – मूल बातें समझना

**GS1 DataBar Omni‑Directional** सिम्बोलॉजी को किसी भी अभिविन्यास पर स्कैनिंग के लिए डिज़ाइन किया गया है, जिससे यह शेल्फ‑एज लेबल्स के लिए परिपूर्ण बनता है। जब आप `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` कॉल करते हैं, तो लाइब्रेरी भारी काम करती है: यह डेटा को एन्कोड करती है, सिम्बोलॉजी नियम लागू करती है, और एक रास्टर इमेज तैयार करती है।

> **Pro tip:** हमेशा कच्चे डेटा को उपयुक्त Application Identifier (AI) फ़ॉर्मेट में लपेटें, जैसे `"(01)12345678901231"` GTIN‑14 के लिए। यह स्कैनर को बताता है कि अंक क्या दर्शाते हैं।

## चरण 1 – बारकोड जेनरेटर सेट अप करें (how to generate barcode c#)

सबसे पहले हम जेनरेटर ऑब्जेक्ट बनाते हैं। यह **how to generate barcode c#** के साथ Aspose का मुख्य आधार है।

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` एनेम वैल्यू इंजन को बताती है कि कौन सी सिम्बोलॉजी उपयोग करनी है। दूसरा आर्ग्यूमेंट कच्चा डेटा स्ट्रिंग है, जो पहले से ही GTIN AI में लिपटा हुआ है।

## चरण 2 – X‑डायमेंशन समायोजित करें (barcode XDimension)

**barcode XDimension** सबसे छोटे बार की चौड़ाई को नियंत्रित करता है। अधिकांश लेबल प्रिंटरों के लिए 2 px का मान पठनीयता और कॉम्पैक्टनेस के बीच अच्छा संतुलन देता है।

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

यदि आपको अधिक महीन या मोटा लुक चाहिए, तो बस संख्या बदल दें। याद रखें: X‑डायमेंशन मूल इकाई है; सभी अन्य बार की चौड़ाइयाँ इस मान के गुणज होते हैं।

## चरण 3 – 30 px बार ऊँचाई के साथ पहली इमेज बनाएं (barcode BarHeight)

अब हम **barcode BarHeight** को 30 px सेट करते हैं और इमेज सहेजते हैं। यह एक मध्यम आकार का बारकोड बनाता है जो मानक लेबल पर अच्छी तरह फिट बैठता है।

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` मेथड एक PNG फ़ाइल को डिस्क पर लिखता है। यदि आप JPEG आउटपुट पसंद करते हैं तो `BarCodeImageFormat.Jpeg` से बदल सकते हैं।

## चरण 4 – बड़े लेबल्स के लिए बार ऊँचाई को 60 px तक बढ़ाएँ (barcode BarHeight)

कभी‑कभी एक बड़ा बारकोड आवश्यक होता है—शायद शेल्फ लेबल के लिए जो स्कैनर से दूर स्थित हो। चलिए ऊँचाई को दोगुना कर देते हैं।

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

ध्यान दें कि हमें जेनरेटर को फिर से बनाने की **ज़रूरत नहीं** है; हम केवल पैरामीटर को बदलते हैं और उसी ऑब्जेक्ट को पुनः उपयोग करते हैं। इससे मेमोरी बचती है और कोड साफ़ रहता है।

## चरण 5 – दूसरी इमेज सहेजें (how to generate barcode c#)

अंत में, हम दूसरी PNG सहेजते हैं। अब आपके पास दो फ़ाइलें हैं जो केवल बार ऊँचाई में अंतर रखती हैं।

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### अपेक्षित आउटपुट

- `DatabarBarHeight30Pixels.png` – 30 px ऊँचा ओम्नी‑डायरेक्शनल बारकोड।  
- `DatabarBarHeight60Pixels.png` – वही डेटा, लेकिन 60 px ऊँचा बारकोड।

किसी भी इमेज व्यूअर में फ़ाइलें खोलें; आपको तेज़, स्कैन करने योग्य बार दिखेंगे जो GS1 DataBar Omni‑Directional स्पेसिफिकेशन का सम्मान करते हैं।

## सामान्य प्रश्न और किनारे के मामले

### अगर मुझे अलग X‑डायमेंशन चाहिए तो?

`Save` कॉल करने से पहले बस नया मान असाइन कर दें। अल्ट्रा‑हाई‑डेंसिटी प्रिंटिंग के लिए आप 1 px तक जा सकते हैं, लेकिन पहले अपने स्कैनर से परीक्षण करें—कुछ डिवाइस सब‑2 px बार में कठिनाई महसूस करते हैं।

### क्या मैं बारकोड के नीचे मानव‑पठनीय टेक्स्ट जोड़ सकता हूँ?

हां। `barcodeGenerator.Parameters.Barcode.CodeText` को किसी स्ट्रिंग पर सेट करें और वैकल्पिक रूप से `barcodeGenerator.Parameters.Barcode.CodeLocation` को `BarCodeTextLocation.Below` पर समायोजित करें। यह रिटेल वातावरण में उपयोगी है जहाँ संख्यात्मक GTIN दिखाई देना आवश्यक है।

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### क्या PNG प्रिंटिंग के लिए सबसे अच्छा फॉर्मेट है?

PNG लॉसलेस है, जो बारकोड स्कैनरों के लिए आवश्यक तीक्ष्ण किनारों को संरक्षित रखता है। यदि आपका डाउनस्ट्रीम सिस्टम कोई अलग फॉर्मेट (TIFF, BMP) अपेक्षित करता है, तो बस `BarCodeImageFormat` एनेम को बदल दें।

## पूर्ण कार्यशील उदाहरण (create omni-directional barcode)

नीचे पूरा, तैयार‑से‑चलाने वाला प्रोग्राम दिया गया है। इसे एक नए कंसोल प्रोजेक्ट में कॉपी‑पेस्ट करें और **F5** दबाएँ।

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

प्रोग्राम चलाएँ, आउटपुट फ़ोल्डर देखें, और आपको दो PNG फ़ाइलें बिल्कुल वही मिलेंगी जैसा वर्णित किया गया है।

## सारांश

हमने **how to generate barcode C#** कोड दिखाया है जो Aspose.BarCode का उपयोग करके **create omni-directional barcode** बनाता है। **barcode XDimension** और **barcode BarHeight** को समायोजित करके आप विज़ुअल आकार पर सूक्ष्म नियंत्रण प्राप्त करते हैं बिना स्कैन विश्वसनीयता से समझौता किए।

## आगे क्या?

- `Color` या `Margin` जैसे अन्य **GS1 DataBar Omni-Directional** सेटिंग्स के साथ प्रयोग करें।  
- जटिल लेबल डिज़ाइन के लिए `Graphics` का उपयोग करके एक ही कैनवास पर कई बारकोड संयोजित करें।  
- जेनरेटर को वेब API में इंटीग्रेट करें ताकि आपका ई‑कॉमर्स प्लेटफ़ॉर्म मांग पर बारकोड उत्पन्न कर सके।

क्या आपके पास कोई ट्विस्ट है जिसे आप साझा करना चाहते हैं? एक टिप्पणी छोड़ें, और बातचीत जारी रखें। Happy coding!

## अब आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोच को एक्सप्लोर कर सकें।

- [बारकोड कैसे जेनरेट करें – कोड 39 कॉन्फ़िगरेशन Aspose.BarCode के साथ](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [ITF-14 के लिए बारकोड क्वाइट ज़ोन कैसे बनाएं Aspose.BarCode for .NET का उपयोग करके](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [कोड 16K के लिए बारकोड क्वाइट ज़ोन कैसे बनाएं Aspose.BarCode for .NET का उपयोग करके](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}