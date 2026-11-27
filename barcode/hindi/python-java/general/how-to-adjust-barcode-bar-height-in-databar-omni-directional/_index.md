---
category: general
date: 2026-11-27
description: DataBar Omni‑Directional बारकोड जेनरेटर में बारकोड की बार ऊँचाई को कैसे
  समायोजित करें, सीखें। चरण‑दर‑चरण कोड दिखाता है कि ऊँचाई को 30 px और 60 px पर कैसे
  सेट किया जाए।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: hi
lastmod: 2026-11-27
og_description: Python के साथ DataBar Omni‑Directional बारकोड जेनरेटर में बारकोड की
  बार ऊँचाई समायोजित करें। ऊँचाइयों, X‑डायमेंशन को सेट करने और PNG छवियों को सहेजने
  के लिए पूर्ण गाइड का पालन करें।
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: डेटाबार ओम्नी‑डायरेक्शनल जनरेटर में बारकोड बार की ऊँचाई समायोजित करें
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: DataBar Omni‑Directional जेनरेटर में बारकोड बार की ऊँचाई कैसे समायोजित करें
url: /hi/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataBar Omni‑Directional जेनरेटर में बारकोड बार की ऊँचाई कैसे समायोजित करें

यदि आपको DataBar Omni‑Directional बारकोड के लिए **बारकोड बार की ऊँचाई** समायोजित करनी है, तो यह गाइड आपको ठीक‑ठीक दिखाता है। आप एक पूर्ण, चलाने योग्य Python उदाहरण देखेंगे जो बार की ऊँचाई को 30 px से 60 px तक बदलता है जबकि X‑dimension और इमेज फ़ॉर्मेट को समान रखता है।

बारकोड के दृश्य आयाम बदलना एक सामान्य आवश्यकता है जब बारकोड को किसी विशिष्ट लेबल आकार या डिज़ाइन गाइडलाइन में फिट करना हो। बार ऊँचाई के अलावा, आप **X‑dimension** (मॉड्यूल आकार) को भी समायोजित करना चाह सकते हैं या PNG या JPEG जैसे अलग **बारकोड इमेज फ़ॉर्मेट** चुन सकते हैं।

इस ट्यूटोरियल में आप करेंगे:

* आवश्यक लाइब्रेरी (GroupDocs.Barcode for Python) स्थापित करें
* DataBar Omni‑Directional बारकोड जेनरेटर बनाएं
* `XDimension` के साथ मॉड्यूल आकार सेट करें
* बार ऊँचाई प्रॉपर्टी को दो बार समायोजित करें
* परिणामस्वरूप इमेजेज को इच्छित **BarCodeImageFormat** में सहेजें

GroupDocs API का कोई पूर्व अनुभव आवश्यक नहीं है—सिर्फ बुनियादी Python ज्ञान चाहिए।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* Python 3.8 या उससे नया स्थापित हो
* `groupdocs.barcode` पैकेज (`pip install groupdocs-barcode`)  
* एक फ़ोल्डर में लिखने की अनुमति जहाँ PNG फ़ाइलें सहेजी जाएँगी

यदि आप **DataBar Omni‑Directional बारकोड** से परिचित नहीं हैं, तो यह 14‑अंकीय GTIN को एन्कोड करता है और रिटेल में किसी भी अभिविन्यास से स्कैन करने के लिए व्यापक रूप से उपयोग होता है।

## चरण 1: DataBar Omni‑Directional बारकोड जेनरेटर सेट अप करें

पहले, आवश्यक क्लासेस इम्पोर्ट करें और वह जेनरेटर इंस्टैंशिएट करें जिसमें आप एन्कोड करना चाहते हैं GTIN डेटा हो।

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` कॉन्स्टेंट लाइब्रेरी को Omni‑Directional सिम्बोलॉजी उत्पन्न करने के लिए बताता है। डेटा स्ट्रिंग में AI `(01)` शामिल है जो GTIN‑14 मान को दर्शाता है।

## चरण 2: X‑dimension (मॉड्यूल आकार) परिभाषित करें

X‑dimension सबसे संकरी बार की चौड़ाई को नियंत्रित करता है। ऑन‑स्क्रीन रेंडरिंग के लिए एक सामान्य मान **2 px प्रति मॉड्यूल** है।

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

सतत **set XDimension** का उपयोग यह सुनिश्चित करता है कि बारकोड विभिन्न प्रिंटर और स्कैनर पर सही ढंग से स्केल हो।

## चरण 3: बार ऊँचाई को 30 px सेट करें और इमेज सहेजें

अब हम बार ऊँचाई प्रॉपर्टी बदलते हैं। पहली ऊँचाई जो हम उपयोग करेंगे वह **30 px** है, जो छोटे लेबल के लिए उपयुक्त है।

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` कॉन्स्टेंट **बारकोड इमेज फ़ॉर्मेट** PNG को चुनता है, जो लॉसलेस क्वालिटी को बनाए रखता है।

### अपेक्षित परिणाम

फ़ाइल `DatabarBarHeight30Pixels.png` में एक DataBar Omni‑Directional बारकोड है जिसकी बार 30 px ऊँची है। नीचे एक प्लेसहोल्डर प्रीव्यू है:

![30 px बार ऊँचाई वाला DataBar बारकोड](images/databar_30px.png "30 px बार ऊँचाई वाला DataBar बारकोड")

> **Tip:** यदि आप PNG को किसी इमेज एडिटर में खोलते हैं, तो आप सटीक बार ऊँचाई देख पाएँगे। संकरी बार 2 px चौड़ी हैं, जैसा कि पहले परिभाषित किया गया था।

## चरण 4: बार ऊँचाई को 60 px बढ़ाएँ

ऐसे अनुप्रयोगों के लिए जो बड़े दृश्य फुटप्रिंट की आवश्यकता रखते हैं—जैसे फ्रेट लेबल—आप बार ऊँचाई को **60 px** तक बढ़ा सकते हैं।

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

केवल `BarHeight` प्रॉपर्टी बदलती है; X‑dimension और एन्कोडिंग समान रहते हैं, इसलिए बारकोड स्कैन करने योग्य बना रहता है।

## चरण 5: अपडेटेड बारकोड इमेज सहेजें

अंत में, बड़े बारकोड को दूसरी PNG फ़ाइल में लिखें।

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### अपेक्षित परिणाम

फ़ाइल `DatabarBarHeight60Pixels.png` वही डेटा एन्कोड दिखाती है, लेकिन प्रत्येक बार अब 60 px ऊँचा है। दृश्य अंतर नीचे दर्शाया गया है:

![60 px बार ऊँचाई वाला DataBar बारकोड](images/databar_60px.png "60 px बार ऊँचाई वाला DataBar बारकोड")

## पूर्ण, चलाने योग्य उदाहरण

सब कुछ एक साथ रखकर, यहाँ पूरा स्क्रिप्ट है जिसे आप `adjust_barcode_height.py` नाम की फ़ाइल में कॉपी‑पेस्ट करके सीधे चला सकते हैं।

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

स्क्रिप्ट चलाएँ:

```bash
python adjust_barcode_height.py
```

आपको `output` फ़ोल्डर में दो PNG फ़ाइलें दिखनी चाहिए, प्रत्येक सेट की गई बार ऊँचाई को दर्शाती हैं।

## सामान्य प्रश्न और किनारे के मामले

| प्रश्न | उत्तर |
|----------|--------|
| **क्या मैं PNG के बजाय JPEG उपयोग कर सकता हूँ?** | हाँ। `BarCodeImageFormat.Png` को `BarCodeImageFormat.Jpeg` से बदलें। JPEG लॉसी है, इसलिए सटीक स्कैनिंग के लिए PNG को प्राथमिकता दें। |
| **यदि मुझे ऐसी बार ऊँचाई चाहिए जो 10 का गुणज न हो तो क्या करें?** | `BarHeight.Pixels` प्रॉपर्टी कोई भी पूर्णांक मान स्वीकार करती है। बस इच्छित पिक्सेल संख्या असाइन करें (उदा., `45`)। |
| **क्या बार ऊँचाई बदलने से एन्कोडेड डेटा प्रभावित होता है?** | नहीं। केवल दृश्य प्रतिनिधित्व बदलता है; अंतर्निहित डेटा स्ट्रिंग समान रहती है। |
| **पहली इमेज सहेजने के बाद X‑dimension कैसे बदलूँ?** | आप `save()` कॉल करने से पहले कभी भी `gen.parameters.barcode.x_dimension.pixels` को संशोधित कर सकते हैं। परिवर्तन अगले इमेजेज पर लागू होगा। |
| **क्या जेनरेटर थ्रेड‑सेफ़ है?** | `BarcodeGenerator` इंस्टेंस थ्रेड‑सेफ़ होने की गारंटी नहीं देता। यदि आप एक साथ कई थ्रेड में बारकोड जेनरेट करते हैं तो प्रत्येक थ्रेड के लिए अलग इंस्टेंस बनाएँ। |

## निष्कर्ष

आप अब Python का उपयोग करके DataBar Omni‑Directional बारकोड जेनरेटर में **बारकोड बार की ऊँचाई** कैसे समायोजित करें, जानते हैं। ट्यूटोरियल ने जेनरेटर बनाना, **X‑dimension** सेट करना, **बारकोड बार ऊँचाई** प्रॉपर्टी को बदलना, और इच्छित **बारकोड इमेज फ़ॉर्मेट** में इमेजेज सहेजना कवर किया।

अब आप विभिन्न ऊँचाइयों, अलग मॉड्यूल आकारों के साथ प्रयोग कर सकते हैं, या JPEG या BMP जैसे वैकल्पिक इमेज फ़ॉर्मेट पर स्विच कर सकते हैं। आप अतिरिक्त **barcode generator python** सुविधाओं जैसे ह्यूमन‑रीडेबल टेक्स्ट जोड़ना या कलर स्कीम बदलना भी एक्सप्लोर कर सकते हैं।

कोडिंग का आनंद लें, और अपने बारकोड को तेज़ और बिल्कुल सही आकार में रखें!

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में महारत हासिल कर सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच को एक्सप्लोर कर सकें।

- [GS1 DataBar Omni‑Directional बारकोड के लिए चौड़ाई सेट करने और ऊँचाई समायोजित करने का तरीका](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Python में Omni Directional Databar और बारकोड इमेज बनाएं](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net बारकोड जेनरेटर – बारकोड ऊँचाई बदलें](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}