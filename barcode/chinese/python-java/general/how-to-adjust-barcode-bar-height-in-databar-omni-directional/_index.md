---
category: general
date: 2026-11-27
description: 了解如何在 DataBar Omni‑Directional 条码生成器中调整条码条的高度。逐步代码演示将高度设置为 30 像素和 60 像素。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: zh
lastmod: 2026-11-27
og_description: 使用 Python 调整 DataBar Omni‑Directional 条码生成器中的条码高度。完整指南教您设置高度、X 维度并保存
  PNG 图像。
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: 在 DataBar 全向生成器中调整条码条高度
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: 如何在 DataBar 全方向生成器中调整条码条的高度
url: /zh/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 DataBar Omni‑Directional 生成器中调整条码条的高度

如果您需要**调整条码条的高度**以适用于 DataBar Omni‑Directional 条码，本指南将为您提供完整的操作步骤。您将看到一个完整、可运行的 Python 示例，它将条码高度从 30 px 改为 60 px，同时保持 X‑dimension 和图像格式不变。

在条码必须适配特定标签尺寸或设计规范时，改变条码的视觉尺寸是常见需求。除了条码高度，您可能还想微调**X‑dimension**（模块大小）或选择不同的**barcode image format**（如 PNG 或 JPEG）。

在本教程中，您将：

* 安装所需库（GroupDocs.Barcode for Python）
* 创建 DataBar Omni‑Directional 条码生成器
* 使用 `XDimension` 设置模块大小
* 两次调整条码高度属性
* 将生成的图像保存为所需的 **BarCodeImageFormat**

无需任何 GroupDocs API 经验——只需具备基础的 Python 知识。

## 前提条件

开始之前，请确保您已具备：

* 已安装 Python 3.8 或更高版本
* `groupdocs.barcode` 包（`pip install groupdocs-barcode`）  
* 对保存 PNG 文件的文件夹具有写入权限

如果您不熟悉 **DataBar Omni‑Directional 条码**，它编码 14 位 GTIN，广泛用于零售业，可从任意方向进行扫描。

## 第 1 步：设置 DataBar Omni‑Directional 条码生成器

首先，导入必要的类并使用您想要编码的 GTIN 数据实例化生成器。

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*为什么重要：* `EncodeTypes.DatabarOmniDirectional` 常量告诉库生成 Omni‑Directional 符号。数据字符串中包含 AI `(01)`，标识 GTIN‑14 值。

## 第 2 步：定义 X‑dimension（模块大小）

X‑dimension 控制最窄条的宽度。屏幕渲染的常用值是 **每模块 2 px**。

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

使用一致的 **set XDimension** 可确保条码在不同打印机和扫描仪上正确缩放。

## 第 3 步：将条码高度调整为 30 px 并保存图像

现在我们更改条码高度属性。首次使用的高度为 **30 px**，适用于小标签。

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` 常量选择 **barcode image format** PNG，能够保持无损质量。

### 预期结果

文件 `DatabarBarHeight30Pixels.png` 包含一个条码高度为 30 px 的 DataBar Omni‑Directional 条码。以下是占位预览：

![DataBar 条码（30 px 条高度）](images/databar_30px.png "DataBar 条码（30 px 条高度）")

> **提示：** 如果在图像编辑器中打开 PNG，您会看到精确的条码高度。窄条宽度为 2 px，正如前面定义的那样。

## 第 4 步：将条码高度更改为 60 px 以获得更高的条码

对于需要更大视觉占位的应用——例如货运标签——您可以将条码高度提升至 **60 px**。

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

仅更改 `BarHeight` 属性；X‑dimension 和编码保持不变，条码仍可被扫描。

## 第 5 步：保存更新后的条码图像

最后，将更高的条码写入第二个 PNG 文件。

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### 预期结果

文件 `DatabarBarHeight60Pixels.png` 显示相同的数据编码，但每条的高度已提升至 60 px。下面展示了视觉差异：

![DataBar 条码（60 px 条高度）](images/databar_60px.png "DataBar 条码（60 px 条高度）")

## 完整、可运行的示例

将所有内容整合在一起，以下是完整脚本，您可以复制粘贴到名为 `adjust_barcode_height.py` 的文件中直接运行。

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

运行脚本：

```bash
python adjust_barcode_height.py
```

您应该会在 `output` 文件夹中看到两个 PNG 文件，每个文件都反映了您设置的条码高度。

## 常见问题与边缘情况

| Question | Answer |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is lossy, so prefer PNG for precise scanning. |
| **What if I need a bar height that isn’t a multiple of 10?** | The `BarHeight.Pixels` property accepts any integer value. Just assign the desired pixel count (e.g., `45`). |
| **Does changing the bar height affect the encoded data?** | No. Only the visual representation changes; the underlying data string remains identical. |
| **How do I change the X‑dimension after saving the first image?** | You can modify `gen.parameters.barcode.x_dimension.pixels` at any time before calling `save()`. The change will apply to subsequent images. |
| **Is the generator thread‑safe?** | The `BarcodeGenerator` instance is not guaranteed to be thread‑safe. Create a separate instance per thread if you generate barcodes concurrently. |

## 结论

您现在已经掌握了如何使用 Python 在 DataBar Omni‑Directional 条码生成器中**调整条码条的高度**。本教程涵盖了创建生成器、设置 **X‑dimension**、修改 **barcode bar height** 属性以及以所需的 **barcode image format** 保存图像的完整流程。

接下来，您可以尝试其他高度、不同的模块大小，或切换到 JPEG、BMP 等其他图像格式。还可以探索更多 **barcode generator python** 功能，例如添加可读文本或更改配色方案。

祝编码愉快，保持条码清晰、尺寸恰当！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 的其他功能，并在项目中探索替代实现方式。每篇资源均提供完整的可运行代码示例和逐步解释。

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}