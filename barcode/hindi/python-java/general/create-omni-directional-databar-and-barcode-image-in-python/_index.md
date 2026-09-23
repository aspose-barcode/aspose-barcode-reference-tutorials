---
category: general
date: 2026-08-12
description: Python के साथ ओम्नि‑डायरेक्शनल डेटाबार बनाएं और Aspose.BarCode का उपयोग
  करके Python में बारकोड इमेज बनाना सीखें। पूर्ण समाधान के लिए चरण‑दर‑चरण गाइड का
  पालन करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: hi
lastmod: 2026-08-12
og_description: Python के साथ ओम्नी‑डायरेक्शनल डेटाबार बनाएं और मिनटों में एक बारकोड
  इमेज जनरेट करें। यह ट्यूटोरियल एक पूर्ण, चलाने योग्य उदाहरण दिखाता है।
og_image_alt: example of create omni directional databar barcode image in Python
og_title: ओम्नि-डायरेक्शनल डेटाबार बनाएं – पूर्ण पायथन गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Python में सर्वदिशात्मक डेटाबार और बारकोड छवि बनाएं
url: /hi/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python में Omni Directional DataBar और बारकोड इमेज बनाएं

यदि आपको **create omni directional databar** Python प्रोजेक्ट में बनाना है, तो यह गाइड आपको यह करने का तरीका दिखाएगा और साथ ही Aspose.BarCode लाइब्रेरी का उपयोग करके **create barcode image python** बनाने का तरीका भी बताएगा। आपको एक तैयार‑से‑चलाने योग्य स्क्रिप्ट मिलेगी जो विभिन्न aspect ratios के साथ दो PNG फ़ाइलें उत्पन्न करती है।

Omni‑directional स्पेसिफिकेशन का पालन करने वाला DataBar उत्पन्न करना रिटेल और लॉजिस्टिक्स एप्लिकेशन्स के लिए एक सामान्य आवश्यकता है। यह ट्यूटोरियल इंस्टॉलेशन, X‑dimension की कॉन्फ़िगरेशन, aspect ratio के समायोजन, और अंतिम इमेज को सेव करने को कवर करता है। कोई बाहरी सेवाएँ आवश्यक नहीं हैं; सब कुछ स्थानीय रूप से चलता है।

## आपको क्या चाहिए

* आपके मशीन पर स्थापित Python 3.8 या उससे नया संस्करण।
* टर्मिनल या कमांड प्रॉम्प्ट तक पहुंच।
* उस फ़ोल्डर में लिखने की अनुमति जहाँ बारकोड इमेज सेव की जाएँगी।

एकमात्र थर्ड‑पार्टी डिपेंडेंसी **Aspose.BarCode for Python via .NET** है, जो बॉक्स से ही Omni‑directional DataBar प्रकार का समर्थन करती है।

## चरण 1: Aspose.BarCode for Python स्थापित करें

Aspose.BarCode उदाहरण कोड में उपयोग की गई `BarcodeGenerator` क्लास प्रदान करता है। पैकेज को `pip` के साथ स्थापित करें:

```bash
pip install aspose-barcode
```

पैकेज में आवश्यक .NET रनटाइम बाइंडिंग्स शामिल हैं, इसलिए आपको अलग से .NET SDK स्थापित करने की जरूरत नहीं है।

## चरण 2: लाइब्रेरी इम्पोर्ट करें और जनरेटर बनाएं

स्क्रिप्ट की पहली पंक्ति एक stacked Omni‑directional DataBar के लिए जनरेटर बनाती है। GTIN‑14 मान `(01)12345678901231` को नमूना डेटा के रूप में उपयोग किया गया है।

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*इस चरण का महत्व*: `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` कॉन्स्टेंट लाइब्रेरी को बताता है कि मान को Omni‑directional DataBar के रूप में एन्कोड किया जाए, जो कई point‑of‑sale स्कैनरों के लिए आवश्यक फॉर्मेट है।

## चरण 3: X‑dimension सेट करें (मॉड्यूल चौड़ाई)

X‑dimension सबसे छोटे बार मॉड्यूल की चौड़ाई निर्धारित करता है। `2` पिक्सेल का मान स्पष्ट, पठनीय बारकोड बनाता है बिना अत्यधिक फ़ाइल आकार के।

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*इस चरण का महत्व*: X‑dimension को समायोजित करने से आप पठनीयता और इमेज आकार के बीच संतुलन बना सकते हैं। बहुत छोटा X‑dimension कम‑रिज़ॉल्यूशन प्रिंटरों पर खराब रेंडर हो सकता है।

## चरण 4: aspect ratio कॉन्फ़िगर करें और पहली इमेज सेव करें

aspect ratio DataBar की कुल ऊँचाई को उसकी चौड़ाई के सापेक्ष प्रभावित करता है। `15` का aspect ratio एक कॉम्पैक्ट विज़ुअल स्टाइल बनाता है।

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tip**: आउटपुट पाथ बनाने के लिए `pathlib.Path` का उपयोग करें, जो स्वचालित रूप से गायब डायरेक्टरीज़ बना देता है।

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## चरण 5: दूसरे विज़ुअल स्टाइल के लिए aspect ratio बदलें और एक और इमेज सेव करें

aspect ratio को `30` करने से एक ऊँचा बारकोड बनता है जो कुछ विशेष स्कैनर हार्डवेयर द्वारा आवश्यक हो सकता है।

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*इस चरण का महत्व*: विभिन्न रिटेलर्स और स्कैनिंग डिवाइसों की आकार संबंधी अलग-अलग सीमाएँ होती हैं। एक ही स्क्रिप्ट में दोनों aspect ratios प्रदान करने से आप बिना कोड दोहराए आवश्यक स्टाइल जनरेट कर सकते हैं।

## पूर्ण स्क्रिप्ट – create omni directional databar और barcode image python

नीचे पूरा, चलाने योग्य उदाहरण है जो सभी पिछले चरणों को सम्मिलित करता है। इसे `generate_databar.py` के रूप में सेव करें और `python generate_databar.py` के साथ चलाएँ।

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### अपेक्षित आउटपुट

स्क्रिप्ट चलाने से निम्नलिखित फ़ाइलें बनती हैं:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

दोनों इमेज एक वैध Omni‑directional DataBar दिखाती हैं जिसे मानक रिटेल उपकरण द्वारा स्कैन किया जा सकता है।

![Python में create omni directional databar barcode image का उदाहरण](example_databar.png "Python में create omni directional databar barcode image")

*ऊपर की इमेज एक प्लेसहोल्डर है जो दो सेव की गई PNG फ़ाइलों को दर्शाती है।*

## सामान्य समस्याओं का समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode स्थापित नहीं है या अलग पर्यावरण में स्थापित है। | सही वर्चुअल एनवायरनमेंट सक्रिय करें और `pip install aspose-barcode` चलाएँ। |
| `PermissionError` when saving | स्क्रिप्ट के पास लक्ष्य फ़ोल्डर के लिए लिखने की अनुमति नहीं है। | ऐसा डायरेक्टरी चुनें जिसका आप मालिक हों या स्क्रिप्ट को उपयुक्त विशेषाधिकारों के साथ चलाएँ। |
| बारकोड स्कैन नहीं हो रहा है | X‑dimension बहुत कम है या aspect ratio स्कैनर के साथ असंगत है। | `x_dimension.pixels` को 3 या 4 तक बढ़ाएँ, और विभिन्न `aspect_ratio` मानों (जैसे 20, 25) का परीक्षण करें। |
| .NET रनटाइम अनुपलब्ध | Aspose.BarCode को Windows/Linux पर .NET रनटाइम की आवश्यकता होती है। | Microsoft की साइट से नवीनतम .NET रनटाइम स्थापित करें; पैकेज दस्तावेज़ प्लेटफ़ॉर्म‑विशिष्ट मार्गदर्शन प्रदान करता है। |

## उदाहरण का विस्तार

आप स्क्रिप्ट को अन्य DataBar वैरिएंट्स (जैसे `DATABAR_STACKED`, `DATABAR_EXPANDED`) उत्पन्न करने के लिए अनुकूलित कर सकते हैं। `EncodeTypes` कॉन्स्टेंट को उसी अनुसार बदलें:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

यदि आपको बारकोड को PDF में एम्बेड करना है, तो Aspose.PDF for Python PNG फ़ाइल को सीधे इम्पोर्ट कर सकता है या आप `save` मेथड को `BarCodeImageFormat.Pdf` के साथ उपयोग कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल ने Aspose.BarCode का उपयोग करके **create omni directional databar** और **create barcode image python** कैसे बनाएं, दिखाया। अब आपके पास एक पूर्ण, पुनरुत्पादनीय स्क्रिप्ट है जो विभिन्न aspect ratios के साथ दो PNG फ़ाइलें उत्पन्न करती है, सामान्य समस्याओं को संभालती है, और अन्य बारकोड फ़ॉर्मेट्स के लिए विस्तारित की जा सकती है।

अब, QR कोड जनरेट करना, बारकोड को PDF इनवॉइस में जोड़ना, या बड़े प्रोडक्ट कैटलॉग के लिए बैच प्रोसेसिंग को ऑटोमेट करना एक्सप्लोर करें। इन सभी विषयों का आधार यहाँ प्रदर्शित `BarcodeGenerator` पैटर्न है। कोडिंग का आनंद लें!

## अगला आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स इस गाइड में दिखाए गए तकनीकों पर आधारित निकट-संबंधित विषयों को कवर करते हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में निपुण बनने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करती हैं।

- [बारकोड इमेज जनरेट करें – GS1 कूपन UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode बारकोड इमेज बनाएं – पंक्तियाँ और कॉलम (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [बारकोड इमेज कैसे बनाएं और Java में रेंडर करें](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}