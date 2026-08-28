---
category: general
date: 2026-08-09
description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
  extended codetext, adjust appearance, and save the image—all in one tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: en
lastmod: 2026-08-09
og_description: Create QR barcode in Python with Aspose.BarCode. This guide shows
  how to build extended codetext, set visual parameters, and export the image.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Create QR barcode with Aspose.BarCode in Python – full code example
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
title: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
url: /python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide

If you need to **create QR barcode** in Python, this tutorial walks you through the entire process using the Aspose.BarCode library. Whether you’re encoding product IDs, multilingual text, or custom data, you’ll see how to build an extended codetext, tweak visual settings, and save the final image in a single, runnable script.

The example also demonstrates how to display the library version, which helps you verify that you’re running a compatible release. By the end of this guide you’ll have a ready‑to‑use QR barcode image and a clear understanding of each configuration option.

## Prerequisites

Before you start, make sure you have:

- Python 3.8+ installed.
- The `aspose-barcode` package (install via `pip install aspose-barcode`).
- Basic familiarity with Python syntax.
- Write permission to the output directory where the PNG file will be saved.

> **Pro tip:** Use a virtual environment to avoid version conflicts with other projects.

## Step 1: Verify the Aspose.BarCode library version

Displaying the library version ensures you’re using a release that supports extended codetext and QR encoding.

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
Older releases may lack the `ExtCodetextBuilder` class required for mixed plain and ECI segments. Confirming the version prevents runtime errors later in the workflow.

## Step 2: Build an extended codetext string

An extended codetext lets you combine plain ASCII data with Unicode (ECI) segments, which is essential for multilingual QR codes.

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
The `add_plain_codetext` method stores data as standard ASCII, while `add_eci_codetext` prefixes a Unicode block with the appropriate ECI designator. This approach ensures QR scanners interpret the Japanese text correctly, avoiding garbled characters.

### Common variations

- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to mix several languages.
- **Different ECI identifiers:** Use `27` for ISO‑8859‑1, `28` for ISO‑8859‑2, etc., depending on your target encoding.

## Step 3: Generate the QR barcode using the extended codetext

Now that we have a properly formatted string, we can create the QR code.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Why this matters:**  
`EncodeTypes.QR` tells Aspose.BarCode to use the QR symbology. Passing the `extended_codetext` directly links the mixed data to the QR matrix, preserving both plain and Unicode parts.

## Step 4: Adjust visual appearance (optional but recommended)

Fine‑tuning the barcode’s visual parameters improves scan reliability and matches branding guidelines.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Why this matters:**  
- **`x_dimension`** controls the size of each QR module; too small may cause read errors on low‑resolution devices.
- **`border_width`** adds a quiet zone. Some scanners require at least a 4‑module quiet zone; the library adds this automatically, but you can increase it for extra safety.

### Edge case handling

- **High‑density data:** If the encoded data is large, you may need to increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
- **Transparent background:** Set `qr_generator.parameters.barcode.bg_color = Color.Transparent` for PNGs with alpha channels.

## Step 5: Save the QR barcode image

Finally, write the image to disk in your preferred format.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Why this matters:**  
Saving as PNG preserves lossless quality, which is ideal for QR codes that need crisp edges. If you need a different format for a web application, simply change the `BarCodeImageFormat` enumeration.

### Verifying the result

Open the saved file in any image viewer. You should see a QR code that, when scanned, returns the combined string:

```
ABC12345
こんにちは
```

Most modern QR scanner apps display the plain segment first and then render the Japanese greeting correctly.

---

## Full runnable script

Copy the entire block below into a file named `create_qr_barcode.py` and run it with `python create_qr_barcode.py`. Adjust `YOUR_DIRECTORY` to a writable folder on your machine.

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

Running this script prints the version, the extended codetext, and a confirmation that the PNG file was created.

---

## Conclusion

You now know how to **create QR barcode** images in Python using Aspose.BarCode. The tutorial covered:

1. Verifying the library version.
2. Building extended codetext with plain and ECI (Unicode) segments.
3. Generating the QR code.
4. Customizing visual parameters such as module size and border width.
5. Saving the final image in PNG format.

From here you can explore:

- Changing error‑correction levels (`qr_generator.parameters.qr.error_correction_level`).
- Adding a logo or background image (`qr_generator.parameters.qr.logo`).
- Exporting to other formats like SVG for scalable web graphics.
- Integrating the generator into a Flask or Django endpoint for on‑the‑fly QR creation.

Experiment with different data payloads and visual settings to fit your application’s branding and scanning requirements. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}