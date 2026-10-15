---
category: general
date: 2026-10-15
description: Create barcode from string with Aspose.Barcode for Python. Learn how
  to generate barcode, set dimensions, and save as PNG in minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: en
lastmod: 2026-10-15
og_description: Create barcode from string with Aspose.Barcode for Python. This tutorial
  shows you step‑by‑step how to generate a postal barcode and save it as PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Create barcode from string in Python – Aspose guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: How to create barcode from string in Python using Aspose
url: /python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode from string in Python using Aspose

If you need to **create barcode from string** quickly, Aspose.Barcode for Python makes it straightforward. In this guide you’ll see exactly **how to generate barcode** images, adjust the X‑dimension, and save the result as a PNG file—all with just a few lines of code.

You’ll also get a complete **barcode generator example** that you can copy‑paste into your own project. No external scripts or complex configuration are required, and the tutorial works with the current Aspose.Barcode 23.10 release.

## Prerequisites

Before you start, make sure you have:

- Python 3.8+ installed on your machine  
- An active Aspose.Barcode for Python license (the free trial works for evaluation)  
- `pip install aspose-barcode` executed in your virtual environment  

These items ensure the code runs without import errors.

## Create barcode from string with Aspose.Barcode (Python)

The first step is to instantiate the `BarcodeGenerator` with the desired symbology—in this case the **Planet** postal barcode—and the string you want to encode.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Why this matters:**  
`EncodeTypes.Planet` tells Aspose to use the Planet postal symbology, which is designed for mail sorting in many countries. The second argument (`"123456"`) is the raw string that will be encoded into the barcode. Changing this value lets you **create barcode from string** for any postal code or tracking number you need.

## How to generate barcode with custom dimensions

A postal barcode’s module width (the X‑dimension) often needs to match printing specifications. Aspose lets you set the width in pixels while automatically calculating the height.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Why you might adjust this:**  
A larger X‑dimension makes the bars thicker, which can improve scan reliability on low‑resolution printers. Conversely, a smaller value reduces image size for web use. This line demonstrates **how to generate barcode** images that meet exact size requirements.

## Save the barcode image

After configuring the generator, you simply call `save`. The method accepts the output path and the image format you want.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**What you get:**  
A PNG file named `PostalPlanetAuto.png` containing the Planet barcode that encodes `"123456"`. You can open the file in any image viewer to verify the result.

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="Screenshot of a generated postal barcode saved as PNG"}

## Full barcode generator example

Below is the complete, ready‑to‑run script that includes all the steps above. Copy it into a file called `generate_postal_barcode.py` and execute `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Expected output

Running the script produces:

```
Barcode saved to PostalPlanetAuto.png
```

…and creates a file `PostalPlanetAuto.png` that looks like this:

![Generated Planet barcode](barcode_example.png){.align-center alt="Generated Planet barcode saved as PNG"}

## Common variations and edge cases

| Situation | What to change | Why |
|-----------|----------------|-----|
| **Different symbology** (e.g., Code128) | Replace `EncodeTypes.Planet` with `EncodeTypes.Code128` | Allows you to **generate barcode** for inventory tags, not just postal codes. |
| **Longer data strings** | Ensure the chosen symbology supports the length; for Planet you must keep 6 digits. | Prevents runtime `ValueError`. |
| **Higher resolution** | Increase `x_dimension.pixels` to 6 or 8. | Produces thicker bars for high‑DPI printing. |
| **Other image formats** | Use `BarCodeImageFormat.JPEG` or `BarCodeImageFormat.GIF`. | Useful when PNG is not suitable for your workflow. |
| **Running in a web service** | Replace the file‑system `save` call with a `BytesIO` stream and return the bytes. | Enables on‑the‑fly barcode generation in Flask or Django. |

**Pro tip:** Always validate the input string before calling `BarcodeGenerator`. Invalid data (wrong length, non‑numeric characters for Planet) will raise an exception and break your application.

## How to generate barcode in a Flask endpoint (optional next step)

If you want to expose the **barcode generator example** as a REST API, you can wrap the `create_postal_barcode` function:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

This snippet shows how to **generate barcode** on demand without writing to disk, which is handy for micro‑services.

## Conclusion

You now know how to **create barcode from string** in Python using Aspose.Barcode, how to **generate barcode** with custom dimensions, and how to **save** the result as a PNG file. The full **barcode generator example** includes input validation, error handling, and a reusable function you can integrate into larger applications.

Next, explore other symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) or embed the generator in a web framework like Flask or Django. Both steps will deepen your understanding of the **aspose barcode python** library and expand the ways you can **generate postal barcode** images for real‑world projects.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}