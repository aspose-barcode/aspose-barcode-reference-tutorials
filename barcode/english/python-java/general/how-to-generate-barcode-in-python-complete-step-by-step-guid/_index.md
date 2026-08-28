---
category: general
date: 2026-08-12
description: How to generate barcode quickly using Python. Learn to create barcode
  from data and export barcode image with a single library.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: en
lastmod: 2026-08-12
og_description: How to generate barcode in Python with Aspose.BarCode. Follow this
  guide to create barcode from data and export barcode image as PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: How to generate barcode in Python – fast, reliable guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: How to generate barcode in Python – complete step‑by‑step guide
url: /python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode in Python – complete step‑by‑step guide

If you need to **how to generate barcode** in a Python application, this tutorial shows you the exact code you need. You’ll learn to **create barcode from data**, adjust its appearance, and **export barcode image** as a PNG file—all in under ten lines of code.

Generating a barcode can feel like a separate concern from the rest of your business logic, but with a single library you can keep the process inline with your existing code base. In the sections that follow you’ll see a full, runnable example, understand why each line matters, and discover common variations such as changing the module width or drawing an outline‑only barcode.

## How to generate barcode with the Aspose.BarCode library

The Aspose.BarCode library for Python (via .NET) provides a straightforward API for many symbologies, including the Planet barcode used in this guide. Before you start, make sure you have the package installed:

```bash
pip install aspose-barcode
```

> **Pro tip:** Use a virtual environment to avoid version conflicts with other projects.

### 1. Import the required classes

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

These imports give you access to the generator class, the enumeration of barcode types, and the image format enum used when saving the result.

### 2. Create barcode from data

The first step is to **create barcode from data**. The `BarcodeGenerator` constructor takes the symbology and the raw string you want to encode.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

The `EncodeTypes.Planet` value selects the Planet barcode, while `"123456"` is the payload that will appear in the final image.

### 3. Adjust the X‑dimension (module width)

The X‑dimension controls the width of each barcode module (the thin bar). Setting it to 4 pixels gives a clear, readable image without making the file too large.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Why this matters:** A larger X‑dimension improves scan reliability on low‑resolution printers, while a smaller value reduces file size for web use.

### 4. Export barcode image (filled style)

Now you can **export barcode image** using the `save` method. The example saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat` enum.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

The file `PlanetFilled.png` contains a fully filled Planet barcode, ready for printing or embedding in a PDF.

### 5. Create a second generator for an outline‑only barcode

If you need an outline version (empty bars), you must create a new generator because the `filled_bars` flag cannot be toggled after the image is saved.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Apply the same X‑dimension setting

When you create a second generator, you must repeat any visual settings you want to keep consistent.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Disable filled bars for an outline barcode

Setting `filled_bars` to `False` tells the renderer to draw only the outlines of each module, producing a lighter image that can be useful for design purposes.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Export the outline barcode image

Finally, **export barcode image** again, this time storing the outline version.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

You now have two PNG files: one with solid bars (`PlanetFilled.png`) and one with only outlines (`PlanetEmpty.png`).

## Export barcode image in other formats (optional)

The `save` method supports several formats. To export as JPEG with 90 % quality:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

If you need a transparent background for web use, choose PNG with an alpha channel:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Common variations and edge cases

| Scenario | Change needed | Code snippet |
|----------|---------------|--------------|
| **Different symbology** (e.g., QR) | Use a different `EncodeTypes` value | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Custom foreground color** | Set `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Higher resolution** | Increase DPI via `image_width` and `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Large data strings** | Ensure data length fits the symbology spec | Validate length before creating the generator |

> **Watch out for:** Supplying data that exceeds the maximum length for the chosen symbology raises a runtime exception. Always validate the string length or catch `ArgumentException`.

## Full, runnable example

Below is the complete script that you can copy‑paste into a file named `generate_planet_barcode.py`. Adjust `YOUR_DIRECTORY` to a folder that exists on your machine.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

Running this script produces two PNG files in the specified directory. Verify the output by opening the images in any image viewer; both should display a Planet barcode encoding the string `123456`.

## Conclusion

You now know **how to generate barcode** in Python using Aspose.BarCode, how to **create barcode from data**, and how to **export barcode image** in both filled and outline styles. The same pattern applies to other symbologies, image formats, and visual customizations, giving you a flexible foundation for any barcode‑related feature in your application.

### Next steps

* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping `EncodeTypes.Planet` with the desired value.  
* Integrate the generated PNG files into PDF reports using libraries like `ReportLab` or `PyPDF2`.  
* Experiment with dynamic X‑dimension values to adapt barcode size based on screen resolution or printer DPI.

Happy coding, and feel free to adapt the example to fit your own project requirements!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}