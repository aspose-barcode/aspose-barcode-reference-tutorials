---
date: 2026-01-12
description: Aspose.BarCode for .NET का उपयोग करके कस्टम DataMatrix अनुपात के साथ
  बारकोड PNG बनाना सीखें। बारकोड जेनरेशन और आकार अनुकूलन के लिए चरण‑दर‑चरण मार्गदर्शिका।
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: बारकोड PNG बनाएं – डेटा मैट्रिक्स अनुपात – Aspose.BarCode
url: /hi/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बारकोड PNG बनाएं – DataMatrix अनुपात – Aspose.BarCode

एक कस्टम DataMatrix अनुपात के साथ **barcode PNG** बनाना एक सामान्य आवश्यकता है जब आपको बारकोड को विशिष्ट लेआउट प्रतिबंधों में फिट करना होता है। इस ट्यूटोरियल में हम Aspose.BarCode for .NET का उपयोग करके **barcode PNG** फ़ाइलें बनाने के सटीक चरणों को दिखाएंगे, समझाएंगे कि आप अनुपात को क्यों समायोजित करना चाह सकते हैं, और आपके अनुप्रयोग के लिए आउटपुट को कैसे फाइन‑ट्यून करें।

## त्वरित उत्तर
- **“अनुपात” (aspect ratio) क्या नियंत्रित करता है?** यह DataMatrix मॉड्यूल्स की चौड़ाई‑से‑ऊँचाई अनुपात को परिभाषित करता है।  
- **क्या मैं PNG, JPEG, या SVG आउटपुट कर सकता हूँ?** हाँ – `Save` मेथड PNG, JPEG, BMP, GIF, और अधिक को सपोर्ट करता है।  
- **क्या इस फीचर के लिए लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन‑से .NET संस्करण समर्थित हैं?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7।  
- **कितने अनुपात मान वैध हैं?** कोई भी सकारात्मक फ्लोट; सामान्य मान 0.5 – 2.0 हैं।

## DataMatrix बारकोड क्या है और उसका अनुपात क्यों बदलें?
DataMatrix एक द्वि‑आयामी मैट्रिक्स बारकोड है जो छोटे स्थान में बड़ी मात्रा में डेटा संग्रहीत करता है। **अनुपात** (aspect ratio) को समायोजित करने से आप मॉड्यूल्स को क्षैतिज रूप से फैल या संकुचित कर सकते हैं, जिससे बारकोड को संकरी कॉलम या विस्तृत लेबल में फिट किया जा सकता है बिना पठनीयता खोए।

## पूर्वापेक्षाएँ

कस्टम DataMatrix अनुपात शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Visual Studio** – कोई भी नवीनतम संस्करण चलेगा।  
2. **Aspose.BarCode for .NET** – इसे [यहाँ](https://releases.aspose.com/barcode/net/) डाउनलोड करें।  
3. **.NET Framework / .NET Core** – आपका प्रोजेक्ट समर्थित संस्करण को टार्गेट करना चाहिए।

## नेमस्पेस आयात करें

पहले, अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करें:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** इस `using` स्टेटमेंट को फ़ाइल के शीर्ष पर रखें ताकि `BarcodeGenerator` क्लास हमेशा उपलब्ध रहे।

## चरण‑दर‑चरण गाइड

### चरण 1: अपना प्रोजेक्ट सेट करें
Visual Studio में एक नया कंसोल या Windows Forms प्रोजेक्ट बनाएं और Aspose.BarCode DLL का रेफ़रेंस जोड़ें।

### चरण 2: बारकोड जेनरेटर प्रारंभ करें
DataMatrix प्रकार और आप जो डेटा एन्कोड करना चाहते हैं, उसके साथ `BarcodeGenerator` को इंस्टैंशिएट करें:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> यह लाइन एक जेनरेटर बनाती है जो एक DataMatrix बारकोड उत्पन्न करने के लिए तैयार है जिसमें नमूना टेक्स्ट शामिल है।

### चरण 3: अनुपात को अनुकूलित करें और PNG फ़ाइलें सहेजें
अब आप **अनुपात** (aspect ratio) बदल सकते हैं और प्रत्येक संस्करण को PNG इमेज के रूप में सहेज सकते हैं:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- पहला कॉल एक वर्ग‑आकार का बारकोड बनाता है (`AspectRatio = 1`)।  
- दूसरा कॉल बारकोड को क्षैतिज रूप से संकुचित करता है (`AspectRatio = 0.5`), जिससे यह अधिक चौड़ा दिखता है।

आप अब दो **barcode PNG** फ़ाइलें विभिन्न अनुपातों के साथ प्राप्त कर चुके हैं, जिन्हें रिपोर्ट, लेबल, या UI तत्वों में उपयोग किया जा सकता है।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **Generated image is blurry** | सहेजने से पहले `Resolution` पैरामीटर बढ़ाएँ (`gen.Parameters.ImageResolution = 300`)। |
| **Barcode does not scan** | सुनिश्चित करें कि अनुपात 0.5 – 2.0 के भीतर रहे और पर्याप्त क्वाइट ज़ोन रखें (`gen.Parameters.Barcode.CodeTextParameters.Margin`)। |
| **File path errors** | आउटपुट पाथ बनाने के लिए `Path.Combine` का उपयोग करें और फ़ोल्डर मौजूद है यह सत्यापित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.BarCode for .NET का उपयोग करके अन्य बारकोड प्रकारों का अनुपात कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, कई 2‑D बारकोड (जैसे QR, PDF417) अपने विशिष्ट पैरामीटर ऑब्जेक्ट्स के माध्यम से अनुपात समायोजन का समर्थन करते हैं।

**Q: क्या Aspose.BarCode for .NET के लिए कोई मुफ्त ट्र उपलब्ध है?**  
A: हाँ, आप Aspose.BarCode for .NET का मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**Q: Aspose.BarCode for .NET का लाइसेंस कहाँ खरीद सकता हूँ?**  
A: आप Aspose वेबसाइट पर लाइसेंस [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

**Q: क्या Aspose.BarCode for .NET विभिन्न .NET Framework संस्करणों के साथ संगत है?**  
A: हाँ, यह .NET Framework 4.x, .NET Core 3.1+, और नवीनतम .NET रिलीज़ के साथ काम करता है।

**Q: क्या मैं Aspose.BarCode for .NET से विभिन्न फ़ॉर्मेट में बारकोड जेनरेट कर सकता हूँ?**  
A: बिल्कुल – PNG, JPEG, BMP, GIF, TIFF, SVG, और PDF सभी आउट‑ऑफ़‑द‑बॉक्स समर्थित हैं।

## निष्कर्ष

DataMatrix बारकोड का **अनुपात** (aspect ratio) कस्टमाइज़ करना और **बारकोड PNG** फ़ाइलें बनाना Aspose.BarCode for .NET के साथ सरल है। उपरोक्त चरणों का पालन करके आप अपने प्रोजेक्ट की लेआउट आवश्यकताओं के अनुसार बिल्कुल सही आकार के बारकोड जेनरेट कर सकते हैं। अतिरिक्त पैरामीटर जैसे `Resolution`, `Margin`, और `Color` को एक्सप्लोर करके आउटपुट को और भी अनुकूलित करें।

गहराई से खोजने के लिए आधिकारिक [documentation](https://reference.aspose.com/barcode/net/) देखें या [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) पर समुदाय से जुड़ें।

---

**अंतिम अद्यतन:** 2026-01-12  
**परीक्षित संस्करण:** Aspose.BarCode 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}