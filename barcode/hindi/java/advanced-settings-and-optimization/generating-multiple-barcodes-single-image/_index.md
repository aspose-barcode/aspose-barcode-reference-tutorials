---
date: 2026-04-03
description: Aspose.BarCode for Java का उपयोग करके QR कोड जावा कैसे बनाएं और एक ही
  छवि पर कई बारकोड उत्पन्न करें, सीखें। इसमें सेटअप, कोड और समस्या निवारण शामिल है।
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: एक ही छवि पर कई बारकोड बनाना
second_title: Aspose.BarCode Java API
title: QR कोड जावा बनाएं – एक ही छवि पर कई बारकोड उत्पन्न करें
url: /hi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR कोड जावा बनाएं – एक छवि पर कई बारकोड उत्पन्न करना

## परिचय

इस ट्यूटोरियल में, आप **how to create QR code java** सीखेंगे और **Aspose.BarCode for Java** का उपयोग करके कई विभिन्न बारकोड प्रकारों को एक ही छवि में संयोजित करेंगे। चाहे आपको एक कॉम्पैक्ट QR लेबल, एक प्रोडक्ट बारकोड, या 2‑D और लीनियर सिम्बोलॉजीज़ का मिश्रण चाहिए, यह गाइड आपको हर चरण से ले जाता है—प्रोजेक्ट सेटअप से लेकर अंतिम संयुक्त छवि को सहेजने तक—ताकि आप तुरंत अपने Java एप्लिकेशन में बारकोड जेनरेशन को एकीकृत करना शुरू कर सकें।

## त्वरित उत्तर
- **What library should I use?** Aspose.BarCode for Java सबसे पूर्ण सिम्बोलॉजी सेट प्रदान करता है।  
- **Can I generate different barcode types together?** हाँ, आप एक ही कैनवास पर CODE_39, QR, AZTEC और अधिक को मिलाकर उपयोग कर सकते हैं।  
- **Do I need a license for development?** परीक्षण के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **Which Java version is supported?** Java 8 और उसके बाद के संस्करण पूरी तरह संगत हैं।  
- **Is the output format configurable?** आप संयुक्त छवि को PNG, JPEG, BMP आदि के रूप में निर्यात कर सकते हैं।  

## create QR code java क्या है?

Java में QR कोड बनाना मतलब एक टेक्स्ट स्ट्रिंग को दो‑आयामी मैट्रिक्स में बदलना है जिसे स्मार्टफ़ोन या बारकोड रीडर स्कैन कर सकते हैं। **Aspose.BarCode for Java** एन्कोडिंग और रेंडरिंग को संभालता है, जिससे आप लो‑लेवल इमेज प्रोसेसिंग के बजाय बिजनेस लॉजिक पर ध्यान केंद्रित कर सकते हैं।

## Aspose.BarCode Java का उपयोग बारकोड जावा उत्पन्न करने के लिए क्यों करें?

- **Broad symbology support** – क्लासिक लीनियर कोड्स से लेकर आधुनिक 2‑D मैट्रिक्स तक।  
- **High‑quality rendering** – एंटी‑एलियास्ड आउटपुट जो किसी भी डिवाइस पर काम करता है।  
- **Simple API** – कुछ ही मेथड कॉल्स के साथ बारकोड बनाएं, कस्टमाइज़ करें और संयोजित करें।  
- **No external dependencies** – सभी चीज़ें JVM पर चलती हैं बिना किसी नेटिव लाइब्रेरी के।  

## पूर्वापेक्षाएँ

ट्यूटोरियल में डुबने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- Java प्रोग्रामिंग की बुनियादी समझ।  
- सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.BarCode for Java लाइब्रेरी डाउनलोड और सेट अप की हुई हो। आप इसे [here](https://releases.aspose.com/barcode/java/) से डाउनलोड कर सकते हैं।  
- Eclipse या IntelliJ IDEA जैसे इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) हो।  

## नेमस्पेसेस आयात करें

अपने Java प्रोजेक्ट में, Aspose.BarCode कार्यक्षमता तक पहुंचने के लिए आवश्यक नेमस्पेसेस आयात करें। अपने Java क्लास की शुरुआत में निम्नलिखित इम्पोर्ट स्टेटमेंट्स जोड़ें:

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

## चरण 1: रिसोर्स डायरेक्टरी सेट करें

उस रिसोर्स डायरेक्टरी का पाथ परिभाषित करें जहाँ उत्पन्न बारकोड सहेजे जाएंगे। यह डायरेक्टरी आपके बारकोड इमेजेज को व्यवस्थित और प्रबंधित करने के लिए महत्वपूर्ण है।

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## चरण 2: बारकोड्स का संग्रह बनाएं

`HashMap` को इनिशियलाइज़ करें ताकि बारकोड डेटा स्टोर किया जा सके। संग्रह में प्रत्येक एंट्री एक बारकोड को उसके संबंधित एन्कोडिंग टाइप के साथ दर्शाती है।

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## चरण 3: बारकोड छवियां उत्पन्न करें

संग्रह के माध्यम से इटररेट करें और Aspose.BarCode लाइब्रेरी का उपयोग करके बारकोड इमेजेज उत्पन्न करें। आगे की प्रोसेसिंग के लिए इमेजेज को `ArrayList` में स्टोर करें।

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## चरण 4: संयुक्त छवि बनाएं

बारकोड इमेजेज की अधिकतम चौड़ाई और कुल ऊँचाई निर्धारित करें। व्यक्तिगत बारकोड इमेजेज को एक ही आउटपुट इमेज में संयोजित करने के लिए `BufferedImage` बनाएं।

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

## चरण 5: परिणाम सहेजें

अंतिम संयुक्त इमेज को निर्दिष्ट फ़ाइल लोकेशन पर सहेजें।

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## एकाधिक बारकोड उत्पन्न करने के सामान्य उपयोग केस

- **Packaging labels** – एक ही लेबल पर प्रोडक्ट, बैच और शिपिंग कोड्स को संयोजित करें।  
- **Event tickets** – विभिन्न स्कैनिंग स्टेशनों के लिए QR, Data Matrix, और Code 128 आइडेंटिफ़ायर्स एम्बेड करें।  
- **Inventory management** – तेज़ ऑडिट के लिए SKU, RFID टैग डेटा और सीरियल नंबर एक साथ दिखाएं।  

## समस्या निवारण और टिप्स

- **Image size issues** – बारकोड्स के बीच स्पेसिंग बढ़ाने या घटाने के लिए `offset` वेरिएबल को समायोजित करें।  
- **Unsupported symbology** – सुनिश्चित करें कि आपका Aspose.BarCode संस्करण इच्छित बारकोड टाइप को सपोर्ट करता है।  
- **Performance** – यदि आप लूप में कई इमेजेज बनाते हैं तो एक ही `Graphics` ऑब्जेक्ट को पुन: उपयोग करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं उत्पन्न इमेज में व्यक्तिगत बारकोड की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A1: हाँ, Aspose.BarCode बारकोड की उपस्थिति के लिए विस्तृत कस्टमाइज़ेशन विकल्प प्रदान करता है, जिससे आप प्रत्येक बारकोड की शैली को अपनी पसंद के अनुसार अनुकूलित कर सकते हैं।

**Q2: क्या Aspose.BarCode विभिन्न बारकोड सिम्बोलॉजीज़ के साथ संगत है?**  
A2: बिल्कुल! Aspose.BarCode कई सिम्बोलॉजीज़ को सपोर्ट करता है, जिसमें CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, और AZTEC शामिल हैं, जैसा कि इस ट्यूटोरियल में दिखाया गया है।

**Q3: मैं Aspose.BarCode को अपने Java प्रोजेक्ट में कैसे इंटीग्रेट कर सकता हूँ?**  
A3: बस [here](https://releases.aspose.com/barcode/java/) से Aspose.BarCode for Java लाइब्रेरी डाउनलोड करें और दस्तावेज़ में दी गई इंस्टॉलेशन निर्देशों का पालन करें।

**Q4: क्या मैं Aspose.BarCode को व्यावसायिक एप्लिकेशन्स में उपयोग कर सकता हूँ?**  
A4: हाँ, आप [here](https://purchase.aspose.com/buy) से लाइसेंस प्राप्त करके Aspose.BarCode को व्यावसायिक उद्देश्यों के लिए उपयोग कर सकते हैं।

**Q5: क्या Aspose.BarCode के लिए कोई ट्रायल विकल्प उपलब्ध हैं?**  
A5: बिल्कुल! आप [here](https://releases.aspose.com/) से एक फ्री ट्रायल लाइसेंस प्राप्त करके Aspose.BarCode की सुविधाओं को एक्सप्लोर कर सकते हैं।

**Q6: प्रिंटिंग के लिए हाई‑रेज़ोल्यूशन QR कोड कैसे जनरेट करूँ?**  
A6: `generateBarCodeImage()` कॉल करने से पहले `BarcodeGenerator` पर इच्छित DPI सेट करें, फिर इमेज को PNG जैसे लॉस‑लेस फॉर्मेट में सहेजें।

**Q7: यदि संयुक्त इमेज कट गई दिखे तो मुझे क्या करना चाहिए?**  
A7: सुनिश्चित करें कि `offset` और कैनवास साइज की गणनाएँ सभी बारकोड की ऊँचाइयों को सही ढंग से ध्यान में रखती हैं; कैनवास की ऊँचाई बढ़ाने या व्यक्तिगत बारकोड साइज को घटाने से अधिकांश ट्रंकेशन समस्याएँ हल हो जाती हैं।

---

**अंतिम अपडेट:** 2026-04-03  
**परीक्षण किया गया:** Aspose.BarCode for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}