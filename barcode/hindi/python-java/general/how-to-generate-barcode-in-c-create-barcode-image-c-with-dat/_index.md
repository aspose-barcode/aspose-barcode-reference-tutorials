---
category: general
date: 2026-08-22
description: Aspose.BarCode का उपयोग करके C# में बारकोड कैसे जेनरेट करें। चरण‑दर‑चरण
  C# में बारकोड इमेज बनाना सीखें, 2‑D कॉम्पोनेन्ट को डिसेबल करें, और PNG फ़ाइलें सहेजें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: hi
lastmod: 2026-08-22
og_description: C# में Aspose.BarCode के साथ बारकोड कैसे जेनरेट करें। यह ट्यूटोरियल
  दिखाता है कि DataBar Expanded का उपयोग करके, 2‑D घटक को टॉगल करके, C# में बारकोड
  इमेज कैसे बनाएं और PNG फ़ाइलें सहेजें।
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: C# में बारकोड कैसे जनरेट करें – बारकोड इमेज बनाने के लिए पूर्ण गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: C# में बारकोड कैसे जेनरेट करें – DataBar Expanded के साथ C# में बारकोड इमेज
  बनाएं
url: /hi/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में बारकोड कैसे जेनरेट करें – DataBar Expanded के साथ बारकोड इमेज c# बनाएं

C# में बारकोड जेनरेट करना अक्सर आवश्यक होता है जब आपको अपने एप्लिकेशन में मशीन‑रीडेबल डेटा एम्बेड करना हो। यह गाइड आपको Aspose.BarCode लाइब्रेरी का उपयोग करके barcode image c# बनाने, 2‑D कॉम्पोजिट कॉम्पोनेंट को डिसेबल करने, और परिणाम को PNG फ़ाइलों के रूप में सेव करने का तरीका दिखाता है।

आप एक पूर्ण, चलाने योग्य प्रोग्राम, प्रत्येक कॉन्फ़िगरेशन विकल्प की व्याख्या, और आउटपुट को कस्टमाइज़ करने के टिप्स देखेंगे। कोई बाहरी दस्तावेज़ीकरण आवश्यक नहीं है—सिर्फ नीचे दिया गया कोड और एक .NET डेवलपमेंट एनवायरनमेंट।

## आवश्यकताएँ

* .NET 6.0 SDK या बाद का संस्करण स्थापित हो  
* Visual Studio 2022 (या कोई भी IDE जो .NET को सपोर्ट करता हो)  
* Aspose.BarCode for .NET NuGet पैकेज (`Aspose.BarCode`)  

आप निम्नलिखित कमांड से पैकेज जोड़ सकते हैं:

```bash
dotnet add package Aspose.BarCode
```

यह लाइब्रेरी `BarcodeGenerator` क्लास प्रदान करती है जिसका उपयोग इस ट्यूटोरियल में पूरे किया गया है।

## चरण 1: प्रोजेक्ट सेट अप करें और नेमस्पेस इम्पोर्ट करें

एक नया कंसोल एप्लिकेशन बनाएं और आवश्यक नेमस्पेस इम्पोर्ट करें:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` नेमस्पेस में सभी क्लासेज़ हैं जो बारकोड को कॉन्फ़िगर और रेंडर करने के लिए आवश्यक हैं।

## चरण 2: DataBar Expanded बारकोड जेनरेटर को इनिशियलाइज़ करें

पहली कार्यात्मक लाइन **DataBar Expanded** सिम्बोलॉजी के लिए एक `BarcodeGenerator` बनाती है और रॉ डेटा स्ट्रिंग प्रदान करती है। डेटा स्ट्रिंग GS1 एप्लिकेशन आइडेंटिफायर फॉर्मेट `(01)12345678901231` का पालन करती है।

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

जेनरेटर बनाते समय आंतरिक बिटमैप कैनवास आवंटित हो जाता है, जिससे आप रेंडर करने से पहले आकार और रूप-रंग को समायोजित कर सकते हैं।

## चरण 3: मॉड्यूल चौड़ाई (X‑डायमेंशन) निर्धारित करें

X‑डायमेंशन सबसे छोटे बारकोड एलिमेंट की चौड़ाई को नियंत्रित करता है। इसे पिक्सेल में सेट करने से आपको अंतिम इमेज साइज पर सटीक नियंत्रण मिलता है।

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` पिक्सेल का मान स्क्रीन डिस्प्ले के लिए उपयुक्त है; उच्च‑रिज़ॉल्यूशन प्रिंट के लिए इसे बढ़ा सकते हैं।

## चरण 4: 2‑D कॉम्पोजिट कॉम्पोनेंट को डिसेबल करें

DataBar Expanded वैकल्पिक रूप से एक 2‑D कॉम्पोनेंट शामिल कर सकता है जो अतिरिक्त जानकारी ले जाता है। इस कॉम्पोनेंट **बिना** बारकोड जेनरेट करने के लिए, फ़्लैग को `false` सेट करें।

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

कॉम्पोनेंट को डिसेबल करने से दृश्य जटिलता कम होती है और एक छोटा PNG फ़ाइल बनता है।

## चरण 5: 2‑D कॉम्पोनेंट के बिना बारकोड इमेज सेव करें

एक आउटपुट डायरेक्टरी चुनें और इमेज को डिस्क पर लिखें। `BarCodeImageFormat.Png` एनेम एक लॉसलेस PNG फ़ाइल सुनिश्चित करता है।

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

इस कॉल के बाद, `Databar2DComponentDisabled.png` में एक साफ़ DataBar Expanded बारकोड होगा।

## चरण 6: 2‑D कॉम्पोजिट कॉम्पोनेंट को एनेबल करें

यदि आपको अतिरिक्त डेटा लेयर चाहिए, तो फ़्लैग को फिर से एनेबल करें। वही जेनरेटर इंस्टेंस पुनः उपयोग किया जा सकता है, जिससे दूसरा ऑब्जेक्ट बनाने से बचा जा सकता है।

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## चरण 7: 2‑D कॉम्पोनेंट एनेबल के साथ बारकोड इमेज सेव करें

दूसरी इमेज को उसी सेटिंग्स के साथ रेंडर करें, केवल 2‑D फ़्लैग को छोड़कर।

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

अब `Databar2DComponentEnabled.png` में अतिरिक्त 2‑D पैटर्न के साथ बारकोड दिखेगा।

## पूर्ण स्रोत कोड

नीचे दिया गया पूरा स्निपेट `Program.cs` में कॉपी करें और प्रोजेक्ट चलाएँ। प्रोग्राम निर्दिष्ट फ़ोल्डर में दोनों PNG फ़ाइलें बनाता है।

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### अपेक्षित आउटपुट

प्रोग्राम चलाने पर यह प्रिंट करता है:

```
Barcode images generated successfully.
```

और दो फ़ाइलें बनाता है:

* `Databar2DComponentDisabled.png` – 2‑D कॉम्पोनेंट के बिना बारकोड  
* `Databar2DComponentEnabled.png` – 2‑D कॉम्पोनेंट के साथ बारकोड  

किसी भी इमेज व्यूअर में PNG खोलें ताकि दृश्य अंतर की पुष्टि हो सके।

## सामान्य विविधताएँ और किनारे के केस

| स्थिति | समायोजन |
|-----------|------------|
| **विभिन्न सिम्बोलॉजी** | `EncodeTypes.DatabarExpanded` को किसी अन्य वैल्यू से बदलें, जैसे `EncodeTypes.Code128`. |
| **उच्च रिज़ॉल्यूशन** | `XDimension.Pixels` को 4 या 5 तक बढ़ाएँ, या `barcodeGenerator.Parameters.Image` में `Resolution` सेट करें. |
| **अन्य इमेज फॉर्मेट** | `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, या `BarCodeImageFormat.Svg` का उपयोग करें. |
| **वेब ऐप में चलाना** | इमेज बाइट्स को सीधे HTTP रिस्पॉन्स में स्ट्रीम करें, डिस्क पर सेव करने के बजाय. |
| **मेमोरी मैनेजमेंट** | यदि आप .NET Framework को टार्गेट कर रहे हैं तो अनमैनेज्ड रिसोर्सेज़ रिलीज़ करने के लिए जेनरेटर को `using` ब्लॉक में रैप करें. |

## प्रो टिप्स

* **जेनरेटर को पुनः उपयोग करें** – केवल 2‑D फ़्लैग बदलने से ऑब्जेक्ट को फिर से इंस्टैंशिएट करने की जरूरत नहीं पड़ती, जिससे CPU साइकिल बचते हैं।  
* **डेटा वैलिडेट करें** – GS1 डेटा को सटीक लंबाई और चेकसम नियमों का पालन करना चाहिए; अमान्य इनपुट `ArgumentException` फेंकेगा।  
* **बैच प्रोसेसिंग** – डेटा स्ट्रिंग्स के कलेक्शन पर लूप करें, आवश्यकतानुसार 2‑D फ़्लैग टॉगल करें, और प्रत्येक इमेज को यूनिक फ़ाइलनाम के साथ सेव करें।  

## निष्कर्ष

अब आप जानते हैं कि C# में बारकोड कैसे जेनरेट करें और 2‑D कॉम्पोजिट कॉम्पोनेंट पर पूर्ण नियंत्रण के साथ barcode image c# कैसे बनाएं। यह उदाहरण जेनरेटर को इनिशियलाइज़ करने, X‑डायमेंशन को कॉन्फ़िगर करने, कॉम्पोनेंट को टॉगल करने, और PNG फ़ाइलें सेव करने को दर्शाता है। अब आप अन्य सिम्बोलॉजीज़ का अन्वेषण कर सकते हैं, इमेज को PDFs में एम्बेड कर सकते हैं, या बारकोड जेनरेशन को ASP.NET Core सर्विसेज़ में इंटीग्रेट कर सकते हैं।

--- 

*अगले कदम*: QR कोड जेनरेट करने की कोशिश करें, विभिन्न इमेज रिज़ॉल्यूशन के साथ प्रयोग करें, या Aspose.PDF का उपयोग करके जेनरेट किए गए PNG को PDF में एम्बेड करें। ये एक्सटेंशन उसी `BarcodeGenerator` API पर आधारित हैं और आपके वर्कफ़्लो को सुसंगत रखते हैं।

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर करने में मदद करती हैं।

- [Aspose.BarCode for .NET का उपयोग करके DataMatrix बारकोड कैसे जेनरेट करें – चरण‑दर‑चरण गाइड](/barcode/english/net/datamatrix-barcode-configuration/)
- [Aspose.BarCode for .NET का उपयोग करके वन‑डायमेंशनल Databar के लिए बारकोड ऊँचाई कैसे जेनरेट और एडजस्ट करें](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Aspose.BarCode for .NET का उपयोग करके कस्टम एस्पेक्ट रेशियो के साथ Aztec बारकोड कैसे जेनरेट करें](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}