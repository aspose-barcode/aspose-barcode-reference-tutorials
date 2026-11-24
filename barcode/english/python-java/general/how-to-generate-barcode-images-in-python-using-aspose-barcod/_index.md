---
category: general
date: 2026-11-23
description: How to generate barcode images in Python with Aspose.BarCode. Learn to
  create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: en
lastmod: 2026-11-23
og_description: How to generate barcode in Python using Aspose.BarCode. This tutorial
  walks you through creating a Planet barcode with empty bars and saving it as a PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: How to generate barcode in Python – complete guide
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: How to generate barcode images in Python using Aspose.BarCode
url: /python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode images in Python using Aspose.BarCode

How to generate barcode images in Python is straightforward with the Aspose.BarCode library. This guide shows you step‑by‑step how to generate barcode using the Planet symbology, customize the X‑dimension, and produce an empty‑bars style PNG file.

You’ll see a complete, runnable script that you can copy into your project. The tutorial also covers common variations—such as switching to a different symbology or output format—so you can adapt the solution to your own requirements.

## Prerequisites

Before you start, make sure you have:

* Python 3.8 or newer installed.
* Access to a terminal or command prompt.
* An active Aspose.BarCode for Python license (the free evaluation works for testing).
* Basic familiarity with Python package management (`pip`).

## Step 1: Install the Aspose.BarCode package

Aspose distributes its Python API via PyPI. Install it with the standard package manager:

```bash
pip install asposebarcode
```

> **Pro tip:** Use a virtual environment (`python -m venv venv`) to keep dependencies isolated from other projects.

## Step 2: Import the required Aspose.BarCode classes

The import statement pulls in the generator, the enumeration of symbologies, and the image format enum.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` creates the barcode object.
* `EncodeTypes` enumerates all supported symbologies—here we’ll use `Planet`.
* `BarCodeImageFormat` defines the output file type (PNG, JPEG, etc.).

## Step 3: Create a barcode generator for the Planet symbology

Instantiate the generator with the desired symbology and the data you want to encode.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

The `Planet` symbology produces a circular pattern that is ideal for decorative or branding purposes.

## Step 4: Adjust the X‑dimension (module width)

The X‑dimension controls the width of the smallest bar (module). Setting it to 4 pixels yields a clear, high‑resolution image.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Changing the X‑dimension is useful when you need a barcode that scales well for printing or screen display.

## Step 5: Disable the filled bars for an empty‑bars style

An empty‑bars barcode shows only the outlines of the bars, which can be useful for design‑heavy applications.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

When `filled_bars` is `False`, the generator draws hollow shapes instead of solid ones.

## Step 6: Save the barcode image as a PNG file

Finally, write the barcode to disk. PNG is lossless and widely supported.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

The `save` method automatically creates the target directory if it does not exist.

## Full example – a complete, runnable script

Putting all the pieces together gives you a self‑contained program you can run immediately:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Expected output:** After running the script, `output/PlanetEmptyBars.png` contains a 200 × 200 pixel image of a Planet barcode with hollow bars. Opening the file in any image viewer will display the circular pattern with the numeric value encoded inside.

## Common variations and edge cases

### Switching to a different symbology

If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet` with the appropriate enum value:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Changing the image format

Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Adjusting image size without losing quality

You can control the overall image dimensions via the `resolution` property or by scaling the X‑dimension and Y‑dimension together. For high‑resolution prints, set a higher DPI:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Handling long data strings

The Planet symbology has a limited data capacity (up to 8 characters). If you try to encode a longer string, the generator raises an exception. Validate the length before creating the barcode:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Tips and pitfalls

* **License activation:** For production use, apply your license file early in the script with `asposebarcode.License().set_license("Aspose.Total.lic")`. Skipping this step will embed a watermark in the output image.
* **Thread safety:** `BarcodeGenerator` instances are not thread‑safe. Create a separate instance per thread if you generate barcodes in parallel.
* **Performance:** Reusing a generator for multiple values (by calling `barcode.value = "new data"`) is faster than constructing a new object each time.
* **File paths:** Use `os.path.join` to build platform‑independent paths, especially when deploying on Linux or macOS.

## Conclusion

You now know how to generate barcode images in Python with Aspose.BarCode, customize the X‑dimension, produce an empty‑bars style, and save the result as a PNG. The complete example can be adapted to other symbologies, output formats, and visual styles, giving you a flexible foundation for any barcode‑related feature in your applications.

**Next steps:** Explore additional secondary keywords such as *Python barcode generation* by trying different encodings, experiment with *barcode image PNG* compression settings, or integrate the generated images into a web service using Flask or FastAPI. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}