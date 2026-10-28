---
category: general
date: 2026-10-28
description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
  Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: en
lastmod: 2026-10-28
og_description: Create extended codetext in Python with ExtCodetextBuilder. This tutorial
  shows plain and ECI‑encoded data handling, complete runnable code, and common pitfalls.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Create extended codetext in Python – complete guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: How to create extended codetext in Python with ExtCodetextBuilder
url: /python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create extended codetext in Python with ExtCodetextBuilder

If you need to **create extended codetext** for barcode or data‑matrix applications, this guide shows you exactly how to do it in Python. You’ll see how to combine plain text, add ECI (Extended Channel Interpretation) sections for Unicode characters, and retrieve a single, correctly‑formatted string ready for encoding.

The tutorial covers everything from installing the required library to handling edge cases such as unsupported ECI values. By the end you’ll have a reusable pattern you can drop into any project that needs to **create extended codetext**.

## What you’ll learn

* The role of `ExtCodetextBuilder` when building mixed‑encoding strings.  
* How to **add plain codetext** and **add ECI codetext** in a single builder instance.  
* How to verify the final output and troubleshoot common pitfalls.  
* Variations for other character sets (e.g., ISO‑8859‑1, Shift‑JIS).  

### Prerequisites

* Python 3.8 or newer.  
* The `extcodetext` package (or a similar library that provides `ExtCodetextBuilder`). Install it with:

```bash
pip install extcodetext
```

* Basic familiarity with Unicode and ECI values – ECI 3 corresponds to UTF‑8, ECI 4 to ISO‑8859‑1, etc.

> **Pro tip:** Keep a reference table of ECI numbers handy. It prevents accidental mismatches between the declared encoding and the actual byte sequence.

## Understanding ExtCodetextBuilder

`ExtCodetextBuilder` is a small utility that concatenates multiple text fragments while automatically inserting the required ECI markers. An ECI marker tells the downstream barcode encoder which character set to use for the following bytes. Without the marker, non‑ASCII characters would be misinterpreted.

The builder works in three simple phases:

1. **Create** the builder instance.  
2. **Append** plain or ECI‑encoded fragments.  
3. **Retrieve** the combined extended‑codetext string.

Below we walk through each phase with concrete code.

## Step 1: Create an ExtCodetextBuilder instance

The first line constructs the object that will hold all fragments. There is no configuration required at this point.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Why this matters*: Instantiating the builder allocates an internal buffer. All subsequent `add_*` calls operate on that buffer, guaranteeing the order you specify.

## Step 2: Append plain (un‑encoded) data

Plain data consists of characters that belong to the default character set (usually ASCII). Use `add_plain_codetext` for such fragments.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explanation*: The string `"ABC123"` contains only ASCII characters, so no ECI marker is needed. The method simply appends the raw bytes to the internal buffer.

## Step 3: Append data that must be preceded by an ECI

When you need to embed Unicode characters—like Cyrillic, Japanese, or emoji—you must tell the encoder which charset to use. This is done with `add_eci_codetext(eci, text)`. The first argument is the numeric ECI value; the second is the actual text.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Why ECI 3*: According to the ISO/IEC 18004 specification, ECI 3 maps to UTF‑8. By inserting this marker, the barcode reader knows to decode the following bytes as UTF‑8, preserving the Cyrillic characters.

### Handling other encodings

If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4, "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Always verify that the target barcode library supports the chosen ECI value; unsupported ECIs will cause encoding failures.

## Step 4: Retrieve the combined extended‑codetext string

After all fragments are added, call `get_extended_codetext()` to obtain the final string. This string includes any necessary ECI escape sequences.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Expected output** (displayed as a Python `repr` for clarity):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Breakdown*:

* `ABC123` – plain ASCII segment.  
* `\x1B\x1D\x03` – the ECI escape sequence for UTF‑8 (ESC GS 0x03).  
* `Привет` – the UTF‑8 encoded Cyrillic word.

The exact escape bytes may differ depending on the library implementation, but the logical order will always be *plain → ECI marker → Unicode text*.

## Full runnable example

Putting everything together, here’s a self‑contained script you can copy‑paste into a file named `create_extended_codetext.py` and run immediately.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Running the script prints the combined string, ready for any barcode encoder that accepts extended‑codetext input.

## Common pitfalls and how to avoid them

| Symptom | Likely cause | Fix |
|---|---|---|
| `UnicodeEncodeError` when calling `add_eci_codetext` | Supplying a string that contains characters not representable in the chosen ECI | Verify the ECI matches the string’s actual encoding (e.g., use ECI 3 for any UTF‑8 text). |
| Missing ECI marker in the final output | Accidentally using `add_plain_codetext` for non‑ASCII data | Switch to `add_eci_codetext` for any character outside the ASCII range. |
| Barcode scanner shows garbled characters | The scanner does not support the selected ECI value | Choose a universally supported ECI (UTF‑8 is widely supported) or fall back to ISO‑8859‑1 if the target language permits. |
| `get_extended_codetext` returns an empty string | No fragments were added before calling the method | Ensure at least one `add_*` call is executed. |

### Edge case: Empty strings

Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless; the builder simply ignores the empty fragment. However, repeated empty calls can lead to unnecessary ECI markers. Guard against this by checking string length before adding.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Extending the pattern for dynamic data

In real‑world applications you often build the extended codetext from user input or a database record. The following snippet shows a loop that processes a list of `(type, value)` tuples, where `type` is either `"plain"` or `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

This approach scales nicely: you can read the fragment definitions from JSON, CSV, or an API without changing the core building logic.

## Testing the output

A quick unit test ensures the builder behaves as expected. Using `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Running `pytest` should pass, confirming that the ECI marker appears exactly where it should.

## Related concepts you might explore next

* **Barcode encoding libraries** – e.g., `python-barcode`, `zxing` bindings, which accept the extended codetext string directly.  
* **ECI table reference** – a full list of numeric ECI values is published by ISO/IEC 18004 and can be stored as a Python dictionary for lookup.  
* **Error correction levels** – when generating QR codes, combine the extended codetext with appropriate error correction (L, M, Q, H) for robust scanning.

## Conclusion

You now know how to **create extended codetext** in Python using `ExtCodetextBuilder`. The process is straightforward:

1. Instantiate the builder.  
2. Append plain and ECI‑encoded fragments as needed.  
3. Retrieve the final string and feed it to your barcode generator.

By following the pattern above you can handle any mix of ASCII and Unicode data, avoid common encoding errors, and produce barcode‑ready strings that work across a wide range of scanners. Experiment with different ECIs, integrate the builder into your data‑pipeline, and you’ll have a solid foundation for all your extended‑codetext needs.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}