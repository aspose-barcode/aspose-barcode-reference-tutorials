---
category: general
date: 2026-10-24
description: 条形码生成器示例，展示如何使用 Python 创建 Planet 条码以及如何设置条码高度。请按照分步指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: zh
lastmod: 2026-10-24
og_description: 条形码生成器示例，演示如何在 Python 中创建 Planet 条码以及如何设置条码高度。获取完整、可运行的解决方案。
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: 条码生成器示例 – 创建 Planet 和 RM4SCC 条码
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: 条形码生成器示例——使用自定义高度创建 Planet 和 RM4SCC 条码
url: /zh/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成示例 – 使用自定义高度创建 Planet 和 RM4SCC 条形码

如果你在寻找 **条形码生成示例**，本指南提供了一个完整、可直接运行的解决方案。你将看到 **如何创建 Planet 条形码** 图像，学习 **如何设置条形码高度**，并了解自动与手动尺寸之间的细微差别。

本教程通过两个真实场景进行演示：使用默认（自动）高度的 Planet 条形码，以及将高度强制为 100 px 的 RM4SCC 条形码。完成后，你可以使用统一的 API 为任何受支持的条形码类型生成 PNG 文件。

## 前置条件

开始之前，请确保你已具备：

* 已安装 Python 3.8 或更高版本。
* `aspose-barcode` 包（或任何提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的库）。使用以下方式安装  

  ```bash
  pip install aspose-barcode
  ```
* 对将保存 PNG 文件的文件夹拥有写入权限。

无需其他系统依赖。

## 解决方案概览

**条形码生成示例**的核心由三个可复用步骤组成：

1. **实例化** `BarcodeGenerator`，并指定所需的 `EncodeTypes` 值和数据字符串。
2. **配置** X 维度（模块宽度），必要时设置条形码高度。
3. **保存** 图像为 PNG 格式到磁盘。

两个示例共用步骤 1 和 3；只有步骤 2 不同，因为 Planet 条形码依赖库的自动高度计算，而 RM4SCC 条形码演示了 **如何手动设置条形码高度**。

下面是一张高层次流程图：

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Alt text: Barcode generator example showing Planet and RM4SCC barcodes with different heights.*

## 如何创建 Planet 条形码 – 自动高度

Planet 条形码属于许多国家邮政服务使用的邮政系列。大多数情况下，你让 SDK 决定高度，以保持不同数据长度下的视觉比例正确。

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**工作原理**

* `EncodeTypes.Planet` 告诉库使用 Planet 符号。
* 将 `x_dimension.pixels` 设置为 4，使每个模块宽度为 4 px，这是打印标签的常用默认值。
* 未显式设置高度；SDK 根据数据和 X 维度计算最佳高度，这也是针对邮政编码的最简 **条形码生成示例**。

**预期结果**

生成名为 `PostalPlanetBarHeightAuto.png` 的 2‑D PNG 文件，包含清晰的 Planet 条形码。高度约为 30 px（取决于库版本），宽度为 4 px × 模块数量。

## 如何设置条形码高度 – 自定义 RM4SCC 示例

RM4SCC 是另一种邮政条形码，通常需要固定高度以匹配标签模板。本教程展示了 **如何将条形码高度** 设置为精确的像素值。

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**工作原理**

* `EncodeTypes.RM4SCC` 选择 RM4SCC 符号。
* X 维度保持 4 px，以确保两个条形码的模块尺寸一致。
* `bar_height.pixels = 100` 强制条形码高度恰好为 100 px，覆盖自动计算。当布局要求特定尺寸时，这就是推荐的 **如何设置条形码高度** 方法。

**预期结果**

生成名为 `PostalRM4SCCBarHeight100Pixels.png` 的 PNG 文件，显示高度为 100 px 的 RM4SCC 条形码。宽度仍由 X 维度决定，而高度固定为 100 px，适用于高分辨率标签打印机。

## 完整脚本 – 合并两个示例

如果你希望使用单个脚本生成两张图像，请将以下代码复制到 `generate_barcodes.py` 并运行。

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**脚本说明**

* 两个辅助函数保持代码 DRY（Don’t Repeat Yourself），并便于为其他符号扩展脚本。
* `if __name__ == "__main__":` 保护使文件可以作为模块导入而不执行生成逻辑，这对单元测试很有帮助。
* 所有参数（数据字符串、X 维度、高度）均显式声明，因此该脚本可作为未来项目的参考 **条形码生成示例**。

## 常见问题与边缘情况

| Question | Answer |
|----------|--------|
| *What if I need a different X‑dimension?* | Change `x_dimension.pixels` to the desired module width. Larger values increase overall barcode size proportionally. |
| *Can I generate other image formats?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpg`, `Bmp`, or `Gif` depending on the library’s enum. |
| *What happens if the data string contains invalid characters?* | The generator throws an `ArgumentException`. Validate the data against the symbology’s character set before calling the constructor. |
| *Is it possible to set a minimum height while keeping auto‑scaling?* | Use `gen.parameters.barcode.bar_height.min_pixels = <value>` (if the SDK exposes a `min_pixels` property). This keeps the barcode from shrinking below a readable size. |
| *Do I need to dispose of the generator?* | The `BarcodeGenerator` class implements `IDisposable` in .NET; in Python the garbage collector handles it, but you can call `gen.dispose()` if you create many instances in a loop. |

## 生产环境使用技巧

* **Pro tip:** 将 X 维度和高度值存放在配置文件中，以便在不重新编译的情况下进行调整。
* **Watch out for:** 使用对所选符号来说过小的高度；扫描仪可能无法读取条形码。
* **Performance note:** 生成大批量条形码时，复用同一个 `BarcodeGenerator` 实例并仅在保存之间更改其 `code_text` 属性，可提升速度。

## 结论

本 **条形码生成示例** 展示了 **如何创建 Planet 条形码**（自动尺寸）以及 **如何手动设置条形码高度**（RM4SCC）的完整流程。通过本分步指南，你可以将条形码创建集成到任何 Python 应用中，自定义尺寸，并生成可直接用于打印或数字显示的 PNG 文件。

### 后续步骤

* 探索其他符号，如 `EncodeTypes.Postnet` 或 `EncodeTypes.Code128` —— 同样的模式适用。
* 试验 **如何设置条形码高度** 用于 QR 码或 DataMatrix 符号；大多数库都提供类似的 `bar_height` 属性。
* 将生成器与 PDF 库结合，直接在发票或运单中嵌入条形码。

欢迎自行改编脚本、分享成果，并告诉我们你接下来会添加哪些条形码类型！

## 接下来你应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助你在项目中进一步使用 API 功能并探索其他实现方式。

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}