---
category: general
date: 2026-11-23
description: 如何使用 Aspose.BarCode 在 Python 中生成条形码图像。学习创建 Planet 条码，调整 X 维度，并输出空条 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: zh
lastmod: 2026-11-23
og_description: 如何使用 Aspose.BarCode 在 Python 中生成条形码。本教程将指导您创建带空白条的 Planet 条码并将其保存为
  PNG。
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: 如何在Python中生成条形码 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: 如何使用 Aspose.BarCode 在 Python 中生成条形码图像
url: /zh/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 Python 中生成条形码图像

使用 Aspose.BarCode 库在 Python 中生成条形码图像非常简单。本指南将一步步演示如何使用 Planet 符号生成条形码、自定义 X‑dimension，并生成空条样式的 PNG 文件。

您将看到一个完整、可运行的脚本，直接复制到项目中即可使用。教程还涵盖了常见的变体——例如切换到其他符号或输出格式——帮助您根据自己的需求进行调整。

## 前置条件

在开始之前，请确保您已具备以下条件：

* 已安装 Python 3.8 或更高版本。
* 可使用终端或命令提示符。
* 拥有有效的 Aspose.BarCode for Python 许可证（免费评估版可用于测试）。
* 对 Python 包管理（`pip`）有基本了解。

## 第 1 步：安装 Aspose.BarCode 包

Aspose 通过 PyPI 分发其 Python API。使用标准包管理器进行安装：

```bash
pip install asposebarcode
```

> **专业提示：** 使用虚拟环境（`python -m venv venv`）可将依赖与其他项目隔离。

## 第 2 步：导入所需的 Aspose.BarCode 类

导入语句会引入生成器、符号枚举以及图像格式枚举。

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` 用于创建条形码对象。
* `EncodeTypes` 列举所有受支持的符号——这里我们使用 `Planet`。
* `BarCodeImageFormat` 定义输出文件类型（PNG、JPEG 等）。

## 第 3 步：为 Planet 符号创建条形码生成器

使用所需的符号和要编码的数据实例化生成器。

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`Planet` 符号会生成圆形图案，适用于装饰或品牌化场景。

## 第 4 步：调整 X‑dimension（模块宽度）

X‑dimension 控制最小条（模块）的宽度。将其设为 4 像素可得到清晰的高分辨率图像。

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

在需要条形码在打印或屏幕显示时具备良好可伸缩性的情况下，修改 X‑dimension 非常有用。

## 第 5 步：禁用实心条以实现空条样式

空条条形码仅显示条的轮廓，适用于设计感强的应用。

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

当 `filled_bars` 为 `False` 时，生成器绘制空心形状而非实心形状。

## 第 6 步：将条形码图像保存为 PNG 文件

最后，将条形码写入磁盘。PNG 为无损格式，兼容性广。

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

`save` 方法会在目标目录不存在时自动创建该目录。

## 完整示例 – 可直接运行的脚本

将所有代码片段组合在一起，即可得到一个自包含的程序，立即运行：

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**预期输出：** 运行脚本后，`output/PlanetEmptyBars.png` 将包含一张 200 × 200 像素的 Planet 条形码图像，条为空心。使用任意图像查看器打开文件，即可看到圆形图案以及内部编码的数值。

## 常见变体与边缘情况

### 切换到其他符号

如果需要 QR 码、Code 128 或其他格式，只需将 `EncodeTypes.Planet` 替换为相应的枚举值：

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### 更改图像格式

Aspose.BarCode 支持 PNG、JPEG、BMP 和 TIFF。若要生成 JPEG：

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### 在不失真情况下调整图像尺寸

可以通过 `resolution` 属性或同时缩放 X‑dimension 与 Y‑dimension 来控制整体图像尺寸。对于高分辨率打印，设置更高的 DPI：

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### 处理过长的数据字符串

Planet 符号的数据容量有限（最多 8 个字符）。若尝试编码更长的字符串，生成器会抛出异常。请在创建条形码前先验证长度：

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## 提示与陷阱

* **许可证激活：** 在生产环境中，请在脚本开头使用 `asposebarcode.License().set_license("Aspose.Total.lic")` 加载许可证文件。省略此步骤会在输出图像中嵌入水印。
* **线程安全：** `BarcodeGenerator` 实例并非线程安全。若在并行生成条形码时，请为每个线程创建独立实例。
* **性能优化：** 通过 `barcode.value = "new data"` 更改值来复用同一生成器，比每次构造新对象更快。
* **文件路径：** 使用 `os.path.join` 构建跨平台路径，特别是在 Linux 或 macOS 部署时。

## 结论

现在，您已经掌握了如何使用 Aspose.BarCode 在 Python 中生成条形码图像、定制 X‑dimension、生成空条样式，并将结果保存为 PNG。完整示例可轻松迁移到其他符号、输出格式和视觉风格，为您在应用程序中实现任何条形码相关功能提供了灵活的基础。

**后续步骤：** 通过尝试不同的编码方式，探索 *Python 条形码生成* 的更多关键词，实验 *条形码图像 PNG* 的压缩设置，或将生成的图像集成到使用 Flask 或 FastAPI 的 Web 服务中。祝编码愉快！

## 接下来您可以学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您在已有技术基础上进一步深入。每篇资源均提供完整可运行的代码示例和逐步解释，助您掌握更多 API 功能并探索替代实现方案。

- [如何使用 Python 创建 Planet 条形码 PNG](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [如何使用 Aspose.BarCode 在 Python 中创建条形码图像](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [使用 Aspose.Barcode 在 Python 中生成二维码图像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}