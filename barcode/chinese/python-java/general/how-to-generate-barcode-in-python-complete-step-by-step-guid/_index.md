---
category: general
date: 2026-08-12
description: 如何使用 Python 快速生成条形码。学习从数据创建条形码并使用单一库导出条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: zh
lastmod: 2026-08-12
og_description: 如何使用 Aspose.BarCode 在 Python 中生成条形码。请按照本指南从数据创建条形码并将条形码图像导出为 PNG。
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: 如何在 Python 中生成条形码——快速可靠的指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: 如何在 Python 中生成条形码——完整的逐步指南
url: /zh/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中生成条形码 – 完整分步指南

如果您需要在 Python 应用程序中 **如何生成条形码**，本教程将展示您所需的完整代码。您将学习 **从数据创建条形码**、调整其外观，以及 **导出条形码图像** 为 PNG 文件——全部代码不超过十行。

生成条形码看似与业务逻辑无关，但只需一个库即可将其流程直接嵌入现有代码库。接下来的章节中，您将看到一个完整、可运行的示例，了解每行代码的意义，并发现常见的变体，例如更改模块宽度或绘制仅轮廓的条形码。

## 如何使用 Aspose.BarCode 库生成条形码

Aspose.BarCode for Python（通过 .NET）提供了简洁的 API，支持多种符号体系，包括本指南使用的 Planet 条形码。开始之前，请确保已安装该包：

```bash
pip install aspose-barcode
```

> **专业提示：** 使用虚拟环境可以避免与其他项目的版本冲突。

### 1. 导入所需类

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

这些导入让您可以访问生成器类、条形码类型枚举以及保存结果时使用的图像格式枚举。

### 2. 从数据创建条形码

第一步是 **从数据创建条形码**。`BarcodeGenerator` 构造函数接受符号体系和要编码的原始字符串。

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`EncodeTypes.Planet` 选择 Planet 条形码，而 `"123456"` 则是最终图像中显示的有效负载。

### 3. 调整 X 维度（模块宽度）

X 维度控制每个条形码模块（细条）的宽度。将其设为 4 像素可获得清晰、易读的图像，同时不会使文件过大。

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **为什么重要：** 较大的 X 维度可提升低分辨率打印机的扫描可靠性，而较小的数值则可在网页使用时减小文件体积。

### 4. 导出条形码图像（实心样式）

现在可以使用 `save` 方法 **导出条形码图像**。示例保存为 PNG 文件，您也可以通过更改 `BarCodeImageFormat` 枚举来选择 JPEG、BMP 或 TIFF。

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

文件 `PlanetFilled.png` 包含完整实心的 Planet 条形码，可直接用于打印或嵌入 PDF。

### 5. 为仅轮廓条形码创建第二个生成器

如果需要仅轮廓版本（空心条），必须创建新生成器，因为在图像保存后 `filled_bars` 标志无法再切换。

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. 应用相同的 X 维度设置

创建第二个生成器时，需要再次设置所有希望保持一致的视觉参数。

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. 为轮廓条形码禁用实心条

将 `filled_bars` 设置为 `False` 告诉渲染器仅绘制每个模块的轮廓，生成的图像更轻，可用于设计需求。

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. 导出轮廓条形码图像

最后，再次 **导出条形码图像**，这次保存的是轮廓版本。

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

现在您拥有两个 PNG 文件：一个实心条（`PlanetFilled.png`），一个仅轮廓条（`PlanetEmpty.png`）。

## 以其他格式导出条形码图像（可选）

`save` 方法支持多种格式。以 90% 质量导出 JPEG：

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

如果需要用于网页的透明背景，请选择带 alpha 通道的 PNG：

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## 常见变体和边缘情况

| 场景 | 需要的更改 | 代码片段 |
|----------|---------------|--------------|
| **不同符号体系**（例如 QR） | 使用不同的 `EncodeTypes` 值 | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **自定义前景色** | 设置 `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **更高分辨率** | 通过 `image_width` 和 `image_height` 增加 DPI | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **大数据字符串** | 确保数据长度符合符号体系规范 | 在创建生成器前验证长度 |

> **注意：** 提供超出所选符号体系最大长度的数据会抛出运行时异常。请始终验证字符串长度或捕获 `ArgumentException`。

## 完整可运行示例

下面是完整脚本，您可以复制粘贴到名为 `generate_planet_barcode.py` 的文件中。将 `YOUR_DIRECTORY` 替换为您机器上实际存在的文件夹路径。

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

运行此脚本后，会在指定目录生成两个 PNG 文件。使用任意图像查看器打开它们，您应看到编码字符串 `123456` 的 Planet 条形码。

## 结论

现在您已经掌握了 **如何在 Python 中生成条形码**，了解了 **从数据创建条形码** 的方法，并能够 **导出条形码图像**（实心和轮廓两种样式）。相同的模式同样适用于其他符号体系、图像格式和视觉自定义，为您在应用程序中实现任何条形码相关功能提供了灵活的基础。

### 后续步骤

* 通过将 `EncodeTypes.Planet` 替换为其他值，探索 QR、Code‑128、DataMatrix 等符号体系。  
* 使用 `ReportLab` 或 `PyPDF2` 等库将生成的 PNG 文件嵌入 PDF 报告。  
* 试验动态 X 维度值，以根据屏幕分辨率或打印机 DPI 自动调整条形码大小。

祝编码愉快，欢迎根据项目需求自由改进示例！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您进一步掌握 API 功能并探索替代实现方式：

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}