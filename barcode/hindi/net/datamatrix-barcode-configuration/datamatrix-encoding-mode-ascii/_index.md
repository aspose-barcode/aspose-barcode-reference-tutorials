---
date: 2026-06-09
description: Aspose.BarCode for .NET का उपयोग करके ASCII मोड में DataMatrix बारकोड
  बनाना सीखें। यह गाइड तेज़ी से C# में बारकोड जेनरेट करने का तरीका दिखाता है।
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix एन्कोडिंग मोड (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET के साथ ASCII मोड में DataMatrix बारकोड बनाएं
url: /hi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET के साथ ASCII मोड में DataMatrix बारकोड बनाएं

## परिचय

क्या आप **DataMatrix बारकोड** छवियों को बनाना चाहते हैं जो कुशल ASCII एन्कोडिंग का उपयोग करती हैं? इस ट्यूटोरियल में आप सीखेंगे कि Aspose.BarCode for .NET का उपयोग करके ASCII मोड में DataMatrix बारकोड कैसे जनरेट किया जाए। हम हर कदम से गुजरेंगे—परियोजना सेटअप से लेकर अंतिम छवि को सहेजने तक—ताकि आप कुछ ही मिनटों में अपने C# एप्लिकेशन में बारकोड जेनरेशन जोड़ सकें।

## त्वरित उत्तर
- **.NET में DataMatrix के लिए सबसे अच्छा लाइब्रेरी कौन सा है?** Aspose.BarCode for .NET  
- **कोड की कितनी लाइनों की आवश्यकता है?** बुनियादी ASCII बारकोड के लिए लगभग 5‑7 लाइनों की आवश्यकता होती है  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है  
- **समर्थित प्लेटफ़ॉर्म?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **क्या मैं आकार या रंग बदल सकता हूँ?** हाँ, Aspose.BarCode आयाम और फ़ोरग्राउंड/बैकग्राउंड रंगों के लिए प्रॉपर्टीज़ प्रदान करता है  

## DataMatrix बारकोड क्या है?

DataMatrix एक द्वि‑आयामी बारकोड है जो टेक्स्ट और बाइनरी डेटा को एक कॉम्पैक्ट वर्गाकार पैटर्न में संग्रहीत करता है।  
DataMatrix बारकोड जानकारी को काले और सफेद मॉड्यूल की ग्रिड में एन्कोड करता है, जिससे एक ही प्रतीक में अधिकतम 2,335 अल्फ़ान्यूमेरिक अक्षर सम्मिलित किए जा सकते हैं। यह निर्माण, लॉजिस्टिक्स और स्वास्थ्य देखभाल में व्यापक रूप से उपयोग किया जाता है क्योंकि इसे बहुत छोटे आकार में प्रिंट किया जा सकता है और फिर भी अत्यधिक स्कैन योग्य रहता है।

## ASCII मोड में DataMatrix बारकोड कैसे बनाएं?

Aspose.BarCode नेमस्पेस लोड करें, एक `BarcodeGenerator` का इंस्टैंस बनाएं, `EncodeMode` को **EncodeMode.ASCII** पर सेट करें, अपना डेटा स्ट्रिंग असाइन करें, और इमेज फ़ाइल लिखने के लिए `Save` कॉल करें। यह तरीका कुछ ही C# कोड लाइनों में ASCII‑केवल एन्कोडिंग के साथ पूर्णतः मानक DataMatrix बारकोड उत्पन्न करता है।

## DataMatrix के लिए ASCII एन्कोडिंग क्यों उपयोग करें?

ASCII मोड साधारण‑टेक्स्ट डेटा के लिए डिफ़ॉल्ट और सबसे कुशल एन्कोडिंग है, जो अल्फ़ान्यूमेरिक स्ट्रिंग्स के लिए सबसे छोटा संभव प्रतीक आकार प्रदान करता है। यह सभी 128 ASCII अक्षरों का समर्थन करता है, विस्तारित मोड्स की तुलना में डेटा को तेज़ी से प्रोसेस करता है, और उन लेगेसी स्कैनरों के साथ अधिकतम संगतता सुनिश्चित करता है जो मानक ASCII प्रतीकों की अपेक्षा करते हैं।

## पूर्वापेक्षाएँ

1. **डेवलपमेंट एनवायरनमेंट** – Visual Studio, Rider, या कोई भी C#‑संगत IDE।  
2. **Aspose.BarCode for .NET** – नवीनतम पैकेज [here](https://releases.aspose.com/barcode/net/) से डाउनलोड करें।  
   - डॉक्यूमेंटेशन: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - कम्युनिटी सहायता: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **बेसिक C# ज्ञान** – .NET प्रोजेक्ट स्ट्रक्चर की परिचितता आपको चरणों को जल्दी फॉलो करने में मदद करेगी।  
4. **अन्य Aspose प्रोडक्ट्स** [here](https://releases.aspose.com/) पर पाए जा सकते हैं।

## नेमस्पेस इम्पोर्ट करें

शुरू करने के लिए, अपने C# फ़ाइल के शीर्ष पर आवश्यक `using` निर्देश जोड़ें:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

ये नेमस्पेस आपको `BarcodeGenerator` क्लास और आउटपुट सहेजने के लिए आवश्यक इमेज‑संबंधित टाइप्स तक पहुँच प्रदान करते हैं।

## चरण 1: डायरेक्टरी बनाएं

एक फ़ोल्डर चुनें जहाँ जनरेट किए गए बारकोड इमेजेस संग्रहीत होंगी। `"Your Directory Path"` को अपने मशीन पर मौजूद किसी भी एब्सोल्यूट या रिलेटिव पाथ से बदलें।

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

कोड फ़ाइलें लिखने से पहले यह सुनिश्चित करता है कि डायरेक्टरी मौजूद है, जिससे रनटाइम एरर से बचा जा सके।

## चरण 2: ASCII मोड में डेटा एन्कोड करना

`BarcodeGenerator` क्लास बारकोड इमेजेस बनाता और कॉन्फ़िगर करता है। `DataMatrixEncodeMode` एनेमरेशन DataMatrix प्रतीकों के लिए एन्कोडिंग एल्गोरिद्म चुनता है।

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

कोड चलाने के बाद, आप निर्दिष्ट फ़ोल्डर में `datamatrix_ascii.png` पाएँगे। इस इमेज में एक DataMatrix बारकोड है जो स्ट्रिंग `"1234567890"` को कॉम्पैक्ट ASCII मोड का उपयोग करके एन्कोड करता है।

## सामान्य समस्याएँ और समाधान

- **फ़ाइल‑एक्सेस त्रुटियाँ** – सुनिश्चित करें कि एप्लिकेशन को लक्ष्य फ़ोल्डर में लिखने की अनुमति है। Windows पर Visual Studio को एडमिनिस्ट्रेटर के रूप में चलाने से अनुमति समस्याएँ हल हो सकती हैं।  
- **गलत प्रतीक आकार** – यदि बारकोड बहुत बड़ा या बहुत छोटा दिखता है, तो `generator.Parameters.Image.Width` और `Height` को समायोजित करें या इन प्रॉपर्टीज़ को छोड़कर Aspose को स्वचालित रूप से इष्टतम आकार गणना करने दें।  
- **असमर्थित अक्षर** – ASCII मोड केवल 0‑127 रेंज के अक्षरों को स्वीकार करता है। Unicode डेटा के लिए, `DataMatrixEncodeMode.Base256` या कोई अन्य उपयुक्त मोड चुनें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इसे व्यावसायिक एप्लिकेशन में उपयोग कर सकता हूँ?**  
A: हाँ, उत्पादन उपयोग के लिए एक वैध Aspose लाइसेंस आवश्यक है; मूल्यांकन के लिए एक फ्री ट्रायल उपलब्ध है।

**Q: क्या लाइब्रेरी .NET Core के साथ काम करती है?**  
A: बिल्कुल – Aspose.BarCode पूरी तरह से .NET Core 3.1+, .NET 5, .NET 6, और बाद के संस्करणों को सपोर्ट करती है।

**Q: ASCII मोड में मैं कितने अक्षर एन्कोड कर सकता हूँ?**  
A: ASCII एन्कोडिंग का उपयोग करने पर एकल DataMatrix प्रतीक में अधिकतम 2,335 अल्फ़ान्यूमेरिक अक्षर फिट होते हैं।

**Q: क्या मैं बारकोड के फ़ोरग्राउंड या बैकग्राउंड रंग को बदल सकता हूँ?**  
A: हाँ, `generator.Parameters.Image.ForeColor` और `BackColor` को किसी भी `System.Drawing.Color` वैल्यू पर सेट कर सकते हैं।

**Q: अधिक उन्नत उदाहरण कहाँ मिल सकते हैं?**  
A: आधिकारिक डॉक्यूमेंटेशन में कस्टम साइज, रंग, और एरर‑करैक्शन लेवल्स को कवर करने वाले कई सैंपल्स उपलब्ध हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.BarCode for .NET को C# के अलावा अन्य प्रोग्रामिंग भाषाओं में उपयोग कर सकता हूँ?
A1: Aspose.BarCode कई प्रोग्रामिंग भाषाओं का समर्थन करता है, लेकिन यह ट्यूटोरियल C# पर केंद्रित है।

### Q2: DataMatrix बारकोड में उपलब्ध विभिन्न एन्कोडिंग मोड कौन से हैं?
A2: DataMatrix बारकोड विभिन्न एन्कोडिंग मोड्स को सपोर्ट करता है, जैसे ASCII, C40, Text, और Base256। प्रत्येक मोड विभिन्न प्रकार के डेटा के लिए उपयुक्त है।

### Q3: क्या मैं जनरेट किए गए बारकोड की उपस्थिति, जैसे आकार और रंग, को कस्टमाइज़ कर सकता हूँ?
A3: हाँ, Aspose.BarCode बारकोड की उपस्थिति को कस्टमाइज़ करने के लिए कई पैरामीटर्स प्रदान करता है, जिसमें आकार, रंग, और अन्य विकल्प शामिल हैं।

### Q4: क्या Aspose.BarCode for .NET का फ्री ट्रायल संस्करण उपलब्ध है?
A4: हाँ, आप Aspose.BarCode for .NET को [here](https://releases.aspose.com/) से फ्री ट्रायल के साथ एक्सप्लोर कर सकते हैं।

### Q5: मैं Aspose.BarCode for .NET का लाइसेंस कहाँ खरीद सकता हूँ?
A5: आप Aspose वेबसाइट से लाइसेंस खरीद सकते हैं [here](https://purchase.aspose.com/buy)।

---

**अंतिम अपडेट:** 2026-06-09  
**परीक्षण किया गया:** Aspose.BarCode 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.BarCode for .NET के साथ बाइट्स में DataMatrix एन्कोडिंग](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix बारकोड पढ़ें C# – DataMatrix मोड (ऑटो) जेनरेट करें](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Aspose.BarCode for .NET के साथ DataMatrix बारकोड (ECC 200) कैसे जेनरेट करें](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}