---
category: general
date: 2026-07-30
description: Python में Databar Stacked Omnidirectional बारकोड बनाएं। इस चरण‑दर‑चरण
  गाइड का पालन करके aspect ratio, XDimension को कॉन्फ़िगर करें और Python बारकोड जेनरेटर
  का उपयोग करके PNG निर्यात करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: hi
lastmod: 2026-07-30
og_description: Python में Databar Stacked Omnidirectional बारकोड बनाएं। यह ट्यूटोरियल
  दिखाता है कि XDimension कैसे सेट करें, DataBar का अनुपात कैसे समायोजित करें, और
  BarCodeImageFormat के साथ PNG के रूप में कैसे सहेजें।
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: डेटाबार स्टैक्ड ओम्निडायरेक्शनल बारकोड बनाएं – पाइथन ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Python में डेटाबार स्टैक्ड ओम्निडायरेक्शनल बारकोड बनाएँ
url: /hi/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python में Databar Stacked Omnidirectional बारकोड बनाएं

क्या आपको कभी Python में **databar stacked omnidirectional** बारकोड बनाना पड़ा लेकिन शुरुआत नहीं पता थी? आप अकेले नहीं हैं—कई डेवलपर्स को `BarcodeGenerator` क्लास के साथ पहली बार काम करते समय यही समस्या आती है। अच्छी बात यह है कि मुख्य प्रॉपर्टीज़ को समझने के बाद पूरी प्रक्रिया काफी सरल है।

इस गाइड में हम एक पूर्ण, चलाने योग्य उदाहरण के माध्यम से चलेंगे जो **python barcode generator** का उपयोग करके XDimension सेट करता है, DataBar का aspect ratio समायोजित करता है, और अंत में दो PNG फ़ाइलें एक्सपोर्ट करता है। अंत तक आप किसी भी इन्वेंट्री या लॉजिस्टिक्स प्रोजेक्ट के लिए उच्च‑गुणवत्ता वाले stacked omnirectional सिम्बॉल बनाने की ठोस समझ प्राप्त करेंगे।

## आप क्या सीखेंगे

- कैसे **databar stacked omnidirectional** जेनरेटर को GTIN‑14 पेलोड के साथ इंस्टैंसिएट करें।  
- स्कैन विश्वसनीयता के लिए **XDimension pixel size** क्यों महत्वपूर्ण है।  
- **DataBar aspect ratio** का पंक्ति की चौड़ाई बनाम ऊँचाई पर प्रभाव।  
- परिणाम को **BarCodeImageFormat PNG** फ़ाइल के रूप में कैसे सहेजें।  
- एक ही जेनरेटर ऑब्जेक्ट को पुनः उपयोग करके अतिरिक्त मेमोरी ओवरहेड के बिना कई वेरिएंट बनाने के टिप्स।

### आवश्यकताएँ

- Python 3.8+ (हमारी लाइब्रेरी शुद्ध‑Python है, कोई कम्पाइल्ड व्हील्स आवश्यक नहीं)।  
- `barcode-generator` पैकेज (इंस्टॉल करने के लिए `pip install barcode-generator`)।  
- एक फ़ोल्डर जहाँ आप लिख सकते हैं – स्क्रिप्ट दो PNG इमेजेज़ वहाँ डंप करेगी।

यदि आप बेसिक Python इम्पोर्ट्स और ऑब्जेक्ट‑ओरिएंटेड कोड से परिचित हैं, तो आप शुरू करने के लिए तैयार हैं।

## Databar Stacked Omnidirectional बारकोड बनाना – चरण सारांश

नीचे हम वर्कफ़्लो को छह छोटे‑छोटे चरणों में विभाजित करते हैं। प्रत्येक चरण एक स्वतंत्र कोड ब्लॉक है जिसे आप REPL या स्क्रिप्ट फ़ाइल में कॉपी‑पेस्ट कर सकते हैं। प्रयोग करने में संकोच न करें—aspect ratio या XDimension बदलने से तुरंत एक अलग विज़ुअल स्टाइल मिलेगा।

---

## चरण 1: Databar Stacked Omnidirectional जेनरेटर बनाएं

पहला काम हम **databar stacked omnidirectional** जेनरेटर इंस्टेंस बनाते हैं, जिसमें उपयुक्त `EncodeTypes` एन्नुम और डेटा स्ट्रिंग पास करते हैं।

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **यह क्यों महत्वपूर्ण है:** `EncodeTypes.DatabarStackedOmniDirectional` फ़्लैग लाइब्रेरी को बताता है कि वह एक stacked omnirectional सिम्बॉल उत्पन्न करे, जो कि एकमात्र DataBar वैरिएंट है जो 14 अंकों तक एन्कोड कर सकता है और फिर भी किसी भी कोण से पढ़ा जा सकता है।

---

## XDimension पिक्सेल आकार कॉन्फ़िगर करें

**XDimension पिक्सेल आकार** सबसे छोटे मॉड्यूल (सबसे पतली काली बार) को नियंत्रित करता है। `2` पिक्सेल का मान अधिकांश स्क्रीन‑डिस्प्ले परियों के लिए उपयुक्त है।

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **प्रो टिप:** यदि आप बारकोड को हाई DPI पर प्रिंट करने की योजना बना रहे हैं, तो धुंधले किनारों से बचने के लिए इस मान को 3 या 4 तक बढ़ा दें।

---

## DataBar Aspect Ratio (15) समायोजित करें

**DataBar aspect ratio** निर्धारित करता है कि प्रत्येक पंक्ति की चौड़ाई उसकी ऊँचाई की तुलना में कितनी है। `15` का aspect ratio अधिक चौड़ी पंक्तियों को देता है, जिसे कई स्कैनर तेज़ मोशन कैप्चर के लिए पसंद करते हैं।

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **क्यों 15?** आधिकारिक GS1 स्पेसिफिकेशन stacked omnidirectional सिम्बॉल के लिए 10 से 20 के बीच का अनुपात सुझाता है। हमने संतुलित डिफ़ॉल्ट के रूप में `15` चुना है।

---

## BarCodeImageFormat का उपयोग करके बारकोड को PNG के रूप में एक्सपोर्ट करें

अब जब जेनरेटर कॉन्फ़िगर हो गया है, हम इमेज को सहेजते हैं। `BarCodeImageFormat.Png` एन्नुम लॉसलेस आउटपुट सुनिश्चित करता है, जो डाउनस्ट्रीम प्रोसेसिंग के लिए परफेक्ट है।

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **आप क्या देखेंगे:** उत्पन्न PNG खोलें; आपको एक साफ़, हाई‑कॉन्ट्रास्ट बारकोड दिखेगा जिसमें अपेक्षाकृत चौड़ी पंक्तियाँ होंगी।

---

## DataBar Aspect Ratio को 30 में बदलें

कभी‑कभी आपको चौड़ी पंक्तियों के बजाय ऊँची पंक्तियों की जरूरत होती है—शायद एक संकरी लेबल में फिट करने के लिए। **DataBar aspect ratio** को `30` करने से प्रत्येक पंक्ति ऊँची हो जाती है।

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **एज केस:** बहुत उच्च अनुपात (जैसे >40) बारकोड को सामान्य लेबल ऊँचाई से अधिक बना सकते हैं, इसलिए लागू करने से पहले वास्तविक प्रिंटर पर परीक्षण करें।

---

## नई Aspect Ratio के साथ बारकोड को फिर से एक्सपोर्ट करें

अंत में, हम वही `barcode_generator` ऑब्जेक्ट पुनः उपयोग करके दूसरा PNG लिखते हैं। जेनरेटर को फिर से बनाने की जरूरत नहीं—सिर्फ प्रॉपर्टी बदलें और फिर से `Save` कॉल करें।

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **परिणाम:** अब आपके पास दो PNG फ़ाइलें हैं—एक चौड़ी पंक्तियों (`AR15`) के साथ और दूसरी ऊँची पंक्तियों (`AR30`) के साथ। उन्हें साइड‑बाय‑साइड तुलना करें ताकि तय कर सकें कि आपके स्कैनर सेटअप के लिए कौन बेहतर है।

---

## पूर्ण कार्यशील उदाहरण

सब कुछ मिलाकर, यहाँ पूर्ण स्क्रिप्ट है जिसे आप तुरंत चला सकते हैं। `YOUR_DIRECTORY` को अपने मशीन पर एक पूर्ण पाथ से बदलें।

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**अपेक्षित आउटपुट** (आपके कंसोल में):

```
✅ Two PNG files created – AR15 and AR30
```

और दो इमेज फ़ाइलें लक्ष्य फ़ोल्डर में दिखाई देंगी, स्कैनिंग टेस्ट के लिए तैयार।

---

## निष्कर्ष

हमने अभी **databar stacked omnidirectional** बारकोड Python में बनाए, **XDimension पिक्सेल आकार** को समायोजित किया, दो अलग‑अलग **DataBar aspect ratio** सेटिंग्स के साथ प्रयोग किया, और परिणामों को **BarCodeImageFormat PNG** फ़ाइलों के रूप में एक्सपोर्ट किया। पूरी वर्कफ़्लो कुछ ही लाइनों में समा जाता है, फिर भी स्कैनरों के लिए सबसे महत्वपूर्ण विज़ुअल विशेषताओं पर पूर्ण नियंत्रण देता है।

अगला क्या? पेलोड को किसी अन्य GTIN से बदलें, PNG को पैलेट‑आधारित इमेज में बदलकर रंगों के साथ खेलें, या एक PDF रिपोर्ट बनाएं जिसमें दोनों PNG साइड‑बाय‑साइड एम्बेड हों। `BarcodeGenerator` क्लास इन सभी परिदृश्यों को संभालने के लिए पर्याप्त लचीली है, इसलिए प्रयोग करने में संकोच न करें।

क्या आपके पास किसी विशेष उपयोग‑केस के बारे में प्रश्न हैं या कोई त्रुटि आ रही है? नीचे टिप्पणी छोड़ें, मैं मदद करने में खुशी महसूस करूंगा। कोडिंग का आनंद लें!

## अब आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं ताकि आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ का अन्वेषण कर सकें।

- [बारकोड इमेज जेनरेट करें – GS1 कूपन UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}