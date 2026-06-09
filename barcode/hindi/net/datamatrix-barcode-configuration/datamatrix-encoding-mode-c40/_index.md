---
date: 2026-06-09
description: Aspose.BarCode के साथ C40 एन्कोडिंग का उपयोग करके DataMatrix बारकोड जनरेट
  करने और PNG सहेजने का तरीका सीखें – .NET Core बारकोड जेनरेशन के लिए पूर्ण गाइड।
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix एन्कोडिंग मोड (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode का उपयोग करके C40 के साथ DataMatrix PNG कैसे जनरेट करें
url: /hi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# मुख्य DataMatrix एन्कोडिंग मोड (C40) Aspose.BarCode for .NET

## परिचय

इस ट्यूटोरियल में आप सीखेंगे **डेटा मैट्रिक्स कैसे जेनरेट करें** बारकोड और उन्हें PNG फ़ाइलों के रूप में सहेजें, C40 एन्कोडिंग मोड का उपयोग करके Aspose.BarCode for .NET के साथ। चाहे आप इन्वेंटरी सिस्टम, शिपिंग‑लेबल जेनरेटर, या कोई भी समाधान बना रहे हों जिसे कॉम्पैक्ट, हाई‑डेंसिटी सिम्बॉल चाहिए, C40 में निपुण होने से आप छोटे सिम्बॉल प्राप्त कर सकते हैं बिना पठनीयता खोए। हम हर कदम को विस्तार से दिखाएंगे—पर्यावरण सेटअप से लेकर अंतिम PNG बनाने तक—ताकि आप कोड को तुरंत अपने प्रोजेक्ट में इंटीग्रेट कर सकें।

## त्वरित उत्तर
- **“how to generate datamatrix” क्या दर्शाता है?** प्रोग्रामेटिकली DataMatrix बारकोड इमेज बनाना।  
- **कौन सा एन्कोडिंग मोड कवर किया गया है?** DataMatrix C40, एक प्रभावी अल्फ़ान्यूमेरिक स्कीम।  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं इसे .NET Core पर चला सकता हूँ?** हाँ, Aspose.BarCode पूरी तरह से .NET Core, .NET 5, .NET 6 और बाद के संस्करणों को सपोर्ट करता है।  
- **कौन सा फ़ाइल फ़ॉर्मेट उत्पन्न होता है?** PNG – एक लॉस‑लेस, वेब‑फ्रेंडली इमेज फ़ॉर्मेट।

## C40 एन्कोडिंग के साथ DataMatrix कैसे जेनरेट करें

अपने डेटा को लोड करें, जनरेटर को कॉन्फ़िगर करें, और `Save` को कॉल करें – यह तीन संक्षिप्त चरणों में पूरा वर्कफ़्लो है। `BarcodeGenerator` क्लास सिम्बॉल निर्माण को संभालती है, जबकि `BarCodeImageFormat.Png` एनेम Aspose.BarCode को परिणाम PNG फ़ाइल के रूप में लिखने के लिए बताता है। `Save` जेनरेटेड बारकोड इमेज को निर्दिष्ट फ़ाइल पाथ में चुने हुए फ़ॉर्मेट में लिखता है। यह सीधे‑उत्तर वाला पैराग्राफ आपको अंत‑से‑अंत समाधान देता है इससे पहले कि हम कोड की प्रत्येक लाइन में जाएँ।

## DataMatrix एन्कोडिंग मोड (C40) क्या है?

`DataMatrixEncodeMode` एक एनेमरेशन है जो निर्धारित करता है कि Aspose.BarCode को DataMatrix सिम्बॉल के लिए कौन सा एन्कोडिंग स्कीम उपयोग करना चाहिए। `DataMatrixEncodeMode.C40` विकल्प C40 अल्फ़ान्यूमेरिक एन्कोडिंग चुनता है, जो अक्षर, अंक और सीमित विराम चिह्नों को कम मॉड्यूल में पैक करता है, जिससे कुल सिम्बॉल आकार घटता है जबकि सामान्य इन्वेंटरी टेक्स्ट की पठनीयता बनी रहती है। यह प्रभावी स्कीम तब आदर्श है जब आपको अल्फ़ान्यूमेरिक डेटा को कॉम्पैक्ट रूप में एन्कोड करना हो।

## Aspose.BarCode for .NET का उपयोग क्यों करें?

Aspose.BarCode **30+ कॉन्फ़िगरेबल पैरामीटर** प्रदान करता है जो आयाम, एरर‑करैक्शन लेवल और एन्कोडिंग मोड्स को नियंत्रित करते हैं, और यह **50+ इमेज और बारकोड फ़ॉर्मेट** को सपोर्ट करता है। यह लाइब्रेरी **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+** पर चलती है, जिससे शून्य‑डिपेंडेंसी जेनरेशन संभव होता है जो सर्वर, डेस्कटॉप और मोबाइल डिवाइसों पर समान रूप से काम करता है।

## पूर्वापेक्षाएँ

कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **.NET Development Environment** – Visual Studio, Rider, या कोई भी IDE जो C# को सपोर्ट करता हो।  
2. **Aspose.BarCode for .NET** – NuGet या आधिकारिक इंस्टॉलर के माध्यम से स्थापित किया गया। विवरण के लिए [documentation](https://reference.aspose.com/barcode/net/) देखें।  
3. **Basic C# knowledge** – आपको नेमस्पेस, क्लासेज, और using स्टेटमेंट्स में सहज होना चाहिए।  
4. **Write‑access folder** – आपके मशीन पर वह डायरेक्टरी जहाँ PNG सहेजा जाएगा।

## आवश्यक नेमस्पेस इम्पोर्ट करना

`BarcodeGenerator` क्लास किसी भी बारकोड को बनाने का एंट्री पॉइंट है। अपने C# सोर्स फ़ाइल के शीर्ष पर आवश्यक नेमस्पेस जोड़ें ताकि आप जेनरेशन API तक पहुँच सकें:

```csharp
using Aspose.BarCode.Generation;
```

## स्टेप‑बाय‑स्टेप बारकोड जेनरेशन

नीचे एक **स्टेप‑बाय‑स्टेप बारकोड** walkthrough दिया गया है। प्रत्येक चरण को सरल भाषा में समझाया गया है, और मूल प्लेसहोल्डर कॉपी‑पेस्ट की सुविधा के लिए अपरिवर्तित रखे गए हैं।

### चरण 1: डायरेक्टरी पाथ निर्धारित करें
उस फ़ोल्डर को सेट करें जहाँ PNG इमेज संग्रहीत होगी। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें।

```csharp
string path = "Your Directory Path";
```

### चरण 2: बारकोड जेनरेशन सेट अप करें
`BarcodeGenerator` का एक इंस्टेंस बनाएं, `EncodeTypes.DataMatrix` निर्दिष्ट करें, और वह डेटा प्रदान करें जिसे आप एन्कोड करना चाहते हैं।

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### चरण 3: बारकोड को कस्टमाइज़ करें
X‑डायमेंशन (मॉड्यूल की पिक्सेल चौड़ाई) को कॉन्फ़िगर करें और एन्कोडिंग मोड को C40 में बदलें।

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### चरण 4: बारकोड इमेज सहेजें
अंत में, जेनरेटेड बारकोड को PNG फ़ाइल के रूप में सहेजें। यह **how to save png** का ठोस उत्तर है Aspose.BarCode के साथ।

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

जब आप प्रोग्राम चलाएंगे, तो आपको निर्दिष्ट फ़ोल्डर में `DataMatrixEncodeModeC40.png` मिलेगा, जो रिपोर्ट, लेबल या वेब पेजों में उपयोग के लिए तैयार है।

## सामान्य समस्याएँ और टिप्स

- **Invalid Path** – सुनिश्चित करें कि डायरेक्टरी मौजूद है और आपके पास लिखने की अनुमति है; अन्यथा `gen.Save` एक एक्सेप्शन फेंकेगा।  
- **Incorrect Encoding Mode** – यदि आपको C40 सेट के बाहर के कैरेक्टर एन्कोड करने की जरूरत है, तो `DataMatrixEncodeMode.Auto` या कोई अन्य उपयुक्त मोड चुनें।  
- **Image Size** – `XDimension.Pixels` को समायोजित करके आप कुल बारकोड आकार को बढ़ा या घटा सकते हैं बिना पठनीयता को प्रभावित किए।

## अक्सर पूछे जाने वाले प्रश्न

**Q: DataMatrix एन्कोडिंग मोड (C40) क्या है?**  
A: C40 DataMatrix सिम्बॉल के लिए एक कॉम्पैक्ट अल्फ़ान्यूमेरिक एन्कोडिंग स्कीम है, जो उन टेक्स्ट के लिए आदर्श है जिसमें अक्षर, संख्या और सीमित विशेष कैरेक्टर शामिल होते हैं।

**Q: Aspose.BarCode for .NET दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: आप दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/barcode/net/) पा सकते हैं। यह सभी बारकोड प्रकारों और एन्कोडिंग विकल्पों पर विस्तृत मार्गदर्शन प्रदान करता है।

**Q: क्या Aspose.BarCode for .NET सभी .NET संस्करणों के साथ संगत है?**  
A: हाँ, लाइब्रेरी .NET Framework 4.5+ से लेकर .NET 6 और बाद के संस्करणों तक के विस्तृत रेंज को सपोर्ट करती है।

**Q: क्या मैं Aspose.BarCode for .NET को खरीदने से पहले आज़मा सकता हूँ?**  
A: हाँ, आप [इस लिंक](https://releases.aspose.com/) पर जाकर Aspose.BarCode for .NET का फ्री ट्रायल एक्सप्लोर कर सकते हैं। यह आपको लाइब्रेरी की सुविधाओं और क्षमताओं का परीक्षण करने की अनुमति देता है।

**Q: Aspose.BarCode for .NET के लिए समर्थन कहाँ मिल सकता है?**  
A: आप [Aspose फ़ोरम](https://forum.aspose.com/c/barcode/13) पर एक सहायक समुदाय और समर्थन पा सकते हैं।

## निष्कर्ष

इस **स्टेप‑बाय‑स्टेप बारकोड** गाइड का पालन करके, अब आप बिल्कुल जानते हैं **डेटा मैट्रिक्स कैसे जेनरेट करें** बारकोड और उन्हें PNG फ़ाइलों के रूप में सहेजें, C40 एन्कोडिंग मोड के साथ Aspose.BarCode for .NET का उपयोग करके। यह तरीका आपको बारकोड की उपस्थिति, आकार और डेटा प्रतिनिधित्व पर पूर्ण नियंत्रण देता है, जिससे किसी भी .NET एप्लिकेशन में हाई‑क्वालिटी बारकोड एम्बेड करना आसान हो जाता है।

---

**अंतिम अपडेट:** 2026-06-09  
**परीक्षित संस्करण:** Aspose.BarCode 24.11 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.BarCode for .NET के साथ बाइट्स में DataMatrix एन्कोडिंग](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Aspose.BarCode for .NET के साथ ASCII में मुख्य DataMatrix एन्कोडिंग](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aspose.BarCode for .NET के साथ DataMatrix बारकोड (ECC 200) कैसे जेनरेट करें](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}