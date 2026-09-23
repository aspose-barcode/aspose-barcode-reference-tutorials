---
date: 2026-03-07
description: Aspose.BarCode का उपयोग करके .NET में एक-आयामी डेटाबार GS1 एन्कोडेड बारकोड
  बनाना सीखें। यह गाइड दिखाता है कि GS1 कैसे सेट करें, बारकोड जेनरेटर को कैसे कॉन्फ़िगर
  करें, और बारकोड को जल्दी से कैसे जेनरेट करें।
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode के साथ एक-आयामी डेटाबार GS1 एन्कोडिंग बनाएं
url: /hi/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode के साथ एक-आयामी डेटाबार GS1 एन्कोडिंग बनाएं

इस ट्यूटोरियल में आप **एक-आयामी डेटाबार** बारकोड बनाएँगे जो GS1 मानक के अनुरूप हों, Aspose.BarCode लाइब्रेरी for .NET का उपयोग करके। चाहे आपको सख्त GS1 वैधता चाहिए या अधिक लचीला बारकोड, हम लाइब्रेरी को इंस्टॉल करने से लेकर एन्कोडिंग एक्सेप्शन को हैंडल करने तक हर कदम को विस्तार से दिखाएंगे—ताकि आप अपने एप्लिकेशन में विश्वसनीय बारकोड जेनरेट कर सकें।

## Quick Answers
- **“एक-आयामी डेटाबार बनाना” का क्या अर्थ है?** इसका मतलब है डेटाबार परिवार का एक रैखिक (1‑D) बारकोड बनाना, जो अक्सर रिटेल और लॉजिस्टिक्स में उपयोग होता है।  
- **मैं GS1 वैधता कैसे सेट करूँ?** `DataBar` पैरामीटर्स पर `IsAllowOnlyGS1Encoding` को `true` सेट करें।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल चल सकता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **लाइब्रेरी कहाँ डाउनलोड करूँ?** आधिकारिक Aspose रिलीज़ पेज से (पूर्वापेक्षाएँ देखें)।

## “एक-आयामी डेटाबार बनाना” क्या है?
एक-आयामी डेटाबार (जिसे RSS भी कहा जाता है) एक कॉम्पैक्ट रैखिक बारकोड है जो संख्यात्मक डेटा, तिथियाँ या AI (Application Identifier) स्ट्रिंग्स को एन्कोड कर सकता है। जब इसे GS1 एन्कोडिंग के साथ जोड़ा जाता है, तो बारकोड एक वैश्विक मान्यता प्राप्त डेटा संरचना का पालन करता है, जिससे यह रिटेल, हेल्थकेयर और सप्लाई‑चेन परिदृश्यों के लिए आदर्श बन जाता है।

## .NET के लिए Aspose.BarCode क्यों उपयोग करें?
Aspose.BarCode एक सहज API, पूर्ण GS1 समर्थन, और बारकोड के प्रत्येक दृश्य पहलू को बारीकी से ट्यून करने की क्षमता प्रदान करता है। यह लो‑लेवल एन्कोडिंग की जटिलता को हटाता है और आपको व्यापारिक लॉजिक पर ध्यान केंद्रित करने देता है।

## Prerequisites

1. **Aspose.BarCode for .NET** – इसे [यहाँ](https://releases.aspose.com/barcode/net/) से डाउनलोड और इंस्टॉल करें।  
2. **Your Directory Path** – नमूनों में `"Your Directory Path"` को उस फ़ोल्डर से बदलें जहाँ आपके पास लिखने की अनुमति है।

## Importing Namespaces

अपने C# फ़ाइल के शीर्ष पर आवश्यक `using` स्टेटमेंट्स जोड़ें:

```csharp
using Aspose.BarCode;
using System;
```

## Step 1: Initialize the Barcode Generator

एक `BarcodeGenerator` इंस्टेंस बनाएँ और Databar Expanded सिम्बोलॉजी निर्दिष्ट करें:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Step 2: How to set GS1 – Generate a barcode with strict GS1 validation

GS1‑केवल एन्कोडिंग सक्षम करें, एक GS1‑अनुपालन कोडटेक्स्ट असाइन करें, और इमेज को सहेजें:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Step 3: Barcode generation with Aspose – Variable encoding (no GS1 check)

यदि आपको ऐसा बारकोड चाहिए जो **GS1 नियमों** को लागू न करे, तो जांच को बंद कर दें:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Step 4: Barcode generator GS1 check – Handling an exception

जब `IsAllowOnlyGS1Encoding` `true` हो लेकिन कोडटेक्स्ट GS1‑अनुपालन न हो, तो Aspose एक एक्सेप्शन फेंकेगा। नीचे दिया गया पैटर्न दिखाता है कि इसे कैसे कैच और लॉग किया जाए:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Common Pitfalls & Tips
- **पिटफ़ॉल:** GS1 जांच सक्षम होने पर गैर‑GS1 स्ट्रिंग प्रदान करने से बारकोड जेनरेशन रुक जाएगा।  
- **प्रो टिप:** `CodeText` को असाइन करने से पहले अपने AI स्ट्रिंग्स को वैध करें ताकि रन‑टाइम त्रुटियों से बचा जा सके।  
- **टिप:** फ़ाइल नामों को सुरक्षित रूप से बनाने के लिए एब्सोल्यूट पाथ या `Path.Combine` का उपयोग करें।

## Conclusion

अब आप **एक-आयामी डेटाबार** बारकोड को GS1 एन्कोडिंग के साथ कैसे बनाना है, GS1 जांच को कैसे टॉगल करना है, और संबंधित एक्सेप्शन को कैसे हैंडल करना है—सब Aspose.BarCode for .NET का उपयोग करके जान चुके हैं। आप `Parameters.Barcode` ऑब्जेक्ट के माध्यम से बारकोड आकार, रंग, मार्जिन आदि अतिरिक्त स्टाइलिंग विकल्पों का भी अन्वेषण कर सकते हैं।

यदि आपको कोई समस्या आती है, तो आधिकारिक दस्तावेज़ीकरण और कम्युनिटी फ़ोरम उत्कृष्ट संसाधन हैं:

- [Aspose.BarCode दस्तावेज़ीकरण](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode समर्थन फ़ोरम](https://forum.aspose.com/c/barcode/13)

## Frequently Asked Questions

### 1. बारकोड में GS1 एन्कोडिंग क्या है?
GS1 एन्कोडिंग डेटा (जैसे उत्पाद पहचानकर्ता) को बारकोड के भीतर संरचित करने का एक मानकीकृत तरीका है, जो रिटेलर, निर्माता और लॉजिस्टिक्स प्रदाताओं के बीच इंटरऑपरेबिलिटी सुनिश्चित करता है।

### 2. क्या मैं जेनरेट किए गए बारकोड की उपस्थिति को कस्टमाइज़ कर सकता हूँ?
हाँ। Aspose.BarCode आपको आकार, रंग, मार्जिन, और `Parameters.Barcode` सेटिंग्स के माध्यम से मानव‑पठनीय टेक्स्ट जोड़ने की अनुमति देता है।

### 3. Aspose.BarCode के अतिरिक्त संसाधन और दस्तावेज़ीकरण कहाँ मिलेंगे?
आप व्यापक दस्तावेज़ीकरण और उदाहरण [Aspose.BarCode दस्तावेज़ीकरण](https://reference.aspose.com/barcode/net/) पर पा सकते हैं। यह सीखने और समस्या निवारण के लिए एक मूल्यवान स्रोत है।

### 4. क्या Aspose.BarCode के लिए कोई ट्रायल संस्करण उपलब्ध है?
हाँ, आप [यहाँ](https://releases.aspose.com/) से Aspose.BarCode for .NET का फ्री ट्रायल संस्करण प्राप्त कर सकते हैं।

### 5. Aspose.BarCode for .NET का लाइसेंस कैसे खरीदूँ?
Aspose वेबसाइट पर [purchase page](https://purchase.aspose.com/buy) पर जाकर आप Aspose.BarCode for .NET का लाइसेंस खरीद सकते हैं।

---

**अंतिम अपडेट:** 2026-03-07  
**परीक्षण किया गया:** Aspose.BarCode 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}