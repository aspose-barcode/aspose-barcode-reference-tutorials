---
category: general
date: 2026-07-30
description: How to generate barcode using Aspose.BarCode in Python – learn how to
  set dimensions, change fill, and save PNG images in minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: en
lastmod: 2026-07-30
og_description: How to generate barcode quickly with Aspose.BarCode in Python. Discover
  how to set dimensions, change fill, and export PNG files for any app.
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: How to generate barcode with Aspose.BarCode – Python guide
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: How to generate barcode with Aspose.BarCode in Python
url: /python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode with Aspose.BarCode in Python

Ever wondered **how to generate barcode** in a Python project without wrestling with low‑level image libraries? You're not the only one. Whether you're building a shipping label system, a ticketing platform, or just need a quick QR code for a demo, mastering barcode generation can save you hours of trial‑and‑error.

In this tutorial we’ll walk through a complete, ready‑to‑run example that shows **how to generate barcode** using the Aspose.BarCode library, how to set dimensions, and how to change fill. By the end you’ll have two PNG files—one with filled bars and one with empty bars—right in your output folder.

## Prerequisites

Before we dive in, make sure you have:

* Python 3.8+ installed (the code works on Windows, macOS, and Linux)
* An active Aspose.BarCode for Python via .NET license (you can start with a free trial)
* `pip install aspose-barcode` executed in your virtual environment
* A folder you can write to – we’ll call it `YOUR_DIRECTORY` in the examples

No other third‑party packages are required.

## Step 1: Install and import Aspose.BarCode

First things first: we need the library itself. Run this once in your terminal:

```bash
pip install aspose-barcode
```

Now we can import the classes we’ll be using. This is the part where **how to generate barcode** really begins, because without the right imports you can’t even call the generator.

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **Pro tip:** If you’re using a virtual environment, activate it before running `pip install`. It keeps your global Python tidy.

## Step 2: Create a Planet barcode – the default (filled) version

The Planet barcode is a classic 2‑of‑5 symbology used by postal services. Let’s start with the simplest case: a filled barcode. This step demonstrates **how to generate barcode** with default settings.

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### Why set `x_dimension.pixels`?

Even though the default works, you often need to **how to set dimensions** to match printer DPI or UI constraints. The `x_dimension` property controls the width of a single bar in pixels; larger numbers yield a thicker barcode, while smaller numbers make it more compact.

## Step 3: Create a Planet barcode with empty (unfilled) bars

Now let’s answer the question **how to change fill**. By toggling the `filled_bars` flag we can switch from a solid black bar to a hollow bar that still encodes the same data.

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

When you open `PostalPlanetFilled.png` and `PostalPlanetEmpty.png` side by side, you’ll see the visual difference: the filled version is solid black, while the empty version shows bars as outlines. This is handy when you need a lighter visual weight for UI overlays.

## Step 4: Full, runnable script (the complete solution)

Below is the entire program you can copy‑paste into a file named `generate_planet_barcodes.py`. It includes everything from imports to saving the images, so you won’t have to hunt for missing pieces.

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### Expected output

Running the script prints something like:

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

Open the two PNG files with any image viewer; you should see a classic Planet barcode—one solid, one hollow. Both encode the string `123456`.

## Step 5: Tweaking dimensions for different use‑cases

Now that you know **how to set dimensions**, let’s explore a couple of common scenarios.

### 5.1 Making the barcode larger for print

If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look tiny. Increase the `x_dimension` to, say, 8 pixels:

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 Making the barcode smaller for mobile screens

Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension` to 2 pixels reduces the width without breaking readability (Aspose handles the scaling automatically).

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

Remember, the height of the barcode is automatically adjusted based on the symbology’s specifications, so you only need to worry about the width.

## Step 6: Advanced fill options and why you might need them

Beyond the simple `filled_bars` Boolean, Aspose.BarCode lets you customize bar colors, background colors, and even add gradients. If you ever need to **how to change fill** beyond just “filled vs empty,” you can do something like:

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*(Note: The above uses .NET color structs; in pure Python you’d use the appropriate Aspose enum.)* This is handy for branding—imagine a company logo subtly embedded in the background of a barcode.

## Common pitfalls and how to avoid them

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Barcode looks blurry in the saved PNG | `x_dimension` too low for the target DPI | Increase `x_dimension` or upscale the image after saving |
| Scanner refuses to read the empty barcode | `filled_bars = False` not supported by some legacy scanners | Stick with the default filled version for maximum compatibility |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode not installed or mismatched .NET runtime | Re‑install with `pip install aspose-barcode` and ensure .NET Core runtime is present |

## Recap: What we covered

* **How to generate barcode** with Aspose.BarCode in Python
* **How to set dimensions** using `x_dimension.pixels`
* **How to change fill** via the `filled_bars` flag (and a glimpse at color customization)
* A complete, copy‑paste‑ready script that you can adapt for any data string

## What’s next? (Next steps and related topics)

If you found this guide useful, consider exploring:

* **Generating QR codes** (`EncodeTypes.QR`) – perfect for URLs and contact info.
* **Adding text captions** below the barcode (`parameters.caption`) for human‑readable values.
* **Exporting to other formats** like SVG or PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) – great for vector graphics.
* **Batch generation** – loop over a CSV of product IDs to create a whole catalog of barcodes in one go.

All of those topics also tie back to our secondary keywords: *generate barcode with aspose* and *how to set dimensions* for different output formats.

---

Feel free to drop a comment if you hit any snags, or share your own variations. Happy barcode crafting!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to Colorize Barcode Images in Java with Aspose.BarCode](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}