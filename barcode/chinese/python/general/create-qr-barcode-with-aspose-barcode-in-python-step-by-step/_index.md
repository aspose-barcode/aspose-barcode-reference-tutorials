---
category: general
date: 2026-08-09
description: 使用 Aspose.BarCode 在 Python 中创建 QR 条码。学习如何构建扩展码文本、调整外观并保存图像——全部在一个教程中。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: zh
lastmod: 2026-08-09
og_description: 使用 Aspose.BarCode 在 Python 中创建 QR 条码。本指南展示了如何构建扩展码文本、设置视觉参数以及导出图像。
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: 使用 Aspose.BarCode 在 Python 中创建 QR 条码 – 完整代码示例
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: 使用 Aspose.BarCode 在 Python 中创建 QR 条码 – 步骤指南
url: /zh/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Python 中创建 QR 条码 – 步骤指南

如果您需要在 Python 中**创建 QR 条码**，本教程将使用 Aspose.BarCode 库手把手带您完成整个过程。无论是对产品 ID、多语言文本还是自定义数据进行编码，您都将看到如何构建扩展码文本、微调视觉设置，并在一个可直接运行的脚本中保存最终图像。

示例还演示了如何显示库版本，以帮助您确认正在使用兼容的发行版。阅读完本指南后，您将拥有可直接使用的 QR 条码图像，并清晰了解每个配置选项的作用。

## 前置条件

开始之前，请确保您已具备：

- 已安装 Python 3.8+。
- `aspose-barcode` 包（通过 `pip install aspose-barcode` 安装）。
- 对 Python 语法有基本了解。
- 对将保存 PNG 文件的输出目录拥有写入权限。

> **专业提示：** 使用虚拟环境可避免与其他项目的版本冲突。

## 第 1 步：验证 Aspose.BarCode 库版本

显示库版本可确保您使用的发行版支持扩展码文本和 QR 编码。

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**为什么重要：**  
旧版可能缺少用于混合普通和 ECI 段的 `ExtCodetextBuilder` 类。确认版本可以防止后续工作流中出现运行时错误。

## 第 2 步：构建扩展码文本字符串

扩展码文本允许您将普通 ASCII 数据与 Unicode（ECI）段组合，这对于多语言 QR 码至关重要。

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**为什么重要：**  
`add_plain_codetext` 方法以标准 ASCII 存储数据，而 `add_eci_codetext` 会在 Unicode 块前加上相应的 ECI 标识符。此做法确保 QR 扫描器能够正确解释日文文本，避免出现乱码。

### 常见变体

- **多个 ECI 段：** 多次调用 `add_eci_codetext` 可混合多种语言。
- **不同的 ECI 标识符：** 根据目标编码使用 `27` 表示 ISO‑8859‑1、`28` 表示 ISO‑8859‑2 等。

## 第 3 步：使用扩展码文本生成 QR 条码

有了正确格式的字符串后，即可创建 QR 码。

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**为什么重要：**  
`EncodeTypes.QR` 告诉 Aspose.BarCode 使用 QR 符号。直接传入 `extended_codetext` 可将混合数据映射到 QR 矩阵中，保留普通和 Unicode 部分。

## 第 4 步：调整视觉外观（可选但推荐）

微调条码的视觉参数可提升扫描可靠性并符合品牌规范。

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**为什么重要：**  
- **`x_dimension`** 控制每个 QR 模块的大小；过小可能导致低分辨率设备读取错误。  
- **`border_width`** 添加安静区。部分扫描器要求至少 4 模块的安静区；库会自动添加，但您可以增大以获得额外安全性。

### 边缘情况处理

- **高密度数据：** 若编码数据量大，可能需要增大 `x_dimension` 或通过 `qr_generator.parameters.qr.error_correction_level` 选择更高的纠错级别。  
- **透明背景：** 将 `qr_generator.parameters.barcode.bg_color = Color.Transparent` 设置为 PNG 的透明通道。

## 第 5 步：保存 QR 条码图像

最后，将图像写入磁盘，使用您偏好的格式。

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**为什么重要：**  
保存为 PNG 可保留无损质量，适合需要清晰边缘的 QR 码。如果 Web 应用需要其他格式，只需更改 `BarCodeImageFormat` 枚举即可。

### 验证结果

在任意图像查看器中打开保存的文件。您应看到一个 QR 码，扫描后返回组合后的字符串：

```
ABC12345
こんにちは
```

大多数现代 QR 扫描应用会先显示普通段，然后正确渲染日文问候语。

---

## 完整可运行脚本

将下方代码块完整复制到名为 `create_qr_barcode.py` 的文件中，并使用 `python create_qr_barcode.py` 运行。将 `YOUR_DIRECTORY` 替换为您机器上可写入的文件夹路径。

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

运行此脚本后会打印库版本、扩展码文本以及 PNG 文件创建成功的确认信息。

---

## 结论

您现在已经掌握了使用 Aspose.BarCode 在 Python 中**创建 QR 条码**图像的方法。教程涵盖了：

1. 验证库版本。  
2. 使用普通和 ECI（Unicode）段构建扩展码文本。  
3. 生成 QR 码。  
4. 自定义模块大小、边框宽度等视觉参数。  
5. 以 PNG 格式保存最终图像。

接下来您可以进一步探索：

- 更改纠错级别 (`qr_generator.parameters.qr.error_correction_level`)。  
- 添加徽标或背景图像 (`qr_generator.parameters.qr.logo`)。  
- 导出为 SVG 等可缩放的 Web 图形格式。  
- 将生成器集成到 Flask 或 Django 接口，实现即时 QR 码生成。

尝试不同的数据负载和视觉设置，以匹配您应用的品牌和扫描需求。祝编码愉快！

## 接下来您可以学习什么？

以下教程与本指南紧密相关，帮助您进一步掌握 API 功能并探索在项目中的其他实现方式。

- [如何使用 Aspose.BarCode for .NET 为 dotcode 创建扩展码文本](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [创建条码 Aspose .NET - 配置 DataMatrix 码文本](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [如何使用 Aspose.BarCode for .NET 为 ITF-14 创建条码静区](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}