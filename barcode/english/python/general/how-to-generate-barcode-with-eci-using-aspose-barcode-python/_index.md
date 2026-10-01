---
category: general
date: 2026-08-19
description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
  how to add eci data, mix plain text, and save the image in one clear guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: en
lastmod: 2026-08-19
og_description: How to generate barcode with ECI using Aspose.Barcode for Python.
  Follow this tutorial to learn how to add eci data, customize appearance, and save
  the result.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: How to generate barcode with ECI using Aspose.Barcode Python – step‑by‑step
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: How to generate barcode with ECI using Aspose.Barcode Python
url: /python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode with ECI using Aspose.Barcode Python

If you need to know **how to generate barcode** that contains both plain characters and ECI‑encoded data, this guide shows the complete process. You’ll see exactly **how to add eci** sections, adjust size, and write the image to disk with a single, runnable script.

The tutorial covers:

* Retrieving the Aspose.Barcode library version (optional but useful for debugging).  
* Building an extended codetext string that mixes plain and ECI‑encoded characters.  
* Creating a barcode generator for a symbology that supports extended codetext.  
* Customizing barcode dimensions and saving the final PNG file.

No external documentation is required; copy the code, run it, and you’ll have a barcode image that includes Chinese characters encoded with ECI 26 (UTF‑8).

## Prerequisites

Before you start, make sure you have:

* Python 3.8 or newer installed.  
* `aspose-barcode` package installed (`pip install aspose-barcode`).  
* Write permission to the folder where you intend to save the PNG file.

If you’re using a virtual environment, activate it first to keep dependencies isolated.

## Step 1: Verify the Aspose.Barcode version (optional)

Knowing the exact library version helps when you need to report bugs or compare features across releases.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Why this matters*: The version output confirms that the runtime matches the documentation you’re following. Different versions may support different ECI values, so it’s a quick sanity check.

## Step 2: Build an extended codetext with plain and ECI‑encoded parts

Aspose.Barcode provides `ExtCodetextBuilder` to concatenate plain data and ECI‑encoded segments. In this example we mix a numeric string with Chinese characters.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Explanation*:  
* `add_plain_codetext` inserts data that the barcode symbology treats as ordinary characters.  
* `add_eci_codetext` tells the generator to prepend an ECI indicator (here **26**, which maps to UTF‑8) before the supplied text. This is exactly **how to add eci** data to a barcode.

You can call `add_eci_codetext` multiple times to embed several different language blocks. The builder handles the required escape sequences automatically.

## Step 3: Choose a symbology that supports extended codetext

Not every barcode type can store ECI segments. Code 128, QR, and Data Matrix are common choices. The example uses Code 128 because it is widely supported and works well for mixed alphanumeric data.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Why Code 128?*: It accepts the full ASCII range and the ECI escape sequences produced by the builder, making it ideal for the “how to generate barcode” scenario that mixes plain and encoded text.

## Step 4: Adjust barcode appearance

You can control size, height, margins, and many other visual aspects via the `parameters` object.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tip*: If you plan to print the barcode, increase `x_dimension` and `bar_height` proportionally to maintain readability at the target DPI.

## Step 5: Save the barcode image

Finally, write the generated image to a file. Aspose.Barcode supports PNG, JPEG, BMP, and many other formats.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Make sure the `output` folder exists or create it with `os.makedirs("output", exist_ok=True)` before calling `save`.

### Expected result

When you open `extended_codetext.png`, you should see a Code 128 barcode that encodes the numeric string `1234567890` followed by the Chinese characters “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return the original mixed string.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode generated with how to generate barcode example"}

## Common questions and edge cases

### What if I need a different character set?

Choose the appropriate ECI value from the ISO/IEC 18004 table. For example, ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext` accordingly.

### Can I embed more than one ECI block?

Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary ECI switch codes between blocks, preserving the order you add them.

### Does the generator support QR codes with ECI?

Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR` and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### How to handle very long data strings?

For linear barcodes like Code 128, the maximum length is about 80 characters when using extended codetext. If you exceed that, consider switching to a two‑dimensional symbology such as QR or Data Matrix, which can store thousands of characters.

## Full, runnable script

Below is the complete program you can copy‑paste into a file named `generate_extended_barcode.py` and run directly.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}