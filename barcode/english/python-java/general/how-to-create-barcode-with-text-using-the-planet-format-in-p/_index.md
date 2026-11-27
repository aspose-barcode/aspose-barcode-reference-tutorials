---
category: general
date: 2026-11-27
description: Learn how to create barcode with text and generate planet barcode in
  Python—step‑by‑step guide for high‑resolution PNG output.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: en
lastmod: 2026-11-27
og_description: Create barcode with text and generate planet barcode in Python. Follow
  this complete guide to output a high‑resolution PNG.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Create barcode with text in Python – generate Planet barcode easily
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: How to create barcode with text using the Planet format in Python
url: /python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode with text using the Planet format in Python

If you need to **create barcode with text** for a mailing system, this tutorial shows you exactly how to do it. You’ll see a concise, end‑to‑end example that generates a Planet barcode, adjusts the resolution, and saves the result as a PNG image.

Generating barcodes is a common requirement for logistics, inventory, and ticketing applications. In this guide you’ll learn not only **how to generate barcode** files, but also why each configuration step matters and how to avoid typical pitfalls.

## What you’ll learn

* Set up the Planet barcode generator with custom text.
* Adjust the X‑dimension to increase image sharpness.
* Save the barcode as a PNG file that can be printed or displayed on the web.
* Extend the example to other barcode types or output formats.

**Prerequisites**

* Python 3.8 or newer.
* The `aspose-barcode` package (or any compatible library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`).
* Basic familiarity with Python scripting.

You can install the required package with:

```bash
pip install aspose-barcode
```

---

## Step 1: Create barcode with text – initialize the generator

The first thing you must do is create a `BarcodeGenerator` instance that knows which symbology to use and which text to encode. For a Planet barcode the `EncodeTypes.Planet` enum value tells the library to follow the USPS Planet specification.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Why this matters:**  
The `BarcodeGenerator` object encapsulates all settings for the barcode. Supplying the text at construction time guarantees that the encoded value is immutable throughout the rest of the process, which eliminates accidental mismatches later on.

---

## Step 2: Adjust settings – how to generate barcode with higher resolution

A low‑resolution barcode can look blurry when printed on a label printer. The X‑dimension (module width) controls the size of each individual bar. Setting it to 4 pixels yields a crisp, high‑resolution image suitable for most modern printers.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Explanation:**  
* `gen.parameters.barcode.x_dimension.pixels` directly maps to the physical width of a single module.  
* A value of **4** means each bar is four pixels wide, which roughly corresponds to 0.127 mm at 300 dpi—well within the recommended range for USPS Planet barcodes.  

**Pro tip:** If you need a different DPI, calculate the pixel width accordingly (e.g., 2 pixels for 150 dpi, 8 pixels for 600 dpi).

---

## Step 3: Save the image – generate planet barcode as PNG

Now that the generator is configured, you can render the barcode to an image file. PNG is loss‑less, ensuring that the exact module pattern is preserved.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Result:**  
Running the script creates a file named `PostalPlanetBarHeightNone.png` that contains a Planet barcode encoding the string “123456”. The image dimensions will be approximately 200 × 100 pixels, depending on the X‑dimension you chose.

---

## Optional: Verify the barcode visually

You can quickly open the generated PNG with any image viewer to confirm that the barcode looks sharp and the human‑readable text is present beneath the pattern.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

If the image appears fuzzy, revisit **Step 2** and increase the X‑dimension until the bars are clearly defined.

---

## Common variations and edge cases

| Situation | Adjustment |
|-----------|------------|
| **Different text length** | Planet barcodes support up to 12 numeric characters. If you exceed this, the library will raise an exception. |
| **Alternative output format** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp` for other use‑cases. |
| **Custom foreground/background colors** | Use `gen.parameters.barcode.barcode_color = Color.Blue` and `gen.parameters.barcode.back_color = Color.White`. |
| **No human‑readable text** | Set `gen.parameters.barcode.hide_code_text = True` to generate a barcode without the bottom caption. |
| **Batch generation** | Loop over a list of strings, create a new `BarcodeGenerator` for each, and save them to uniquely named files. |

These variations let you **generate planet barcode** files that fit a wide range of business requirements.

---

## Full script – ready to run

Below is the complete, self‑contained script that you can copy, paste, and execute. It includes all imports, error handling, and comments.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Explanation of the script**

* The `create_planet_barcode` function encapsulates the three core steps, making the code reusable.
* Input validation ensures you’re following the Planet specification (numeric only, max 12 digits).
* The function creates the output folder automatically, so you don’t need to manage directories manually.
* After generation, the script opens the image using Pillow (`PIL`) for immediate verification.

---

## Conclusion

You now know how to **create barcode with text** and **generate planet barcode** files in Python. The guide covered initialization, resolution tuning, and file output, along with optional customizations and common edge cases.  

From here you can:

* Replace `EncodeTypes.Planet` with other symbologies (e.g., `EncodeTypes.Code128`) to reuse the same pattern.
* Integrate the function into a web service that returns barcode images on demand.
* Experiment with batch processing to produce thousands of barcodes for bulk mailing.

Feel free to adapt the script to your project’s needs and share your results in the comments. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}