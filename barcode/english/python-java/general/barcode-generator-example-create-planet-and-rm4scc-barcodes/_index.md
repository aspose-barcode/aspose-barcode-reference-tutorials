---
category: general
date: 2026-10-24
description: Barcode generator example that shows how to create Planet barcode and
  how to set barcode height using Python. Follow the step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: en
lastmod: 2026-10-24
og_description: Barcode generator example that demonstrates how to create Planet barcode
  and how to set barcode height in Python. Get a complete, runnable solution.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Barcode generator example – create Planet and RM4SCC barcodes
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Barcode generator example – create Planet and RM4SCC barcodes with custom height
url: /python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator example – create Planet and RM4SCC barcodes with custom height

If you are looking for a **barcode generator example**, this guide gives you a complete, ready‑to‑run solution. You will see **how to create planet barcode** images, learn **how to set barcode height**, and understand the small differences between automatic and manual sizing.

The tutorial walks through two realistic scenarios: a Planet barcode that uses the default (auto) height, and an RM4SCC barcode where the height is forced to 100 px. By the end you can generate PNG files for any supported barcode type with a single, consistent API.

## Prerequisites

Before you start, make sure you have:

* Python 3.8 or newer installed.
* The `aspose-barcode` package (or any library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`). Install it with  

  ```bash
  pip install aspose-barcode
  ```
* Write permission to a folder where the PNG files will be saved.

No additional system dependencies are required.

## Overview of the solution

The core of the **barcode generator example** consists of three reusable steps:

1. **Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value and the data string.
2. **Configure** the X‑dimension (module width) and, when needed, the barcode height.
3. **Save** the image to disk in PNG format.

Both examples share steps 1 and 3; only step 2 differs because the Planet barcode relies on the library’s automatic height calculation, while the RM4SCC barcode demonstrates **how to set barcode height** manually.

Below is a high‑level diagram that illustrates the flow:

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Alt text: Barcode generator example showing Planet and RM4SCC barcodes with different heights.*

## How to create planet barcode – automatic height

The Planet barcode is part of the postal family used by many national postal services. In most cases you let the SDK decide the height, which keeps the visual proportions correct for varying data lengths.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Why this works**

* `EncodeTypes.Planet` tells the library to use the Planet symbology.
* Setting `x_dimension.pixels` to 4 gives each module a width of 4 px, which is a common default for printed labels.
* No explicit height is set; the SDK calculates the optimal height based on the data and the X‑dimension, which is why this is the simplest **barcode generator example** for postal codes.

**Expected result**

A 2‑D PNG file named `PostalPlanetBarHeightAuto.png` that contains a crisp Planet barcode. The height will be around 30 px (depending on the library version) and the width will be 4 px × number of modules.

## How to set barcode height – custom RM4SCC example

RM4SCC is another postal barcode that often requires a fixed height to match label templates. This part of the tutorial shows **how to set barcode height** to an exact pixel count.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Why this works**

* `EncodeTypes.RM4SCC` selects the RM4SCC symbology.
* The X‑dimension remains at 4 px to keep the module size consistent across both barcodes.
* `bar_height.pixels = 100` forces the barcode to be exactly 100 px tall, overriding the automatic calculation. This is the recommended way **how to set barcode height** when your layout demands a specific size.

**Expected result**

A PNG file named `PostalRM4SCCBarHeight100Pixels.png` that displays a tall RM4SCC barcode. The width is still driven by the X‑dimension, while the height is fixed at 100 px, making it suitable for high‑resolution label printers.

## Full script – combine both examples

If you prefer a single script that generates both images, copy the following code into `generate_barcodes.py` and run it.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explanation of the script**

* Two helper functions keep the code DRY (Don’t Repeat Yourself) and make it easy to extend the script for other symbologies.
* The `if __name__ == "__main__":` guard allows the file to be imported as a module without executing the generation logic, which is useful for unit testing.
* All parameters (data string, X‑dimension, height) are explicit, so the script serves as a reference **barcode generator example** for future projects.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| *What if I need a different X‑dimension?* | Change `x_dimension.pixels` to the desired module width. Larger values increase overall barcode size proportionally. |
| *Can I generate other image formats?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpg`, `Bmp`, or `Gif` depending on the library’s enum. |
| *What happens if the data string contains invalid characters?* | The generator throws an `ArgumentException`. Validate the data against the symbology’s character set before calling the constructor. |
| *Is it possible to set a minimum height while keeping auto‑scaling?* | Use `gen.parameters.barcode.bar_height.min_pixels = <value>` (if the SDK exposes a `min_pixels` property). This keeps the barcode from shrinking below a readable size. |
| *Do I need to dispose of the generator?* | The `BarcodeGenerator` class implements `IDisposable` in .NET; in Python the garbage collector handles it, but you can call `gen.dispose()` if you create many instances in a loop. |

## Tips for production use

* **Pro tip:** Store the X‑dimension and height values in a configuration file so you can adjust them without recompiling.
* **Watch out for:** Using a height that is too small for the selected symbology; scanners may fail to read the barcode.
* **Performance note:** Generating a large batch of barcodes is faster when you reuse a single `BarcodeGenerator` instance and only change its `code_text` property between saves.

## Conclusion

This **barcode generator example** demonstrates both **how to create planet barcode** images with automatic sizing and **how to set barcode height** manually for RM4SCC codes. By following the step‑by‑step guide you can integrate barcode creation into any Python application, customize dimensions, and produce PNG files ready for printing or digital display.

### Next steps

* Explore additional symbologies such as `EncodeTypes.Postnet` or `EncodeTypes.Code128` – the same pattern applies.
* Experiment with **how to set barcode height** for QR codes or DataMatrix symbols; most libraries expose a similar `bar_height` property.
* Combine the generator with a PDF library to embed barcodes directly into invoices or shipping labels.

Feel free to adapt the script, share your results, and let us know which barcode types you add next!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}