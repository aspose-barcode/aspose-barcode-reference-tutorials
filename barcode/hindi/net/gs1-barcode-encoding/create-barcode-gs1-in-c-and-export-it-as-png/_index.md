---
category: general
date: 2026-09-29
description: C# में GS1 बारकोड बनाएं और BarcodeGenerator का उपयोग करके बारकोड PNG
  इमेजेज जनरेट करें। बारकोड इमेज को कुशलतापूर्वक निर्यात करने के लिए चरण‑दर‑चरण गाइड
  का पालन करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: hi
lastmod: 2026-09-29
og_description: C# में GS1 बारकोड बनाएं और BarcodeGenerator के साथ बारकोड PNG फ़ाइलें
  जनरेट करें। बारकोड इमेज को जल्दी एक्सपोर्ट करने के लिए इस पूर्ण गाइड का पालन करें।
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: C# में GS1 बारकोड बनाएं – मिनटों में PNG के रूप में निर्यात करें
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: C# में GS1 बारकोड बनाएं और इसे PNG के रूप में निर्यात करें
url: /hi/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में GS1 बारकोड बनाएं और इसे PNG के रूप में निर्यात करें

यदि आपको .NET एप्लिकेशन में **create barcode GS1** बनाने की आवश्यकता है, तो यह गाइड आपको बिल्कुल बताता है कि इसे कैसे करें। आप एक संक्षिप्त समाधान देखेंगे जो एक बारकोड PNG इमेज जनरेट करता है और बारकोड इमेज को डिस्क पर निर्यात करता है, सभी Aspose.BarCode `BarcodeGenerator` क्लास का उपयोग करके।

GS1 बारकोड बनाना इन्वेंटरी, शिपिंग और पॉइंट‑ऑफ़‑सेल सिस्टम के लिए एक सामान्य आवश्यकता है। इस ट्यूटोरियल के अंत तक आप एक छोटा C# प्रोग्राम लिख सकेंगे जो GS1‑compliant MicroPDF417 बारकोड बनाता है और इसे हाई‑क्वालिटी PNG फ़ाइल के रूप में सहेजता है।

## पूर्वापेक्षाएँ

* **.NET 6** (या कोई भी बाद का .NET संस्करण) स्थापित हो।
* **Visual Studio 2022** या कोई भी IDE जो C# का समर्थन करता हो।
* **Aspose.BarCode for .NET** NuGet पैकेज (`Aspose.BarCode`) – यह उदाहरणों में उपयोग किए गए `BarcodeGenerator` API को प्रदान करता है।
* C# सिंटैक्स की बुनियादी परिचितता।

> **Pro tip:** प्रयोग करते समय Aspose.BarCode का मुफ्त कम्युनिटी एडिशन उपयोग करें; पूर्ण संस्करण किसी भी इवैल्यूएशन वाटरमार्क को हटा देता है।

## चरण 1 – BarcodeGenerator के साथ barcode GS1 बनाएं

सबसे पहले आपको *MicroPDF417* फ़ॉर्मेट के लिए `BarcodeGenerator` को इंस्टैंशिएट करना होगा और उसे एक GS1 डेटा स्ट्रिंग देना होगा। GS1 एप्लिकेशन आइडेंटिफ़ायर्स (AIs) को कोष्ठकों में लपेटा जाता है, उदाहरण के लिए GTIN‑14 के लिए `(01)` और सीरियल नंबर के लिए `(21)`।

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**यह क्यों महत्वपूर्ण है:**  
`EncodeTypes.MicroPdf417` स्वचालित रूप से इनपुट को GS1 डेटा मानता है जब स्ट्रिंग में वैध AIs होते हैं। यह सुनिश्चित करता है कि जनरेट किया गया बारकोड अतिरिक्त कॉन्फ़िगरेशन के बिना GS1 स्पेसिफिकेशन के अनुरूप हो।

## चरण 2 – इष्टतम आकार के लिए बारकोड आयाम सेट करें

बारकोड का दृश्य आकार उसकी **X‑dimension** (एकल मॉड्यूल की चौड़ाई) द्वारा नियंत्रित होता है। `XDimension.Pixels` को समायोजित करने से आप अंतिम इमेज आकार को बारीकी से ट्यून कर सकते हैं जबकि पठनीयता बनी रहती है।

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **How to generate barcode PNG** – X‑dimension एन्कोडेड डेटा को प्रभावित नहीं करता; यह केवल जनरेट की गई इमेज के भौतिक आयाम बदलता है। यदि आपको हाई‑रिज़ॉल्यूशन प्रिंटिंग के लिए बड़ा बारकोड चाहिए, तो इस मान को बढ़ाएँ (उदाहरण के लिए, `3` या `4`)।

## चरण 3 – barcode PNG जनरेट करें और बारकोड इमेज निर्यात करें

अब आप बारकोड को रेंडर कर सकते हैं और इसे PNG फ़ाइल में लिख सकते हैं। `Save` मेथड लक्ष्य पाथ और इच्छित इमेज फ़ॉर्मेट लेता है।

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**आंतरिक प्रक्रिया:**  
`BarcodeGenerator.Save` बारकोड को बिटमैप में रास्टराइज़ करता है, पहले सेट की गई X‑dimension लागू करता है, और बिटमैप को PNG फ़ाइल के रूप में एन्कोड करता है। परिणामी फ़ाइल को सीधे वेब पेजों में उपयोग किया जा सकता है, लेबल पर प्रिंट किया जा सकता है, या PDFs में एम्बेड किया जा सकता है।

## पूरा स्रोत कोड उदाहरण

नीचे एक पूर्ण, स्व-निहित कंसोल एप्लिकेशन है जिसे आप कॉपी, पेस्ट और रन कर सकते हैं। यह **how to generate barcode PNG** फ़ाइलें, **export barcode image** को दर्शाता है, और बुनियादी त्रुटि हैंडलिंग शामिल करता है।

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### अपेक्षित आउटपुट

जब आप प्रोग्राम चलाएँगे, आपको यह दिखना चाहिए:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

PNG फ़ाइल खोलने पर एक स्पष्ट **GS1 MicroPDF417** बारकोड दिखेगा जो GTIN‑14 `12345678901234` और सीरियल नंबर `ABC123` को एन्कोड करता है। इसे किसी भी GS1‑compatible स्कैनर से स्कैन करने पर मूल डेटा स्ट्रिंग वापस मिलेगी।

## सामान्य समस्याएँ और सर्वोत्तम प्रथाएँ

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **गलत AI फ़ॉर्मेटिंग** | कोष्ठकों की कमी या गलत क्रम के कारण बारकोड GS1 नहीं बनता। | हमेशा प्रत्येक AI को कोष्ठकों में लपेटें, उदाहरण के लिए, `(01)`। |
| **बहुत छोटा X‑dimension** | बारकोड कम‑रिज़ॉल्यूशन डिवाइसों पर पढ़ने योग्य नहीं रहता। | अधिकांश प्रिंटरों के लिए `XDimension.Pixels` को ≥ 2 रखें; हाई‑DPI आउटपुट के लिए बढ़ाएँ। |
| **आउटपुट फ़ोल्डर मौजूद नहीं है** | `Save` `DirectoryNotFoundException` फेंकता है। | `Save` कॉल करने से पहले `Directory.CreateDirectory` का उपयोग करें। |
| **गलत EncodeType का उपयोग** | कुछ प्रकार (जैसे `Code128`) बॉक्स से बाहर GS1 डेटा का समर्थन नहीं करते। | `EncodeTypes.MicroPdf417` या कोई भी GS1‑compatible प्रकार चुनें। |
| **NuGet रेफ़रेंस गायब** | `The type or namespace name 'Aspose' could not be found` जैसी कंपाइल‑टाइम त्रुटियाँ। | NuGet के माध्यम से `Aspose.BarCode` पैकेज इंस्टॉल करें। |

## उदाहरण का विस्तार

* **Different image formats** – यदि आपको कोई अन्य फ़ॉर्मेट चाहिए तो `BarCodeImageFormat.Png` को `Jpeg`, `Gif`, या `Bmp` से बदलें।
* **Higher‑resolution output** – सहेजने से पहले `generator.Parameters.ImageResolution.DpiX` और `DpiY` सेट करें।
* **Embedding in PDF** – PNG को PDF इनवॉइस या लेबल में रखने के लिए `Aspose.Pdf` का उपयोग करें।

## निष्कर्ष

अब आप जानते हैं कि C# में Aspose.BarCode `BarcodeGenerator` का उपयोग करके **create barcode GS1** कैसे किया जाता है, **generate barcode PNG** कैसे किया जाता है, और **export barcode image** को फ़ाइल सिस्टम में कैसे निर्यात किया जाता है। गाइड ने हर चरण को कवर किया—GS1 डेटा के साथ जनरेटर को इनिशियलाइज़ करने से, X‑dimension को समायोजित करने तक, अंतिम PNG फ़ाइल को सहेजने तक—और सामान्य त्रुटियों को संबोधित किया तथा विस्तार विचार प्रस्तुत किए।

अन्य GS1 एप्लिकेशन आइडेंटिफ़ायर्स, विभिन्न बारकोड सिम्बोलॉजीज़, या हाई‑रिज़ॉल्यूशन इमेजेज़ के साथ प्रयोग करने में संकोच न करें। जब आप इन बुनियादों में महारत हासिल कर लेते हैं, तो इन्वेंटरी, शिपिंग, या रिटेल के लिए अनुपालन योग्य बारकोड जनरेट करना आपके .NET टूलबॉक्स का नियमित हिस्सा बन जाता है।

## अगले क्या सीखना चाहिए?

निम्नलिखित ट्यूटोरियल्स उन निकट संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर करने में मदद करती हैं।

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}