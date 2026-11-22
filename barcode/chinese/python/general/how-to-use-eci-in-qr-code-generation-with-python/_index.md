---
category: general
date: 2026-11-20
description: 学习如何使用 ECI、从文本生成二维码、清除构建器，并使用 Python 条形码库保存二维码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: zh
lastmod: 2026-11-20
og_description: 如何使用 ECI 从文本生成二维码，清空二维码构建器，并保存二维码图像——完整的分步指南。
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: 如何在 Python 中使用 ECI 生成二维码
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
title: 如何在 Python 中使用 ECI 生成 QR 码
url: /zh/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中使用 ECI 生成 QR 码的方式

如果您在创建 QR 码时需要 **how to use eci**，本指南将展示具体步骤。您将看到如何从文本生成 QR 码、清除构建器，最后保存 QR 图像——只需几行 Python 代码。

包含多语言数据的 QR 码通常需要一个扩展通道解释（Extended Channel Interpretation，ECI）段，以便扫描器知道使用哪种字符集。本教程将带您一步步构建扩展码文本、在重复使用时清除构建器，并将结果保存为 PNG 文件。

## Prerequisites

在开始之前，请确保您拥有：

- 已安装 Python 3.8+。
- Aspose.BarCode for Python via .NET 包（或任何提供 `ExtCodetextBuilder` 和 `BarcodeGenerator` 的兼容 `barcode` 库）。
- 对 QR 码概念有基本了解。

使用 pip 安装库：

```bash
pip install aspose-barcode
```

> **Pro tip:** 使用虚拟环境以避免版本冲突。

## Step 1: Import the required classes

您将主要使用的类是用于构建扩展码文本的 `ExtCodetextBuilder`，以及用于渲染 QR 码的 `BarcodeGenerator`。

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

这些导入让您可以使用构建器方法（`add_plain_codetext`、`add_eci_codetext` 等）以及生成器的 `set_code_text`、`set_symbology` 和 `save` 功能。

## Step 2: Create and configure the ExtCodetextBuilder

创建新的构建器实例是 **how to use eci** 的第一个具体示例。稍后如果需要复用，也可以清除构建器。

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

调用 `clear()` 可确保构建器从干净的状态开始，这在循环中生成多个 QR 码时尤为重要。

## Step 3: Add plain (non‑ECI) codetext

普通文本不需要 ECI 段。使用 `add_plain_codetext` 处理 ASCII 兼容的字符串。

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

构建器现在持有普通段 `"HelloWorld"`。

## Step 4: Add an ECI‑encoded segment

这里展示 **how to use eci** 的核心：指定 ECI 值（UTF‑8 为 26）并提供要编码的 Unicode 字符串。这样 QR 码即可携带俄语、中文或其他默认 ISO‑8859‑1 集合未覆盖的语言。

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** 如果没有 ECI 指示符，扫描器会使用默认字符集解释字节，导致非 ASCII 文本出现乱码。

## Step 5: Retrieve the combined extended codetext string

添加完所有必需段后，获取将传递给 QR 生成器的最终字符串。

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

打印的值大致如下：

```
Extended codetext: [ECI26]ПриветHelloWorld
```

具体格式取决于库实现，但关键是 ECI 标记（`[ECI26]`）位于 UTF‑8 负载之前。

## Step 6: Generate the QR code using the combined text

现在您可以通过将扩展码文本传递给 `BarcodeGenerator` 来 **generate QR from text**。

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

打开 `qr_extended.png` 时，会看到一个同时编码普通英文字符串和俄语问候的 QR 码。使用现代 QR 扫描器扫描，可正确显示 “HelloWorld” 与 “Привет”。

### Why you should call `clear()` before reusing the builder

如果在循环中生成多个 QR 码而忘记清除构建器，旧的段会与新的段拼接，导致生成的码无效。下面是一个快速模式：

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

此代码片段演示了 **how to clear builder** 和 **how to generate QR from text** 的重复使用方式。

## Edge cases and common pitfalls

| 情况 | 需要注意的事项 | 处理方法 |
|-----------|-------------------|---------------|
| **不支持的 ECI 值** | 库会抛出 `InvalidArgumentException`。 | 仅使用规范中列出的 ECI 值（例如，UTF‑8 为 26，Shift‑JIS 为 20）。 |
| **组合文本过长** | QR 版本可能超过最大容量。 | 自动提升 QR 版本 (`qr_generator.set_qr_version(QRVersion.AUTO)`) 或将数据拆分到多个 QR 码中。 |
| **文件系统权限错误** | `save` 因 `IOError` 失败。 | 确保目标目录存在且进程拥有写入权限。 |
| **字符集显示错误** | 扫描仪显示乱码。 | 确认正确的 ECI 值与字符串的实际编码相匹配。 |

## Full runnable example

下面是一个完整的可运行脚本，您可以复制、粘贴并执行。它包含所有导入、错误处理以及清晰的注释。

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

运行此脚本会生成 `output/qr_extended.png`，该 QR 码能够正确编码英文和俄文文本。

## Conclusion

您现在已经了解 **how to use eci** 在构建 QR 码时的使用方法，掌握了在复用前 **clear the QR builder**，以及 **generate QR from text** 的步骤，并知道如何使用 Python **save QR image**。遵循上述模式，您可以将任意 Unicode 字符串嵌入 QR 码，同时保持构建器状态可预测。

### What’s next?

- 探索其他语言的 ECI 值，如中文（ECI 20）或 ISO‑8859‑5。
- 调整错误纠正级别（`qr_generator.set_error_correction_level`）以提升扫描可靠性。
- 在单个 QR 中组合多个 ECI 段，实现混合语言信息。

Happy coding, and enjoy creating multilingual QR codes!

## What Should You Learn Next?

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整的可运行代码示例和分步解释。

- [如何使用 Aspose.Barcode Python 生成带 ECI 的条形码](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [如何使用 Aspose.Barcode 在 Python 中生成 QR 码图像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [如何在 Python 中生成条形码 – 完整分步指南](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}