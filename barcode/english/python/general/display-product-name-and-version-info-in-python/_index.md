---
category: general
date: 2026-09-29
description: Display product name in Python while printing release date and retrieving
  version details from the barcode library.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: en
lastmod: 2026-09-29
og_description: Display product name in Python and learn how to print release date,
  get version, and show minor version with a few lines of code.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Display product name and version info in Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Display product name and version info in Python
url: /python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Display product name and version info in Python

If you need to **display product name** from a library, this guide shows you exactly how. You’ll also learn to **print release date**, **how to get version**, and **show minor version** using concise Python code.

Many developers integrate barcode scanning or generation features and must surface the library’s metadata to users or logs. This tutorial covers everything required to retrieve and present that information reliably.

## What you’ll learn

* Retrieve version information from the `barcode` library.  
* **Display product name** together with major and minor version numbers.  
* **Print release date** in a human‑readable format.  
* Handle missing attributes gracefully.  

**Prerequisites**  
* Python 3.8 or newer.  
* Access to the `barcode` package (install with `pip install python-barcode` or the library that provides `BuildVersionInfo`).  

---

## How to display product name and version info in Python

The first step is to import the library and call the method that returns a version‑info object. The object contains attributes such as `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR`, and `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Why this works**  
`BuildVersionInfo()` returns a lightweight object whose attributes are populated at import time. Accessing the attributes directly avoids extra I/O and guarantees that the displayed data matches the library version that your code is actually using.

### Expected output

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

The exact values depend on the installed version of the barcode library.

---

## How to get version from the barcode library

If you only need the version numbers, you can skip printing the product name and focus on the numeric fields.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*The `PRODUCT_MAJOR` and `PRODUCT_MINOR` attributes follow semantic versioning, letting you compare versions programmatically.*

---

## How to print release date

The release date is stored as a string in `YYYY‑MM‑DD` format. To present it in a different locale, convert it to a `datetime` object first.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tip:** Always validate the date string before parsing to avoid `ValueError` when the library changes its format.

---

## Show minor version alongside major version

Sometimes you need to display the minor version separately, for example when logging compatibility warnings.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Use the minor version to trigger feature flags:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Handling missing attributes (edge cases)

Older releases of the barcode library might not expose all attributes. Wrap attribute access in `getattr` with sensible defaults.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

This pattern ensures your script never crashes because of a missing field, making it robust for CI pipelines that may run against multiple library versions.

---

## Full, runnable example

Below is the complete script that combines all best practices: attribute validation, date formatting, and clear output.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Running this script on a system with the barcode library installed yields output similar to the earlier example, but it now protects against missing fields and formats the date nicely.

---

## Conclusion

You now know how to **display product name**, **print release date**, **how to get version**, **how to print product**, and **show minor version** using a straightforward Python workflow. The complete example demonstrates reliable attribute access, date handling, and version comparison—skills you can reuse for any third‑party library that exposes metadata objects.

**Next steps**

* Explore the barcode library’s other metadata methods, such as `BuildCommitInfo()`.  
* Integrate the output into a logging framework (e.g., `logging.info`).  
* Compare versions programmatically to enforce minimum required versions in your application.

Feel free to experiment with different output formats or extend the script to write the information to a file for audit purposes. Happy coding!  

![Terminal output showing product name and version details](image.png "Terminal output")


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [How to Print Version of Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [How to generate barcode with Aspose.BarCode in Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}