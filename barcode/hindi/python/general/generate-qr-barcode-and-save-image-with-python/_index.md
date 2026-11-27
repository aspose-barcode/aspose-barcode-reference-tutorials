---
category: general
date: 2026-11-27
description: Aspose.Barcode का उपयोग करके Python में QR बारकोड जेनरेट करें और जल्दी
  से बारकोड छवि को डिस्क पर सहेजना सीखें।
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: hi
lastmod: 2026-11-27
og_description: Aspose.Barcode के साथ Python में QR बारकोड बनाएं और तुरंत बारकोड छवि
  सहेजें। QR कोड बनाने, अनुकूलित करने और संग्रहित करने के लिए पूर्ण उदाहरण का पालन
  करें।
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Python के साथ QR बारकोड बनाएं और इमेज सहेजें – चरण‑दर‑चरण गाइड
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Python के साथ QR बारकोड बनाएं और छवि सहेजें
url: /hi/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate QR barcode and save image with Python

यदि आपको Python एप्लिकेशन में **QR बारकोड जेनरेट** करना है, तो यह गाइड Aspose.Barcode लाइब्रेरी का उपयोग करके इसे कैसे करें, दिखाती है। आप यह भी सीखेंगे कि **बारकोड इमेज को** स्थानीय फ़ोल्डर में सही तरीके से **सेव** कैसे करें, लाइब्रेरी संस्करण विवरण कैसे प्राप्त करें, और विस्तारित कोडटेक्स्ट सेगमेंट को कैसे हैंडल करें।

QR कोड बनाना टिकटिंग सिस्टम, मोबाइल पेमेंट्स, और प्रोडक्ट ट्रैकिंग के लिए एक सामान्य आवश्यकता है। इस ट्यूटोरियल के अंत तक आपके पास एक तैयार‑चलाने‑योग्य स्क्रिप्ट होगी जो QR बारकोड इमेज फ़ाइल बनाती है और डिबगिंग या अनुपालन उद्देश्यों के लिए संस्करण जानकारी प्रिंट करती है।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

* Python 3.8 या उससे नया संस्करण स्थापित हो।
* `aspose-barcode` पैकेज। इसे `pip install aspose-barcode` से इंस्टॉल करें।
* उस डायरेक्टरी में लिखने की अनुमति जहाँ बारकोड इमेज संग्रहीत होगी।

कोई अतिरिक्त बाहरी सेवा आवश्यक नहीं है; पूरी प्रक्रिया स्थानीय रूप से चलती है।

## Step 1: Build an extended codetext with `ExtCodetextBuilder`

विस्तारित कोडटेक्स्ट आपको एक ही QR कोड में प्लेन टेक्स्ट और ECI (Extended Channel Interpretation) सेगमेंट को मिलाने की अनुमति देता है। यह तब उपयोगी होता है जब आपको विभिन्न कैरेक्टर सेट्स के अक्षरों को एम्बेड करना हो, जैसे यूरो साइन।

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Why this step matters:**  
`ExtCodetextBuilder` अंतिम स्ट्रिंग को असेंबल करता है जिसे QR एन्कोडर प्रोसेस करेगा। विस्तारित कोडटेक्स्ट बनाए बिना, बारकोड में केवल प्लेन ASCII कैरेक्टर्स ही होंगे और वह लोकेल‑स्पेसिफिक सिंबल्स को प्रदर्शित नहीं कर पाएगा।

## Step 2: Retrieve the combined extended codetext string

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

आउटपुट इस प्रकार दिखेगा:

```
Extended codetext: ABC123[ECI3]€123
```

ब्रैकेटेड `[ECI3]` मार्कर QR एन्कोडर को बताता है कि अगले कैरेक्टर्स के लिए निर्दिष्ट कैरेक्टर सेट पर स्विच करना है।

## Step 3: Generate the QR barcode using the extended codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Explanation:**  
`BarcodeGenerator` दो आर्ग्यूमेंट लेता है: बारकोड प्रकार (`QR`) और एन्कोड करने के लिए डेटा (`extended_codetext`)। जेनरेटर रेंडरिंग के लिए आवश्यक सभी आंतरिक संरचनाओं को तैयार करता है।

## Step 4: Save the generated barcode image

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Why you should use this approach:**  
`save` को सीधे कॉल करने से इमेज डिस्क पर लिखी जाती है, फ़ाइल एक्सटेंशन से फ़ॉर्मेट का अनुमान लगाया जाता है। यह मेथड PNG, JPEG, BMP, और TIFF को सपोर्ट करता है, जिससे विभिन्न डाउनस्ट्रीम कंज्यूमर्स के लिए लचीलापन मिलता है।

### Verifying the saved image

फ़ाइल `output/qr_extended.png` को किसी भी इमेज व्यूअर में खोलें। आपको एक QR कोड दिखना चाहिए जो स्कैन करने पर स्ट्रिंग `ABC123€123` लौटाता है। अधिकांश आधुनिक मोबाइल QR स्कैनर ECI सेगमेंट को स्वचालित रूप से हैंडल करते हैं।

## Step 5: Query Aspose.BarCode version information (optional but useful)

Aspose.BarCode लाइब्रेरी का सटीक संस्करण जानना उपयोगी होता है जब आपको बग रिपोर्ट करना हो या संगतता सत्यापित करनी हो।

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typical output:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Full script – copy, paste, and run

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

स्क्रिप्ट चलाने से QR कोड इमेज बनती है और कंसोल में विस्तारित कोडटेक्स्ट तथा संस्करण विवरण दोनों प्रिंट होते हैं।

## Common variations and edge cases

| Situation | Recommended adjustment |
|-----------|------------------------|
| **Different character set** | `add_eci_codetext` को पास किया गया ECI आइडेंटिफ़ायर बदलें। UTF‑8 के लिए `5` उपयोग करें। |
| **Higher error correction** | `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` को `save` कॉल करने से पहले सेट करें। |
| **Custom image size** | पिक्सेल डाइमेंशन नियंत्रित करने के लिए `barcode.parameters.image_width` और `barcode.parameters.image_height` का उपयोग करें। |
| **Non‑PNG output** | `output_path` में फ़ाइल एक्सटेंशन को `.jpg` या `.bmp` में बदलें। लाइब्रेरी स्वचालित रूप से सही एन्कोडर चुन लेगी। |

## Pro tips

* **Create the output folder** programmatically if it may not exist:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validate the QR code** after generation by reading it back with `aspose.barcode.BarcodeReader`. यह सुनिश्चित करता है कि एन्कोडेड डेटा अपेक्षाओं से मेल खाता है, विशेषकर जब ECI सेगमेंट उपयोग में हों।

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Performance tip** – यदि आपको लूप में कई QR कोड जेनरेट करने हैं तो एक ही `BarcodeGenerator` इंस्टेंस को पुनः उपयोग करें। प्रत्येक इटरशन में नया ऑब्जेक्ट बनाने के बजाय `code_text` प्रॉपर्टी को रीसेट करें।

## Conclusion

अब आप जानते हैं कि **Python में Aspose.Barcode के साथ QR बारकोड कैसे जेनरेट** करें, प्लेन और ECI सेगमेंट को मिलाकर विस्तारित कोडटेक्स्ट बनाएं, और **बारकोड इमेज को** डिस्क पर सही तरीके से **सेव** करें। स्क्रिप्ट लाइब्रेरी संस्करण जानकारी को भी प्राप्त करने का तरीका दिखाती है, जिससे ट्रबलशूटिंग आसान हो जाता है।

अगले कदम जिन पर आप विचार कर सकते हैं:

* QR कोड में लोगो ओवरले या कस्टम रंग जोड़ना।
* Aspose.PDF का उपयोग करके QR बारकोड को सीधे PDFs में एम्बेड करना।
* बड़े डेटासेट के लिए बैच जेनरेशन को ऑटोमेट करना।

विभिन्न डेटा पेलोड, एरर‑करेक्शन लेवल, और इमेज फ़ॉर्मेट के साथ प्रयोग करने में संकोच न करें। Happy coding!

## What Should You Learn Next?

निम्नलिखित ट्यूटोरियल्स उन विषयों को कवर करते हैं जो इस गाइड में प्रदर्शित तकनीकों पर आधारित हैं। प्रत्येक संसाधन में पूर्ण कार्यशील कोड उदाहरण और चरण‑दर‑चरण व्याख्याएँ शामिल हैं, जिससे आप अतिरिक्त API फीचर्स में निपुण हो सकें और अपने प्रोजेक्ट्स में वैकल्पिक इम्प्लीमेंटेशन अप्रोच को एक्सप्लोर कर सकें।

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}