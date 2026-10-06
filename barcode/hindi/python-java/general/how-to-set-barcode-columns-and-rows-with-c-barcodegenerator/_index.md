---
category: general
date: 2026-09-16
description: C# में BarcodeGenerator का उपयोग करके बारकोड कॉलम कैसे सेट करें और DataBar
  Expanded Stacked बारकोड के लिए बारकोड पंक्तियों को भी सेट करना सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: hi
lastmod: 2026-09-16
og_description: C# में बारकोड कॉलम जल्दी सेट करें। यह गाइड दिखाता है कि आप BarcodeGenerator
  के साथ कॉलम, पंक्तियों और इमेज फ़ॉर्मेट को कैसे कॉन्फ़िगर कर सकते हैं।
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: C# में बारकोड कॉलम और पंक्तियों को सेट करें – पूरा BarcodeGenerator गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C# BarcodeGenerator के साथ बारकोड कॉलम और रो कैसे सेट करें
url: /hi/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# BarcodeGenerator के साथ बारकोड कॉलम और रो सेट कैसे करें

यदि आपको C# एप्लिकेशन में बारकोड कॉलम सेट करने की आवश्यकता है, तो यह ट्यूटोरियल आवश्यक चरणों को दिखाता है। आप देखेंगे कि DataBar Expanded Stacked बारकोड के लिए कॉलम और रो दोनों को कैसे कॉन्फ़िगर करें, फिर परिणाम को PNG इमेज के रूप में सहेजें।

बारकोड को प्रोग्रामेटिकली जेनरेट करने से मैन्युअल डिज़ाइन कार्य से बचा जा सकता है और रिपोर्ट, इनवॉइस और प्रोडक्ट लेबल्स में स्थिरता सुनिश्चित होती है। नीचे दिया गया उदाहरण पूरी वर्कफ़्लो को कवर करता है, लाइब्रेरी को इंस्टॉल करने से लेकर दो इमेजेज़ बनाने तक—एक कस्टम कॉलम काउंट के साथ और दूसरा कस्टम रो काउंट के साथ।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* .NET 6.0 या बाद का संस्करण इंस्टॉल किया हुआ।
* **Aspose.BarCode for .NET** NuGet पैकेज का रेफ़रेंस। इसे इस कमांड से इंस्टॉल करें:

```bash
dotnet add package Aspose.BarCode
```

* उस फ़ोल्डर में लिखने की अनुमति जहाँ जेनरेट की गई PNG फ़ाइलें सहेजी जाएँगी।

इन आवश्यकताओं से कोड बिना अतिरिक्त कॉन्फ़िगरेशन के कंपाइल और रन करेगा।

## C# में बारकोड कॉलम कैसे सेट करें

पहला मुख्य कदम **DataBar Expanded Stacked** सिंबोलॉजी के लिए `BarcodeGenerator` इंस्टेंस बनाना और इच्छित कॉलम काउंट असाइन करना है।

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**यह क्यों काम करता है:**  
`EncodeTypes.DatabarExpandedStacked` लाइब्रेरी को बताता है कि कौन सी सिंबोलॉजी रेंडर करनी है। `Parameters.Barcode.DataBar.Columns` सेट करने से आंतरिक मॉड्यूल लेआउट बदलता है, जो सीधे बारकोड की दृश्य चौड़ाई को प्रभावित करता है। `Save` मेथड इमेज को डिस्क पर निर्दिष्ट `BarCodeImageFormat` में लिखता है।

### Expected result
`C:\Barcodes\DatabarCols4.png` को किसी भी इमेज व्यूअर में खोलें। आपको एक DataBar Expanded Stacked बारकोड दिखेगा जो डिफ़ॉल्ट से चौड़ा है क्योंकि इसमें चार कॉलम उपयोग किए गए हैं।

## C# में बारकोड रो कैसे सेट करें

कॉलम‑आधारित इमेज सहेजने के बाद, आप रो को समायोजित करके ऊँचाई बदलना चाह सकते हैं। प्रक्रिया कॉलम कॉन्फ़िगरेशन के समान है, लेकिन `Rows` प्रॉपर्टी का उपयोग करती है।

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**यह क्यों काम करता है:**  
जेनरेटर को फिर से इनिशियलाइज़ करने से पहले की कॉलम सेटिंग रो कॉन्फ़िगरेशन में बाधा नहीं बनती। `Parameters.Barcode.DataBar.Rows` बदलने से बारकोड की ऊँचाई बदलती है, और जब रो काउंट डिफ़ॉल्ट से अधिक होता है तो इमेज लंबी बनती है।

### Expected result
`C:\Barcodes\DatabarRows3.png` खोलें। बारकोड लंबा दिखेगा, जो तीन‑रो कॉन्फ़िगरेशन को दर्शाता है।

## पूर्ण एंड‑टू‑एंड उदाहरण

नीचे एक ही प्रोग्राम दिया गया है जो एक ही रन में दोनों इमेज बनाता है। कोड को एक फ़ाइल में रखने से आप एप्लिकेशन को रीस्टार्ट किए बिना कॉलम और रो कॉन्फ़िगरेशन के बीच स्विच कर सकते हैं।

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

प्रोग्राम चलाने पर दो PNG फ़ाइलें बनती हैं:

* **DatabarCols4.png** – चार कॉलम वाला बारकोड।  
* **DatabarRows3.png** – तीन रो वाला बारकोड।

दोनों फ़ाइलें **बारकोड इमेज फ़ॉर्मेट** PNG का उपयोग करती हैं, जो तेज़ किनारे बनाए रखती हैं और लॉसलेस कम्प्रेशन सपोर्ट करती हैं—प्रिंटिंग और डिजिटल डिस्प्ले दोनों के लिए आदर्श।

## सामान्य प्रश्न और टिप्स

| Question | Answer |
|----------|--------|
| *Can I use JPEG instead of PNG?* | हाँ। `BarCodeImageFormat.Png` को `BarCodeImageFormat.Jpeg` से बदल दें। JPEG फ़ाइल आकार छोटा करता है लेकिन कम्प्रेशन आर्टिफैक्ट्स जोड़ता है, जो स्कैनर की विश्वसनीयता को प्रभावित कर सकते हैं। |
| *What is the maximum number of columns or rows?* | लाइब्रेरी DataBar स्पेसिफ़िकेशन के विरुद्ध मानों को वैलिडेट करती है। अनुमत रेंज से बाहर के मान `ArgumentException` फेंकते हैं। सटीक लिमिट्स के लिए Aspose.BarCode दस्तावेज़ देखें। |
| *Do I need to dispose the `BarcodeGenerator`?* | यह क्लास `IDisposable` को इम्प्लीमेंट करती है। यदि आप लूप में कई इंस्टेंस बनाते हैं तो अनमैनेज्ड रिसोर्सेज़ को तुरंत मुक्त करने के लिए `using` ब्लॉक में जेनरेटर को रैप करें। |
| *How do I change the barcode size without altering columns/rows?* | `barcodeGenerator.Parameters.Image.Width` और `Height` का उपयोग करके आउटपुट इमेज को स्केल करें, जबकि मॉड्यूल लेआउट अपरिवर्तित रहे। |

**Pro tip:** हाई‑रेज़ोल्यूशन प्रिंटिंग के लिए बारकोड जेनरेट करते समय कॉलम या रो काउंट बढ़ाने के बजाय आउटपुट इमेज डायमेंशन (`Width`/`Height`) बढ़ाएँ। यह सिंबोलॉजी द्वारा परिभाषित मानक मॉड्यूल साइज को बनाए रखता है और आपको तेज़ इमेज देता है।

## निष्कर्ष

अब आप **BarcodeGenerator** क्लास का उपयोग करके C# में बारकोड कॉलम और रो सेट करना जानते हैं। इस गाइड में जेनरेटर को इनिशियलाइज़ करना, कॉलम और रो काउंट कॉन्फ़िगर करना, PNG फ़ॉर्मेट में बारकोड सहेजना, और इमेज फ़ॉर्मेट बदलने तथा रिसोर्स डिस्पोज़ल जैसे सामान्य वैरिएशन को हैंडल करना शामिल था।

अब आगे **बारकोड रंग कस्टमाइज़ करना**, **ह्यूमन‑रीडेबल टेक्स्ट जोड़ना**, और **बारकोड को PDF दस्तावेज़ में एम्बेड करना** जैसे विषयों को एक्सप्लोर करें। ये सभी एक्सटेंशन उसी कॉन्फ़िगरेशन पैटर्न पर आधारित हैं, जिससे आप किसी भी .NET एप्लिकेशन के लिए पूर्ण फीचर वाले बारकोड समाधान बना सकते हैं।

## What Should You Learn Next?

नीचे दिए गए ट्यूटोरियल्स उसी तकनीक पर आधारित हैं और आपको अतिरिक्त API फीचर्स सीखने तथा विभिन्न इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करेंगे:

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}