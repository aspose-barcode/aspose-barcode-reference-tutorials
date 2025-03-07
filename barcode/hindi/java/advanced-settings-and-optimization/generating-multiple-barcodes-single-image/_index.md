---
title: Aspose.BarCode के साथ जावा में एक ही छवि पर एकाधिक बारकोड उत्पन्न करना
linktitle: एक ही छवि पर एकाधिक बारकोड उत्पन्न करना
second_title: Aspose.BarCode जावा एपीआई
description: Java के लिए Aspose.BarCode का उपयोग करके आसानी से एक ही छवि पर एकाधिक बारकोड उत्पन्न करें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 19
url: /hi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode के साथ जावा में एक ही छवि पर एकाधिक बारकोड उत्पन्न करना

## परिचय

जावा प्रोग्रामिंग की गतिशील दुनिया में, विभिन्न अनुप्रयोगों के लिए बारकोड को कुशलतापूर्वक बनाना और प्रबंधित करना महत्वपूर्ण है। जावा के लिए Aspose.BarCode इस प्रक्रिया को सरल बनाता है, जिससे डेवलपर्स को एक ही छवि पर निर्बाध रूप से कई बारकोड उत्पन्न करने की अनुमति मिलती है। यह ट्यूटोरियल जावा वातावरण में Aspose.BarCode का उपयोग करके इसे प्राप्त करने के चरणों के माध्यम से आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- जावा प्रोग्रामिंग की बुनियादी समझ.
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- जावा लाइब्रेरी के लिए Aspose.BarCode डाउनलोड और सेटअप किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/barcode/java/).
- एक एकीकृत विकास वातावरण (आईडीई) जैसे कि एक्लिप्स या इंटेलीजे आईडीईए।

## नामस्थान आयात करें

अपने जावा प्रोजेक्ट में, Aspose.BarCode कार्यक्षमता तक पहुँचने के लिए आवश्यक नामस्थान आयात करें। अपनी जावा क्लास की शुरुआत में निम्नलिखित आयात विवरण जोड़ें:

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

## चरण 1: संसाधन निर्देशिका सेट करें

संसाधन निर्देशिका के पथ को परिभाषित करें जहां जेनरेट किए गए बारकोड सहेजे जाएंगे। यह निर्देशिका आपकी बारकोड छवियों को व्यवस्थित और प्रबंधित करने के लिए महत्वपूर्ण है।

```java
// संसाधन निर्देशिका का पथ.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## चरण 2: बारकोड का एक संग्रह बनाएं

बारकोड डेटा संग्रहीत करने के लिए हैशमैप प्रारंभ करें। संग्रह में प्रत्येक प्रविष्टि अपने संबंधित एन्कोडिंग प्रकार के साथ एक बारकोड का प्रतिनिधित्व करती है।

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## चरण 3: बारकोड छवियाँ उत्पन्न करें

संग्रह के माध्यम से पुनरावृति करें और Aspose.BarCode लाइब्रेरी का उपयोग करके बारकोड छवियां उत्पन्न करें। आगे की प्रक्रिया के लिए छवियों को ArrayList में संग्रहीत करें।

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## चरण 4: एक संयुक्त छवि बनाएं

बारकोड छवियों की अधिकतम चौड़ाई और कुल ऊंचाई निर्धारित करें। अलग-अलग बारकोड छवियों को एकल आउटपुट छवि में संयोजित करने के लिए एक बफ़र्डइमेज बनाएं।

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

अंतिम संयुक्त छवि को निर्दिष्ट फ़ाइल स्थान पर सहेजें।

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## निष्कर्ष

बधाई हो! आपने जावा के लिए Aspose.BarCode का उपयोग करके एक ही छवि पर सफलतापूर्वक कई बारकोड जेनरेट किए हैं। यह शक्तिशाली लाइब्रेरी बारकोड हैंडलिंग को सरल बनाती है, जिससे यह जावा डेवलपर्स के लिए एक अमूल्य टूल बन जाती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं उत्पन्न छवि में अलग-अलग बारकोड की उपस्थिति को अनुकूलित कर सकता हूँ?

A1: हाँ, Aspose.BarCode बारकोड उपस्थिति के लिए व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप प्रत्येक बारकोड की शैली को अपनी प्राथमिकताओं के अनुसार तैयार कर सकते हैं।

### Q2: क्या Aspose.BarCode विभिन्न बारकोड प्रतीकों के साथ संगत है?

ए2: बिल्कुल! Aspose.BarCode, Code_39, DATA_MATRIX, QR, Code_128, EAN_13, और AZTEC सहित सहजीवन की एक विस्तृत श्रृंखला का समर्थन करता है, जैसा कि इस ट्यूटोरियल में दिखाया गया है।

### Q3: मैं Aspose.BarCode को अपने जावा प्रोजेक्ट में कैसे एकीकृत कर सकता हूं?

 A3: बस जावा लाइब्रेरी के लिए Aspose.BarCode डाउनलोड करें[यहाँ](https://releases.aspose.com/barcode/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### Q4: क्या मैं व्यावसायिक अनुप्रयोगों के लिए Aspose.BarCode का उपयोग कर सकता हूँ?

 उ4: हां, आप यहां से लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/buy) व्यावसायिक उद्देश्यों के लिए Aspose.BarCode का उपयोग करना।

### Q5: क्या Aspose.BarCode के लिए कोई परीक्षण विकल्प उपलब्ध है?

 ए5: निश्चित रूप से! आप निःशुल्क परीक्षण लाइसेंस प्राप्त करके Aspose.BarCode की सुविधाओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
