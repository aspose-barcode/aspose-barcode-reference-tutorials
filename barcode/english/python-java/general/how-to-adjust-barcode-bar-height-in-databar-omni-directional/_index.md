---
category: general
date: 2026-11-27
description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
  barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: en
lastmod: 2026-11-27
og_description: Adjust barcode bar height in a DataBar Omni‑Directional barcode generator
  with Python. Follow the complete guide to set heights, X‑dimension, and save PNG
  images.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Adjust barcode bar height in DataBar Omni‑Directional generator
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: How to adjust barcode bar height in DataBar Omni‑Directional generator
url: /python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to adjust barcode bar height in DataBar Omni‑Directional generator

If you need to **adjust barcode bar height** for a DataBar Omni‑Directional barcode, this guide shows you exactly how. You’ll see a complete, runnable Python example that changes the bar height from 30 px to 60 px while keeping the X‑dimension and image format consistent.

Changing a barcode’s visual dimensions is a common requirement when the barcode must fit a specific label size or design guideline. In addition to bar height, you may also want to tweak the **X‑dimension** (module size) or choose a different **barcode image format** such as PNG or JPEG.

In this tutorial you will:

* Install the required library (GroupDocs.Barcode for Python)
* Create a DataBar Omni‑Directional barcode generator
* Set the module size with `XDimension`
* Adjust the bar height property twice
* Save the resulting images in the desired **BarCodeImageFormat**

No prior experience with the GroupDocs API is needed—just basic Python knowledge.

## Prerequisites

Before you begin, make sure you have:

* Python 3.8 or newer installed
* `groupdocs.barcode` package (`pip install groupdocs-barcode`)  
* Write permission to a folder where the PNG files will be saved

If you’re unfamiliar with **DataBar Omni‑Directional barcode**, it encodes a 14‑digit GTIN and is widely used in retail for scanning from any orientation.

## Step 1: Set up the DataBar Omni‑Directional barcode generator

First, import the necessary classes and instantiate the generator with the GTIN data you want to encode.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Why this matters:* The `EncodeTypes.DatabarOmniDirectional` constant tells the library to produce the Omni‑Directional symbology. The data string includes the AI `(01)` that marks a GTIN‑14 value.

## Step 2: Define the X‑dimension (module size)

The X‑dimension controls the width of the narrowest bar. A common value for on‑screen rendering is **2 px per module**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Using a consistent **set XDimension** ensures that the barcode scales correctly across different printers and scanners.

## Step 3: Adjust the bar height to 30 px and save the image

Now we change the bar height property. The first height we’ll use is **30 px**, which is suitable for small labels.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

The `BarCodeImageFormat.Png` constant selects the **barcode image format** PNG, which preserves lossless quality.

### Expected result

The file `DatabarBarHeight30Pixels.png` contains a DataBar Omni‑Directional barcode whose bars are 30 px tall. Below is a placeholder preview:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tip:** If you open the PNG in an image editor, you’ll see the exact bar height. The narrow bars are 2 px wide, as defined earlier.

## Step 4: Change the bar height to 60 px for a taller barcode

For applications that require a larger visual footprint—such as a freight label—you can increase the bar height to **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Only the `BarHeight` property changes; the X‑dimension and encoding remain the same, so the barcode stays scannable.

## Step 5: Save the updated barcode image

Finally, write the taller barcode to a second PNG file.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Expected result

The file `DatabarBarHeight60Pixels.png` shows the same data encoded, but each bar is now 60 px tall. The visual difference is illustrated below:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Full, runnable example

Putting everything together, here is the complete script you can copy‑paste into a file named `adjust_barcode_height.py` and run directly.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Run the script:

```bash
python adjust_barcode_height.py
```

You should see two PNG files in the `output` folder, each reflecting the bar height you set.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is lossy, so prefer PNG for precise scanning. |
| **What if I need a bar height that isn’t a multiple of 10?** | The `BarHeight.Pixels` property accepts any integer value. Just assign the desired pixel count (e.g., `45`). |
| **Does changing the bar height affect the encoded data?** | No. Only the visual representation changes; the underlying data string remains identical. |
| **How do I change the X‑dimension after saving the first image?** | You can modify `gen.parameters.barcode.x_dimension.pixels` at any time before calling `save()`. The change will apply to subsequent images. |
| **Is the generator thread‑safe?** | The `BarcodeGenerator` instance is not guaranteed to be thread‑safe. Create a separate instance per thread if you generate barcodes concurrently. |

## Conclusion

You now know how to **adjust barcode bar height** in a DataBar Omni‑Directional barcode generator using Python. The tutorial covered creating the generator, setting the **X‑dimension**, modifying the **barcode bar height** property, and saving images in the desired **barcode image format**. 

From here you can experiment with other heights, different module sizes, or switch to alternative image formats such as JPEG or BMP. You might also explore additional **barcode generator python** features like adding human‑readable text or changing color schemes.

Happy coding, and keep your barcodes crisp and perfectly sized!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}