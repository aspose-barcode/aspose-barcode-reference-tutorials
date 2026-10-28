---
category: general
date: 2026-10-28
description: C# में बारकोड इमेज बनाएं और BarcodeGenerator API का उपयोग करके ऊँचाई
  कैसे समायोजित करें, सीखें। कस्टम बारकोड ऊँचाई और बार की ऊँचाई बदलने के लिए चरण‑दर‑चरण
  गाइड।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: hi
lastmod: 2026-10-28
og_description: C# में बारकोड इमेज बनाएं और तुरंत देखें कि ऊँचाई कैसे समायोजित करें।
  बारकोडजनरेटर के साथ कस्टम बारकोड ऊँचाई सेट करने के लिए इस पूर्ण उदाहरण का पालन करें।
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: C# में कस्टम ऊँचाई के साथ बारकोड इमेज बनाएं – पूर्ण गाइड
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: C# में कस्टम ऊँचाई के साथ बारकोड छवि बनाएं
url: /hi/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में कस्टम ऊँचाई के साथ बारकोड इमेज बनाएं

यदि आपको **बारकोड इमेज बनानी** है और उसके आयामों को नियंत्रित करना है, तो यह गाइड आपको बिल्कुल बताता है कि कैसे। Aspose.BarCode .NET लाइब्रेरी का उपयोग करके आप एक GS1‑Databar Omni‑Directional बारकोड जेनरेट कर सकते हैं, फिर **ऊँचाई को कैसे समायोजित करें** किसी भी लेआउट आवश्यकता को पूरा करने के लिए।

आप एक पूर्ण, चलाने योग्य प्रोग्राम के माध्यम से चलेंगे जो एक **c# barcode generator** को दर्शाता है, आप जो प्रत्येक प्रॉपर्टी सेट करते हैं उसकी व्याख्या करता है, और दो अलग-अलग आउटपुट दिखाता है—एक 30‑पिक्सेल बार ऊँचाई के साथ और दूसरा 60‑पिक्सेल बार ऊँचाई के साथ। अंत तक आप प्रोग्रामेटिक रूप से **बारकोड ऊँचाई बदलने** में सक्षम हो जाएंगे, लाइब्रेरी द्वारा समर्थित किसी भी बारकोड प्रकार के लिए।

## आवश्यकताएँ

- .NET 6.0 SDK या बाद का (कोड .NET Framework 4.6+ के साथ भी काम करता है)
- Visual Studio 2022 या कोई भी एडिटर जो C# प्रोजेक्ट बना सके
- Aspose.BarCode for .NET NuGet पैकेज (`Install-Package Aspose.BarCode`)
- C# सिंटैक्स की बुनियादी परिचितता

> **Pro tip:** यदि आप CI पाइपलाइन का उपयोग कर रहे हैं, तो NuGet पैकेज को अपने `csproj` फ़ाइल में जोड़ें ताकि बिल्ड इसे स्वचालित रूप से पुनर्स्थापित करे।

## चरण 1: प्रोजेक्ट सेट अप करें और नेमस्पेस इम्पोर्ट करें

एक नया कंसोल प्रोजेक्ट बनाएं और आवश्यक `using` स्टेटमेंट्स जोड़ें। नेमस्पेस आपको `BarcodeGenerator`, `EncodeTypes`, और इमेज‑फ़ॉर्मेट हेल्पर्स तक पहुंच प्रदान करते हैं।

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **यह क्यों महत्वपूर्ण है:** सही नेमस्पेस इम्पोर्ट करने से कंपाइल‑टाइम एरर रोकते हैं और IntelliSense में API को खोजने योग्य बनाते हैं।

## चरण 2: एक GS1‑Databar Omni‑Directional कोड के लिए **c# barcode generator** को इनिशियलाइज़ करें

कंस्ट्रक्टर दो आर्ग्यूमेंट लेता है: बारकोड प्रकार (`EncodeTypes.DatabarOmniDirectional`) और डेटा स्ट्रिंग। डेटा स्ट्रिंग को GS1 एप्लिकेशन आइडेंटिफायर फॉर्मेट का पालन करना चाहिए, उदाहरण के लिए `(01)12345678901231`।

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **व्याख्या:** `BarcodeGenerator` ऑब्जेक्ट सभी बारकोड‑संबंधित सेटिंग्स के लिए एंट्री पॉइंट है। एक बार जब आपके पास यह इंस्टेंस हो जाता है, तो आप आयाम, रंग, और आउटपुट फ़ॉर्मेट को समायोजित कर सकते हैं।

## चरण 3: सामान्य X‑डायमेंशन (सबसे संकरी बार की पिक्सेल चौड़ाई) परिभाषित करें

अधिकांश स्क्रीन‑डिस्प्ले परिदृश्यों के लिए 2‑पिक्सेल X‑डायमेंशन एक अच्छा शुरुआती बिंदु है।

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **X‑डायमेंशन क्यों सेट करें?** यह बारकोड की कुल चौड़ाई को नियंत्रित करता है। इसे स्थिर रखने से यह सुनिश्चित होता है कि बार ऊँचाई बदलने से दृश्य संतुलन बिगड़ता नहीं है।

## चरण 4: **बारकोड इमेज बनाएं** 30‑पिक्सेल बार ऊँचाई के साथ

अब हम बार ऊँचाई को कॉन्फ़िगर करते हैं, पहली इमेज सहेजते हैं, फिर दूसरे के लिए ऊँचाई बदलते हैं।

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **परिणाम:** आपको एक PNG फ़ाइल मिलती है जहाँ प्रत्येक वर्टिकल बार 30 पिक्सेल ऊँचा है। X‑डायमेंशन 2 पिक्सेल बना रहता है, इसलिए कुल चौड़ाई अपरिवर्तित रहती है।

## चरण 5: **ऊँचाई को कैसे समायोजित करें** – बार ऊँचाई को 60 पिक्सेल बदलें

**कस्टम बारकोड ऊँचाई** दिखाने के लिए, बस उसी प्रॉपर्टी को नया मान असाइन करें और फिर से सहेजें।

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **मुख्य अंतर्दृष्टि:** `BarHeight` प्रॉपर्टी परिवर्तनशील है; आपको `BarcodeGenerator` इंस्टेंस को फिर से बनाने की आवश्यकता नहीं है। यह लूप या बैच प्रोसेस में कई आकार उत्पन्न करने को सस्ता बनाता है।

## चरण 6: आउटपुट सत्यापित करें

कंसोल प्रोग्राम चलाएँ (`dotnet run`)। निष्पादन के बाद आपको प्रोजेक्ट के आउटपुट फ़ोल्डर में दो PNG फ़ाइलें दिखनी चाहिए:

- `DatabarBarHeight30Pixels.png` – छोटे बार (30 px)
- `DatabarBarHeight60Pixels.png` – बड़े बार (60 px)

दोनों इमेज में समान एन्कोडेड डेटा है, लेकिन दृश्य ऊँचाई अलग है, जो फॉर्म, प्रोडक्ट लेबल, या विभिन्न स्थान सीमाओं वाले UI कंपोनेंट्स में बारकोड को एकीकृत करने के लिए उपयोगी है।

![कस्टम ऊँचाई के साथ बारकोड इमेज बनाएं](barcode-example.png){.align-center width="600" alt="कस्टम ऊँचाई के साथ बारकोड इमेज बनाएं"}

> **टिप:** किसी भी इमेज व्यूअर में PNG फ़ाइलें खोलें। लंबा बारकोड छोटा बारकोड की ऊँचाई का ठीक दो गुना होना चाहिए, जबकि क्षैतिज स्पेसिंग समान रहती है।

## चरण 7: सामान्य विविधताएँ और किनारे के मामलों

| स्थिति | सिफारिश सेटिंग |
|-----------|---------------------|
| **उच्च‑रिज़ॉल्यूशन लेबल प्रिंटर पर प्रिंटिंग** | बड़े X‑डायमेंशन (जैसे, 4 px) का उपयोग करें और `BarHeight` को अनुपातिक रूप से बढ़ाएँ। |
| **कम‑dpi स्क्रीन पर डिस्प्ले** | `XDimension` को 1 px पर रखें और पठनीयता के लिए `BarHeight` को 20‑40 px के बीच रखें। |
| **QR कोड या 2‑D बारकोड जेनरेट करना** | `BarHeight` प्रॉपर्टी को नजरअंदाज़ किया जाता है; इसके बजाय `EncodeTypes.QR` का उपयोग करें और `ImageHeight` को समायोजित करें। |
| **कई ऊँचाइयों का बैच जेनरेट करना** | ऊँचाइयों की एक एरे पर लूप करें और लूप के भीतर `Save` कॉल करें; प्रत्येक इटरेशन में जेनरेटर को फिर से बनाने की आवश्यकता नहीं है। |

### अमान्य ऊँचाइयों को संभालना

यदि आप `BarHeight` को गैर‑धनात्मक मान पर सेट करते हैं तो लाइब्रेरी `ArgumentOutOfRangeException` फेंकती है। एक सरल जांच के साथ इसे रोकें:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## पूर्ण स्रोत कोड (कॉपी करने के लिए तैयार)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **यह क्यों काम करता है:** सभी आवश्यक सेटिंग्स (`EncodeTypes`, `XDimension`, `BarHeight`) प्रत्येक `Save` कॉल से पहले लागू की जाती हैं। वही `BarcodeGenerator` इंस्टेंस पुन: उपयोग किया जाता है, जो मेमोरी‑कुशल और पढ़ने में आसान है।

## निष्कर्ष

अब आप जानते हैं कि C# में **बारकोड इमेज** फ़ाइलें कैसे बनाएं और `BarcodeGenerator` API का उपयोग करके **बारकोड ऊँचाई** को सटीक रूप से **बदलें**। `BarHeight.Pixels` को समायोजित करके आप **कस्टम बारकोड ऊँचाई** प्राप्त कर सकते हैं बिना जेनरेटर को पुनः बनाये, जिससे समाधान गतिशील लेबल निर्माण, UI रेंडरिंग, या बैच प्रोसेसिंग पाइपलाइन के लिए आदर्श बनता है।

अगला, संबंधित विषयों का अन्वेषण करें जैसे **चौड़ाई को कैसे समायोजित करें**, **ह्यूमन‑रीडेबल टेक्स्ट जोड़ना**, या **स्केलेबल वेब उपयोग के लिए SVG एक्सपोर्ट करना**। वही पैटर्न—एक प्रॉपर्टी सेट करें, `Save` कॉल करें—इन परिदृश्यों में लागू होता है, जिससे आप इस उदाहरण को आत्मविश्वास के साथ विस्तारित कर सकते हैं।

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स निकटतम संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को खोजने में मदद करती हैं।

- [C# में बारकोड ऊँचाई बदलने का तरीका – पूर्ण गाइड](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [बारकोड जेनरेटर उदाहरण – कस्टम ऊँचाई के साथ Planet और RM4SCC बारकोड बनाएं](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [C# में rm4scc बारकोड बनाना और उसकी ऊँचाई नियंत्रित करना](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}