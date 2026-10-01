---
category: general
date: 2026-08-09
description: Aspose.BarCode का उपयोग करके Python में QR बारकोड बनाएं। विस्तारित कोडटेक्स्ट
  कैसे बनाएं, दिखावट को कैसे समायोजित करें, और छवि को कैसे सहेजें—सब कुछ एक ही ट्यूटोरियल
  में सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: hi
lastmod: 2026-08-09
og_description: Aspose.BarCode के साथ Python में QR बारकोड बनाएं। यह गाइड दिखाता है
  कि विस्तारित कोडटेक्स्ट कैसे बनाएं, दृश्य पैरामीटर सेट करें, और छवि निर्यात करें।
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Python में Aspose.BarCode के साथ QR बारकोड बनाएं – पूर्ण कोड उदाहरण
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python में Aspose.BarCode के साथ QR बारकोड बनाएं – चरण‑दर‑चरण मार्गदर्शिका
url: /hi/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Python में Aspose.BarCode के साथ QR बारकोड बनाएं – चरण‑दर‑चरण गाइड

यदि आपको Python में **QR बारकोड बनाना** है, तो यह ट्यूटोरियल Aspose.BarCode लाइब्रेरी का उपयोग करके पूरी प्रक्रिया को समझाता है। चाहे आप प्रोडक्ट आईडी, बहुभाषी टेक्स्ट, या कस्टम डेटा एन्कोड कर रहे हों, आप देखेंगे कि कैसे विस्तारित कोडटेक्स्ट बनाएं, विज़ुअल सेटिंग्स को समायोजित करें, और अंतिम इमेज को एक ही चलाने योग्य स्क्रिप्ट में सहेजें।

उदाहरण यह भी दर्शाता है कि लाइब्रेरी संस्करण कैसे प्रदर्शित करें, जिससे आप यह सत्यापित कर सकें कि आप संगत रिलीज़ चला रहे हैं। इस गाइड के अंत तक आपके पास उपयोग के लिए तैयार QR बारकोड इमेज और प्रत्येक कॉन्फ़िगरेशन विकल्प की स्पष्ट समझ होगी।

## पूर्वापेक्षाएँ

- Python 3.8+ स्थापित हो।
- `aspose-barcode` पैकेज (इंस्टॉल करने के लिए `pip install aspose-barcode`)।
- Python सिंटैक्स की मूल समझ।
- PNG फ़ाइल को सहेजने वाले आउटपुट डायरेक्टरी में लिखने की अनुमति।

> **Pro tip:** अन्य प्रोजेक्ट्स के साथ संस्करण टकराव से बचने के लिए वर्चुअल एनवायरनमेंट का उपयोग करें।

## चरण 1: Aspose.BarCode लाइब्रेरी संस्करण सत्यापित करें

लाइब्रेरी संस्करण प्रदर्शित करने से यह सुनिश्चित होता है कि आप वह रिलीज़ उपयोग कर रहे हैं जो विस्तारित कोडटेक्स्ट और QR एन्कोडिंग का समर्थन करता है।

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Why this matters:**  
पुराने रिलीज़ में `ExtCodetextBuilder` क्लास नहीं हो सकता है, जो मिश्रित प्लेन और ECI सेगमेंट्स के लिए आवश्यक है। संस्करण की पुष्टि करने से बाद में वर्कफ़्लो में रनटाइम त्रुटियों से बचा जा सकता है।

## चरण 2: विस्तारित कोडटेक्स्ट स्ट्रिंग बनाएं

एक विस्तारित कोडटेक्स्ट आपको प्लेन ASCII डेटा को Unicode (ECI) सेगमेंट्स के साथ मिलाने की अनुमति देता है, जो बहुभाषी QR कोड्स के लिए आवश्यक है।

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Why this matters:**  
`add_plain_codetext` मेथड डेटा को मानक ASCII के रूप में संग्रहीत करता है, जबकि `add_eci_codetext` उपयुक्त ECI डिज़ाइनटर के साथ Unicode ब्लॉक को प्रीफ़िक्स करता है। यह दृष्टिकोण सुनिश्चित करता है कि QR स्कैनर जापानी टेक्स्ट को सही ढंग से व्याख्या करे, जिससे गड़बड़ अक्षर नहीं आएँगे।

### सामान्य विविधताएँ

- **एकाधिक ECI खंड:** कई भाषाओं को मिलाने के लिए `add_eci_codetext` को कई बार कॉल करें।
- **विभिन्न ECI पहचानकर्ता:** अपने लक्ष्य एन्कोडिंग के अनुसार `27` को ISO‑8859‑1, `28` को ISO‑8859‑2 आदि के लिए उपयोग करें।

## चरण 3: विस्तारित कोडटेक्स्ट का उपयोग करके QR बारकोड जनरेट करें

अब हमारे पास सही फ़ॉर्मेटेड स्ट्रिंग है, हम QR कोड बना सकते हैं।

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Why this matters:**  
`EncodeTypes.QR` Aspose.BarCode को QR सिम्बोलॉजी उपयोग करने के लिए बताता है। `extended_codetext` को सीधे पास करने से मिश्रित डेटा QR मैट्रिक्स से जुड़ता है, जिससे प्लेन और Unicode दोनों भाग संरक्षित रहते हैं।

## चरण 4: दृश्य रूप को समायोजित करें (वैकल्पिक लेकिन अनुशंसित)

बारकोड के विज़ुअल पैरामीटर को फाइन‑ट्यून करने से स्कैन विश्वसनीयता में सुधार होता है और ब्रांडिंग गाइडलाइन्स के साथ मेल खाता है।

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Why this matters:**  
- **`x_dimension`** प्रत्येक QR मॉड्यूल का आकार नियंत्रित करता है; बहुत छोटा होने पर कम‑रिज़ॉल्यूशन डिवाइस पर पढ़ने में त्रुटियां हो सकती हैं।  
- **`border_width`** एक क्वाइट ज़ोन जोड़ता है। कुछ स्कैनर कम से कम 4‑मॉड्यूल क्वाइट ज़ोन की आवश्यकता रखते हैं; लाइब्रेरी इसे स्वचालित रूप से जोड़ती है, लेकिन आप अतिरिक्त सुरक्षा के लिए इसे बढ़ा सकते हैं।

### किनारे के मामलों का प्रबंधन

- **उच्च‑घनत्व डेटा:** यदि एन्कोडेड डेटा बड़ा है, तो आपको `x_dimension` बढ़ाने या उच्च त्रुटि‑सुधार स्तर चुनने की आवश्यकता हो सकती है (`qr_generator.parameters.qr.error_correction_level` के माध्यम से)।  
- **पारदर्शी पृष्ठभूमि:** PNG में अल्फा चैनल के लिए `qr_generator.parameters.barcode.bg_color = Color.Transparent` सेट करें।

## चरण 5: QR बारकोड इमेज सहेजें

अंत में, इमेज को अपनी पसंदीदा फ़ॉर्मेट में डिस्क पर लिखें।

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Why this matters:**  
PNG के रूप में सहेजने से लॉसलेस क्वालिटी बनी रहती है, जो तेज़ किनारों वाले QR कोड्स के लिए आदर्श है। यदि आपको वेब एप्लिकेशन के लिए अलग फ़ॉर्मेट चाहिए, तो बस `BarCodeImageFormat` एनेमरेशन बदल दें।

### परिणाम की पुष्टि

किसी भी इमेज व्यूअर में सहेजी गई फ़ाइल खोलें। आपको एक QR कोड दिखना चाहिए जो स्कैन करने पर संयुक्त स्ट्रिंग लौटाता है:

```
ABC12345
こんにちは
```

अधिकांश आधुनिक QR स्कैनर ऐप्स पहले प्लेन सेगमेंट दिखाते हैं और फिर जापानी अभिवादन को सही ढंग से रेंडर करते हैं।

---

## पूर्ण चलाने योग्य स्क्रिप्ट

नीचे दिया गया पूरा ब्लॉक `create_qr_barcode.py` नाम की फ़ाइल में कॉपी करें और `python create_qr_barcode.py` के साथ चलाएँ। `YOUR_DIRECTORY` को अपने मशीन पर लिखने योग्य फ़ोल्डर में बदलें।

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

इस स्क्रिप्ट को चलाने से संस्करण, विस्तारित कोडटेक्स्ट, और यह पुष्टि प्रिंट होगी कि PNG फ़ाइल बनाई गई है।

---

## निष्कर्ष

आप अब जानते हैं कि Python में Aspose.BarCode का उपयोग करके **QR बारकोड** इमेज कैसे बनाते हैं। ट्यूटोरियल ने निम्नलिखित विषयों को कवर किया:

1. लाइब्रेरी संस्करण की पुष्टि करना।  
2. प्लेन और ECI (Unicode) सेगमेंट्स के साथ विस्तारित कोडटेक्स्ट बनाना।  
3. QR कोड जनरेट करना।  
4. मॉड्यूल आकार और बॉर्डर चौड़ाई जैसे विज़ुअल पैरामीटर को कस्टमाइज़ करना।  
5. अंतिम इमेज को PNG फ़ॉर्मेट में सहेजना।

अब आप आगे खोज सकते हैं:

- त्रुटि‑सुधार स्तर बदलना (`qr_generator.parameters.qr.error_correction_level`)।  
- लोगो या बैकग्राउंड इमेज जोड़ना (`qr_generator.parameters.qr.logo`)।  
- SVG जैसे अन्य फ़ॉर्मैट में एक्सपोर्ट करना, जो स्केलेबल वेब ग्राफ़िक्स के लिए उपयुक्त है।  
- Flask या Django एन्डपॉइंट में जनरेटर को इंटीग्रेट करना ताकि ऑन‑द‑फ्लाई QR निर्माण हो सके।

विभिन्न डेटा पेलोड और विज़ुअल सेटिंग्स के साथ प्रयोग करें ताकि आपके एप्लिकेशन की ब्रांडिंग और स्कैनिंग आवश्यकताओं के अनुरूप हो सके। Happy coding!

## आगे आप क्या सीखें?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन एप्रोच का अन्वेषण कर सकें।

- [Aspose.BarCode के साथ .NET के लिए डॉटकोड विस्तारित कोडटेक्स्ट कैसे बनाएं](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose .NET में बारकोड बनाएं - DataMatrix कोड टेक्स्ट कॉन्फ़िगर करना](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aspose.BarCode for .NET का उपयोग करके ITF-14 के लिए बारकोड क्वाइट ज़ोन कैसे बनाएं](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}