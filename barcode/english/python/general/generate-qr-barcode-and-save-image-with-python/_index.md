---
category: general
date: 2026-11-27
description: Generate QR barcode in Python using Aspose.Barcode and learn how to save
  barcode image to disk quickly.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: en
lastmod: 2026-11-27
og_description: Generate QR barcode in Python with Aspose.Barcode and instantly save
  barcode image. Follow the complete example to create, customize, and store QR codes.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Generate QR barcode and save image with Python – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Generate QR barcode and save image with Python
url: /python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate QR barcode and save image with Python

If you need to **generate QR barcode** in a Python application, this guide shows you how to do it using the Aspose.Barcode library. You will also learn the correct way to **save barcode image** to a local folder, retrieve library version details, and handle extended codetext segments.

Creating QR codes is a common requirement for ticketing systems, mobile payments, and product tracking. By the end of this tutorial you will have a ready‑to‑run script that produces a QR barcode image file and prints version information for debugging or compliance purposes.

## Prerequisites

Before you start, make sure you have:

* Python 3.8 or newer installed.
* The `aspose-barcode` package. Install it with `pip install aspose-barcode`.
* Write permission to the directory where the barcode image will be stored.

No additional external services are required; the entire process runs locally.

## Step 1: Build an extended codetext with `ExtCodetextBuilder`

Extended codetext lets you mix plain text and ECI (Extended Channel Interpretation) segments in a single QR code. This is useful when you need to embed characters from different character sets, such as the Euro sign.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Why this step matters:**  
`ExtCodetextBuilder` assembles the final string that the QR encoder will process. Without building the extended codetext, the barcode would contain only plain ASCII characters and could not represent locale‑specific symbols.

## Step 2: Retrieve the combined extended codetext string

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

The output looks like:

```
Extended codetext: ABC123[ECI3]€123
```

The bracketed `[ECI3]` marker tells the QR encoder to switch to the specified character set for the following characters.

## Step 3: Generate the QR barcode using the extended codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Explanation:**  
`BarcodeGenerator` receives two arguments: the barcode type (`QR`) and the data to encode (`extended_codetext`). The generator prepares all internal structures needed for rendering.

## Step 4: Save the generated barcode image

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Why you should use this approach:**  
Calling `save` directly writes the image to disk using the format inferred from the file extension. The method supports PNG, JPEG, BMP, and TIFF, giving you flexibility for different downstream consumers.

### Verifying the saved image

Open the file `output/qr_extended.png` with any image viewer. You should see a QR code that, when scanned, returns the string `ABC123€123`. Most modern mobile QR scanners handle the ECI segment automatically.

## Step 5: Query Aspose.BarCode version information (optional but useful)

Knowing the exact version of the Aspose.BarCode library helps when you need to report bugs or verify compatibility.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typical output:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Full script – copy, paste, and run

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Running the script produces the QR code image and prints both the extended codetext and version details to the console.

## Common variations and edge cases

| Situation | Recommended adjustment |
|-----------|------------------------|
| **Different character set** | Change the ECI identifier passed to `add_eci_codetext`. For UTF‑8 use `5`. |
| **Higher error correction** | Set `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` before calling `save`. |
| **Custom image size** | Use `barcode.parameters.image_width` and `barcode.parameters.image_height` to control pixel dimensions. |
| **Non‑PNG output** | Change the file extension in `output_path` to `.jpg` or `.bmp`. The library automatically selects the correct encoder. |

## Pro tips

* **Create the output folder** programmatically if it may not exist:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validate the QR code** after generation by reading it back with `aspose.barcode.BarcodeReader`. This ensures the encoded data matches expectations, especially when using ECI segments.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Performance tip** – reuse a single `BarcodeGenerator` instance if you need to generate many QR codes in a loop. Reset the `code_text` property instead of creating a new object each iteration.

## Conclusion

You now know how to **generate QR barcode** in Python with Aspose.Barcode, build an extended codetext that mixes plain and ECI segments, and correctly **save barcode image** to disk. The script also shows how to retrieve library version information for troubleshooting.

Next steps you might explore include:

* Adding logo overlay or custom colors to the QR code.
* Embedding the QR barcode directly into PDFs using Aspose.PDF.
* Automating batch generation for large datasets.

Feel free to experiment with different data payloads, error‑correction levels, and image formats. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}