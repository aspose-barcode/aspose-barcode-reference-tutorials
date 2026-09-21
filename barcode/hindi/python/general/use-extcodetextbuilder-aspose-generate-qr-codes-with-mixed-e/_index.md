---
category: general
date: 2026-07-18
description: extcodetextbuilder aspose का उपयोग करके ऐसे QR कोड बनाएं जो साधारण ASCII
  और UTF‑8 रूसी टेक्स्ट को मिलाते हैं। Python में Aspose.Barcode QR कोड जेनरेशन सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: hi
lastmod: 2026-07-18
og_description: extcodetextbuilder aspose का उपयोग करके आप QR कोड में साधारण और UTF‑8
  एन्कोडेड फ्रैगमेंट्स को मिलाकर बना सकते हैं। Python में Aspose.Barcode के लिए इस
  चरण‑दर‑चरण गाइड का पालन करें।
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: extcodetextbuilder aspose का उपयोग करें – मिश्रित ECI टेक्स्ट के साथ QR
  कोड बनाएं
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'extcodetextbuilder aspose का उपयोग करें: मिश्रित ECI टेक्स्ट के साथ QR कोड
  जनरेट करें'
url: /hi/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# extcodetextbuilder aspose का उपयोग – मिश्रित ECI टेक्स्ट के साथ QR कोड बनाएं

क्या आप कभी सोचते थे कि **use extcodetextbuilder aspose** का उपयोग करके साधारण अंग्रेज़ी और सिरिलिक अक्षरों को एक ही QR कोड में कैसे एम्बेड किया जाए? आप अकेले नहीं हैं। कई डेवलपर्स को ASCII और non‑ASCII डेटा को मिलाने में समस्या आती है, विशेषकर जब लक्ष्य स्कैनर उचित ECI (Extended Channel Interpretation) मार्कर की अपेक्षा करता है।  

इस ट्यूटोरियल में हम ठीक‑ठीक चरण‑दर‑चरण दिखाएंगे कि कैसे एक QR कोड बनाया जाए जिसमें “HELLO123” **और** रूसी शब्द “Привет” दोनों हों, वह भी Aspose.Barcode के Python API के साथ। अंत तक आपके पास चलाने योग्य स्क्रिप्ट होगी, आप समझेंगे कि प्रत्येक कॉल क्यों महत्वपूर्ण है, और अन्य भाषाओं या डेटा फ़ॉर्मेट के लिए प्रक्रिया को कैसे अनुकूलित किया जाए।

## आप क्या सीखेंगे

- कैसे **initialize ExtCodetextBuilder** करें और साधारण साथ‑साथ ECI‑encoded भाग जोड़ें।  
- क्यों **ECI encoding** मान `3` UTF‑8 के अनुरूप है और यह स्कैनिंग को कैसे प्रभावित करता है।  
- Aspose.Barcode के साथ **QR Code generator** सेट करने की सटीक क्रमबद्धता।  
- उत्पन्न छवि को कैसे सहेजें और मिश्रित सामग्री को कैसे सत्यापित करें।  

**Prerequisites** – आपको Python 3.8+, `aspose-barcode` पैकेज स्थापित (`pip install aspose-barcode`) होना चाहिए, और एक फ़ोल्डर चाहिए जहाँ आप छवियाँ लिख सकें। और कुछ नहीं।

---

## extcodetextbuilder aspose का उपयोग करके मिश्रित कोडटेक्स्ट बनाएं

सबसे पहले हमें एक `ExtCodetextBuilder` इंस्टेंस चाहिए। इसे एक बिल्डर पैटर्न की तरह सोचें जो विभिन्न टेक्स्ट टुकड़ों को जोड़ता है और पीछे से सही ECI मार्कर स्वचालित रूप से डालता है।

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Why this matters:**  
- `add_plain_codetext` डेटा को जैसा है वैसा रखता है, जो संख्याओं या अंग्रेज़ी अक्षरों के लिए परफ़ेक्ट है।  
- `add_eci_codetext` प्रदान किए गए स्ट्रिंग से पहले एक ECI सेगमेंट (`[ECI:3]`) डालता है, जिससे कोई भी कम्प्लायंट रीडर समझता है कि अगले बाइट्स UTF‑8 हैं। बिना इस के, स्कैनर सिरिलिक बाइट्स को गड़बड़ के रूप में पढ़ेगा।

> **Pro tip:** यदि आपको अलग कैरेक्टर सेट चाहिए, तो ECI तालिका के अनुसार `eci_encoding` मान बदलें (उदाहरण के लिए, ISO‑8859‑1 के लिए `26`)।  

---

## Initialise QR Code generation with Aspose.Barcode

अब जब हमारे पास सही‑फ़ॉर्मेटेड `extended_codetext` है, हम इसे QR कोड जेनरेटर को दे सकते हैं। Aspose.Barcode लो‑लेवल QR मैट्रिक्स निर्माण को एब्स्ट्रैक्ट करता है, जिससे आप डेटा पर ध्यान केंद्रित कर सकते हैं।

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**What’s happening here?**  
- `BarcodeGenerator()` एक नया जेनरेटर ऑब्जेक्ट बनाता है जिसमें डिफ़ॉल्ट सेटिंग्स (आकार, रिज़ॉल्यूशन, आदि) होती हैं।  
- `set_symbology` इंजन को बताता है कि हम QR Code चाहते हैं, न कि Code128।  

यदि आपको उच्च त्रुटि‑सुधार स्तर चाहिए, तो कोडटेक्स्ट असाइन करने से पहले `qr_generator.parameters.barcode.qr_error_level = ...` कॉल कर सकते हैं।

---

## Assign the extended codetext to the QR generator

जेनरेटर तैयार होने पर, अगला कदम बस वह मिश्रित स्ट्रिंग फीड करना है जो हमने पहले बनाई थी।

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Why not use `set_codetext`?**  
`set_codetext` इनपुट को साधारण टेक्स्ट मानता है और किसी भी ECI मार्कर को हटा देता है। `set_extended_codetext` कच्चे बाइट्स को, जिसमें ECI सेगमेंट भी शामिल है, बरकरार रखता है, जिससे स्कैनर सही भाषा स्विच देखता है।

---

## Save the QR Code image and verify the result

अंत में हम QR कोड को डिस्क पर लिखते हैं। Aspose.Barcode PNG, JPEG, BMP आदि को सपोर्ट करता है; PNG एक सुरक्षित डिफ़ॉल्ट है क्योंकि यह लॉसलेस डेटा रखता है।

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

अब आपके पास निर्दिष्ट स्थान पर एक PNG फ़ाइल होगी। इसे किसी भी QR स्कैनर ऐप से खोलें जो ECI सपोर्ट करता हो (ज्यादातर आधुनिक स्मार्टफ़ोन करते हैं)। एक बार स्कैन करें – आपको “HELLO123” दिखेगा। फिर से स्कैन करें (या ऐसा स्कैनर उपयोग करें जो कच्चा डेटा दिखाए) – आपको “Привет” भी मिलेगा। दोनों भाग एक ही पेलोड के रूप में दिखाई देंगे, बिल्कुल उसी तरह जैसा हमने बनाया था।

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: use extcodetextbuilder aspose QR code example showing mixed ECI text* → *छवि वैकल्पिक पाठ: मिश्रित ECI टेक्स्ट दिखाते हुए use extcodetextbuilder aspose QR कोड उदाहरण*

---

## Full, Ready‑to‑Run Script

सब कुछ मिलाकर, यहाँ पूरा प्रोग्राम है जिसे आप `qr_mixed_eci.py` नाम की फ़ाइल में कॉपी‑पेस्ट कर सकते हैं:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

इसे चलाएँ:

```bash
python qr_mixed_eci.py
```

आपको कंसोल में सहेजने की जगह की पुष्टि वाला संदेश दिखेगा, और PNG उसी स्थान पर बन जाएगा जहाँ आपने बताया था।

---

## Common Questions & Edge Cases

### क्या होगा अगर मेरा स्कैनर सिरिलिक भाग को पहचान नहीं पाता?
सुनिश्चित करें कि स्कैनिंग ऐप ECI सपोर्ट का विज्ञापन करता हो। पुराने हार्डवेयर ECI सेगमेंट को अनदेखा कर सकते हैं और बाइट्स को ISO‑8859‑1 मान सकते हैं, जिससे अक्षर गड़बड़ दिखेंगे।

### क्या मैं दो से अधिक फ़्रैगमेंट जोड़ सकता हूँ?
बिल्कुल। जितनी बार जरूरत हो `add_plain_codetext` या `add_eci_codetext` कॉल करें। बिल्डर उन्हें उसी क्रम में जोड़ देगा जैसा आप मेथड्स को कॉल करेंगे।

### QR कोड का आकार या फ़ोरग्राउंड रंग कैसे बदलें?
`qr_generator.parameters` ऑब्जेक्ट का उपयोग करें:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### क्या टेक्स्ट के साथ बाइनरी डेटा (जैसे छोटा फ़ाइल) एम्बेड करने का कोई तरीका है?
हाँ। `add_binary_codetext` को बाइट एरे के साथ उपयोग करें, और यदि बाइनरी किसी विशेष कैरेक्टर सेट का प्रतिनिधित्व करता है तो उपयुक्त ECI जोड़ें। बिल्डर आवश्यक मोड स्विच को संभाल लेगा।

---

## निष्कर्ष

अब आप जानते हैं **how to use extcodetextbuilder aspose** ताकि QR कोड बन सकें जो साधारण ASCII और UTF‑8 एन्कोडेड रूसी टेक्स्ट को सहजता से मिलाए। `ExtCodetextBuilder` का उपयोग करके, सही **ECI encoding** सेट करके, और परिणाम को **Aspose.Barcode QR Code generator** में फीड करके, आप एक मानक‑अनुपालन छवि प्राप्त करते हैं जो आधुनिक स्कैनरों पर काम करती है।  

अब `eci_encoding=3` को अन्य भाषा पहचानकर्ताओं से बदलें, या अतिरिक्त साधारण फ़्रैगमेंट जोड़कर बहुभाषी पेलोड बनाएं। आप `BarCodeImageFormat` विकल्पों को देख सकते हैं ताकि SVG या PDF जैसे वेक्टर ग्राफ़िक्स आउटपुट कर सकें।  

कोडिंग का आनंद लें, और यदि कोई समस्या आती है तो टिप्पणी छोड़ें—आपकी प्रतिक्रिया इन गाइड्स को और बेहतर बनाती है!

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स इस गाइड में दिखाए गए तकनीकों पर आधारित हैं और अतिरिक्त API फीचर्स तथा वैकल्पिक इम्प्लीमेंटेशन तरीकों को समझने में मदद करेंगे।

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}