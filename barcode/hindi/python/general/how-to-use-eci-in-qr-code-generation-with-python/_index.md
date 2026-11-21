---
category: general
date: 2026-11-20
description: ECI का उपयोग कैसे करें, टेक्स्ट से QR बनाएं, बिल्डर को साफ़ करें, और
  Python बारकोड लाइब्रेरी का उपयोग करके QR इमेज सहेजना सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: hi
lastmod: 2026-11-20
og_description: ECI का उपयोग करके टेक्स्ट से QR कैसे बनाएं, QR बिल्डर को साफ़ करें,
  और QR इमेज सहेजें – एक पूर्ण चरण‑दर‑चरण गाइड।
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Python के साथ QR कोड जनरेशन में ECI का उपयोग कैसे करें
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Python के साथ QR कोड जनरेशन में ECI का उपयोग कैसे करें
url: /hi/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python के साथ QR कोड जनरेशन में ECI का उपयोग कैसे करें

यदि आपको QR कोड बनाते समय **how to use eci** की आवश्यकता है, तो यह गाइड सटीक चरण दिखाता है। आप देखेंगे कि टेक्स्ट से QR कैसे जनरेट करें, बिल्डर को कैसे साफ़ करें, और अंत में QR इमेज कैसे सेव करें—सिर्फ कुछ पंक्तियों के Python कोड से।

बहु-भाषी डेटा वाले QR कोड अक्सर एक Extended Channel Interpretation (ECI) सेगमेंट की आवश्यकता रखते हैं ताकि स्कैनर को पता चल सके कि कौन सा कैरेक्टर सेट लागू करना है। यह ट्यूटोरियल आपको विस्तारित कोडटेक्स्ट बनाने, पुनः उपयोग करते समय बिल्डर को साफ़ करने, और परिणाम को PNG फ़ाइल के रूप में सहेजने की प्रक्रिया दिखाता है।

## पूर्वापेक्षाएँ

- Python 3.8+ स्थापित हो।
- Aspose.BarCode for Python via .NET पैकेज (या कोई भी संगत `barcode` लाइब्रेरी जो `ExtCodetextBuilder` और `BarcodeGenerator` प्रदान करती हो)।
- QR कोड अवधारणाओं की बुनियादी समझ।

Install the library with pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** संस्करण संघर्षों से बचने के लिए एक वर्चुअल एनवायरनमेंट का उपयोग करें।

## चरण 1: आवश्यक क्लासेस इम्पोर्ट करें

मुख्य क्लासेस जिनके साथ आप काम करेंगे, वे हैं `ExtCodetextBuilder` विस्तारित कोडटेक्स्ट बनाने के लिए और `BarcodeGenerator` QR कोड रेंडर करने के लिए।

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

ये इम्पोर्ट्स आपको बिल्डर मेथड्स (`add_plain_codetext`, `add_eci_codetext`, आदि) और जेनरेटर के `set_code_text`, `set_symbology`, और `save` फ़ंक्शन्स तक पहुँच प्रदान करते हैं।

## चरण 2: ExtCodetextBuilder बनाएं और कॉन्फ़िगर करें

एक नया बिल्डर इंस्टेंस बनाना **how to use eci** का पहला ठोस उदाहरण है। आप बाद में बिल्डर को साफ़ भी कर सकते हैं यदि आपको इसे पुनः उपयोग करने की आवश्यकता हो।

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

`clear()` को कॉल करने से बिल्डर साफ़ स्थिति से शुरू होता है, जो लूप में कई QR कोड जनरेट करते समय आवश्यक है।

## चरण 3: साधारण (non‑ECI) कोडटेक्स्ट जोड़ें

साधारण टेक्स्ट को ECI सेगमेंट की आवश्यकता नहीं होती। ASCII‑संगत स्ट्रिंग्स के लिए `add_plain_codetext` का उपयोग करें।

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

अब बिल्डर में साधारण सेगमेंट `"HelloWorld"` मौजूद है।

## चरण 4: एक ECI‑एन्कोडेड सेगमेंट जोड़ें

यह **how to use eci** का मुख्य भाग है: आप ECI वैल्यू (UTF‑8 के लिए 26) निर्दिष्ट करते हैं और वह यूनिकोड स्ट्रिंग प्रदान करते हैं जिसे आप एन्कोड करना चाहते हैं। इससे QR कोड रूसी, चीनी, या किसी भी अन्य भाषा को ले जा सकता है जो डिफ़ॉल्ट ISO‑8859‑1 सेट में नहीं है।

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **यह क्यों महत्वपूर्ण है:** ECI संकेतक के बिना, स्कैनर बाइट्स को डिफ़ॉल्ट कैरेक्टर सेट से व्याख्या करेगा और non‑ASCII टेक्स्ट के लिए गड़बड़ अक्षर दिखाएगा।

## चरण 5: संयुक्त विस्तारित कोडटेक्स्ट स्ट्रिंग प्राप्त करें

सभी आवश्यक सेगमेंट जोड़ने के बाद, अंतिम स्ट्रिंग प्राप्त करें जिसे QR जेनरेटर को दिया जाएगा।

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

प्रिंट किया गया मान कुछ इस प्रकार दिखेगा:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

सटीक फ़ॉर्मेट लाइब्रेरी पर निर्भर करता है, लेकिन महत्वपूर्ण बात यह है कि ECI मार्कर (`[ECI26]`) UTF‑8 पेलोड से पहले आता है।

## चरण 6: संयुक्त टेक्स्ट का उपयोग करके QR कोड जनरेट करें

अब आप `BarcodeGenerator` को विस्तारित कोडटेक्स्ट पास करके **generate QR from text** कर सकते हैं।

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

जब आप `qr_extended.png` खोलते हैं, तो एक QR कोड दिखाई देता है जो साधारण अंग्रेज़ी स्ट्रिंग और रूसी अभिवादन दोनों को एन्कोड करता है। इसे आधुनिक QR स्कैनर से स्कैन करने पर “HelloWorld” और “Привет” सही ढंग से दिखेंगे।

### बिल्डर को पुनः उपयोग करने से पहले `clear()` क्यों कॉल करें

यदि आप लूप में कई QR कोड जनरेट करते हैं, तो बिल्डर को साफ़ करना भूलने से पुराने सेगमेंट नए के साथ जुड़ जाएंगे, जिससे एक अमान्य कोड बन जाएगा। यहाँ एक त्वरित पैटर्न है:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

यह स्निपेट **how to clear builder** और **how to generate QR from text** को बार‑बार करने का उदाहरण देता है।

## किनारे के मामलों और सामान्य जाल

| स्थिति | ध्यान देने योग्य बात | कैसे संभालें |
|-----------|-------------------|---------------|
| **असमर्थित ECI मान** | लाइब्रेरी `InvalidArgumentException` थ्रो करती है। | स्पेसिफिकेशन में सूचीबद्ध केवल ECI मानों का उपयोग करें (जैसे, UTF‑8 के लिए 26, Shift‑JIS के लिए 20)। |
| **बहुत लंबा संयुक्त टेक्स्ट** | QR संस्करण अधिकतम क्षमता से अधिक हो सकता है। | QR संस्करण को स्वचालित रूप से बढ़ाएँ (`qr_generator.set_qr_version(QRVersion.AUTO)`) या डेटा को कई QR कोड में विभाजित करें। |
| **फ़ाइल‑सिस्टम अनुमति त्रुटियाँ** | `save` `IOError` के साथ फेल हो जाता है। | सुनिश्चित करें कि लक्ष्य डायरेक्टरी मौजूद है और प्रक्रिया के पास लिखने की अनुमति है। |
| **गलत कैरेक्टरसेट डिस्प्ले** | स्कैनर गड़बड़ अक्षर दिखाता है। | सही ECI मान की जाँच करें कि वह स्ट्रिंग की वास्तविक एन्कोडिंग से मेल खाता है। |

## पूर्ण चलाने योग्य उदाहरण

नीचे एक स्व-निहित स्क्रिप्ट है जिसे आप कॉपी, पेस्ट और चलाकर उपयोग कर सकते हैं। इसमें सभी इम्पोर्ट्स, एरर हैंडलिंग, और स्पष्टता के लिए टिप्पणियाँ शामिल हैं।

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

इस स्क्रिप्ट को चलाने से `output/qr_extended.png` बनता है, एक QR कोड जो सही ढंग से अंग्रेज़ी और रूसी दोनों टेक्स्ट को एन्कोड करता है।

## निष्कर्ष

अब आप QR कोड बनाते समय **how to use eci**, पुनः उपयोग से पहले **clear the QR builder**, **generate QR from text**, और Python के साथ **save QR image** करने के सटीक चरण जानते हैं। ऊपर दिखाए गए पैटर्न का पालन करके, आप किसी भी यूनिकोड स्ट्रिंग को QR कोड में एम्बेड कर सकते हैं जबकि बिल्डर की स्थिति पूर्वानुमेय रहती है।

### आगे क्या?

- Chinese (ECI 20) या ISO‑8859‑5 जैसी भाषाओं के लिए अन्य ECI मानों का अन्वेषण करें।
- स्कैन विश्वसनीयता बढ़ाने के लिए एरर‑करेक्शन लेवल (`qr_generator.set_error_correction_level`) को समायोजित करें।
- मिश्रित‑भाषा संदेशों के लिए एक ही QR में कई ECI सेगमेंट को संयोजित करें।

कोडिंग का आनंद लें, और बहुभाषी QR कोड बनाने का मज़ा उठाएँ!

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में निपुण बनने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ का अन्वेषण करने में मदद करती हैं।

- [Aspose.Barcode Python का उपयोग करके ECI के साथ बारकोड कैसे जनरेट करें](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Aspose.Barcode के साथ Python में QR कोड इमेज कैसे जनरेट करें – पूर्ण गाइड](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Python में बारकोड कैसे जनरेट करें – पूर्ण चरण‑दर‑चरण गाइड](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}