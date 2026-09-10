---
category: general
date: 2026-09-10
description: एक साधारण Python बिल्डर के साथ QR कोड में गैर‑ASCII अक्षरों को एन्कोड
  करें और QR कोड छवि को सहेजें। ExtCodetextBuilder और BarcodeGenerator का उपयोग करके
  चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: hi
lastmod: 2026-09-10
og_description: Python का उपयोग करके QR कोड में गैर‑ASCII अक्षरों को एन्कोड करें और
  QR कोड छवि को सहेजें। यह ट्यूटोरियल दिखाता है कि विस्तारित कोडटेक्स्ट कैसे बनाएं,
  QR कोड जेनरेट करें, और छवि को स्टोर करें।
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: QR कोड में गैर‑ASCII अक्षरों को एन्कोड करें और QR कोड छवि सहेजें – चरण‑दर‑चरण
  Python गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: QR कोड में गैर‑ASCII अक्षरों को एन्कोड करें और QR कोड छवि सहेजें
url: /hi/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR कोड में गैर-ASCII अक्षरों को एन्कोड करें और QR कोड छवि सहेजें

यदि आपको QR कोड में **गैर-ASCII अक्षरों को एन्कोड** करने की आवश्यकता है, तो यह गाइड आपको ठीक-ठीक बताता है कि इसे कैसे करें और फिर **QR कोड छवि सहेजें** डिस्क पर। चाहे आप रूसी, चीनी, या इमोजी डेटा को संभाल रहे हों, ExtCodetextBuilder आपको प्लेन टेक्स्ट और ECI‑एन्कोडेड सेगमेंट को मैन्युअल बाइट हेरफेर के बिना मिलाने देता है।

आप सीखेंगे कि विस्तारित कोडटेक्स्ट स्ट्रिंग कैसे बनाएं, उस स्ट्रिंग को समझने वाला QR कोड कैसे जनरेट करें, और अंत में बारकोड छवि को फ़ाइल में लिखें। ट्यूटोरियल मानता है कि आपके पास बुनियादी Python ज्ञान है और `barcode` SDK स्थापित है।

## आवश्यकताएँ

* Python 3.8+ स्थापित हो।
* `barcode` Python पैकेज (या उपयुक्त SDK) जो `ExtCodetextBuilder`, `CodetextEncodingType`, और `BarcodeGenerator` प्रदान करता है।
* उस डायरेक्टरी में लिखने की अनुमति जहाँ आप **QR कोड छवि सहेजना** चाहते हैं।

आप pip के साथ SDK स्थापित कर सकते हैं (`barcode-sdk` को वास्तविक पैकेज नाम से बदलें):

```bash
pip install barcode-sdk
```

## चरण 1: एक विस्तारित कोडटेक्स्ट बिल्डर बनाएं

पहला कदम `ExtCodetextBuilder` का इंस्टैंस बनाना है। यह ऑब्जेक्ट कई टेक्स्ट सेगमेंट एकत्र करता है और एक सिंगल स्ट्रिंग उत्पन्न करता है जिसे QR कोड सिम्बोलॉजी समझ सकती है।

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*क्यों यह महत्वपूर्ण है*: QR कोड **विस्तारित कोडटेक्स्ट** को सपोर्ट करते हैं, जिसका अर्थ है आप एक बारकोड में कई एन्कोडिंग मोड (प्लेन, ECI, आदि) एम्बेड कर सकते हैं। बिल्डर QR स्पेसिफिकेशन द्वारा आवश्यक लो‑लेवल फॉर्मेटिंग को एब्स्ट्रैक्ट करता है।

## चरण 2: एक प्लेन‑टेक्स्ट सेगमेंट जोड़ें

प्लेन टेक्स्ट डिफ़ॉल्ट मोड है और ASCII अक्षरों के लिए काम करता है। इसे पहले जोड़ने से उन स्कैनरों के लिए एक पठनीय फॉलबैक मिलता है जो ECI को अनदेखा करते हैं।

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

यदि आप इस चरण को छोड़ देते हैं, तो QR कोड में केवल ECI सेगमेंट रहेगा, जिसे कुछ पुराने रीडर सही ढंग से डिकोड नहीं कर पाएंगे।

## चरण 3: गैर‑ASCII अक्षरों के लिए ECI‑एन्कोडेड सेगमेंट जोड़ें

ASCII रेंज के बाहर के अक्षरों—जैसे कि सिरिलिक, चीनी, या इमोजी—को शामिल करने के लिए आपको एक ECI (Extended Channel Interpretation) एन्कोडिंग निर्दिष्ट करनी होगी। यहाँ हम रूसी शब्द “Привет” के लिए UTF‑8 का उपयोग करते हैं।

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*क्यों यह काम करता है*: QR स्पेसिफिकेशन ECI वैल्यूज़ को परिभाषित करता है जो स्कैनर को बताती हैं कि कौन सा कैरेक्टर सेट लागू करना है। ECI मार्कर के बिना, रॉ बाइट्स को ISO‑8859‑1 के रूप में व्याख्यायित किया जाएगा, जिससे गड़बड़ आउटपुट मिलेगा।

## चरण 4: संयुक्त विस्तारित कोडटेक्स्ट स्ट्रिंग प्राप्त करें

सभी इच्छित सेगमेंट जोड़ने के बाद, `get_extended_codetext()` को कॉल करके अंतिम स्ट्रिंग प्राप्त करें जो बारकोड जेनरेटर की अपेक्षा करता है।

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

प्रिंटेड वैल्यू कंट्रोल कैरेक्टर्स की श्रृंखला के बाद वास्तविक टेक्स्ट जैसी दिखती है, लेकिन आपको इसे मैन्युअली पार्स करने की जरूरत नहीं है।

## चरण 5: विस्तारित कोडटेक्स्ट का उपयोग करके QR कोड जनरेट करें

अब एक `BarcodeGenerator` बनाएं, सिम्बोलॉजी को QR पर सेट करें (एकमात्र सामान्य 2‑D सिम्बोलॉजी जो विस्तारित कोडटेक्स्ट को सपोर्ट करता है), और संयुक्त स्ट्रिंग को फीड करें।

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*टिप*: यदि आप वही प्रक्रिया Code‑128 या DataMatrix के साथ आज़माते हैं, तो SDK एक एक्सेप्शन उठाएगा क्योंकि ये फॉर्मेट ECI मार्कर को व्याख्यायित नहीं कर सकते।

## चरण 6: QR कोड छवि सहेजें

अंत में, बारकोड को PNG फ़ाइल में लिखें। यही वह जगह है जहाँ आप **QR कोड छवि सहेजते** हैं बाद में उपयोग के लिए।

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

सुनिश्चित करें कि `output` फ़ोल्डर मौजूद है या `save` कॉल करने से पहले `os.makedirs('output', exist_ok=True)` से इसे बनाएं।

### पूर्ण चलाने योग्य उदाहरण

सभी चरणों को मिलाकर आपको एक स्व-निहित स्क्रिप्ट मिलती है जिसे आप तुरंत चला सकते हैं:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**अपेक्षित आउटपुट** (कंसोल):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

`qr_extended.png` को किसी भी QR स्कैनर से खोलने पर `HelloWorldПривет` प्रदर्शित होगा। ECI को समझने वाले स्कैनर सिरिलिक अक्षरों को सही ढंग से रेंडर करेंगे; अन्य केवल ASCII भाग दिखाएंगे।

## सामान्य प्रश्न और किनारे के मामले

| प्रश्न | उत्तर |
|----------|--------|
| *क्या मैं Shift‑JIS जैसी अन्य एन्कोडिंग्स का उपयोग कर सकता हूँ?* | हाँ। `CodetextEncodingType.UTF_8` को `CodetextEncodingType.SHIFT_JIS` से बदलें और उपयुक्त टेक्स्ट प्रदान करें। |
| *अगर संयुक्त डेटा QR क्षमता से अधिक हो जाए तो क्या होगा?* | QR कोड के संस्करण सीमाएँ होती हैं (अधिकतम 177 × 177 मॉड्यूल)। यदि बिल्डर साइज एक्सेप्शन फेंके, तो या तो एरर‑करैक्शन लेवल बढ़ाएँ या डेटा को कई QR कोड में विभाजित करें। |
| *क्या मुझे कोई विशिष्ट QR संस्करण सेट करना आवश्यक है?* | SDK स्वचालित रूप से डेटा के अनुसार सबसे छोटा संस्करण चुनता है। यदि आवश्यक हो तो आप `qr_generator.set_qr_version(10)` से एक संस्करण बाध्य कर सकते हैं। |
| *क्या छवि पारदर्शी होगी?* | डिफ़ॉल्ट रूप से SDK एक सफ़ेद बैकग्राउंड के साथ PNG लिखता है। यदि आपको पारदर्शिता चाहिए तो `save` से पहले `qr_generator.set_background_color(Color.Transparent)` का उपयोग करें। |

## निष्कर्ष

इस ट्यूटोरियल में आपने `ExtCodetextBuilder` का उपयोग करके QR कोड में **गैर-ASCII अक्षरों को एन्कोड** करना और फिर `BarcodeGenerator` के साथ **QR कोड छवि सहेजना** सीखा। प्रक्रिया में एक विस्तारित कोडटेक्स्ट स्ट्रिंग बनाना, प्लेन और ECI‑एन्कोडेड दोनों सेगमेंट जोड़ना, QR सिम्बोलॉजी जनरेट करना, और अंत में इमेज फ़ाइल लिखना शामिल है।

अब आप आगे खोज सकते हैं:

* अधिक ECI सेगमेंट जोड़ना (विभिन्न भाषाएँ या इमोजी)।
* उच्च विश्वसनीयता के लिए QR एरर‑करैक्शन लेवल समायोजित करना।
* जनरेट किए गए PNG को PDFs या वेब पेजों में एम्बेड करना।

कोडिंग का आनंद लें, और बहुभाषी QR कोड बनाने का मज़ा उठाएँ!

## अब आपको क्या सीखना चाहिए?

निम्नलिखित ट्यूटोरियल्स निकट-संबंधित विषयों को कवर करते हैं जो इस गाइड में दिखाए गए तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण-दर-चरण व्याख्याएँ शामिल हैं जो आपको अतिरिक्त API फीचर्स में महारत हासिल करने और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोचेज़ को एक्सप्लोर करने में मदद करती हैं।

- [Python में Aspose.Barcode के साथ QR कोड इमेज कैसे जनरेट करें – पूर्ण गाइड](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Aspose.Barcode Python के साथ Code128 बारकोड जनरेट करें – पूर्ण गाइड](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Python बारकोड लाइब्रेरी का उपयोग करके प्रोडक्ट नाम दिखाएँ – चरण-दर-चरण गाइड](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}