---
category: general
date: 2026-08-22
description: Learn to generate DataMatrix barcode in Python and encode Russian text
  using Aspose.BarCode – step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: en
lastmod: 2026-08-22
og_description: Generate DataMatrix barcode in Python and encode Russian text with
  Aspose.BarCode. Follow the full example and run it instantly.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Generate DataMatrix barcode in Python – complete Aspose.BarCode tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: How to generate DataMatrix barcode in Python with Aspose.BarCode
url: /python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate DataMatrix barcode in Python with Aspose.BarCode

If you need to **generate DataMatrix barcode** in Python while **encoding Russian text**, this guide shows you the exact steps. You’ll see a complete, runnable example that builds an extended codetext, configures the barcode, and saves the image in a single script.

Creating barcodes that contain non‑ASCII characters often raises questions about character sets and data encoding. By using Aspose.BarCode’s `ExtCodetextBuilder`, you can safely embed UTF‑8 text such as Cyrillic characters inside a DataMatrix symbol. The result works with any scanner that supports the DataMatrix standard.

In this tutorial you will:

* Install the required Aspose.BarCode package.
* Build an extended codetext that mixes plain data and Russian text.
* **Generate DataMatrix barcode** with the extended string.
* Adjust barcode parameters like module size.
* Save the barcode as a PNG file.

No external services are required; everything runs locally on your machine.

## Prerequisites

Before you start, make sure you have:

* Python 3.8 or newer installed.
* An active Aspose.BarCode for Python license (a free trial works for development).
* Basic familiarity with Python scripting.

You can install the Aspose.BarCode library via pip:

```bash
pip install aspose-barcode
```

## Step 1: Build an extended codetext string

The first task is to create a single string that contains both the plain product identifier and the Russian phrase. `ExtCodetextBuilder` lets you concatenate different codetext parts while preserving their encoding information.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Why this step matters** – DataMatrix symbols store raw bytes. When you need to mix alphabets, you must tell the encoder which character set applies to each segment. The `add_eci_codetext` method inserts an ECI indicator before the Russian text, ensuring that scanners interpret the bytes as UTF‑8. Without ECI, the Cyrillic characters would appear as garbled data.

## Step 2: Create a DataMatrix barcode generator

With the extended codetext ready, instantiate a `BarcodeGenerator` specifying the `EncodeTypes.DATA_MATRIX` type.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Why DataMatrix?** – DataMatrix is a two‑dimensional barcode that can store up to 2,335 alphanumeric characters or 1,556 bytes. It’s ideal for small items, industrial parts, and situations where you need to embed multilingual text.

## Step 3: (Optional) Configure barcode parameters

Aspose.BarCode exposes many parameters. For most use cases, the default settings produce a readable symbol. However, you may want to control the size of each module (the smallest square in the matrix) to match printing requirements.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Other useful parameters include error correction level, margin, and background color. Adjust them only if your target scanning environment demands specific tolerances.

## Step 4: Save the barcode image

Finally, write the barcode to a file. The `save` method supports PNG, JPEG, BMP, and several vector formats.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

When you open `extended_codetext.png`, you’ll see a crisp DataMatrix symbol. Scanning it with a standard DataMatrix reader returns the two parts:

1. **ABC123** – the plain identifier.
2. **Привет** – the Russian greeting, correctly decoded as UTF‑8.

## Full, runnable example

Below is the complete script you can copy‑paste into a file named `generate_datamatrix.py`. Replace `YOUR_DIRECTORY` with an existing folder on your system.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Run the script from the command line:

```bash
python generate_datamatrix.py
```

You should see console output similar to:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Verifying the result

To confirm that the barcode correctly encodes the Russian phrase:

1. Open the PNG file in an image viewer.
2. Use any DataMatrix scanning app (many mobile apps support it) or a hardware scanner.
3. The decoded string should display `ABC123Привет` (or the two parts separated depending on the scanner UI).

If the Russian characters appear as gibberish, double‑check that the scanner supports ECI UTF‑8. Most modern readers do, but legacy devices may need explicit configuration.

## Common pitfalls and how to avoid them

| Issue | Cause | Fix |
|-------|-------|-----|
| Garbled Cyrillic output | Missing ECI indicator | Use `add_eci_codetext` with `eci_encoding=3`. |
| Barcode too small for printer | Default module size too fine for low DPI | Increase `x_dimension` (e.g., `3.0` or `4.0`). |
| File not saved | Invalid directory path | Ensure `YOUR_DIRECTORY` exists and is writable. |
| Scanner cannot read | Excessive data density | Reduce the amount of encoded data or increase error correction level (`generator.parameters.barcode.error_correction_level`). |

## Extending the example

You can adapt this pattern for other languages or data types:

* **Encode Japanese or Arabic text** – change `eci_encoding` to the appropriate value (e.g., 5 for ISO‑8859‑5, 6 for ISO‑8859‑7).  
* **Add multiple ECI segments** – call `add_eci_codetext` multiple times, each with its own encoding.  
* **Create a QR code instead** – replace `EncodeTypes.DATA_MATRIX` with `EncodeTypes.QR`.  

All other steps remain identical because the `ExtCodetextBuilder` abstracts the low‑level byte handling.

## Conclusion

You now know how to **generate DataMatrix barcode** in Python and **encode Russian text** using Aspose.BarCode’s extended codetext feature. The complete script handles character‑set negotiation, barcode creation, and image output with just a few lines of code.

Next, explore other barcode symbologies (PDF417, Aztec) or integrate the generator into a web service that returns PNG images on demand. The same principles—building an extended codetext and selecting the appropriate `EncodeTypes`—apply across the entire Aspose.BarCode suite.

Happy coding, and enjoy the power of multilingual barcode generation!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}