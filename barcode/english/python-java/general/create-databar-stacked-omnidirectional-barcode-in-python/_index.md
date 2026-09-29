---
category: general
date: 2026-07-30
description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
  step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using a
  python barcode generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: en
lastmod: 2026-07-30
og_description: Create Databar Stacked Omnidirectional barcode in Python. This tutorial
  shows how to set XDimension, tweak DataBar aspect ratio, and save as PNG with BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Create Databar Stacked Omnidirectional Barcode – Python Tutorial
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Create Databar Stacked Omnidirectional Barcode in Python
url: /python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Databar Stacked Omnidirectional Barcode in Python

Ever needed to **create databar stacked omnidirectional** barcode in Python but weren’t sure where to start? You’re not alone—many developers hit that wall when they first play with the `BarcodeGenerator` class. The good news is that the whole process is pretty straightforward once you understand the key properties.

In this guide we’ll walk through a complete, runnable example that uses a **python barcode generator** to set the XDimension, tweak the DataBar aspect ratio, and finally export two PNG files. By the end you’ll have a solid grasp of how to generate high‑quality stacked omnidirectional symbols for any inventory or logistics project.

## What You’ll Learn

- How to instantiate a **databar stacked omnidirectional** generator with a GTIN‑14 payload.  
- Why the **XDimension pixel size** matters for scan reliability.  
- The impact of the **DataBar aspect ratio** on row width vs. height.  
- How to save the result as a **BarCodeImageFormat PNG** file.  
- Tips for re‑using the same generator object to produce multiple variants without extra memory overhead.

### Prerequisites

- Python 3.8+ (the library we use is pure‑Python, no compiled wheels needed).  
- The `barcode-generator` package (install via `pip install barcode-generator`).  
- A folder you can write to – the script will dump two PNG images there.

If you’re comfortable with basic Python imports and object‑oriented code, you’re ready to roll.

## Create Databar Stacked Omnidirectional Barcode – Step Overview

Below we break the workflow into six bite‑size steps. Each step is a self‑contained chunk of code you can copy‑paste into a REPL or script file. Feel free to experiment—changing the aspect ratio or XDimension will instantly give you a different visual style.

---

## Step 1: Create Databar Stacked Omnidirectional Generator

The first thing we do is **create databar stacked omnidirectional** generator instance, passing the appropriate `EncodeTypes` enum and the data string.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Why this matters:** The `EncodeTypes.DatabarStackedOmniDirectional` flag tells the library to produce a stacked omnidirectional symbol, which is the only DataBar variant that can encode up to 14 digits while still being readable from any angle.

---

## Configure XDimension Pixel Size

The **XDimension pixel size** controls the smallest module (the thinnest black bar). A value of `2` pixels works well for most screen‑display scenarios.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** If you plan to print the barcode at high DPI, bump this value up to 3 or 4 to avoid blurry edges.

---

## Adjust DataBar Aspect Ratio (15)

The **DataBar aspect ratio** determines how wide each row is compared to its height. An aspect ratio of `15` yields wider rows, which many scanners prefer for fast motion capture.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Why 15?** The official GS1 specification recommends a ratio between 10 and 20 for stacked omnidirectional symbols. We pick `15` as a balanced default.

---

## Export Barcode as PNG Using BarCodeImageFormat

Now that the generator is configured, we persist the image. The `BarCodeImageFormat.Png` enum ensures lossless output, perfect for downstream processing.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **What you’ll see:** Open the resulting PNG; you should notice a clean, high‑contrast barcode with relatively wide rows.

---

## Change DataBar Aspect Ratio to 30

Sometimes you need taller rows instead of wider ones—perhaps to fit a narrow label. Switching the **DataBar aspect ratio** to `30` makes each row taller.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** Very high ratios (e.g., >40) can cause the barcode to exceed typical label heights, so test on a real printer before committing.

---

## Export Barcode Again with New Aspect Ratio

Finally, we reuse the same `barcode_generator` object to write a second PNG. No need to recreate the generator—just change the property and call `Save` again.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Result:** You now have two PNG files—one with wide rows (`AR15`) and another with tall rows (`AR30`). Compare them side‑by‑side to decide which works best for your scanner setup.

---

## Full Working Example

Putting it all together, here’s the complete script you can run instantly. Replace `YOUR_DIRECTORY` with an absolute path on your machine.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Expected output** (in your console):

```
✅ Two PNG files created – AR15 and AR30
```

And two image files appear in the target folder, ready for scanning tests.

---

## Conclusion

We just **created databar stacked omnidirectional** barcodes in Python, adjusted the **XDimension pixel size**, experimented with two different **DataBar aspect ratio** settings, and exported the results as **BarCodeImageFormat PNG** files. The entire workflow fits into a handful of lines, yet gives you full control over the visual characteristics that matter most for scanners.

What’s next? Try swapping the payload to a different GTIN, play with colors by converting the PNG to a palette‑based image, or generate a PDF report that embeds both PNGs side‑by‑side. The `BarcodeGenerator` class is flexible enough to handle all of those scenarios, so feel free to experiment.

Got questions about a particular use‑case or run into an error? Drop a comment below, and I’ll be happy to help. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}