---
category: general
date: 2026-08-15
description: BarCodeReader का उपयोग करके C# में छवि से बारकोड पढ़ें। जानें कि C# में
  कई बारकोड कैसे पढ़ें, PDF417 बारकोड कैसे पढ़ें, और एक पूर्ण C# BarCodeReader उदाहरण
  देखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: hi
lastmod: 2026-08-15
og_description: C# में इमेज से बारकोड पढ़ें, चरण‑दर‑चरण गाइड के साथ। जानें कैसे कई
  बारकोड C# में पढ़ें, PDF417 प्रतीकों को डिकोड करें, और एक पूर्ण C# BarCodeReader
  उदाहरण चलाएँ।
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: C# में छवि से बारकोड पढ़ें – BarCodeReader ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: C# में छवि से बारकोड पढ़ें – BarCodeReader ट्यूटोरियल
url: /hi/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में इमेज से बारकोड पढ़ें – BarCodeReader ट्यूटोरियल

यदि आपको .NET एप्लिकेशन में **इमेज से बारकोड पढ़ना** है, तो यह गाइड आपको `BarCodeReader` क्लास के साथ यह कैसे करना है, बिल्कुल दिखाएगा। आप यह भी देखेंगे कि **C# में कई बारकोड कैसे पढ़ें**, PDF417 सिंबल को डिकोड करें, और एक पूरा **C# BarCodeReader उदाहरण** प्राप्त करें जिसे आप अपने प्रोजेक्ट में कॉपी कर सकते हैं।

ट्यूटोरियल हर कदम को कवर करता है—आवश्यक NuGet पैकेज जोड़ने से लेकर विस्तारित PDF417 फ़ील्ड प्रिंट करने तक—ताकि आप एक चलाने योग्य कंसोल प्रोग्राम के साथ समाप्त हो सकें। कोई बाहरी दस्तावेज़ीकरण आवश्यक नहीं है; सभी कोड और व्याख्याएँ शामिल हैं।

## आपको क्या चाहिए

* .NET 6.0 SDK या बाद का (कोड .NET Core और .NET Framework के साथ काम करता है)
* Visual Studio 2022 या कोई भी C#‑compatible एडिटर
* `Aspose.BarCode` NuGet पैकेज (या समकक्ष लाइब्रेरी जो `BarCodeReader` प्रदान करती है)
* एक इमेज फ़ाइल जिसमें Macro PDF417 बारकोड हो (उदाहरण के लिए `ExtPDF417Meta.png`)

इन आवश्यकताओं को पूरा करने से यह सुनिश्चित होता है कि सैंपल अतिरिक्त कॉन्फ़िगरेशन के बिना कंपाइल हो जाता है।

## BarCodeReader के साथ इमेज से बारकोड पढ़ें

पहला कदम एक `BarCodeReader` इंस्टेंस बनाना है जो इमेज फ़ाइल की ओर इशारा करता है और लाइब्रेरी को बताता है कि किस बारकोड प्रकार को देखना है।

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**यह क्यों काम करता है:**  
`BarCodeReader` इमेज को खोलता है, निर्दिष्ट `DecodeType` के लिए स्कैन करता है, और `BarCodeResult` ऑब्जेक्ट्स का एक संग्रह लौटाता है। प्रत्येक परिणाम में सामान्य बारकोड डेटा (`CodeTypeName`, `CodeText`) और Macro PDF417 के लिए एक `Extended.Pdf417` ऑब्जेक्ट होता है जो मानक द्वारा परिभाषित सभी अतिरिक्त फ़ील्ड को उजागर करता है।

## एक इमेज में कई बारकोड C# में पढ़ें

कभी-कभी एक इमेज में एक से अधिक बारकोड होते हैं (उदाहरण के लिए, PDF417 के बगल में QR कोड)। इस स्थिति को संभालने के लिए, बस स्पष्ट `DecodeType` को छोड़ दें या `DecodeType.AllSupported` पास करें और परिणामों पर लूप करें।

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**आपको यह क्यों चाहिए:**  
`AllSupported` निर्दिष्ट करने से इंजन को वह सभी बारकोड फ़ॉर्मेट आज़माने को कहा जाता है जो उसे पता है, जिससे यह सुनिश्चित होता है कि आप इमेज में हर सिम्बल को कैप्चर कर लें। यह अनुशंसित तरीका है जब आप पहले से बारकोड प्रकारों की भविष्यवाणी नहीं कर सकते।

## C# का उपयोग करके PDF417 बारकोड कैसे पढ़ें

यदि आपको केवल क्लासिक PDF417 (नॉन‑मैक्रो) फ़ॉर्मेट की परवाह है, तो `DecodeType` को `Pdf417` में बदल दें। बाकी कोड समान रहता है, सिवाय इसके कि विस्तारित फ़ील्ड उपलब्ध नहीं होते।

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**यह क्यों महत्वपूर्ण है:**  
क्लासिक PDF417 मैक्रो‑विशिष्ट प्रॉपर्टीज़ को उजागर नहीं करता, इसलिए `Extended.Pdf417` ब्लॉक की आवश्यकता नहीं है। सटीक `DecodeType` का उपयोग करने से स्कैनिंग तेज़ हो जाती है क्योंकि लाइब्रेरी असमर्थित एल्गोरिदम को छोड़ देती है।

## पूर्ण C# BarCodeReader उदाहरण जिसे आप कॉपी कर सकते हैं

नीचे पूर्ण प्रोग्राम दिया गया है जो तीनों परिदृश्यों को एक ही, चलाने में आसान कंसोल एप्लिकेशन में जोड़ता है। `YOUR_DIRECTORY/ExtPDF417Meta.png` को अपनी इमेज के वास्तविक पथ से बदलें।

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### अपेक्षित आउटपुट

जब सैंपल इमेज में Macro PDF417 बारकोड होता है, तो कंसोल कुछ इस तरह प्रिंट करता है:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

यदि इमेज में केवल सामान्य PDF417 है, तो “Macro PDF417” सेक्शन खाली रहेगा, और “Classic PDF417” सेक्शन डिकोड किया हुआ टेक्स्ट दिखाएगा।

## निष्कर्ष

अब आप जानते हैं कि C# में `BarCodeReader` का उपयोग करके **इमेज से बारकोड कैसे पढ़ें**, एक फ़ाइल में **C# में कई बारकोड कैसे पढ़ें**, और **PDF417 बारकोड कैसे पढ़ें**—मैक्रो और क्लासिक दोनों वेरिएंट। पूर्ण **C# BarCodeReader उदाहरण** किसी भी .NET प्रोजेक्ट में पेस्ट करने के लिए तैयार है, और आप इसे अन्य फ़ॉर्मेट को संभालने या बड़े इमेज‑प्रोसेसिंग पाइपलाइन में एकीकृत करने के लिए विस्तारित कर सकते हैं।

**अगले कदम**

* `try / catch` जैसे error‑handling पैटर्न को रीडर ब्लॉक के आसपास एक्सप्लोर करें।  
* `ReaderParameters` ऑब्जेक्ट के साथ प्रयोग करके डिटेक्शन स्पीड और एक्यूरेसी को ट्यून करें।  
* बारकोड रीडिंग को इमेज प्री‑प्रोसेसिंग लाइब्रेरीज़ के साथ संयोजित करें (

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोच को एक्सप्लोर करने में मदद करती हैं।

- [Aspose.BarCode for .NET के साथ DataMatrix बारकोड कैसे पढ़ें](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix बारकोड C# पढ़ें – DataMatrix मोड (ऑटो) जेनरेट करें](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [इमेज से बारकोड पढ़ें – Java में Aspose.BarCode के साथ बारकोड रीजन एक्सट्रैक्शन में महारत हासिल करें](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}