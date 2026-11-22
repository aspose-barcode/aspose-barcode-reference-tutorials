---
category: general
date: 2026-11-20
description: Learn how to use ECI, generate QR from text, clear the builder, and save
  QR image using the Python barcode library.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: en
lastmod: 2026-11-20
og_description: How to use ECI to generate QR from text, clear the QR builder, and
  save QR image – a complete step‑by‑step guide.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: How to use ECI in QR code generation with Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: How to use ECI in QR code generation with Python
url: /python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use ECI in QR code generation with Python

If you need to **how to use eci** when creating QR codes, this guide shows the exact steps. You’ll see how to generate QR from text, clear the builder, and finally save QR image—all with a few lines of Python.

QR codes that contain multilingual data often require an Extended Channel Interpretation (ECI) segment so scanners know which character set to apply. This tutorial walks you through building an extended codetext, clearing the builder when re‑using it, and persisting the result as a PNG file.

## Prerequisites

Before you start, make sure you have:

- Python 3.8+ installed.
- The Aspose.BarCode for Python via .NET package (or any compatible `barcode` library that provides `ExtCodetextBuilder` and `BarcodeGenerator`).
- Basic familiarity with QR code concepts.

Install the library with pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Use a virtual environment to avoid version conflicts.

## Step 1: Import the required classes

The primary classes you’ll work with are `ExtCodetextBuilder` for constructing extended codetext and `BarcodeGenerator` for rendering the QR code.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

These imports give you access to the builder methods (`add_plain_codetext`, `add_eci_codetext`, etc.) and the generator’s `set_code_text`, `set_symbology`, and `save` functions.

## Step 2: Create and configure the ExtCodetextBuilder

Creating a new builder instance is the first concrete example of **how to use eci**. You can also clear the builder later if you need to reuse it.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Calling `clear()` ensures the builder starts with a clean state, which is essential when generating multiple QR codes in a loop.

## Step 3: Add plain (non‑ECI) codetext

Plain text does not need an ECI segment. Use `add_plain_codetext` for ASCII‑compatible strings.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

The builder now holds the plain segment `"HelloWorld"`.

## Step 4: Add an ECI‑encoded segment

Here’s the core of **how to use eci**: you specify the ECI value (26 for UTF‑8) and provide the Unicode string you want to encode. This allows the QR code to carry Russian, Chinese, or any other language that isn’t covered by the default ISO‑8859‑1 set.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** Without the ECI indicator, a scanner would interpret the bytes using the default character set and display garbled characters for non‑ASCII text.

## Step 5: Retrieve the combined extended codetext string

After adding all required segments, fetch the final string that will be fed to the QR generator.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

The printed value looks something like:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

The exact format depends on the library, but the important part is that the ECI marker (`[ECI26]`) precedes the UTF‑8 payload.

## Step 6: Generate the QR code using the combined text

Now you can **generate QR from text** by passing the extended codetext to `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

When you open `qr_extended.png`, a QR code appears that encodes both the plain English string and the Russian greeting. Scanning it with a modern QR scanner will correctly display “HelloWorld” and “Привет”.

### Why you should call `clear()` before reusing the builder

If you generate multiple QR codes in a loop, forgetting to clear the builder will concatenate old segments with new ones, producing an invalid code. Here’s a quick pattern:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

This snippet illustrates **how to clear builder** and **how to generate QR from text** repeatedly.

## Edge cases and common pitfalls

| Situation | What to watch for | How to handle |
|-----------|-------------------|---------------|
| **Unsupported ECI value** | The library throws `InvalidArgumentException`. | Use only ECI values listed in the specification (e.g., 26 for UTF‑8, 20 for Shift‑JIS). |
| **Very long combined text** | QR version may exceed the maximum capacity. | Increase the QR version automatically (`qr_generator.set_qr_version(QRVersion.AUTO)`) or split data across multiple QR codes. |
| **File‑system permission errors** | `save` fails with `IOError`. | Ensure the target directory exists and the process has write permission. |
| **Incorrect charset display** | Scanner shows garbled characters. | Verify the correct ECI value matches the actual encoding of the string. |

## Full runnable example

Below is a self‑contained script that you can copy, paste, and run. It includes all imports, error handling, and comments for clarity.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Running this script produces `output/qr_extended.png`, a QR code that correctly encodes both English and Russian text.

## Conclusion

You now know **how to use eci** when building QR codes, how to **clear the QR builder** before reuse, how to **generate QR from text**, and the exact steps to **save QR image** with Python. By following the pattern above, you can embed any Unicode string into a QR code while keeping the builder state predictable.

### What’s next?

- Explore other ECI values for languages like Chinese (ECI 20) or ISO‑8859‑5.
- Adjust error‑correction levels (`qr_generator.set_error_correction_level`) to improve scan reliability.
- Combine multiple ECI segments in a single QR for mixed‑language messages.

Happy coding, and enjoy creating multilingual QR codes!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}