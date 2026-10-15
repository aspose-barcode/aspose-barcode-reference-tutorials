---
category: general
date: 2026-10-15
description: 使用 Aspose.BarCode 在 Python 中从字符串创建条形码，学习如何生成 Code 128 条形码并仅用几行代码将条形码保存为
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: zh
lastmod: 2026-10-15
og_description: 使用 Python 从字符串创建条形码，将数据编码为 Code 128 条码，并使用 Aspose.BarCode 将其保存为 PNG
  文件。
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: 在 Python 中从字符串创建条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: 使用 Aspose.BarCode 在 Python 中从字符串创建条形码
url: /zh/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Python 中从字符串创建条形码

如果您需要在 Python 中 **从字符串创建条形码**，本指南将向您展示使用 Aspose.BarCode 的完整步骤。您将学习如何 **生成 Code 128 条形码**、调整其外观以及 **将条形码 PNG 保存** 到磁盘。该解决方案可在任何支持 Python 3.9+ 的平台上运行，并且只需几行代码。

以编程方式生成条形码可以消除手动输入错误，并简化库存跟踪、票务和标签打印等工作流。完成本教程后，您将能够 **将数据编码为条形码**、自定义尺寸，并在需要的任何位置存储图像。

## Prerequisites

在开始之前，请确保您具备：

- 已安装 Python 3.9 或更高版本  
- 具备下载 Aspose.BarCode 包的互联网访问权限  
- 对将保存 PNG 文件的目录拥有写入权限  

如果您使用虚拟环境（强烈推荐），请立即激活它。

## Install Aspose.BarCode Python package

Aspose 提供了一个纯 Python 库，能够处理所有常见的条形码符号，包括 Code 128。使用 pip 安装：

```bash
pip install aspose-barcode
```

*Pro tip:* 固定版本号（例如 `aspose-barcode==23.9`）可避免生产环境中出现意外的破坏性更改。

## Create barcode from string in Python

第一步是导入所需的类并实例化所需符号的生成器。本示例使用 **Code 128**，它非常适合字母数字数据。

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Why this matters:** `EncodeTypes.CODE_128` 告诉库使用哪种条形码标准，而第二个参数（`"1234567890"`）是 **您想要编码为条形码的字符串**。您可以将其替换为任意最长 80 个字符的 ASCII 字符串（适用于 Code 128）。

## Generate Code 128 barcode

生成器准备好后，您可以在内存中生成条形码图像。库会根据提供的数据自动渲染条形码。

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

此时 `barcode_image` 是 `System.Drawing.Image` 的实例（在 Windows 上）或其他平台上的兼容图像对象。您可以直接在 GUI 中显示它、嵌入 PDF，或继续进行自定义。

## Adjust barcode appearance

微调视觉属性可确保条形码在您的特定环境中可靠扫描。常见的调整包括 X‑dimension（最窄条的宽度）和整体条高。

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Why adjust these values?*  
- **X dimension** 影响条形码的密度；较小的值会生成更紧凑的条形码，适合小标签。  
- **Bar height** 影响可读性；较高的条更容易被扫描器从远处检测到。

您还可以更改颜色、添加边距，或通过 `parameters` 对象嵌入可读文本。完整选项列表请参阅 Aspose.BarCode 文档。

## How to save barcode as PNG

将生成的图像保存是 **从字符串创建条形码** 工作流的最后一步。库支持多种格式；PNG 是无损且广泛支持的格式。

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

`save` 方法使用您指定的格式将图像写入文件系统。如果目标目录（本例中的 `output/`）不存在，Python 将抛出 `FileNotFoundError`。请提前创建目录或捕获异常：

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Expected result:** 运行脚本后，`output/barcode.png` 将包含一个清晰的 Code 128 条形码，编码内容为 `"1234567890"`。在任何图像查看器中打开该文件，都能看到黑底白字的条形码，已准备好扫描。

## Full, runnable example

将所有代码片段组合在一起，以下是一个可直接复制、粘贴并运行的完整脚本：

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

使用 `python create_barcode.py` 运行脚本。如果所有依赖已正确安装，您将看到：

```
Barcode saved to output/barcode.png
```

打开 PNG 文件，并使用任意条形码扫描应用验证条形码是否与原始字符串匹配。

## Common questions and edge cases

- **What if I need a different symbology?**  
  将 `EncodeTypes.CODE_128` 替换为其他枚举值，例如 `EncodeTypes.QR`、`EncodeTypes.EAN_13` 或 `EncodeTypes.PDF_417`。其余代码保持不变。

- **Can I generate a barcode from non‑ASCII characters?**  
  Code 128 支持完整的 128 字符 ASCII 集。对于 Unicode 数据，建议使用 QR Code（`EncodeTypes.QR`），它原生支持 UTF‑8。

- **How do I change the image format?**  
  向 `save` 方法传入 `BarCodeImageFormat` 的其他成员，例如 `BarCodeImageFormat.JPEG` 或 `BarCodeImageFormat.BMP`。

- **What if the output directory is read‑only?**  
  将 `save` 调用包装在 try/except 块中，优雅地处理 `PermissionError`，例如提示用户选择其他路径。

- **Performance tip:**  
  在循环中生成成千上万的条形码可能会占用大量 CPU。复用单个 `BarcodeGenerator` 实例，并在每次迭代时仅更新 `generator.parameters.barcode.code_text`。

## Conclusion

您现在已经掌握了如何使用 Aspose.BarCode 在 Python 中 **从字符串创建条形码**、**生成 Code 128 条形码**、自定义尺寸，并 **将条形码 PNG 保存** 到磁盘。此端到端方案让您能够快速、可靠地 **将数据编码为条形码**，并轻松将条形码集成到库存系统、票务平台或任何需要机器可读标识符的应用中。

**Next steps**

- 探索其他符号（如 QR 或 DataMatrix）的替代方案（`generate code 128 barcode`）。  
- 为脚本添加错误处理逻辑，使其在生产环境中更具鲁棒性（`how to save barcode` 失败处理）。  
- 将生成的 PNG 嵌入 PDF 或 HTML 报告中（`generate barcode png` 用于 Web）。  

祝编码愉快，享受程序化生成条形码的简洁之美！

## What Should You Learn Next?

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每个资源均提供完整可运行的代码示例和逐步解释。

- [如何使用 Aspose.BarCode 生成 Code 128 条形码并保存条形码图像](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [如何在 Python 中使用 Aspose.Barcode 生成 QR 码图像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [在 Python 中创建条形码 PNG – 完整 Aspose.Barcode 指南](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}