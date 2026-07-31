---
category: general
date: 2026-07-30
description: 如何在 Python 中使用 Aspose.BarCode 生成条形码——学习如何设置尺寸、修改填充并在几分钟内保存 PNG 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: zh
lastmod: 2026-07-30
og_description: 如何在 Python 中使用 Aspose.BarCode 快速生成条形码。了解如何设置尺寸、修改填充以及导出 PNG 文件，以适用于任何应用程序。
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: 如何使用 Aspose.BarCode 生成条形码 – Python 指南
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: 如何在 Python 中使用 Aspose.BarCode 生成条形码
url: /zh/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.BarCode 生成条形码

有没有想过 **如何生成条形码** 在 Python 项目中，而不必与底层图像库搏斗？你并不是唯一的。无论是构建运输标签系统、票务平台，还是仅仅需要一个快速的 QR 码用于演示，掌握条形码生成都能为你节省大量的试错时间。

在本教程中，我们将演示一个完整、可直接运行的示例，展示 **如何生成条形码** 使用 Aspose.BarCode 库、如何设置尺寸以及如何更改填充方式。完成后，你将在输出文件夹中得到两个 PNG 文件——一个是实心条形码，一个是空心条形码。

## 前置条件

在开始之前，请确保你已经具备：

* 已安装 Python 3.8+（代码在 Windows、macOS 和 Linux 上均可运行）
* 拥有 Aspose.BarCode for Python via .NET 的有效许可证（可先使用免费试用版）
* 在虚拟环境中执行 `pip install aspose-barcode`
* 一个可写入的文件夹——本文示例中我们称之为 `YOUR_DIRECTORY`

除此之外不需要其他第三方包。

## 第一步：安装并导入 Aspose.BarCode

首先要做的就是获取库本身。在终端中运行一次：

```bash
pip install aspose-barcode
```

现在可以导入我们将要使用的类。这正是 **如何生成条形码** 真正开始的地方，因为没有正确的导入，你甚至无法调用生成器。

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **小贴士：** 如果你使用虚拟环境，请在运行 `pip install` 前先激活它。这样可以保持全局 Python 环境的整洁。

## 第二步：创建 Planet 条形码 – 默认（实心）版本

Planet 条形码是一种经典的 2‑of‑5 编码，常用于邮政服务。我们先从最简单的情况开始：实心条形码。此步骤演示 **如何生成条形码** 的默认设置。

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### 为什么要设置 `x_dimension.pixels`？

即使默认值可以工作，你通常仍需 **如何设置尺寸** 以匹配打印机 DPI 或 UI 限制。`x_dimension` 属性控制单根条的宽度（像素），数值越大条码越粗，数值越小则更紧凑。

## 第三步：创建带空心（未填充）条的 Planet 条形码

现在来回答 **如何更改填充** 的问题。通过切换 `filled_bars` 标志，我们可以将实心黑条切换为仅显示轮廓的空心条，数据编码保持不变。

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

当你并排打开 `PostalPlanetFilled.png` 与 `PostalPlanetEmpty.png` 时，会看到视觉差异：实心版本为纯黑，空心版本则以轮廓形式呈现。这在需要为 UI 叠加提供更轻视觉重量时非常有用。

## 第四步：完整可运行脚本（完整解决方案）

下面是完整的程序代码，你可以复制粘贴到名为 `generate_planet_barcodes.py` 的文件中。它包含了从导入到保存图像的所有内容，无需再寻找缺失的片段。

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### 预期输出

运行脚本后会打印类似如下内容：

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

使用任意图像查看器打开这两个 PNG 文件，你应该会看到经典的 Planet 条形码——一个实心，一个空心。两者均编码字符串 `123456`。

## 第五步：为不同使用场景微调尺寸

既然你已经掌握了 **如何设置尺寸**，接下来我们探讨几种常见情形。

### 5.1 为打印放大条形码

如果在 300 dpi 的标签打印机上打印，4 像素的条可能显得太小。将 `x_dimension` 提升到比如 8 像素：

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 为移动端屏幕缩小条形码

相反，在移动应用中你可能需要更紧凑的条码。将 `x_dimension` 设为 2 像素即可在不影响可读性的前提下降低宽度（Aspose 会自动处理缩放）。

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

请记住，条形码的高度会根据所使用的编码规范自动调整，你只需关注宽度即可。

## 第六步：高级填充选项及其应用场景

除了简单的 `filled_bars` 布尔值，Aspose.BarCode 还允许自定义条的颜色、背景颜色，甚至添加渐变。如果你需要 **如何更改填充** 超出“实心 vs 空心”的范围，可以这样做：

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*（注：上述代码使用 .NET 的颜色结构体；在纯 Python 中请使用相应的 Aspose 枚举。）* 这在品牌化时非常实用——想象一下在条形码背景中巧妙嵌入公司徽标。

## 常见陷阱及规避方法

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| 保存的 PNG 中条形码模糊 | `x_dimension` 对目标 DPI 来说太低 | 增大 `x_dimension` 或在保存后对图像进行放大 |
| 扫描仪无法读取空心条形码 | 某些旧版扫描仪不支持 `filled_bars = False` | 为了兼容性，使用默认的实心版本 |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode 未安装或 .NET 运行时不匹配 | 使用 `pip install aspose-barcode` 重新安装，并确保已安装 .NET Core 运行时 |

## 小结：我们覆盖了哪些内容

* **如何使用 Aspose.BarCode 在 Python 中生成条形码**
* **如何使用 `x_dimension.pixels` 设置尺寸**
* **如何通过 `filled_bars` 标志更改填充**（并简要介绍了颜色自定义）
* 一个完整的、可直接复制粘贴的脚本，能够根据任意数据字符串进行适配

## 接下来该做什么？（后续步骤与相关主题）

如果本指南对你有帮助，建议进一步探索：

* **生成 QR 码** (`EncodeTypes.QR`) – 适用于 URL 与联系信息。
* **在条形码下方添加文字说明** (`parameters.caption`) 以提供可读的数值。
* **导出为其他格式** 如 SVG 或 PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) – 适合矢量图形需求。
* **批量生成** – 通过遍历 CSV 中的产品 ID，一次性生成整套条形码。

所有这些主题也与我们的次要关键词相呼应：*generate barcode with aspose* 与 *how to set dimensions*，适用于不同的输出格式。

---

如果在使用过程中遇到任何问题，欢迎留言讨论，或分享你的个人实现方式。祝你玩转条形码！

## 接下来你应该学习什么？

以下教程涵盖了与本指南紧密相关的主题，帮助你在项目中进一步掌握 API 功能并探索替代实现方式。

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to Colorize Barcode Images in Java with Aspose.BarCode](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}