---
category: general
date: 2026-09-23
description: Learn how to generate Code 128 barcode and save barcode image using Aspose.BarCode
  in Python – step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: en
lastmod: 2026-09-23
og_description: Generate Code 128 barcode and save barcode image with Aspose.BarCode
  in Python. Follow this complete example to create, customize, and export the barcode
  as a PNG file.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Generate Code 128 barcode and save barcode image – Python guide
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
url: /python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate Code 128 barcode and save barcode image with Aspose.BarCode

If you need to **generate Code 128 barcode** and **save barcode image** in a Python project, this tutorial shows the exact steps. Using Aspose.BarCode’s `ExtCodetextBuilder` you can embed plain text and Unicode segments in a single payload, then render the result as a PNG file.

You’ll see a complete, runnable script, an explanation of each line, and tips for common pitfalls such as handling ECI encoding or choosing the correct output folder. No external documentation is required—just copy, paste, and run.

## Prerequisites

Before you start, make sure you have:

* Python 3.8+ installed.
* The `aspose.barcode` package (install with `pip install aspose-barcode`).
* Write permission to the directory where the PNG will be saved.

The code works with any symbology supported by Aspose.BarCode, but the example focuses on **Code 128** because it efficiently encodes alphanumeric data and supports extended character sets.

## Step 1: Import the required classes

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Why this step?* Importing the classes gives you access to the builder for extended codetext, the writer that creates the image, and the version helper that can be useful for debugging library updates.

## Step 2: Build the extended codetext

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

The `ExtCodetextBuilder` lets you mix plain ASCII and Unicode data in a single barcode payload. The ECI (Extended Channel Interpretation) byte `0x03` tells the scanner that the following bytes are UTF‑8 encoded, which is essential for languages like Russian, Chinese, or Arabic.

## Step 3: Configure the barcode writer for Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Setting `encode_type` to `CODE_128` instructs the writer to render a **Code 128 barcode**. The `code_text` property receives the extended string built in the previous step.

## Step 4: Save the barcode image as PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

The `save` method writes the barcode to a file. Using `BarCodeImageFormat.PNG` ensures loss‑less compression and broad compatibility with web and mobile applications.

## Step 5 (optional): Verify the Aspose.BarCode library version

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Knowing the exact library version helps when you need to report bugs or compare behavior across releases.

## Expected output

Running the script produces console output similar to:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

The generated PNG (`extended_codetext.png`) looks like this:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*The image shows a Code 128 barcode that encodes both the ASCII string `ABC123` and the Russian word “Пример”.*

## Common questions and edge‑case handling

| Question | Answer |
|----------|--------|
| **Can I use a different symbology?** | Yes. Replace `BarCodeEncodeMode.CODE_128` with any other supported mode such as `QR`, `EAN_13`, or `PDF_417`. |
| **What if my Unicode text contains emojis?** | Emojis are also UTF‑8 characters, so the same `add_eci_codetext` call works. Ensure the target scanner supports the ECI you use. |
| **How do I change the image size?** | Set `writer.x_dimension` and `writer.bar_height` before calling `save`. |
| **What folder should I use for `output_path`?** | Any folder that the Python process can write to. Use `os.makedirs` with `exist_ok=True` to create it automatically. |

## Pro tips

* **Avoid hard‑coding paths.** Use `os.path.join` and `Path` from the `pathlib` module for cross‑platform compatibility.
* **Validate the barcode.** After saving, you can read the image back with `barcode.BarCodeReader` to confirm that the encoded text matches `extended_codetext`.
* **Performance tip.** If you generate many barcodes in a loop, reuse a single `BarCodeWriter` instance and only update `code_text` each iteration.

## Conclusion

You now know how to **generate Code 128 barcode** with mixed ASCII and Unicode data and **save barcode image** as a PNG using Aspose.BarCode in Python. The complete script covers building extended codetext, configuring the writer, exporting the image, and checking library versions.

From here you can explore:

* Adding foreground/background colors (`writer.back_color`, `writer.fore_color`).
* Embedding the barcode in PDFs with `Aspose.PDF`.
* Using the `BarCodeReader` class to decode the saved image and verify content automatically.

Happy coding, and feel free to experiment with other symbologies and image formats!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}