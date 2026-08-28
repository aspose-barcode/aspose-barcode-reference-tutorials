---
category: general
date: 2026-08-22
description: C# में DataBar Stacked Omni‑Directional जेनरेटर का उपयोग करके बारकोड
  आकार कैसे बदलें। PNG आउटपुट के लिए X‑डायमेंशन और आस्पेक्ट रेशियो सेट करना सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: hi
lastmod: 2026-08-22
og_description: C# में DataBar Stacked Omni‑Directional जेनरेटर के साथ बारकोड आकार
  कैसे बदलें। X‑डायमेंशन और एस्पेक्ट रेशियो को समायोजित करने के लिए चरण‑दर‑चरण गाइड
  का पालन करें।
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: C# में बारकोड आकार कैसे बदलें – पूर्ण गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: C# में DataBar Stacked के साथ बारकोड का आकार कैसे बदलें
url: /hi/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# में DataBar Stacked के साथ बारकोड आकार कैसे बदलें

यदि आपको .NET एप्लिकेशन में **बारकोड आकार कैसे बदलें** की आवश्यकता है, तो यह गाइड DataBar Stacked Omni‑Directional बारकोड जेनरेटर का उपयोग करके सटीक चरण दिखाता है। आप देखेंगे कि पिक्सेल में X‑डायमेंशन को कैसे नियंत्रित करें, बारकोड का एस्पेक्ट रेशियो कैसे समायोजित करें, और परिणाम को PNG फ़ाइल के रूप में कैसे सहेजें।

बारकोड आकार बदलना अक्सर तब आवश्यक होता है जब प्रिंटेड लेबल की जगह सीमित हो या डिजिटल चैनलों के लिए उच्च‑रिज़ॉल्यूशन इमेज चाहिए हो। यह ट्यूटोरियल सब कुछ कवर करता है, जेनरेटर को इनिशियलाइज़ करने से लेकर विभिन्न आकारों की दो इमेजेज़ बनाने तक।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* .NET 6.0 SDK या बाद का संस्करण स्थापित हो  
* **Aspose.BarCode for .NET** NuGet पैकेज का रेफ़रेंस  
* C# सिंटैक्स की बुनियादी समझ  

कोई अतिरिक्त कॉन्फ़िगरेशन आवश्यक नहीं है; कोड Windows, Linux, या macOS पर चलता है।

## C# में बारकोड आकार कैसे बदलें – चरण दर चरण

निम्नलिखित सेक्शन प्रक्रिया को अलग‑अलग, पुन: उपयोग योग्य चरणों में विभाजित करते हैं। प्रत्येक चरण यह बताता है कि **कोड क्यों** आवश्यक है, न कि केवल **क्या** करता है।

### Step 1: DataBar Stacked Omni‑Directional बारकोड जेनरेटर बनाएं

जेनरेटर ऑब्जेक्ट सभी बारकोड सेटिंग्स रखता है। `EncodeTypes.DatabarStackedOmniDirectional` और सैंपल डेटा पास करके आप एक वैध बारकोड बनाते हैं जो आगे की कस्टमाइज़ेशन के लिए तैयार है।

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Why this matters* – **C# barcode generator** क्लास एन्कोडिंग एल्गोरिद्म को एन्कैप्सुलेट करती है। वैध जेनरेटर से शुरू करने से यह सुनिश्चित होता है कि बाद में किए गए आकार परिवर्तन सही बारकोड प्रकार पर लागू हों।

### Step 2: बेसिक मॉड्यूल आकार (X‑डायमेंशन) पिक्सेल में सेट करें

X‑डायमेंशन एकल बारकोड मॉड्यूल की चौड़ाई निर्धारित करता है। इसे बदलने से कुल चौड़ाई और ऊँचाई अनुपातिक रूप से बदलती है।

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Why this matters* – बड़ा X‑डायमेंशन बड़ा बारकोड बनाता है, जो लो‑रिज़ॉल्यूशन प्रिंटरों के लिए उपयोगी है। इसके विपरीत, छोटा मान छोटे लेबलों के लिए कॉम्पैक्ट बारकोड देता है।

### Step 3: बारकोड एस्पेक्ट रेशियो को 15 सेट करें और इमेज सहेजें

**बारकोड एस्पेक्ट रेशियो** ऊँचाई‑से‑चौड़ाई संबंध को नियंत्रित करता है। 15 का एस्पेक्ट रेशियो अपेक्षाकृत लंबा बारकोड देता है।

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Why this matters* – विभिन्न स्कैनिंग डिवाइसों की एस्पेक्ट‑रेशियो आवश्यकताएँ अलग‑अलग होती हैं। रेशियो को 15 पर सेट करने से **बारकोड आकार कैसे बदलें** को ऊँचाई बदलकर, जबकि X‑डायमेंशन द्वारा निर्धारित चौड़ाई को स्थिर रखकर दिखाया जाता है।

#### Expected output

फ़ाइल `DatabarAspectRatio15.png` एक DataBar Stacked Omni‑Directional बारकोड दिखाती है जो डिफ़ॉल्ट से अधिक लंबा है। बारकोड की चौड़ाई 2‑पिक्सेल X‑डायमेंशन को दर्शाती है, और ऊँचाई 15‑रेशियो के अनुसार होती है।

### Step 4: बारकोड एस्पेक्ट रेशियो को 30 सेट करें और नई इमेज सहेजें

एस्पेक्ट रेशियो को 30 करने से बारकोड और भी लंबा हो जाता है, जिससे आकार समायोजन की लचीलापन दिखता है।

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Why this matters* – **बारकोड एस्पेक्ट रेशियो** मान को बदलकर आप तुरंत देख सकते हैं कि **बारकोड आकार कैसे बदलें** बिना जेनरेटर को फिर से बनाये। यह बैच परिदृश्यों में प्रोसेसिंग समय बचाता है।

#### Expected output

फ़ाइल `DatabarAspectRatio30.png` पिछले इमेज से स्पष्ट रूप से लंबा है, जिससे पुष्टि होती है कि एस्पेक्ट रेशियो सीधे बारकोड की ऊँचाई को प्रभावित करता है।

### Step 5: जेनरेटेड इमेजेज़ की पुष्टि करें

PNG फ़ाइलों को किसी भी इमेज व्यूअर में खोलें। आपको दो बारकोड दिखने चाहिए जिनकी चौड़ाई (X‑डायमेंशन द्वारा नियंत्रित) समान हो, लेकिन ऊँचाई (एस्पेक्ट रेशियो द्वारा नियंत्रित) अलग हो। यदि इमेज ब्लरी दिखे, तो X‑डायमेंशन पिक्सेल बढ़ाएँ; यदि बहुत लंबी हो, तो एस्पेक्ट रेशियो घटाएँ।

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Why this matters* – प्रोग्रामेटिक वैरिफिकेशन सुनिश्चित करता है कि आकार परिवर्तन सही ढंग से लागू हुए हैं, जो ऑटोमेटेड बिल्ड पाइपलाइन के लिए महत्वपूर्ण है।

## Common variations and edge cases

| Situation | Adjustment | Reason |
|-----------|------------|--------|
| **बहुत छोटे लेबल** | `XDimension.Pixels = 1` और `AspectRatio = 10` सेट करें | कुल फुटप्रिंट कम करता है जबकि पठनीयता बनी रहती है |
| **हाई‑रेज़ॉल्यूशन प्रिंट** | `XDimension.Pixels = 4` और `AspectRatio = 20` सेट करें | पिक्सेल घनत्व बढ़ाता है जिससे आउटपुट क्रिस्प बनता है |
| **विभिन्न इमेज फॉर्मेट** | `BarCodeImageFormat.Png` को `BarCodeImageFormat.Jpeg` से बदलें | तब उपयोगी जब PNG सपोर्ट सीमित हो |
| **डायनामिक डेटा** | `BarcodeGenerator` कंस्ट्रक्टर में एक वेरिएबल स्ट्रिंग पास करें | प्रत्येक प्रोडक्ट के लिए स्वचालित रूप से बारकोड जनरेट करता है |

जब आपको विभिन्न आकारों के साथ कई बारकोड जनरेट करने हों, तो चरणों को एक मेथड में रैप करें:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

`GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` को कॉल करने से एक ही लाइन कोड में कस्टम आकार वाला बारकोड बनता है।

## Pro tips for reliable size changes

* **हमें हमेशा X‑डायमेंशन को एस्पेक्ट रेशियो से पहले सेट करना चाहिए।** एस्पेक्ट रेशियो पहले बदलने से अनपेक्षित स्केलिंग हो सकती है यदि X‑डायमेंशन डिफ़ॉल्ट रूप से अनुकूल नहीं है।  
* **एक सुसंगत आउटपुट फ़ोल्डर उपयोग करें।** डेमो के लिए `"YOUR_DIRECTORY"` हार्ड‑कोड करना ठीक है, लेकिन प्रोडक्शन में `Path.Combine(Environment.CurrentDirectory, "Barcodes")` पसंद करें।  
* **जेनरेटेड इमेज का आकार वैलिडेट करें।** X‑डायमेंशन में छोटे बदलाव स्क्रीन पर दिख नहीं सकते; पिक्सेल डाइमेंशन चेक करने से सुनिश्चित होता है कि परिवर्तन प्रभावी हुआ।

## Conclusion

अब आप **C# में DataBar Stacked Omni‑Directional बारकोड जेनरेटर** का उपयोग करके **बारकोड आकार कैसे बदलें** जानते हैं। **X‑डायमेंशन पिक्सेल** और **बारकोड एस्पेक्ट रेशियो** को समायोजित करके आप किसी भी लेबल आकार या रिज़ॉल्यूशन आवश्यकता के लिए PNG इमेज बना सकते हैं। ऊपर दिया गया पूरा, रन करने योग्य उदाहरण जेनरेटर निर्माण से लेकर आकार वैरिफिकेशन तक का पूर्ण वर्कफ़्लो दर्शाता है।

### What to explore next

* **कस्टम रंग** – `barcodeGenerator.Parameters.Barcode.ForeColor` और `BackColor` को बदलकर ब्रांड गाइडलाइन के अनुसार रंग सेट करें।  
* **विभिन्न बारकोड प्रकार** – `EncodeTypes.DatabarStackedOmniDirectional` को `EncodeTypes.QR` या `EncodeTypes.Code128` से बदलें और देखें कि आकार पैरामीटर विभिन्न सिम्बोलॉजी में कैसे बदलते हैं।  
* **बैच प्रोसेसिंग** – `GenerateDatabar` मेथड को CSV इम्पोर्ट के साथ जोड़ें और हजारों बारकोड स्वचालित रूप से बनाएं।

कोड स्निपेट्स को अपने प्रोजेक्ट की आर्किटेक्चर के अनुसार अनुकूलित करें, और बारकोड आकार समायोजन से स्कैनिंग विश्वसनीयता और विज़ुअल डिज़ाइन को बेहतर बनाएं। Happy coding!

## What Should You Learn Next?

नीचे दिए गए ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में महारत हासिल कर सकें और अपने प्रोजेक्ट में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर कर सकें।

- [बारकोड आकार कैसे समायोजित करें – Codablock F एस्पेक्ट रेशियो Aspose.BarCode for .NET के साथ](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Aspose.BarCode for .NET का उपयोग करके कस्टम एस्पेक्ट रेशियो के साथ Aztec बारकोड कैसे जनरेट करें](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [One-Dimensional Databar के लिए बारकोड ऊँचाई कैसे जनरेट और समायोजित करें Aspose.BarCode for .NET के साथ](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}