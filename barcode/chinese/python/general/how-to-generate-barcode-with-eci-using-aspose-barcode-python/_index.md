---
category: general
date: 2026-08-19
description: 如何使用 Aspose.Barcode for Python 生成带 ECI 的条形码。了解如何添加 ECI 数据、混合普通文本并保存图像，一站式清晰指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: zh
lastmod: 2026-08-19
og_description: 如何使用 Aspose.Barcode for Python 生成带 ECI 的条形码。请按照本教程学习如何添加 ECI 数据、自定义外观并保存结果。
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: 如何使用 Aspose.Barcode Python 生成带 ECI 的条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: 如何使用 Aspose.Barcode Python 生成带 ECI 的条形码
url: /zh/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Barcode Python 生成带 ECI 的条形码

如果您需要了解 **如何生成条形码**，其中包含普通字符和 ECI 编码的数据，本指南将展示完整的过程。您将看到如何 **添加 eci** 部分、调整尺寸，并使用一个可运行的脚本将图像写入磁盘。

本教程包括：

* 检索 Aspose.Barcode 库版本（可选，但对调试有帮助）。  
* 构建混合普通字符和 ECI 编码字符的扩展 codetext 字符串。  
* 为支持扩展 codetext 的符号创建条形码生成器。  
* 自定义条形码尺寸并保存最终的 PNG 文件。

无需外部文档；复制代码，运行它，您将得到一个包含使用 ECI 26（UTF‑8）编码的中文字符的条形码图像。

## 前提条件

在开始之前，请确保您已具备以下条件：

* 已安装 Python 3.8 或更高版本。  
* 已安装 `aspose-barcode` 包（`pip install aspose-barcode`）。  
* 对您打算保存 PNG 文件的文件夹拥有写入权限。

如果您使用虚拟环境，请先激活它，以保持依赖的隔离。

## 步骤 1：验证 Aspose.Barcode 版本（可选）

了解确切的库版本有助于在报告错误或比较不同版本的功能时使用。

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*为什么这很重要*：版本输出确认运行时与您所参考的文档相匹配。不同版本可能支持不同的 ECI 值，因此这是一个快速的合理性检查。

## 步骤 2：构建包含普通和 ECI 编码部分的扩展 codetext

Aspose.Barcode 提供 `ExtCodetextBuilder` 用于连接普通数据和 ECI 编码段。在本示例中，我们将数字字符串与中文字符混合。

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*说明*：  
* `add_plain_codetext` 插入条形码符号视为普通字符的数据。  
* `add_eci_codetext` 告诉生成器在提供的文本前添加 ECI 指示符（此处为 **26**，对应 UTF‑8）。这正是 **如何添加 eci** 数据到条形码的方式。

您可以多次调用 `add_eci_codetext` 以嵌入多个不同语言的块。构建器会自动处理所需的转义序列。

## 步骤 3：选择支持扩展 codetext 的符号

并非所有条形码类型都能存储 ECI 段。Code 128、QR 和 Data Matrix 是常见的选择。示例使用 Code 128，因为它被广泛支持且适用于混合字母数字数据。

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*为什么选择 Code 128*：它接受完整的 ASCII 范围以及构建器生成的 ECI 转义序列，使其非常适合混合普通和编码文本的 “如何生成条形码” 场景。

## 步骤 4：调整条形码外观

您可以通过 `parameters` 对象控制尺寸、高度、边距以及许多其他视觉属性。

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*提示*：如果计划打印条形码，请按比例增加 `x_dimension` 和 `bar_height`，以在目标 DPI 下保持可读性。

## 步骤 5：保存条形码图像

最后，将生成的图像写入文件。Aspose.Barcode 支持 PNG、JPEG、BMP 等多种格式。

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

在调用 `save` 之前，请确保 `output` 文件夹存在，或使用 `os.makedirs("output", exist_ok=True)` 创建它。

### 预期结果

打开 `extended_codetext.png` 时，您应该看到一个 Code 128 条形码，其中编码了数字字符串 `1234567890`，随后是中文字符 “特殊字符”。使用支持 ECI 的现代扫描仪扫描该条形码，将返回原始的混合字符串。

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="使用生成条形码示例生成的条形码"}

## 常见问题与边缘情况

### 如果需要不同的字符集怎么办？

从 ISO/IEC 18004 表中选择合适的 ECI 值。例如，ECI 27 代表 ISO‑8859‑1（Latin‑1）。相应地在 `add_eci_codetext` 中替换数值标识符。

### 我可以嵌入多个 ECI 块吗？

可以。多次调用 `add_eci_codetext`。构建器会在块之间插入必要的 ECI 切换代码，保持您添加的顺序。

### 生成器是否支持带 ECI 的 QR 码？

当然。将 `barcode.Symbology.CODE_128` 替换为 `barcode.Symbology.QR`，并通过 `generator.parameters.qr` 调整任何 QR 特定参数（例如错误纠正级别）。

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### 如何处理非常长的数据字符串？

对于像 Code 128 这样的线性条形码，在使用扩展 codetext 时最大长度约为 80 字符。如果超过此长度，建议切换到二维符号，如 QR 或 Data Matrix，它们可以存储数千字符。

## 完整、可运行的脚本

下面是完整的程序，您可以复制粘贴到名为 `generate_extended_barcode.py` 的文件中并直接运行。

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## 接下来应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方法。

- [如何使用 Aspose.BarCode 生成带补充空格自定义的条形码图像](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [如何在 Java 中使用 Aspose.BarCode 生成条形码图像](/barcode/english/java/barcode-rendering-techniques/)
- [如何使用 Aspose.BarCode 为 .NET 生成 DataMatrix 条形码](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}