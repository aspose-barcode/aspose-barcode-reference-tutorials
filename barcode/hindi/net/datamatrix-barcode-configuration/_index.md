---
date: 2026-06-09
description: Aspose.BarCode for .NET के साथ datamatrix बारकोड कैसे जनरेट करें, aspect
  ratios, ECC modes, और datamatrix c40 एन्कोडिंग को कस्टमाइज़ करके प्रभावी बारकोड
  निर्माण सीखें।
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix बारकोड कॉन्फ़िगरेशन
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode के साथ DataMatrix बारकोड बनाना – प्रो गाइड
url: /hi/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix बारकोड उत्पन्न करें – Aspose.BarCode के साथ प्रो गाइड

Welcome to our comprehensive tutorial series on **generate datamatrix barcode** using Aspose.BarCode for .NET. Whether you're a seasoned developer fine‑tuning barcode output or a newcomer eager to understand the fundamentals, this guide walks you through every step—from basic configuration to advanced encoding techniques—so you can deliver reliable, scan‑ready barcodes in any .NET application.

## त्वरित उत्तर
- **मुख्य उद्देश्य क्या है?** प्रोग्रामेटिक रूप से DataMatrix बारकोड बनाना और अनुकूलित करना।  
- **कौन सी लाइब्रेरी उपयोग की जाती है?** Aspose.BarCode for .NET।  
- **क्या लाइसेंस की आवश्यकता है?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या मैं पहलू अनुपात (aspect ratio) को अनुकूलित कर सकता हूँ?** हाँ – “How to customize DataMatrix aspect ratio” अनुभाग देखें।

## generate datamatrix barcode क्या है?
DataMatrix बारकोड काले और सफेद कोशिकाओं की दो‑आयामी मैट्रिक्स है जो अधिकतम 2 300 अल्फ़ान्यूमेरिक अक्षर संग्रहीत कर सकती है। Aspose.BarCode का उपयोग करके आप **generate datamatrix barcode** छवियां, PDF या SVG सीधे अपने .NET कोड से बना सकते हैं, आकार, एरर‑करेक्शन लेवल और एन्कोडिंग मोड को नियंत्रित कर किसी भी उद्योग मानक को पूरा कर सकते हैं।

## DataMatrix के लिए Aspose.BarCode क्यों उपयोग करें?
Aspose.BarCode DataMatrix प्रतीकों को **600 dpi** तक बिना पिक्सेलेशन के रेंडर करता है, जिससे हाई‑रेज़ोल्यूशन प्रिंटर पर स्पष्ट स्कैन सुनिश्चित होते हैं। यह **50+ ECC और मैक्रो मोड**—जैसे ECC 000‑140, ECC 200, और Macro 05/06—को सपोर्ट करता है, जिससे आप अपने डेटा आकार के अनुसार इष्टतम एरर‑करेक्शन लेवल चुन सकते हैं। API **ASCII, C40, Text, X12, और Bytes** एन्कोडिंग विकल्प प्रदान करती है, जिससे डेटा को कुशलता से पैक किया जा सकता है। इंटीग्रेशन के लिए केवल एक NuGet पैकेज की आवश्यकता होती है और कोई बाहरी नेटिव लाइब्रेरी नहीं चाहिए।

## DataMatrix पहलू अनुपात (aspect ratio) को अनुकूलित कैसे करें
`BarCodeGenerator` की `AspectRatio` प्रॉपर्टी उत्पन्न DataMatrix प्रतीक की चौड़ाई‑से‑ऊँचाई अनुपात को नियंत्रित करती है। `BarCodeGenerator` Aspose.BarCode में बारकोड छवियां बनाने के लिए मुख्य क्लास है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (या 0.5 से 2.0 के बीच कोई भी मान) को `GenerateBarCodeImage()` कॉल करने से पहले सेट करें। लाइब्रेरी स्वचालित रूप से मॉड्यूल आकार को पुनः गणना करती है ताकि स्कैन विश्वसनीयता बनी रहे जबकि अनुरोधित अनुपात का सम्मान हो।

### चरण‑दर‑चरण
1. **Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.  
2. **Adjust** `AspectRatio` to your desired value.  
3. **Generate** the image and verify with a scanner or Aspose’s built‑in reader.

## DataMatrix ECC 000‑140 बारकोड कैसे बनाएं
ECC 000‑140 छोटे डेटा स्ट्रिंग्स के लिए आदर्श है जहाँ एक कॉम्पैक्ट प्रतीक आवश्यक होता है, यह अधिकतम 140 एरर‑करेक्शन कोडवर्ड प्रदान करता है। `DataMatrixEccMode.Ecc000140` DataMatrix के लिए ECC 000‑140 एरर‑करेक्शन योजना चुनता है।  

**सीधा उत्तर:** रेंडर करने से पहले `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` सेट करें। यह एन्कोडर को ECC 000‑140 एल्गोरिद्म पर स्विच करता है, जिससे दिए गए डेटा के लिए सबसे छोटा संभव मैट्रिक्स बनता है जबकि मजबूत एरर‑करेक्शन प्रदान करता है।

### व्यावहारिक टिप
जब 20 अक्षरों से कम का संख्यात्मक डेटा एन्कोड किया जाता है, तो ECC 000‑140 अक्सर 10 × 10 मैट्रिक्स देता है, जिससे लेबल स्पेस बचता है।

## DataMatrix ECC 200 बारकोड कैसे बनाएं
ECC 200 सबसे व्यापक रूप से अपनाया गया DataMatrix मोड है, जो अधिकतम 2 335 अल्फ़ान्यूमेरिक अक्षर समर्थन करता है और श्रेष्ठ एरर‑करेक्शन प्रदान करता है। `DataMatrixEccMode.Ecc200` DataMatrix के लिए ECC 200 एरर‑करेक्शन योजना चुनता है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` सेट करें और अपना पेलोड `CodeText` के माध्यम से प्रदान करें। लाइब्रेरी तब स्वचालित रूप से इष्टतम मैट्रिक्स आकार चुनती है।

### कब ECC 200 को प्राथमिकता दें
लंबी स्ट्रिंग्स, मिश्रित‑टाइप डेटा, या जब आपको क्षति के खिलाफ सबसे अधिक लचीलापन चाहिए—प्रतीक के **30 %** तक पुनर्स्थापित किया जा सकता है।

## ASCII में DataMatrix एन्कोडिंग में महारत हासिल करें
ASCII मोड प्रत्येक अक्षर को एक बाइट में एन्कोड करता है, जिससे साधारण टेक्स्ट के लिए यह सबसे स्थान‑कुशल होता है। `DataMatrixEncodeMode.Ascii` जेनरेटर को DataMatrix प्रतीक के लिए ASCII एन्कोडिंग उपयोग करने के लिए बताता है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` असाइन करें और `CodeText` को अपनी ASCII स्ट्रिंग पर सेट करें। इंजन अतिरिक्त ओवरहेड के बिना डेटा को पैक करता है, जिससे शुद्ध ASCII कंटेंट के लिए सबसे छोटा संभव मैट्रिक्स बनता है।

### उदाहरण परिदृश्य
एक वेयरहाउस SKU जिसमें बड़े अक्षर और अंक होते हैं (जैसे “AB1234”) ASCII मोड में पूरी तरह फिट बैठता है, अक्सर 12 × 12 मैट्रिक्स देता है।

## DataMatrix मोड (Auto) कैसे बनाएं
Auto मोड Aspose.BarCode को इनपुट का विश्लेषण करने और सबसे कुशल एन्कोडिंग (ASCII, C40, Text, X12, या Bytes) को स्वचालित रूप से चुनने देता है। `DataMatrixEncodeMode.Auto` इस स्वचालित चयन सुविधा को सक्षम करता है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto` सेट करें। लाइब्रेरी पेलोड का मूल्यांकन करती है, इष्टतम मोड चुनती है, और एक ही चरण में बारकोड रेंडर करती है।

### लाभ
Auto मोड विकास प्रयास को कम करता है और मिश्रित‑टाइप डेटा के लिए सबसे छोटा संभव प्रतीक सुनिश्चित करता है, जिससे स्कैन गति में सुधार होता है।

## DataMatrix एन्कोडिंग मोड (Bytes) कैसे उपयोग करें
Bytes मोड बाइनरी डेटा के लिए डिज़ाइन किया गया है, जैसे एन्क्रिप्टेड पेलोड या कंप्रेस्ड फ़ाइलें। `DataMatrixEncodeMode.Bytes` जेनरेटर को प्रत्येक बाइट को कच्चा डेटा मानने के लिए निर्देश देता है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` उपयोग करें और `CodeText` में Base64‑एन्कोडेड स्ट्रिंग प्रदान करें। एन्कोडर प्रत्येक बाइट को कच्चा डेटा मानता है, जिससे सटीक बाइनरी प्रतिनिधित्व बना रहता है।

### उपयोग केस
एक 128‑बिट GUID या छोटा एन्क्रिप्टेड टोकन सीधे DataMatrix प्रतीक में एम्बेड करना।

## C40 में DataMatrix एन्कोडिंग मोड में महारत हासिल करें
C40 मोड बड़े अक्षर अल्फ़ान्यूमेरिक डेटा को संकुचित करता है, जिससे ASCII की तुलना में **40 %** तक आकार घटता है। `DataMatrixEncodeMode.C40` इस संपीड़न एल्गोरिद्म को सक्रिय करता है।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` सेट करें और एक बड़े अक्षर स्ट्रिंग प्रदान करें (जैसे “HELLO WORLD”)। इंजन तीन अक्षरों को दो कोडवर्ड में पैक करता है, जिससे अंतिम मैट्रिक्स छोटा हो जाता है।

### प्रो टिप
C40 तब सबसे अच्छा काम करता है जब पेलोड मुख्यतः बड़े अक्षर, अंक और स्पेस से बना हो। मिश्रित केस के लिए Auto मोड पर विचार करें।

## DataMatrix कोड टेक्स्ट को कॉन्फ़िगर कैसे करें
`CodeText` प्रॉपर्टी बारकोड में संग्रहीत सटीक डेटा को परिभाषित करती है। यह साधारण टेक्स्ट, संख्यात्मक स्ट्रिंग या यहाँ तक कि XML पेलोड भी शामिल कर सकती है। `CodeText` `BarCodeGenerator` की मुख्य स्ट्रिंग प्रॉपर्टी है जो बारकोड पेलोड रखती है।  

**सीधा उत्तर:** रेंडर करने से पहले `generator.Parameters.Barcode.CodeText = "YourDataHere"` असाइन करें। यह प्रॉपर्टी किसी भी UTF‑8 स्ट्रिंग को स्वीकार करती है, जिसकी अधिकतम लंबाई चयनित ECC मोड द्वारा समर्थित होती है।

### उन्नत टिप
`CodeText` को `ExtendedDataMatrix` के साथ मिलाकर अतिरिक्त मेटाडेटा एम्बेड करें, बिना दृश्यमान मैट्रिक्स आकार बढ़ाए।

## DataMatrix मैक्रो कॉन्फ़िगरेशन में महारत हासिल करें
मैक्रो मोड (Macro 05 और Macro 06) आपको प्राथमिक प्रतीक के भीतर एक द्वितीयक DataMatrix प्रतीक एम्बेड करने की अनुमति देते हैं, जो बाहरी डेटा स्रोतों से लिंक करने में उपयोगी है। `DataMatrixMacroMode.Macro05` और `DataMatrixMacroMode.Macro06` इन मैक्रो सुविधाओं को सक्षम करते हैं।  

**सीधा उत्तर:** `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (या `Macro06`) सेट करके मैक्रो मोड सक्षम करें और द्वितीयक पेलोड के लिए `MacroPdf417` प्रॉपर्टीज़ सेट करें। जेनरेटर एक संयुक्त प्रतीक बनाता है जिसे स्कैनर दो जुड़े हुए कोड के रूप में व्याख्या कर सकता है।

### वास्तविक‑विश्व उदाहरण
मैक्रो भाग में एक URL एम्बेड करना जबकि प्राथमिक मैट्रिक्स में उत्पाद पहचानकर्ता रखना, जिससे वेब‑से‑बारकोड एकीकरण सहज हो जाता है।

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## DataMatrix बारकोड कॉन्फ़िगरेशन ट्यूटोरियल
### [DataMatrix पहलू अनुपात को अनुकूलित करना](./datamatrix-aspect-ratio-customization/)
Aspose.BarCode for .NET का उपयोग करके DataMatrix बारकोड पहलू अनुपात को कैसे अनुकूलित करें सीखें। बारकोड जनरेशन के लिए चरण‑दर‑चरण गाइड।
### [DataMatrix ECC 000-140 बारकोड बनाएं](./datamatrix-ecc-000-140-configuration/)
Aspose.BarCode for .NET का उपयोग करके DataMatrix ECC 000-140 बारकोड आसानी से बनाएं। इन्वेंटरी प्रबंधन आदि में दक्षता बढ़ाएँ।
### [DataMatrix ECC 200 बारकोड बनाएं](./datamatrix-ecc-200-configuration/)
Aspose.BarCode के साथ .NET में DataMatrix ECC 200 बारकोड कैसे बनाएं सीखें। कुशल बारकोड निर्माण से संचालन को सरल बनाएँ।
### [ASCII में DataMatrix एन्कोडिंग में महारत हासिल करें](./datamatrix-encoding-mode-ascii/)
Aspose.BarCode for .NET का उपयोग करके ASCII मोड में DataMatrix बारकोड बनाना सीखें। डेवलपर्स के लिए चरण‑दर‑चरण गाइड।
### [DataMatrix मोड (Auto) बनाएं](./datamatrix-encoding-mode-auto/)
Aspose.BarCode for .NET के साथ DataMatrix मोड (Auto) कैसे बनाएं सीखें। यह चरण‑दर‑चरण गाइड पूर्वापेक्षाओं से लेकर बारकोड पढ़ने तक सब कुछ कवर करता है।
### [DataMatrix एन्कोडिंग मोड (Bytes)](./datamatrix-encoding-mode-bytes/)
Aspose.BarCode for .NET के साथ Bytes मोड का उपयोग करके DataMatrix फ़ॉर्मेट में डेटा एन्कोड करना सीखें। बारकोड जनरेशन और पहचान के लिए हमारा चरण‑दर‑चरण गाइड देखें।
### [C40 में DataMatrix एन्कोडिंग मोड सीखें](./datamatrix-encoding-mode-c40/)
Aspose.BarCode for .NET के साथ DataMatrix एन्कोडिंग मोड (C40) सीखें। कस्टम बारकोड को कुशलता से बनाएं। चरण‑दर‑चरण गाइड देखें।
### [DataMatrix कोड टेक्स्ट कॉन्फ़िगर करना](./datamatrix-extended-code-text-configuration/)
Aspose.BarCode for .NET का उपयोग करके DataMatrix विस्तारित कोड टेक्स्ट को कॉन्फ़िगर करना सीखें। अपने .NET एप्लिकेशन में बारकोड जनरेट, पहचान और एकीकृत करें।
### [DataMatrix मैक्रो कॉन्फ़िगरेशन में महारत हासिल करें](./datamatrix-macro-configuration/)
Aspose.BarCode for .NET के साथ DataMatrix मैक्रो बारकोड को कॉन्फ़िगर करना सीखें। अपने .NET एप्लिकेशन में DataMatrix बारकोड जनरेट, अनुकूलित और पहचानें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं कौन सा ECC मोड चुनूँ?**  
A: छोटे डेटा सेट और सीमित एरर‑करेक्शन के लिए ECC 000‑140 चुनें, या बड़े डेटा और उच्च विश्वसनीयता के लिए ECC 200 चुनें। मैक्रो मोड अतिरिक्त डेटा लेयर जोड़ता है लिंकिंग के लिए।

**Q: क्या मैं DataMatrix बारकोड में कस्टम टेक्स्ट एम्बेड कर सकता हूँ?**  
A: हाँ, `CodeText` प्रॉपर्टी को अपनी कस्टम स्ट्रिंग पर सेट करें, फिर उपयुक्त एन्कोडिंग मोड (ASCII, C40, आदि) चुनें ताकि आकार नियंत्रित रहे।

**Q: क्या कोई तरीका है जिससे सबसे अच्छा एन्कोडिंग मोड स्वचालित रूप से चुना जा सके?**  
A: `EncodeMode` को `Auto` सेट करें; Aspose.BarCode पेलोड का मूल्यांकन करता है और स्वचालित रूप से सबसे स्थान‑कुशल मोड चुनता है।

**Q: बड़े बारकोड बैच के लिए प्रदर्शन संबंधी विचार क्या हैं?**  
A: एक ही `BarCodeGenerator` इंस्टेंस को पुन: उपयोग करें, मल्टी‑थ्रेडिंग सक्षम करें, और lossless गुणवत्ता के लिए PNG छवियां या छोटे फ़ाइल आकार के लिए JPEG उत्पन्न करें। 10 000 प्रतीकों को उत्पन्न करने में सामान्य 8‑कोर सर्वर पर आमतौर पर 30 सेकंड से कम समय लगता है।

**Q: क्या Aspose.BarCode .NET Core और .NET 5/6 को सपोर्ट करता है?**  
A: बिल्कुल – लाइब्रेरी .NET Framework, .NET Core, और नवीनतम .NET रिलीज़ के साथ पूरी तरह संगत है, सभी प्लेटफ़ॉर्म पर समान फीचर सेट प्रदान करती है।

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}