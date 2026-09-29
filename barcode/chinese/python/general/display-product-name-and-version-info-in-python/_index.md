---
category: general
date: 2026-09-29
description: 在 Python 中显示产品名称，同时打印发布日期并从条形码库检索版本详情。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: zh
lastmod: 2026-09-29
og_description: 在 Python 中显示产品名称，并学习如何打印发布日期、获取版本以及显示次要版本，只需几行代码。
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: 在 Python 中显示产品名称和版本信息
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
title: 在 Python 中显示产品名称和版本信息
url: /zh/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中显示产品名称和版本信息

如果您需要从库中**显示产品名称**，本指南将准确展示如何操作。您还将学习如何**打印发布日期**、**获取版本**以及使用简洁的 Python 代码**显示次要版本**。

许多开发者集成条形码扫描或生成特性，并且必须向用户或日志展示库的元数据。本教程涵盖了可靠检索和呈现该信息所需的全部内容。

## 您将学习的内容

* 从 `barcode` 库检索版本信息。  
* **显示产品名称**以及主版本号和次版本号。  
* **以人类可读的格式打印发布日期**。  
* 优雅地处理缺失的属性。  

**先决条件**  
* Python 3.8 或更高版本。  
* 获取 `barcode` 包（使用 `pip install python-barcode` 安装，或使用提供 `BuildVersionInfo` 的库）。  

---

## 如何在 Python 中显示产品名称和版本信息

第一步是导入库并调用返回版本信息对象的方法。该对象包含诸如 `PRODUCT`、`PRODUCT_MAJOR`、`PRODUCT_MINOR` 和 `RELEASE_DATE` 等属性。

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

**为什么这样有效**  
`BuildVersionInfo()` 返回一个轻量级对象，其属性在导入时即被填充。直接访问这些属性可避免额外的 I/O，并确保显示的数据与代码实际使用的库版本相匹配。

### 预期输出

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

具体数值取决于已安装的 barcode 库的版本。

---

## 如何从 barcode 库获取版本

如果您只需要版本号，可以省略打印产品名称，直接关注数值字段。

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*`PRODUCT_MAJOR` 和 `PRODUCT_MINOR` 属性遵循语义化版本控制，允许您以编程方式比较版本。*

---

## 如何打印发布日期

发布日期以 `YYYY‑MM‑DD` 格式的字符串存储。若要以不同地区格式展示，需先将其转换为 `datetime` 对象。

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**提示：** 在解析之前始终验证日期字符串，以避免库更改格式时出现 `ValueError`。

---

## 同时显示次要版本和主版本

有时您需要单独显示次要版本，例如在记录兼容性警告时。

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**专业提示：** 使用次要版本来触发功能标志：

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## 处理缺失属性（边缘情况）

barcode 库的旧版本可能未公开所有属性。请使用带有合理默认值的 `getattr` 包装属性访问。

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

此模式可确保脚本不会因缺少字段而崩溃，从而在可能针对多个库版本运行的 CI 流水线中保持稳健。

---

## 完整、可运行的示例

下面是结合所有最佳实践的完整脚本：属性验证、日期格式化以及清晰的输出。

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

在已安装 barcode 库的系统上运行此脚本，将产生类似前述示例的输出，但现在它能够防止缺失字段并友好地格式化日期。

---

## 结论

您现在已经掌握了使用简洁的 Python 工作流**显示产品名称**、**打印发布日期**、**获取版本**、**打印产品**以及**显示次要版本**的方法。完整示例展示了可靠的属性访问、日期处理和版本比较——这些技能可复用于任何提供元数据对象的第三方库。

**后续步骤**

* 探索 barcode 库的其他元数据方法，例如 `BuildCommitInfo()`。  
* 将输出集成到日志框架中（例如 `logging.info`）。  
* 以编程方式比较版本，以在应用程序中强制执行最低所需版本。

欢迎尝试不同的输出格式，或扩展脚本将信息写入文件以用于审计。祝编码愉快！  

![显示产品名称和版本详细信息的终端输出](image.png "终端输出")


## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [使用 Python barcode 库显示产品名称 – 步骤指南](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [如何打印 Aspose.Barcode 的版本（Python）](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [如何在 Python 中使用 Aspose.BarCode 生成条形码](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}