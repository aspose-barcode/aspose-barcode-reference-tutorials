---
category: general
date: 2026-07-18
description: use extcodetextbuilder aspose to create QR codes that combine plain ASCII
  and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: en
lastmod: 2026-07-18
og_description: use extcodetextbuilder aspose lets you blend plain and UTF‑8 encoded
  fragments in a QR Code. Follow this step‑by‑step guide for Aspose.Barcode in Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: use extcodetextbuilder aspose – Build QR Codes with Mixed ECI Text
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
url: /python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – Build QR Codes with Mixed ECI Text

Ever wondered how to **use extcodetextbuilder aspose** to embed both plain English and Cyrillic characters into a single QR Code? You’re not alone. Many developers hit a wall when they need to mix ASCII and non‑ASCII data, especially when the target scanner expects proper ECI (Extended Channel Interpretation) markers.  

In this tutorial we’ll walk through the exact steps to create a QR Code that carries “HELLO123” **and** the Russian word “Привет”, all with Aspose.Barcode’s Python API. By the end you’ll have a ready‑to‑run script, understand why each call matters, and know how to tweak the process for other languages or data formats.

## What You’ll Learn

- How to **initialize ExtCodetextBuilder** and add plain plus ECI‑encoded fragments.  
- Why the **ECI encoding** value `3` corresponds to UTF‑8 and how that affects scanning.  
- The exact sequence to set up a **QR Code generator** with Aspose.Barcode.  
- How to save the resulting image and verify the mixed content.  

**Prerequisites** – you need Python 3.8+, the `aspose-barcode` package installed (`pip install aspose-barcode`), and a folder you can write images to. Nothing else.

---

## use extcodetextbuilder aspose to build mixed codetext

The first thing we need is an `ExtCodetextBuilder` instance. Think of it as a builder pattern that concatenates different pieces of text while automatically inserting the right ECI markers behind the scenes.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Why this matters:**  
- `add_plain_codetext` keeps the data as‑is, which is perfect for numbers or English letters.  
- `add_eci_codetext` inserts an ECI segment (`[ECI:3]`) before the supplied string, telling any compliant reader that the following bytes are UTF‑8. Without this, the scanner would interpret the Cyrillic bytes as garbage.

> **Pro tip:** If you need a different character set, change the `eci_encoding` value according to the ECI table (e.g., `26` for ISO‑8859‑1).  

---

## Initialise QR Code generation with Aspose.Barcode

Now that we have a properly formatted `extended_codetext`, we can hand it over to the QR Code generator. Aspose.Barcode abstracts away the low‑level QR matrix creation, letting you focus on the data.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**What’s happening here?**  
- `BarcodeGenerator()` creates a fresh generator object with default settings (size, resolution, etc.).  
- `set_symbology` tells the engine we want a QR Code rather than, say, Code128.  

If you need a higher error‑correction level, you can call `qr_generator.parameters.barcode.qr_error_level = ...` before assigning the codetext.

---

## Assign the extended codetext to the QR generator

With the generator ready, the next step is simply feeding the mixed string we built earlier.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Why not use `set_codetext`?**  
`set_codetext` treats the input as plain text, stripping any ECI markers. `set_extended_codetext` preserves the raw bytes, including the ECI segment, ensuring the scanner sees the correct language switch.

---

## Save the QR Code image and verify the result

Finally, we write the QR Code to disk. Aspose.Barcode supports PNG, JPEG, BMP, and more; PNG is a safe default because it preserves lossless data.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

You should now have a PNG file at the specified location. Open it with any QR scanner app that supports ECI (most modern smartphones do). Scan once – you’ll see “HELLO123”. Scan again (or use a scanner that shows raw data) – you’ll also get “Привет”. The two pieces appear as a single payload, exactly as we built it.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: use extcodetextbuilder aspose QR code example showing mixed ECI text*

---

## Full, Ready‑to‑Run Script

Putting everything together, here’s the complete program you can copy‑paste into a file named `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Run it with:

```bash
python qr_mixed_eci.py
```

You’ll see a console message confirming the save location, and the PNG will appear right where you told it to go.

---

## Common Questions & Edge Cases

### What if my scanner doesn’t recognize the Cyrillic part?
Make sure the scanning app advertises ECI support. Older hardware may ignore the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.

### Can I add more than two fragments?
Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times as you need. The builder will concatenate them in the order you invoke the methods.

### How do I change the QR Code size or foreground color?
Use the `qr_generator.parameters` object:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Is there a way to embed binary data (e.g., a small file) alongside text?
Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate ECI if the binary represents a specific character set. The builder will handle the necessary mode switches.

---

## Conclusion

You now know **how to use extcodetextbuilder aspose** to craft QR Codes that seamlessly blend plain ASCII and UTF‑8 encoded Russian text. By leveraging `ExtCodetextBuilder`, setting the correct **ECI encoding**, and feeding the result into an **Aspose.Barcode QR Code generator**, you get a single, standards‑compliant image that works on modern scanners.  

From here, try swapping `eci_encoding=3` for other language identifiers, or experiment with additional plain fragments to build multilingual payloads. You might also explore the `BarCodeImageFormat` options to output SVG or PDF if you need vector graphics.  

Happy coding, and feel free to drop a comment if you hit any snags—your feedback helps make these guides even better!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}