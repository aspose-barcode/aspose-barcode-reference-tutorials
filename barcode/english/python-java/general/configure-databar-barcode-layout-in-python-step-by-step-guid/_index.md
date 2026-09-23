---
category: general
date: 2026-08-12
description: Configure Databar barcode layout in Python quickly. Learn to set columns,
  rows, and save images with the barcode generator library.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: en
lastmod: 2026-08-12
og_description: Configure Databar barcode layout in Python to control columns, rows,
  and image output. Follow this guide for a ready‑to‑run solution.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configure Databar barcode layout in Python – complete tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Configure Databar barcode layout in Python – step‑by‑step guide
url: /python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configure Databar barcode layout in Python – step‑by‑step guide

If you need to **configure Databar barcode layout in Python**, this guide walks you through the entire process. You’ll see how to set the number of columns or rows for a Databar Expanded Stacked barcode and how to save the resulting image with a single call to the barcode generator library.

Controlling the layout is essential when you embed barcodes on narrow packaging, receipts, or mobile screens. In the sections below we’ll cover the required imports, the two layout options (columns and rows), and the best practices for saving a clean PNG image.

## What you’ll need

Before you start, make sure you have:

* Python 3.8 or newer
* `aspose.barcode` (or any compatible barcode‑generation package) installed  
  ```bash
  pip install aspose-barcode
  ```
* Write permission to a folder where the PNG files will be stored

No additional external tools are required—the library handles rendering, scaling, and image encoding internally.

## How to configure Databar barcode layout in Python

The core of the solution is the `BarcodeGenerator` class. It accepts an `EncodeTypes` enum that identifies the barcode symbology—in this case `EncodeTypes.DatabarExpandedStacked`. After creating the generator you can adjust the layout by setting the `columns` or `rows` properties on the `data_bar` parameter object.

### Step 1: Import the required classes

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

These imports give you access to the generator, the enumeration for Databar types, and the PNG image format constant.

### Step 2: Create a barcode generator for Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Why this step?*  
`EncodeTypes.DatabarExpandedStacked` tells the library to produce the **Databar Expanded Stacked** symbology, which supports longer numeric strings while keeping a compact footprint. The second argument is the data to encode; it can be any string that meets the Databar specification.

### Step 3: Set the number of columns (horizontal layout)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** is the key phrase for this operation. When you increase the column count, the barcode spreads horizontally, which can be useful for wide labels. The library automatically recalculates the module width to keep the overall size consistent.

#### Pro tip
The maximum column count for Databar Expanded Stacked is 8. Setting a value higher than the limit will clamp it to the maximum, but it’s better to validate your input beforehand.

### Step 4: Save the barcode image with the column layout

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** is the action that writes the rendered barcode to disk. PNG is lossless, which preserves the sharp edges required for reliable scanning.

### Step 5: Create a second generator for the same barcode type (row layout)

If you prefer a vertical stack, you work with rows instead of columns. The code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance to avoid mixing column and row settings.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Step 6: Set the number of rows (vertical layout)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** arranges the barcode modules vertically. A three‑row layout reduces the height of each individual stack, making the barcode suitable for narrow receipts or mobile screens.

#### Edge case
If you set `rows` to 1, the library generates a single‑row Databar (equivalent to a standard Databar). Values below 1 are ignored and reset to the default (1 row).

### Step 7: Save the barcode image with the row layout

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Again, we **save barcode image** using PNG to keep the output crisp.

## Full runnable example

Putting all the pieces together gives you a self‑contained script you can drop into any Python project.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Expected output**

Running the script creates two PNG files:

* `output/ExpandedCols4.png` – a barcode stretched across four columns
* `output/ExpandedRows3.png` – a barcode compressed into three rows

Both images can be opened in any image viewer or imported directly into PDF invoices, label templates, or web pages.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| *What if the barcode looks blurry?* | Increase the image resolution by setting `barcode_generator.parameters.image_width` and `image_height` before calling `save`. |
| *Can I use other image formats?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. |
| *Is there a limit on the data length?* | Databar Expanded Stacked supports up to 74 numeric characters. Exceeding the limit raises a `ArgumentException`. |
| *How do I change the foreground color?* | Use `barcode_generator.parameters.barcode.color = Color.Blue` (import `System.Drawing.Color`). |
| *Can I combine columns and rows?* | No. The API treats columns and rows as mutually exclusive layout modes. Choose one per barcode instance. |

## Next steps

Now that you can **configure Databar barcode layout**, consider exploring these related topics:

* **Add text captions** – use `barcode_generator.parameters.barcode.code_text` to display the encoded value beneath the image.
* **Embed the barcode in a PDF** – combine the generated PNG with `aspose.pdf` to create printable documents.
* **Dynamic sizing** – calculate optimal column or row counts based on label dimensions at runtime.
* **Batch processing** – loop over a CSV of product codes to generate a library of barcode images automatically.

Experiment with different column and row values to see how they affect scan reliability on your target devices. The more you test, the better you’ll understand the trade‑offs between barcode size, readability, and space constraints.

---

*Happy coding! If you found this tutorial useful, share it with teammates or leave a comment about the layout challenges you faced.*


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}