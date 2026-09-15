---
category: general
date: 2026-07-30
description: 在 Python 中创建 Databar Stacked Omnidirectional 条码。按照本分步指南配置宽高比、XDimension，并使用
  Python 条码生成器导出 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: zh
lastmod: 2026-07-30
og_description: 在 Python 中创建 Databar Stacked Omnidirectional 条码。本教程展示如何设置 XDimension、调整
  DataBar 长宽比，并使用 BarCodeImageFormat 将其保存为 PNG。
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: 创建 Databar 堆叠全向条码 – Python 教程
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
title: 在 Python 中创建堆叠式全方向 Databar 条码
url: /zh/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中创建 Databar 堆叠全向条形码

是否曾经需要在 Python 中**创建 databar 堆叠全向**条形码，却不知从何入手？你并不孤单——许多开发者在第一次使用 `BarcodeGenerator` 类时都会遇到这个难题。好消息是，一旦了解关键属性，整个过程其实相当简单。

在本指南中，我们将通过一个完整、可运行的示例，使用**python barcode generator**设置 XDimension、微调 DataBar 长宽比，最终导出两个 PNG 文件。完成后，你将对如何为任何库存或物流项目生成高质量堆叠全向符号有深入了解。

## 您将学习

- 如何使用 GTIN‑14 负载实例化一个 **databar 堆叠全向** 生成器。  
- 为什么 **XDimension 像素大小** 对扫描可靠性至关重要。  
- **DataBar 长宽比** 对行宽与高度的影响。  
- 如何将结果保存为 **BarCodeImageFormat PNG** 文件。  
- 重复使用同一生成器对象生成多个变体而不增加额外内存开销的技巧。

### 前置条件

- Python 3.8+（我们使用的库是纯 Python，无需编译轮子）。  
- `barcode-generator` 包（通过 `pip install barcode-generator` 安装）。  
- 一个可写入的文件夹——脚本会在其中导出两个 PNG 图像。

如果你已经熟悉基本的 Python 导入和面向对象代码，就可以开始了。

## 创建 Databar 堆叠全向条形码 – 步骤概览

下面我们将工作流拆分为六个小步骤。每个步骤都是一个独立的代码块，你可以复制粘贴到 REPL 或脚本文件中。随意实验——更改长宽比或 XDimension 会立即呈现不同的视觉风格。

---

## 步骤 1：创建 Databar 堆叠全向生成器

首先，我们 **创建 databar 堆叠全向** 生成器实例，传入相应的 `EncodeTypes` 枚举和数据字符串。

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **为什么重要：** `EncodeTypes.DatabarStackedOmniDirectional` 标志告诉库生成堆叠全向符号，这是唯一能够编码最多 14 位且在任何角度都可读取的 DataBar 变体。

---

## 配置 XDimension 像素大小

**XDimension 像素大小** 控制最小模块（最细的黑条）。`2` 像素在大多数屏幕显示场景下表现良好。

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **专业提示：** 如果计划在高 DPI 打印条形码，请将此值提升至 3 或 4，以避免出现模糊边缘。

---

## 调整 DataBar 长宽比 (15)

**DataBar 长宽比** 决定每行相对于其高度的宽度。`15` 的长宽比会产生更宽的行，许多扫描器在快速运动捕获时更偏好这种布局。

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **为什么选 15？** 官方 GS1 规范建议堆叠全向符号的长宽比在 10 到 20 之间。我们选择 `15` 作为平衡的默认值。

---

## 使用 BarCodeImageFormat 导出 PNG 条形码

生成器配置完成后，我们将图像持久化。`BarCodeImageFormat.Png` 枚举确保无损输出，适合后续处理。

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **你会看到：** 打开生成的 PNG，应该能看到一张干净、高对比度的条形码，行宽相对较宽。

---

## 将 DataBar 长宽比改为 30

有时需要更高的行而不是更宽的行——比如要适配窄标签。将 **DataBar 长宽比** 改为 `30` 可让每行更高。

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **边缘情况：** 非常高的比例（例如 >40）可能导致条形码超出常规标签高度，务必在真实打印机上测试后再使用。

---

## 使用新长宽比再次导出条形码

最后，我们复用同一个 `barcode_generator` 对象写出第二个 PNG。无需重新创建生成器——只需更改属性并再次调用 `Save` 即可。

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **结果：** 现在你拥有两个 PNG 文件——一个宽行（`AR15`），另一个高行（`AR30`）。并排比较即可决定哪种更适合你的扫描器设置。

---

## 完整工作示例

将所有步骤组合在一起，以下是可直接运行的完整脚本。请将 `YOUR_DIRECTORY` 替换为你机器上的绝对路径。

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

**预期输出**（在控制台中）：

```
✅ Two PNG files created – AR15 and AR30
```

并且两个图像文件会出现在目标文件夹中，随时可用于扫描测试。

---

## 结论

我们已经在 Python 中**创建了 databar 堆叠全向**条形码，调整了 **XDimension 像素大小**，尝试了两种不同的 **DataBar 长宽比** 设置，并将结果导出为 **BarCodeImageFormat PNG** 文件。整个工作流仅需几行代码，却能让你完全掌控对扫描器最关键的视觉特性。

接下来可以尝试将负载换成其他 GTIN，或通过将 PNG 转为调色板图像来玩转颜色，亦或生成包含两张 PNG 的 PDF 报告。`BarcodeGenerator` 类足够灵活，能够应对所有这些场景，尽情实验吧。

如果对特定使用场景有疑问或遇到错误，欢迎在下方留言，我会很乐意帮助。祝编码愉快！

## 接下来你应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在自己的项目中进一步掌握 API 功能并探索替代实现方式。每个资源都提供完整的可运行代码示例和逐步解释。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}