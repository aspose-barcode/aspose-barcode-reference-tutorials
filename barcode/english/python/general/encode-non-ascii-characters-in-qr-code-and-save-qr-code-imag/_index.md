---
category: general
date: 2026-09-10
description: Encode non ASCII characters in a QR code and save QR code image with
  a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder and
  BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: en
lastmod: 2026-09-10
og_description: Encode non ASCII characters in a QR code and save QR code image using
  Python. This tutorial shows how to build extended codetext, generate a QR code,
  and store the image.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Encode non ASCII characters in QR code and save QR code image – step‑by‑step
  Python guide
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
title: Encode non ASCII characters in QR code and save QR code image
url: /python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Encode non ASCII characters in QR code and save QR code image

If you need to **encode non ASCII characters** in a QR code, this guide shows you exactly how to do it and then **save QR code image** to disk. Whether you’re handling Russian, Chinese, or emoji data, the ExtCodetextBuilder lets you mix plain text and ECI‑encoded segments without manual byte fiddling.

You’ll learn how to create an extended codetext string, generate a QR code that understands that string, and finally write the barcode image to a file. The tutorial assumes basic Python knowledge and that you have the `barcode` SDK installed.

## Prerequisites

Before you start, make sure you have:

* Python 3.8+ installed.
* The `barcode` Python package (or the appropriate SDK) that provides `ExtCodetextBuilder`, `CodetextEncodingType`, and `BarcodeGenerator`.
* Write permission to the directory where you want to **save QR code image**.

You can install the SDK with pip (replace `barcode-sdk` with the actual package name):

```bash
pip install barcode-sdk
```

## Step 1: Create an extended codetext builder

The first step is to instantiate `ExtCodetextBuilder`. This object collects multiple text segments and produces a single string that QR code symbology can interpret.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Why this matters*: QR codes support **extended codetext**, which means you can embed several encoding modes (plain, ECI, etc.) in one barcode. The builder abstracts the low‑level formatting required by the QR specification.

## Step 2: Add a plain‑text segment

Plain text is the default mode and works for ASCII characters. Adding it first gives a readable fallback for scanners that ignore ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

If you omitted this step, the QR code would contain only the ECI segment, which some older readers might not decode correctly.

## Step 3: Add an ECI‑encoded segment for non‑ASCII characters

To include characters outside the ASCII range—such as Cyrillic, Chinese, or emojis—you must specify an ECI (Extended Channel Interpretation) encoding. Here we use UTF‑8 for the Russian word “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Why this works*: The QR spec defines ECI values that tell the scanner which character set to apply. Without the ECI marker, the raw bytes would be interpreted as ISO‑8859‑1, resulting in garbled output.

## Step 4: Retrieve the combined extended codetext string

After adding all desired segments, call `get_extended_codetext()` to obtain the final string that the barcode generator expects.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

The printed value looks like a series of control characters followed by the actual text, but you never need to parse it manually.

## Step 5: Generate a QR code using the extended codetext

Now create a `BarcodeGenerator`, set the symbology to QR (the only common 2‑D symbology that supports extended codetext), and feed the combined string.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: If you try the same process with Code‑128 or DataMatrix, the SDK will raise an exception because those formats cannot interpret ECI markers.

## Step 6: Save the QR code image

Finally, write the barcode to a PNG file. This is where you **save QR code image** for later use.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Make sure the `output` folder exists or create it with `os.makedirs('output', exist_ok=True)` before calling `save`.

### Full runnable example

Putting all steps together gives you a self‑contained script you can run immediately:

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

**Expected output** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Opening `qr_extended.png` with any QR scanner will display `HelloWorldПривет`. Scanners that understand ECI will render the Cyrillic characters correctly; others will show only the ASCII part.

## Common questions & edge cases

| Question | Answer |
|----------|--------|
| *Can I use other encodings like Shift‑JIS?* | Yes. Replace `CodetextEncodingType.UTF_8` with `CodetextEncodingType.SHIFT_JIS` and provide the appropriate text. |
| *What if the combined data exceeds QR capacity?* | QR codes have version limits (up to 177 × 177 modules). If the builder throws a size exception, either increase the error‑correction level or split data across multiple QR codes. |
| *Do I need to set a specific QR version?* | The SDK automatically selects the smallest version that fits the data. You can force a version with `qr_generator.set_qr_version(10)` if required. |
| *Will the image be transparent?* | By default the SDK writes a PNG with a white background. Use `qr_generator.set_background_color(Color.Transparent)` before `save` if you need transparency. |

## Conclusion

In this tutorial you learned how to **encode non ASCII characters** in a QR code using the `ExtCodetextBuilder` and then **save QR code image** with the `BarcodeGenerator`. The process involves building an extended codetext string, adding both plain and ECI‑encoded segments, generating the QR symbology, and finally writing the image file.

From here you can explore:

* Adding more ECI segments (different languages or emojis).
* Adjusting QR error‑correction levels for higher reliability.
* Embedding the generated PNG into PDFs or web pages.

Happy coding, and enjoy creating multilingual QR codes!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}