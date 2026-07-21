---
category: general
date: 2026-07-21
description: Aspose.BarCode के साथ C# में जल्दी से बारकोड बनाएं। DataBar बारकोड बनाना
  सीखें, बारकोड का आकार अनुकूलित करें, और कुछ ही चरणों में बारकोड छवि निर्यात करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: hi
lastmod: 2026-07-21
og_description: Aspose.BarCode का उपयोग करके C# में बारकोड जनरेट करें। DataBar बारकोड
  बनाएं, उसका आकार कस्टमाइज़ करें, और तुरंत इमेज निर्यात करें।
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: बारकोड जेनरेट करें C# – कस्टम आकार के साथ DataBar बारकोड बनाएं
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: बारकोड जेनरेट करें C# – DataBar बारकोड बनाएं
url: /hi/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बारकोड C# जनरेट करें – DataBar बारकोड बनाएं

क्या आप **बारकोड C# जनरेट** करना चाहते हैं बिना अनगिनत दस्तावेज़ों में उलझे? आप सही जगह पर हैं। इस गाइड में हम **DataBar बारकोड** बनाने, उसकी आयामों को समायोजित करने, और अंत में **बारकोड छवि निर्यात** करने की प्रक्रिया को कुछ ही C# लाइनों में दिखाएंगे।

कल्पना करें कि आपको एक छोटा प्रोडक्ट लेबल चाहिए जो एक छोटे शेल्फ टैग पर फिट हो। DataBar Expanded Stacked सिंबोलॉजी इस काम के लिए उपयुक्त है, और Aspose.BarCode के साथ आप ठीक‑ठीक तय कर सकते हैं कि कितनी कॉलम या रो उपयोग हों। तैयार हैं? चलिए शुरू करते हैं।

## आप क्या हासिल करेंगे

- **DataBar बारकोड** ( “expanded stacked” वैरिएंट) को शून्य से बनाना।  
- **बारकोड का आकार** कॉलम या रो सेट करके कस्टमाइज़ करना।  
- जनरेटर को पुनः बनाये बिना **बारकोड के आयाम** को बदलना।  
- **बारकोड छवि** को PNG (या Aspose द्वारा सपोर्ट किए किसी भी फॉर्मेट) में एक्सपोर्ट करना।  

कोई बाहरी सर्विस नहीं, कोई जटिल कॉन्फ़िगरेशन नहीं—सिर्फ साफ़, चलने योग्य C# कोड।

## पूर्वापेक्षाएँ

- .NET 6.0 या बाद का संस्करण (कोड .NET Framework 4.7+ पर भी काम करता है)।  
- एक वैध Aspose.BarCode for .NET लाइसेंस (या ट्रायल मोड में चलाएँ)।  
- आपका पसंदीदा IDE—Visual Studio, Rider, या VS Code।  

यदि आपने अभी तक NuGet पैकेज इंस्टॉल नहीं किया है, तो चलाएँ:

```bash
dotnet add package Aspose.BarCode
```

बस इतना ही—और कोई निर्भरताएँ नहीं।

## चरण 1: बारकोड जेनरेटर सेट अप करें (कैसे **generate barcode C#** करें)

सबसे पहले, हमें **DataBar Expanded Stacked** सिंबोलॉजी की ओर इशारा करने वाला `BarcodeGenerator` इंस्टेंस चाहिए। यह ऑब्जेक्ट बाद में इमेज बनाने का इंजन है।

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*क्यों महत्वपूर्ण है*: `EncodeTypes.DatabarExpandedStacked` एनेम Aspose को बताता है कि हमें स्टैक्ड वर्ज़न चाहिए, जो संकरी जगहों के लिए आदर्श है। हम जो टेक्स्ट पास करते हैं वह एन्कोडेड वैल्यू बन जाता है; आप इसे अपनी एप्लिकेशन की आवश्यकता अनुसार किसी भी न्यूमेरिक स्ट्रिंग से बदल सकते हैं।

## चरण 2: **बारकोड का आकार** कस्टमाइज़ करें – कॉलम सेट करें

DataBar बारकोड आपको **कॉलम** या **रो** में से किसी एक को निर्दिष्ट करके विज़ुअल डेंसिटी को नियंत्रित करने की अनुमति देता है। पहले कॉलम सेट करते हैं। रो काउंट स्वचालित रूप से वैध बारकोड रखने के लिए गणना की जाएगी।

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*प्रो टिप*: कॉलम बारकोड की चौड़ाई को प्रभावित करते हैं। अधिक कॉलम → चौड़ा बारकोड, जो लो‑रेज़ोल्यूशन प्रिंटर पर स्कैन विश्वसनीयता को बढ़ा सकता है।

## चरण 3: **बारकोड छवि** को कॉलम सेटिंग के साथ एक्सपोर्ट करें

अब हम इमेज को डिस्क पर लिखते हैं। आप PNG, JPEG, BMP, या यहाँ तक कि SVG भी चुन सकते हैं। यहाँ PNG का उपयोग किया गया है क्योंकि यह क्रिस्प और लॉसलेस आउटपुट देता है।

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **अपेक्षित परिणाम** – `DatabarCols4.png` खोलें और आपको चार कॉलम वाला एक व्यवस्थित स्टैक्ड DataBar दिखेगा। यह ऊर्ध्वाधर बारों का घना स्टैक जैसा दिखता है, छोटे लेबल के लिए एकदम उपयुक्त।

## चरण 4: **बारकोड के आयाम** बदलें – रो सेट करें

कभी‑कभी आपको चौड़ाई के बजाय ऊँचा बारकोड चाहिए होता है। रो कंट्रोल पर स्विच करें; Aspose स्वचालित रूप से कॉलम को पुनः गणना करेगा।

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*क्यों बदलें?* रो बारकोड की ऊँचाई को प्रभावित करती हैं। अधिक रो → प्रतीक ऊँचा, जो तब उपयोगी होता है जब आपके पास ऊर्ध्वाधर जगह अधिक हो लेकिन चौड़ाई सीमित हो।

## चरण 5: **बारकोड छवि** को रो सेटिंग के साथ एक्सपोर्ट करें

दूसरी वैरिएशन को सेव करें। फ़ाइलनाम में बदलाव को देखें; आप तुलना के लिए दोनों इमेज रख सकते हैं।

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **परिणाम** – `DatabarRows3.png` अब उसी डेटा का ऊँचा संस्करण दिखाता है, फिर भी पूरी तरह स्कैन करने योग्य।

## पूर्ण कार्यशील उदाहरण

सब कुछ एक साथ मिलाकर, यहाँ एक स्व-निहित कंसोल एप्लिकेशन है जिसे आप कॉपी‑पेस्ट करके तुरंत चला सकते हैं:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

प्रोग्राम चलाएँ, फिर दो PNG फ़ाइलें खोलें। आपने अब **बारकोड C# जनरेट** किया, **बारकोड का आकार कस्टमाइज़** किया, **बारकोड के आयाम बदले**, और **बारकोड छवि एक्सपोर्ट** की—सभी एक मिनट से भी कम समय में।

## सामान्य प्रश्न एवं किनारे के मामलों

- **यदि मुझे अलग इमेज फॉर्मेट चाहिए?**  
  `BarCodeImageFormat.Png` को `Jpeg`, `Bmp`, `Gif`, या `Svg` से बदलें। API स्वचालित रूप से रूपांतरण संभाल लेगा।

- **क्या मैं एक साथ दोनों रो और कॉलम बदल सकता हूँ?**  
  तकनीकी रूप से आप दोनों सेट कर सकते हैं, लेकिन Aspose अंतिम सेट की गई प्रॉपर्टी को प्राथमिकता देगा। वैध DataBar के लिए एक आयाम सेट करें और लाइब्रेरी को दूसरा गणना करने देना सुरक्षित रहता है।

- **फ़ोरग्राउंड/बैकग्राउंड रंग कैसे लागू करें?**  
  `barcodeGen.Parameters.Barcode.ForegroundColor` और `BackgroundColor` का उपयोग करें। उदाहरण:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **एन्कोडेड डेटा का आकार सीमा क्या है?**  
  DataBar Expanded Stacked अधिकतम 74 न्यूमेरिक कैरेक्टर (या 30 अल्फ़ान्यूमेरिक) सपोर्ट करता है। इससे अधिक होने पर एक्सेप्शन फेंका जाएगा।

## अगले कदम

अब जब आप **create databar barcode** की बुनियादें समझ गए हैं, तो विचार करें:

- बारकोड के नीचे **टेक्स्ट एनोटेशन** जोड़ें (`barcodeGen.Parameters.CaptionAbove.Text`)।  
- PNG को सीधे PDF में एम्बेड करें Aspose.PDF का उपयोग करके।  
- CSV में प्रोडक्ट आईडी की सूची पर लूप करके बारकोड को बल्क में जनरेट करें।

इन सभी विषयों में वही `BarcodeGenerator` ऑब्जेक्ट उपयोग होता है, इसलिए आपको फिर से शुरू नहीं करना पड़ेगा।

---

**निष्कर्ष**: अब आप जानते हैं कैसे **बारकोड C# जनरेट** करें, **बारकोड का आकार कस्टमाइज़** करें, **बारकोड के आयाम बदलें**, और **बारकोड छवि एक्सपोर्ट** करें Aspose.BarCode के साथ। कॉलम/रो वैल्यू के साथ प्रयोग करें, इमेज फॉर्मेट बदलें, और कोड को अपने इन्वेंट्री या POS सिस्टम में इंटीग्रेट करें। कोडिंग का आनंद लें!

## अगला क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर में महारत हासिल कर सकते हैं और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोच को एक्सप्लोर कर सकते हैं।

- [बारकोड छवि उत्पन्न करें – GS1 कूपन UPC‑A डेटाबार](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Aspose.BarCode for .NET के साथ कस्टम एस्पेक्ट रेशियो वाला Aztec बारकोड कैसे जनरेट करें](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [DataMatrix बारकोड जनरेट करें – Aspose.BarCode के साथ प्रो गाइड](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}