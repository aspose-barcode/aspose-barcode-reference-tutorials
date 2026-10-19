---
date: 2026-10-19
description: Aspose.BarCode for Java का उपयोग करके QR code java बनाना और एकल छवि पर
  कई बारकोड उत्पन्न करना सीखें। इसमें setup, code, और troubleshooting शामिल हैं।
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: एकल छवि पर कई बारकोड उत्पन्न करना
og_description: Aspose.BarCode for Java के साथ QR code java बनाएं और कई barcode प्रकारों
  को एकल छवि में संयोजित करें। step‑by‑step guide का पालन करें, code snippets देखें,
  और troubleshooting tips सीखें।
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR code java बनाएं – एक छवि पर कई बारकोड उत्पन्न करें
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR code java बनाएं – एक छवि पर कई बारकोड उत्पन्न करें
url: /hi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR कोड जावा बनाएं – एक छवि पर कई बारकोड उत्पन्न करें

## परिचय

इस ट्यूटोरियल में आप सीखेंगे **how to create QR code java** और **Aspose.BarCode for Java** का उपयोग करके विभिन्न बारकोड प्रकारों को एक ही कैनवास पर मिलाएंगे। चाहे आपको एक कॉम्पैक्ट QR लेबल, प्रोडक्ट बारकोड, या 2‑D और लीनियर सिम्बोलॉजीज़ का मिश्रण चाहिए, यह गाइड आपको प्रोजेक्ट सेटअप से लेकर अंतिम संयुक्त छवि को सेव करने तक हर चरण में मार्गदर्शन करता है—ताकि आप तुरंत अपने जावा एप्लिकेशन में बारकोड जेनरेशन को इंटीग्रेट करना शुरू कर सकें।

## त्वरित उत्तर
- **मैं कौनसी लाइब्रेरी उपयोग करूँ?** Aspose.BarCode for Java सबसे पूर्ण सिम्बोलॉजी सेट प्रदान करता है।  
- **क्या मैं विभिन्न बारकोड प्रकारों को एक साथ जेनरेट कर सकता हूँ?** हाँ, आप CODE_39, QR, AZTEC, और अधिक को एक ही कैनवास पर मिला सकते हैं।  
- **क्या विकास के लिए मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौनसा जावा संस्करण समर्थित है?** Java 8 और उसके बाद के संस्करण पूरी तरह संगत हैं।  
- **क्या आउटपुट फ़ॉर्मेट कॉन्फ़िगर किया जा सकता है?** आप संयुक्त छवि को PNG, JPEG, BMP, या TIFF के रूप में एक्सपोर्ट कर सकते हैं।

## create QR code java क्या है?

`create QR code java` वह प्रक्रिया है जिसमें टेक्स्ट स्ट्रिंग को दो‑आयामी मैट्रिक्स में बदला जाता है जिसे स्मार्टफ़ोन या बारकोड रीडर स्कैन कर सकते हैं। Aspose.BarCode for Java एन्कोडिंग और रेंडरिंग करता है, इसलिए आप पिक्सेल‑लेवल इमेज हैंडलिंग के बजाय बिज़नेस लॉजिक पर ध्यान केंद्रित कर सकते हैं।

## Aspose.BarCode Java का उपयोग बारकोड जावा जनरेट करने के लिए क्यों करें?

Aspose.BarCode **50 से अधिक बारकोड सिम्बोलॉजीज़** का समर्थन करता है—जिसमें QR, Data Matrix, Code 128, AZTEC, और पारंपरिक लीनियर कोड शामिल हैं—जिससे यह सबसे बहुमुखी जावा बारकोड लाइब्रेरी बनती है। यह **1200 dpi तक एंटी‑एलियास्ड इमेज** रेंडर करता है, जिससे स्क्रीन और प्रिंट पर स्पष्ट स्कैन सुनिश्चित होते हैं। API को केवल JVM की आवश्यकता होती है और यह कुछ ही कोड लाइनों में आकार, रंग, मार्जिन, और एरर करेक्शन को कस्टमाइज़ करने के लिए एक सहज कॉन्फ़िगरेशन मॉडल प्रदान करता है।

## पूर्वापेक्षाएँ

- Java मूलभूत अवधारणाओं की ठोस समझ।  
- JDK 8 या उससे नया, स्थापित और आपके PATH में कॉन्फ़िगर किया हुआ।  
- Aspose.BarCode for Java JAR (आधिकारिक Aspose.BarCode for Java डाउनलोड पेज से डाउनलोड करें)।  
- IntelliJ IDEA या Eclipse जैसे IDE, सैंपल को एडिट और रन करने के लिए।  

## नेमस्पेस इम्पोर्ट करें

इम्पोर्ट स्टेटमेंट्स Aspose.BarCode क्लासेज़ जैसे `BarcodeGenerator`, `EncodeTypes`, और `BarCodeImageFormat` को स्कोप में लाते हैं, जिससे आप उन्हें पूरी‑क्वालिफ़ाइड नामों के बिना रेफ़र कर सकते हैं।  
`BarcodeGenerator` वह मुख्य क्लास है जिसका उपयोग बारकोड इमेजेज़ को कॉन्फ़िगर और जेनरेट करने के लिए किया जाता है।  
`EncodeTypes` Aspose.BarCode में एक enum है जो जेनरेट किए जाने वाले बारकोड सिम्बोलॉजी को निर्दिष्ट करता है।  
`BarCodeImageFormat` जेनरेट किए गए बारकोड के आउटपुट इमेज फ़ॉर्मेट को परिभाषित करता है।

## चरण 1: रिसोर्स डायरेक्टरी सेट करें

**resource directory** वह फ़ोल्डर है आपके फ़ाइल सिस्टम पर जहाँ सभी जेनरेट किए गए बारकोड इमेजेज़ लिखे जाएंगे। इसे एक बार परिभाषित करने से आपका प्रोजेक्ट व्यवस्थित रहता है और पुरानी फ़ाइलों को साफ़ करना आसान हो जाता है।

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## चरण 2: बारकोड्स का कलेक्शन बनाएं

`HashMap<String, EncodeTypes>` प्रत्येक बारकोड की डेटा स्ट्रिंग को उस सिम्बोलॉजी के साथ संग्रहीत करता है जिसे आप उपयोग करना चाहते हैं। `HashMap` जावा का एक कलेक्शन है जो कुंजियों को मानों से मैप करता है। यह कलेक्शन आगे के जेनरेशन लूप को चलाता है। `EncodeTypes` एक enum है जो यह निर्दिष्ट करता है कि कौनसा बारकोड प्रकार जेनरेट करना है।

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## चरण 3: बारकोड इमेजेज़ जेनरेट करें

जेनरेशन लूप `HashMap` पर इटरेट करता है, प्रत्येक एंट्री के लिए एक `BarcodeGenerator` बनाता है, और `generateBarCodeImage()` को कॉल करके एक `BufferedImage` प्राप्त करता है। `generateBarCodeImage()` रेंडर किए गए बारकोड वाली `BufferedImage` बनाता है। `BufferedImage` जावा की एक क्लास है जो मेमोरी में इमेज को दर्शाती है। सभी इमेजेज़ को बाद में कॉम्पोज़िंग के लिए एक `ArrayList<BufferedImage>` में जोड़ा जाता है। `ArrayList` जावा में एक रिसाइज़ेबल लिस्ट इम्प्लीमेंटेशन है।

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## चरण 4: संयुक्त इमेज बनाएं

पहले, एल्गोरिद्म सभी बारकोड इमेजेज़ में **अधिकतम चौड़ाई** और उन्हें वैकल्पिक स्पेसिंग के साथ वर्टिकली स्टैक करने के लिए आवश्यक **कुल ऊँचाई** की गणना करता है। फिर वह उस आकार की एक `BufferedImage` बनाता है और प्रत्येक बारकोड को `Graphics2D` ऑब्जेक्ट का उपयोग करके कैनवास पर ड्रॉ करता है। `Graphics2D` जावा की एक क्लास है जो शैप्स और इमेजेज़ को ड्रॉ करने के लिए 2D रेंडरिंग क्षमताएँ प्रदान करती है।

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## चरण 5: परिणाम सहेजें

अंत में, कॉम्पोज़िट इमेज को `ImageIO.write` के साथ डिस्क पर लिखा जाता है, आप द्वारा निर्दिष्ट फ़ॉर्मेट (PNG, JPEG, BMP, या TIFF) का उपयोग करके। `ImageIO.write` निर्दिष्ट फ़ॉर्मेट में `BufferedImage` को फ़ाइल में लिखता है। फ़ाइल पाथ पहले परिभाषित रिसोर्स डायरेक्टरी के सापेक्ष होता है।

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## कई बारकोड जेनरेट करने के सामान्य उपयोग केस

- **Packaging labels** – प्रोडक्ट, बैच, और शिपिंग कोड को एक ही लेबल पर मिलाकर प्रिंटिंग लागत कम की जा सकती है।  
- **Event tickets** – स्थल पर विभिन्न स्कैनिंग स्टेशनों के लिए QR, Data Matrix, और Code 128 आइडेंटिफ़ायर्स एम्बेड करें।  
- **Inventory management** – तेज़ ऑडिट और ट्रेसबिलिटी के लिए SKU, RFID टैग डेटा, और सीरियल नंबर एक साथ प्रदर्शित करें।  

## समस्या निवारण और टिप्स

- **Image size issues** – बारकोड्स के बीच स्पेसिंग बढ़ाने या घटाने के लिए `offset` वेरिएबल को समायोजित करें।  
- **Unsupported symbology** – सुनिश्चित करें कि आपका Aspose.BarCode संस्करण इच्छित बारकोड प्रकार को सपोर्ट करता है; नए रिलीज़ अतिरिक्त 2‑D कोड जोड़ते हैं।  
- **Performance** – लूप में कई इमेजेज़ जेनरेट करते समय ऑब्जेक्ट अलोकेशन ओवरहेड को कम करने के लिए एक ही `Graphics2D` ऑब्जेक्ट को पुनः उपयोग करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं जेनरेट की गई इमेज में व्यक्तिगत बारकोड की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ। `BarcodeGenerator` की प्रॉपर्टीज़ जैसे `setBarColor`, `setBackgroundColor`, और `setXDimension` का उपयोग करके प्रत्येक बारकोड को कैनवास में जोड़ने से पहले स्वतंत्र रूप से स्टाइल करें।

**Q: क्या Aspose.BarCode विभिन्न बारकोड सिम्बोलॉजीज़ के साथ संगत है?**  
A: बिल्कुल। लाइब्रेरी 50+ सिम्बोलॉजीज़ का समर्थन करती है, जिसमें CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, और AZTEC शामिल हैं, जैसा कि इस ट्यूटोरियल में दिखाया गया है।

**Q: मैं Aspose.BarCode को अपने जावा प्रोजेक्ट में कैसे इंटीग्रेट करूँ?**  
A: Aspose.BarCode for Java लाइब्रेरी डाउनलोड पेज से JAR डाउनलोड करें, इसे अपने प्रोजेक्ट के क्लासपाथ में जोड़ें, और “Import namespaces” सेक्शन में दिखाए अनुसार आवश्यक नेमस्पेस इम्पोर्ट करें।

**Q: क्या मैं Aspose.BarCode को कमर्शियल एप्लिकेशन में उपयोग कर सकता हूँ?**  
A: हाँ। ट्रायल सीमाओं को हटाने और पूर्ण प्रोडक्शन सपोर्ट प्राप्त करने के लिए Aspose.BarCode लाइसेंस खरीद पेज से लाइसेंस खरीदें।

**Q: क्या Aspose.BarCode के लिए ट्रायल विकल्प उपलब्ध हैं?**  
A: बिल्कुल। Aspose.BarCode फ्री ट्रायल डाउनलोड पेज से एक फ्री ट्रायल लाइसेंस उपलब्ध है, जो आपको मूल्यांकन के लिए पूर्ण API एक्सेस देता है।

**Q: मैं प्रिंटिंग के लिए हाई‑रिज़ॉल्यूशन QR कोड कैसे जेनरेट करूँ?**  
A: `generateBarCodeImage()` को कॉल करने से पहले `BarcodeGenerator` पर `setResolutionDpi` प्रॉपर्टी सेट करें, फिर परिणाम को PNG जैसे लॉसलेस फ़ॉर्मेट में सेव करें।

**Q: यदि संयुक्त इमेज कट गई दिखे तो मुझे क्या करना चाहिए?**  
A: सुनिश्चित करें कि `offset` और कैनवास साइज की गणनाएँ सभी बारकोड ऊँचाइयों को सही ढंग से ध्यान में रखती हैं; कैनवास की ऊँचाई बढ़ाने या व्यक्तिगत बारकोड साइज घटाने से अधिकांश ट्रंकेशन समस्याएँ हल हो जाती हैं।

---

**अंतिम अपडेट:** 2026-10-19  
**परीक्षित संस्करण:** Aspose.BarCode for Java 24.11  
**लेखक:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## संबंधित ट्यूटोरियल

- [जावा में बारकोड इमेज बनाना – Aspose के साथ बॉर्डर जोड़ें](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [जावा में बारकोड जेनरेट करना: Aspose.BarCode के साथ स्ट्रीम्स में सेव करें](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [जावा में बारकोड जेनरेट करना और Aspose के साथ बारकोड प्रिंट करना](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}