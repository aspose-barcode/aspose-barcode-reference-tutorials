---
category: general
date: 2026-08-12
description: Create omni directional databar with Python and learn how to create barcode
  image python using Aspose.BarCode. Follow the step‑by‑step guide for a complete
  solution.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: en
lastmod: 2026-08-12
og_description: Create omni directional databar with Python and generate a barcode
  image python in minutes. This tutorial shows a complete, runnable example.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Create omni directional databar – full Python guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Create omni directional databar and barcode image in Python
url: /python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create omni directional databar and barcode image in Python

If you need to **create omni directional databar** in a Python project, this guide shows you how to do it and also how to **create barcode image python** using the Aspose.BarCode library. You will get a ready‑to‑run script that produces two PNG files with different aspect ratios.

Generating a DataBar that follows the Omni‑directional specification is a common requirement for retail and logistics applications. The tutorial covers installation, configuration of the X‑dimension, adjustment of the aspect ratio, and saving the final images. No external services are required; everything runs locally.

## What you will need

Before you start, make sure you have:

* Python 3.8 or newer installed on your machine.
* Access to a terminal or command prompt.
* Write permission to a folder where the barcode images will be saved.

The only third‑party dependency is **Aspose.BarCode for Python via .NET**, which supports the Omni‑directional DataBar type out of the box.

## Step 1: Install Aspose.BarCode for Python

Aspose.BarCode provides the `BarcodeGenerator` class used in the example code. Install the package with `pip`:

```bash
pip install aspose-barcode
```

The package includes the necessary .NET runtime bindings, so you do not need to install the .NET SDK separately.

## Step 2: Import the library and create the generator

The first line of the script creates a generator for a stacked Omni‑directional DataBar. The GTIN‑14 value `(01)12345678901231` is used as sample data.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Why this step matters*: The `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` constant tells the library to encode the value as an Omni‑directional DataBar, which is the format required by many point‑of‑sale scanners.

## Step 3: Set the X‑dimension (module width)

The X‑dimension defines the width of the smallest bar module. A value of `2` pixels produces a clear, readable barcode without excessive file size.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Why this step matters*: Adjusting the X‑dimension allows you to balance readability and image dimensions. An X‑dimension that is too small may render poorly on low‑resolution printers.

## Step 4: Configure the aspect ratio and save the first image

The aspect ratio influences the overall height of the DataBar relative to its width. An aspect ratio of `15` creates a compact visual style.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tip**: Use `pathlib.Path` to build the output path, which automatically creates missing directories.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Step 5: Change the aspect ratio for a second visual style and save another image

Switching the aspect ratio to `30` produces a taller barcode that may be required by specific scanner hardware.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Why this step matters*: Different retailers and scanning devices have distinct size constraints. Providing both aspect ratios in a single script lets you generate the exact style you need without duplicating code.

## Full script – create omni directional databar and barcode image python

Below is the complete, runnable example that incorporates all previous steps. Save it as `generate_databar.py` and run it with `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Expected output

Running the script creates the following files:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Both images display a valid Omni‑directional DataBar that can be scanned by standard retail equipment.

![example of create omni directional databar barcode image in Python](example_databar.png "create omni directional databar barcode image python")

*The image above is a placeholder that illustrates the two saved PNG files.*

## Handling common issues

| Issue | Reason | Fix |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode not installed or installed in a different environment. | Activate the correct virtual environment and run `pip install aspose-barcode`. |
| `PermissionError` when saving | The script lacks write permission for the target folder. | Choose a directory you own or run the script with appropriate privileges. |
| Barcode does not scan | X‑dimension too low or aspect ratio incompatible with the scanner. | Increase `x_dimension.pixels` to 3 or 4, and test different `aspect_ratio` values (e.g., 20, 25). |
| Missing .NET runtime | Aspose.BarCode depends on the .NET runtime on Windows/Linux. | Install the latest .NET runtime from Microsoft’s site; the package documentation provides platform‑specific guidance. |

## Extending the example

You can adapt the script to generate other DataBar variants (e.g., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Replace the `EncodeTypes` constant accordingly:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

If you need to embed the barcode in a PDF, Aspose.PDF for Python can import the PNG file directly or you can use the `save` method with `BarCodeImageFormat.Pdf`.

## Conclusion

This tutorial showed how to **create omni directional databar** and how to **create barcode image python** using Aspose.BarCode. You now have a complete, reproducible script that generates two PNG files with different aspect ratios, handles common pitfalls, and can be extended to other barcode formats.

Next, explore generating QR codes, adding the barcode to PDF invoices, or automating batch processing for large product catalogs. Each of those topics builds on the same `BarcodeGenerator` pattern demonstrated here. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}