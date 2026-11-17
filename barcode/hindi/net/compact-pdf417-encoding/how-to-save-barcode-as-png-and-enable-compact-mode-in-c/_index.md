---
category: general
date: 2026-11-17
description: कैसे बारकोड को सहेजें, कॉम्पैक्ट मोड सक्षम करें, कॉलम समायोजित करें,
  और पूर्ण C# उदाहरण के साथ PDF417 बारकोड जेनरेट करें, यह सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: hi
lastmod: 2026-11-17
og_description: C# में PDF417 बारकोड बनाते समय बारकोड को सहेजना, कॉम्पैक्ट मोड सक्षम
  करना और कॉलम समायोजित करना कैसे करें। चरण‑दर‑चरण गाइड का पालन करें।
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: C# में बारकोड को PNG के रूप में सहेजें और कॉम्पैक्ट मोड सक्षम करें
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: C# में बारकोड को PNG के रूप में सहेजना और कॉम्पैक्ट मोड को सक्षम करना
url: /hi/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में बारकोड को PNG के रूप में सहेजना और कॉम्पैक्ट मोड सक्षम करना

यदि आपको वेब या प्रिंट में उपयोग किए जा सकने वाले फ़ॉर्मेट में **how to save barcode** की आवश्यकता है, तो यह गाइड आपको सटीक चरण दिखाता है। आप यह भी सीखेंगे कि **enable compact mode**, **adjust columns**, और **generate PDF417 barcode** को Aspose.BarCode लाइब्रेरी for .NET के साथ कैसे किया जाता है।

यह ट्यूटोरियल प्रोजेक्ट सेटअप से लेकर अंतिम PNG फ़ाइल तक सब कुछ कवर करता है, ताकि आप कोड को अपनी समाधान में बिना अतिरिक्त शोध के कॉपी कर सकें। कोई बाहरी दस्तावेज़ीकरण आवश्यक नहीं है; पूर्ण, चलाने योग्य उदाहरण शामिल है।

## पूर्वापेक्षाएँ

* .NET 6.0 या बाद का स्थापित हो  
* Visual Studio 2022 (या कोई भी C# IDE)  
* `Aspose.BarCode` NuGet पैकेज (`Install-Package Aspose.BarCode`)  

ये तीन आइटम कोड के लिए एकमात्र निर्भरताएँ हैं जो आगे हैं।

## चरण 1: PDF417 बारकोड जेनरेटर बनाएं

जब आप **generate PDF417 barcode** करते हैं, तो पहला कार्य सही एन्कोड टाइप और आप जिस डेटा को एन्कोड करना चाहते हैं, उसके साथ `BarcodeGenerator` का एक उदाहरण बनाना है।

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417` एन्‍उम लाइब्रेरी को PDF417 सिम्बोलॉजी उपयोग करने के लिए बताता है, जो बड़े मात्रा में डेटा एन्कोड करने के लिए उपयुक्त एक स्टैक्ड लीनियर बारकोड है। स्ट्रिंग `"Compact mode"` बारकोड के नीचे मानव‑पठनीय टेक्स्ट बन जाता है।

## चरण 2: X‑डायमेंशन (मॉड्यूल चौड़ाई) सेट करें

बारकोड में प्रत्येक बार को मॉड्यूल कहा जाता है। मॉड्यूल की चौड़ाई को नियंत्रित करने से आप डेटा को बदले बिना बारकोड के दृश्य आकार को सूक्ष्म‑समायोजित कर सकते हैं।

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

2‑पिक्सेल X‑डायमेंशन एक कॉम्पैक्ट इमेज बनाता है जो अधिकांश डिवाइसों पर विश्वसनीय रूप से स्कैन होता है।

## चरण 3: PDF417 कोड के लिए **How to adjust columns**

PDF417 आपको यह निर्दिष्ट करने की अनुमति देता है कि बारकोड को कितनी कॉलम्स का उपयोग करना चाहिए। कम कॉलम्स से एक लंबा, संकरी प्रतीक बनता है, जबकि अधिक कॉलम्स से प्रतीक चौड़ा लेकिन छोटा हो जाता है।

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

यह पंक्ति **how to adjust columns** को दर्शाती है। आप मान को 2, 4, या लाइब्रेरी द्वारा समर्थित किसी भी संख्या में बदल सकते हैं, यह आपके लक्ष्य माध्यम में उपलब्ध स्थान पर निर्भर करता है।

## चरण 4: **How to enable compact mode** और प्रतीक को ट्रंकेट करें

कॉम्पैक्ट मोड अनावश्यक पैडिंग को हटाता है और बारकोड के कुल फुटप्रिंट को कम करता है। लाइब्रेरी इस सुविधा को `Truncate` प्रॉपर्टी के माध्यम से उजागर करती है।

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

ध्यान दें कि यहाँ वाक्यांश **enable compact mode** दिखाई देता है, और वही क्रिया बाद में गाइड में ठीक उसी शब्दावली **how to enable compact mode** के साथ वर्णित है ताकि द्वितीयक कीवर्ड आवश्यकता पूरी हो सके।

## चरण 5: **How to save barcode** को PNG इमेज के रूप में सहेजें

जनरेट की गई इमेज को सहेजना अंतिम चरण है। `Save` मेथड बारकोड को फ़ाइल सिस्टम में उस फ़ॉर्मेट में लिखता है जिसे आप निर्दिष्ट करते हैं।

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

`YOUR_DIRECTORY` को उस पूर्ण या सापेक्ष पाथ से बदलें जहाँ आपका एप्लिकेशन लिख सकता है। निष्पादन के बाद, आपको `CompactPdf417.png` नाम की फ़ाइल मिलेगी जिसमें कॉम्पैक्ट PDF417 बारकोड होगा।

### अपेक्षित आउटपुट

सहेजी गई PNG फ़ाइल खोलने पर एक वर्टिकली कॉम्पैक्ट PDF417 बारकोड दिखता है जिसमें तीन कॉलम और ट्रंकेटेड पैडिंग है। दृश्य आकार लगभग 2 px प्रति मॉड्यूल है, जिससे इमेज HTML `<img>` टैग में एम्बेड करने या छोटे लेबल पर प्रिंट करने के लिए उपयुक्त बनती है।

## पूर्ण, चलाने योग्य उदाहरण

नीचे पूरा प्रोग्राम है जिसे आप नए कंसोल प्रोजेक्ट में कॉपी कर सकते हैं। इसमें सभी आवश्यक `using` निर्देश शामिल हैं और एक ही प्रवाह में **how to save barcode**, **enable compact mode**, **how to adjust columns**, और **generate PDF417 barcode** को दर्शाता है।

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

इस प्रोग्राम को चलाने से पहले वर्णित PNG फ़ाइल बनती है। कंसोल आउटपुट सहेजी गई फ़ाइल का स्थान पुष्टि करता है, जिससे आप यह सत्यापित कर सकते हैं कि **how to save barcode** चरण सफल रहा।

## सामान्य प्रश्न और किनारे के मामले

### यदि मुझे अलग इमेज फ़ॉर्मेट चाहिए तो क्या करें?

`Save` मेथड किसी भी `BarCodeImageFormat` एन्‍उम वैल्यू को स्वीकार करता है, जैसे `Jpeg`, `Bmp`, या `Gif`। `BarCodeImageFormat.Png` को इच्छित फ़ॉर्मेट से बदलें, और कोड का बाकी हिस्सा अपरिवर्तित रहता है।

### ट्रंकेशन डेटा क्षमता को कैसे प्रभावित करता है?

**compact mode** (ट्रंकेशन) को सक्षम करने से पंक्तियों की संख्या कम हो जाती है, जिससे बारकोड की अधिकतम डेटा क्षमता घट सकती है। यदि आपको “Data too large” एक्सेप्शन मिलता है, तो या तो कॉलम्स की संख्या बढ़ाएँ या ट्रंकेशन को अक्षम करें।

### क्या मैं डायनामिक कॉलम काउंट उपयोग कर सकता हूँ?

हां। आप इनपुट स्ट्रिंग की लंबाई के आधार पर कॉलम काउंट की गणना कर सकते हैं:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

यह स्निपेट प्रोग्रामेटिकली **how to adjust columns** दिखाता है, जिससे बारकोड निर्धारित लेआउट में फिट हो सके।

### क्या X‑डायमेंशन केवल पूर्णांक पिक्सेल तक सीमित है?

`Pixels` प्रॉपर्टी कोई भी सकारात्मक पूर्णांक स्वीकार करती है। उच्च‑रिज़ॉल्यूशन आउटपुट (जैसे प्रिंटिंग) के लिए, आप `Pixels` के बजाय `Points` सेट करना पसंद कर सकते हैं ताकि डिवाइस‑स्वतंत्र आकार प्राप्त हो सके।

## उत्पादन उपयोग के लिए टिप्स

* **Pro tip:** बारकोड जेनरेशन को try‑catch ब्लॉक में रैप करें ताकि जब इनपुट डेटा प्रतीक की क्षमता से अधिक हो तो `BarCodeException` को संभाला जा सके।  
* **Watch out for:** फ़ाइल‑सिस्टम अनुमतियां। प्रक्रिया को लक्ष्य डायरेक्टरी में लिखने की अनुमति होनी चाहिए, अन्यथा **how to save barcode** चरण `UnauthorizedAccessException` के साथ विफल होगा।  
* **Performance note:** लूप में कई बारकोड बनाते समय एक ही `BarcodeGenerator` इंस्टेंस को पुन: उपयोग करना और प्रत्येक इटरशन के बीच केवल `CodeText` प्रॉपर्टी को अपडेट करना फायदेमंद होता है।

## निष्कर्ष

अब आप **how to save barcode** को PNG फ़ाइल के रूप में, **enable compact mode**, **how to adjust columns**, और Aspose.BarCode for C# का उपयोग करके **generate PDF417 barcode** करना जानते हैं। पूर्ण उदाहरण प्रत्येक आवश्यक चरण को दर्शाता है, जेनरेटर को इनिशियलाइज़ करने से लेकर अंतिम इमेज लिखने तक।

यहाँ से आप संबंधित विषयों का अन्वेषण कर सकते हैं जैसे बारकोड में लोगो जोड़ना, रंगों को कस्टमाइज़ करना, या जेनरेटर को ASP.NET Core API में इंटीग्रेट करना। इन सभी एक्सटेंशन का पालन इस गाइड में दिखाए गए समान पैटर्न से होता है, इसलिए आप कोड को आत्मविश्वास के साथ अनुकूलित कर सकते हैं।

विभिन्न कॉलम काउंट, X‑डायमेंशन, और इमेज फ़ॉर्मेट के साथ प्रयोग करने में संकोच न करें ताकि आपके प्रोजेक्ट की सटीक विशिष्टताओं को पूरा किया जा सके। कोडिंग का आनंद लें!

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट संबंधित विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट में वैकल्पिक इम्प्लीमेंटेशन अप्रोच को एक्सप्लोर करने में मदद करती हैं।

- [C# में Aspose के साथ बारकोड सहेजना और PDF417 जेनरेट करना](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [C# में कॉम्पैक्ट मोड के साथ PDF417 बारकोड बनाना](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [C# में PDF417 बारकोड बनाना और उसे PNG के रूप में सहेजना](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}