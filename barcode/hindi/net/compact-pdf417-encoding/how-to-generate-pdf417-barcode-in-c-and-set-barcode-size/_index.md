---
category: general
date: 2026-08-22
description: Aspose.BarCode के साथ C# में PDF417 बारकोड बनाना सीखें, बारकोड का आकार
  सेट करें, कॉलम समायोजित करें, और कॉम्पैक्ट मोड सक्षम करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: hi
lastmod: 2026-08-22
og_description: C# में Aspose.BarCode के साथ PDF417 बारकोड जेनरेट करें। यह गाइड दिखाता
  है कि बारकोड का आकार कैसे सेट करें, कॉलम को नियंत्रित करें, और छोटे इमेज के लिए
  कॉम्पैक्ट मोड कैसे सक्षम करें।
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: C# में PDF417 बारकोड बनाएं – आकार, कॉलम और कॉम्पैक्ट मोड सेट करें
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: C# में PDF417 बारकोड कैसे बनाएं और बारकोड का आकार सेट करें
url: /hi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में PDF417 बारकोड कैसे जनरेट करें और बारकोड आकार सेट करें

यदि आपको .NET एप्लिकेशन में **PDF417 बारकोड जनरेट** करने की आवश्यकता है, तो यह गाइड आपको पूरी प्रक्रिया के माध्यम से ले जाएगा। आप देखेंगे कि Aspose.BarCode के साथ **PDF417 कैसे जनरेट करें**, **बारकोड आकार सेट** कैसे समायोजित करें, और एक कॉम्पैक्ट PNG बनाएं जिसे रिपोर्ट या मोबाइल ऐप्स में एम्बेड किया जा सकता है।

बारकोड बनाने के लिए अलग ग्राफ़िक्स एडिटर की आवश्यकता नहीं होती। इस ट्यूटोरियल के अंत तक आपके पास एक पूरी तरह कार्यशील C# मेथड होगा जो आवश्यक सटीक आयामों के साथ PDF417 इमेज बनाता है, जो आगे की प्रोसेसिंग के लिए तैयार है।

## आप क्या सीखेंगे

* Aspose.BarCode लाइब्रेरी को इंस्टॉल और रेफ़रेंस करें।
* एक PDF417 बारकोड जेनरेटर बनाएं और एन्कोडेड टेक्स्ट निर्दिष्ट करें।
* **बारकोड आकार सेट** X‑डायमेंशन और कॉलम काउंट को कॉन्फ़िगर करके।
* सिंबल को छोटा करने के लिए कॉम्पैक्ट (ट्रंकेटेड) मोड सक्षम करें।
* परिणाम को PNG फ़ाइल के रूप में सहेजें।
* असमर्थनीय कोड और अत्यधिक बड़े इमेज जैसी सामान्य समस्याओं का समाधान करें।

### पूर्वापेक्षाएँ

* .NET 6.0 या बाद का संस्करण (API .NET Framework 4.6+ के साथ भी काम करता है)।
* C# और Visual Studio (या कोई भी C# IDE) की बुनियादी परिचितता।
* एक वैध Aspose.BarCode लाइसेंस (नि:शुल्क इवैल्यूएशन परीक्षण के लिए काम करता है)।

> **प्रो टिप:** यदि आप लूप में कई बारकोड जनरेट करने की योजना बना रहे हैं, तो एक ही `BarcodeGenerator` इंस्टेंस को पुन: उपयोग करें और केवल `CodeText` प्रॉपर्टी बदलें। इससे मेमोरी अलोकेशन कम होते हैं।

## Aspose.BarCode के साथ PDF417 बारकोड जनरेट करें

पहला कदम PDF417 सिम्बोलॉजी के लिए `BarcodeGenerator` को इंस्टैंशिएट करना है। यह ऑब्जेक्ट सभी बारकोड ऑपरेशन्स का एंट्री पॉइंट है।

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*यह क्यों महत्वपूर्ण है*: `EncodeTypes.Pdf417` लाइब्रेरी को PDF417 मानक उपयोग करने के लिए बताता है, जो बड़े डेटा वॉल्यूम और एरर करेक्शन को सपोर्ट करता है। कंस्ट्रक्टर भी वह डेटा लेता है जिसे आप एन्कोड करना चाहते हैं, जिससे बाद में अलग `CodeText` असाइनमेंट की आवश्यकता नहीं रहती।

## बारकोड आकार और कॉलम काउंट सेट करें

PDF417 सिम्बॉल छोटे आयताकार मॉड्यूल्स की पंक्तियों और कॉलम्स से बनते हैं। मॉड्यूल की चौड़ाई (X‑डायमेंशन) और कॉलम की संख्या को नियंत्रित करके आप समग्र आयामों को बारीकी से ट्यून कर सकते हैं।

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*व्याख्या*:  
* **X‑डायमेंशन** (`Pixels`) निर्धारित करता है कि प्रत्येक मॉड्यूल कितनी चौड़ी है। छोटे मान एक टाइट बारकोड बनाते हैं, जबकि बड़े मान कम‑रिज़ॉल्यूशन स्कैनर्स पर पढ़ने की क्षमता बढ़ाते हैं।  
* **Columns** क्षैतिज लेआउट को नियंत्रित करते हैं। कम कॉलम बारकोड को लंबा बनाते हैं; अधिक कॉलम इसे चौड़ा बनाते हैं। इन दो सेटिंग्स को साथ में समायोजित करें ताकि आपको आवश्यक सटीक **बारकोड आकार सेट** मिल सके।

## छोटे बारकोड के लिए कॉम्पैक्ट मोड सक्षम करें

PDF417 में एक “कॉम्पैक्ट” (या ट्रंकेटेड) मोड शामिल है जो अनावश्यक पैडिंग को हटाता है और कुल फ़ुटप्रिंट को कम करता है। यह विशेष रूप से तब उपयोगी है जब स्क्रीन स्पेस सीमित हो।

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*ट्रंकेशन क्यों सक्षम करें?*  
जब `Truncate` `true` होता है, तो जेनरेटर स्टॉप पैटर्न और कुछ एरर‑करेक्शन कोडवर्ड्स को छोड़ देता है जो अधिकांश स्कैनिंग परिदृश्यों के लिए आवश्यक नहीं होते। परिणामी इमेज लगभग 15‑20 % छोटी होती है, बिना सामान्य उपयोग मामलों के लिए डेटा इंटेग्रिटी को नुकसान पहुँचाए।

## बारकोड को PNG इमेज के रूप में सहेजें

आकार और मोड कॉन्फ़िगर करने के बाद, बारकोड को डिस्क पर लिखें। PNG लॉसलेस है, जिससे मॉड्यूल किनारे तेज़ रहते हैं।

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

`CompactPdf417.png` फ़ाइल में एक स्पष्ट PDF417 सिम्बॉल होगा जो पिछले चरणों में सेट किए गए आयामों से मेल खाता है।

### अपेक्षित आउटपुट

सेव किए गए PNG को खोलने पर एक वर्टिकल‑ओरिएंटेड PDF417 बारकोड दिखना चाहिए, जिसमें तीन कॉलम हों, प्रत्येक मॉड्यूल 2 px चौड़ा हो, और कुल आकार लगभग **120 × 240 px** (चौड़ाई × ऊँचाई) हो। किसी भी मानक PDF417 रीडर से इमेज स्कैन करने पर मूल टेक्स्ट “Sample text for PDF417” प्राप्त होगा।

## सामान्य समस्याएँ और उन्हें कैसे टालें

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| बारकोड पढ़ा नहीं जा रहा | स्कैनर के लिए X‑डायमेंशन बहुत छोटा | `XDimension.Pixels` को 3 या 4 बढ़ाएँ |
| इमेज UI के लिए बहुत चौड़ी है | बहुत अधिक कॉलम सेट किए गए | `Pdf417.Columns` को कम करें या `Truncate` सक्षम करें |
| Exception `ArgumentOutOfRangeException` | नकारात्मक या शून्य कॉलम काउंट | `Columns` एक सकारात्मक पूर्णांक (न्यूनतम 1) हो, यह सुनिश्चित करें |
| PNG फ़ाइल खाली है | आउटपुट पाथ मौजूद नहीं है या लिखने की अनुमति नहीं है | डायरेक्टरी मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है, यह जांचें |

> **प्रो टिप:** `Save()` कॉल करने से पहले `barcodeGenerator.ValidateParameters()` का उपयोग करें ताकि कॉन्फ़िगरेशन त्रुटियों को जल्दी पकड़ सकें।

## पूर्ण, चलाने योग्य उदाहरण

नीचे एक स्व-निहित कंसोल प्रोग्राम है जो ऊपर बताए गए सभी चरणों को सम्मिलित करता है। इसे एक नए C# प्रोजेक्ट में कॉपी करें, Aspose.BarCode NuGet पैकेज को रिस्टोर करें, और परिणाम देखने के लिए चलाएँ।

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**प्रोग्राम चलाने** से `CompactPdf417.png` निष्पादन योग्य की कार्य निर्देशिका में बनता है। इमेज को मोबाइल ऐप (जैसे, “Barcode Scanner”) से स्कैन करें ताकि एन्कोडेड टेक्स्ट स्रोत स्ट्रिंग से मेल खाता हो, यह सत्यापित हो सके।

## अगले कदम और संबंधित विषय

* **Error correction level बढ़ाएँ** – शोरयुक्त स्कैन वाले वातावरण के लिए `Pdf417.ErrorLevel` को समायोजित करें।  
* **Orientation बदलें** – यदि आपको क्षैतिज लेआउट चाहिए तो `Pdf417.Rotate` को `RotationAngle.Rotate90` सेट करें।  
* **बारकोड को PDF में एम्बेड करें** – Aspose.PDF को Aspose.BarCode के साथ मिलाकर इमेज को सीधे दस्तावेज़ में रखें।  
* **अन्य 2‑D बारकोड जनरेट करें** – वही `BarcodeGenerator` क्लास DataMatrix, QR, और Aztec कोड्स को सपोर्ट करता है; केवल `EncodeTypes.Pdf417` को इच्छित सिम्बोलॉजी से बदलें।

**PDF417 बारकोड जनरेट** तकनीकों में निपुण होकर, आप टिकटिंग, इन्वेंटरी लेबलिंग, और सुरक्षित डेटा ट्रांसमिशन को विभिन्न .NET एप्लिकेशन्स में स्वचालित कर सकते हैं।

## निष्कर्ष

अब आप जानते हैं कि C# में **PDF417 बारकोड जनरेट** कैसे करें, सटीक **बारकोड आकार सेट** करें, कॉलम कॉन्फ़िगर करें, कॉम्पैक्ट मोड सक्षम करें, और परिणाम को PNG के रूप में सहेजें। इन सेटिंग्स को किसी भी UI प्रतिबंध या स्कैनिंग आवश्यकता के अनुसार लागू करें, और आवश्यकता अनुसार अन्य बारकोड फ़ॉर्मैट्स में इस दृष्टिकोण को विस्तारित करें। कोडिंग का आनंद लें!

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जो आपको अतिरिक्त API फीचर्स में निपुण होने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को खोजने में मदद करेंगे।

- [PDF417 बारकोड कैसे जनरेट करें – कॉम्पैक्ट PDF417 एन्कोडिंग](/barcode/english/net/compact-pdf417-encoding/)
- [बारकोड कैसे बनाएं – Aspose.BarCode के साथ कॉम्पैक्ट PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Aspose.BarCode for .NET का उपयोग करके DataMatrix बारकोड कैसे जनरेट करें – चरण‑दर‑चरण गाइड](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}