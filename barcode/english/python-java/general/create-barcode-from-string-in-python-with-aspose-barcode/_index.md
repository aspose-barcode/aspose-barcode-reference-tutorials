---
category: general
date: 2026-10-15
description: Create barcode from string in Python using Aspose.BarCode, learn how
  to generate Code 128 barcode and save barcode PNG in just a few lines.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: en
lastmod: 2026-10-15
og_description: Create barcode from string in Python to encode data into a Code 128
  barcode and save it as a PNG file with Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Create barcode from string in Python – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Create barcode from string in Python with Aspose.BarCode
url: /python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode from string in Python with Aspose.BarCode

If you need to **create barcode from string** in Python, this guide shows you the exact steps with Aspose.BarCode. You’ll learn how to **generate Code 128 barcode**, adjust its appearance, and **save barcode PNG** to disk. The solution works on any platform that supports Python 3.9+ and requires only a few lines of code.

Generating barcodes programmatically eliminates manual entry errors and streamlines workflows such as inventory tracking, ticketing, and label printing. By the end of this tutorial you will be able to **encode data into barcode**, customize dimensions, and store the image wherever you need it.

## Prerequisites

Before you start, make sure you have:

- Python 3.9 or newer installed  
- Internet access to download the Aspose.BarCode package  
- Write permission to the directory where you will save the PNG file  

If you’re using a virtual environment (highly recommended), activate it now.

## Install Aspose.BarCode Python package

Aspose provides a pure‑Python library that handles all common barcode symbologies, including Code 128. Install it with pip:

```bash
pip install aspose-barcode
```

*Pro tip:* Pin the version (e.g., `aspose-barcode==23.9`) to avoid unexpected breaking changes in production.

## Create barcode from string in Python

The first functional step is to import the required classes and instantiate a generator for the desired symbology. This example uses **Code 128**, which is ideal for alphanumeric data.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Why this matters:** `EncodeTypes.CODE_128` tells the library which barcode standard to apply, while the second argument (`"1234567890"`) is the **string you want to encode into barcode**. You can replace it with any ASCII string up to 80 characters for Code 128.

## Generate Code 128 barcode

Once the generator is ready, you can produce the barcode image in memory. The library automatically renders the barcode based on the provided data.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

At this point `barcode_image` is an instance of `System.Drawing.Image` (on Windows) or a compatible image object on other platforms. You could display it directly in a GUI, embed it in a PDF, or continue customizing it.

## Adjust barcode appearance

Fine‑tuning the visual properties ensures the barcode scans reliably in your specific environment. Common adjustments include the X‑dimension (the width of the narrowest bar) and the overall bar height.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Why adjust these values?*  
- **X dimension** influences the barcode’s density; a smaller value yields a tighter barcode that fits on small labels.  
- **Bar height** affects readability; taller bars are easier for scanners to detect from a distance.

You can also change colors, add margins, or embed human‑readable text via the `parameters` object. Refer to the Aspose.BarCode documentation for the full list of options.

## How to save barcode as PNG

Saving the generated image is the final step in the **create barcode from string** workflow. The library supports several formats; PNG is lossless and widely supported.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

The `save` method writes the image to the file system using the format you specify. If the target directory (`output/` in this example) does not exist, Python will raise a `FileNotFoundError`. Create the directory beforehand or handle the exception:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Expected result:** After running the script, `output/barcode.png` contains a clear Code 128 barcode that encodes `"1234567890"`. Opening the file in any image viewer will show a black‑on‑white barcode ready for scanning.

## Full, runnable example

Putting all the pieces together, here is a self‑contained script you can copy, paste, and run:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Run the script with `python create_barcode.py`. If everything is installed correctly, you’ll see:

```
Barcode saved to output/barcode.png
```

Open the PNG file and verify that the barcode matches the original string using any barcode scanner app.

## Common questions and edge cases

- **What if I need a different symbology?**  
  Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`, `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains the same.

- **Can I generate a barcode from non‑ASCII characters?**  
  Code 128 supports the full 128‑character ASCII set. For Unicode data, consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.

- **How do I change the image format?**  
  Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG` or `BarCodeImageFormat.BMP`.

- **What if the output directory is read‑only?**  
  Wrap the `save` call in a try/except block and handle `PermissionError` gracefully, perhaps by prompting the user for an alternative path.

- **Performance tip:**  
  Generating thousands of barcodes in a loop can be CPU‑intensive. Reuse a single `BarcodeGenerator` instance and only update `generator.parameters.barcode.code_text` between iterations.

## Conclusion

You now know how to **create barcode from string** in Python using Aspose.BarCode, **generate Code 128 barcode**, customize its size, and **save barcode PNG** to disk. This end‑to‑end solution lets you **encode data into barcode** quickly and reliably, making it easy to integrate barcodes into inventory systems, ticketing platforms, or any application that requires machine‑readable identifiers.

**Next steps**

- Explore other symbologies (`generate code 128 barcode` alternatives) such as QR or DataMatrix.  
- Add error‑handling logic to make the script robust for production use (`how to save barcode` failures).  
- Embed the generated PNG into PDFs or HTML reports (`generate barcode png` for web).  

Happy coding, and enjoy the simplicity of programmatic barcode generation!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}