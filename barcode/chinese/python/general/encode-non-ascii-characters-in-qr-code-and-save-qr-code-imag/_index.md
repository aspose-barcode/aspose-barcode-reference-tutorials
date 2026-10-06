---
category: general
date: 2026-09-10
description: 使用简单的 Python 构建器对 QR 码进行非 ASCII 字符编码并保存 QR 码图像。按照使用 ExtCodetextBuilder
  和 BarcodeGenerator 的分步指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: zh
lastmod: 2026-09-10
og_description: 使用 Python 对 QR 码进行非 ASCII 字符编码并保存 QR 码图像。本教程展示如何构建扩展的代码文本、生成 QR 码以及保存图像。
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: 在二维码中编码非 ASCII 字符并保存二维码图像 – 步骤详解 Python 指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: 在二维码中编码非 ASCII 字符并保存二维码图像
url: /zh/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 QR 码中编码非 ASCII 字符并保存 QR 码图像

如果您需要在 QR 码中 **编码非 ASCII 字符**，本指南将向您展示具体操作步骤，并随后 **将 QR 码图像** 保存到磁盘。无论是处理俄语、中文还是表情符号数据，ExtCodetextBuilder 都可以让您在不手动处理字节的情况下混合普通文本和 ECI 编码段。

您将学习如何创建扩展码文本字符串、生成能够识别该字符串的 QR 码，并最终将条形码图像写入文件。本教程假设您具备基础的 Python 知识，并已安装 `barcode` SDK。

## 前置条件

* 已安装 Python 3.8+。
* 包含 `ExtCodetextBuilder`、`CodetextEncodingType` 和 `BarcodeGenerator` 的 `barcode` Python 包（或相应的 SDK）。
* 对您希望 **保存 QR 码图像** 的目录拥有写入权限。

您可以使用 pip 安装 SDK（将 `barcode-sdk` 替换为实际的包名）：

```bash
pip install barcode-sdk
```

## 步骤 1：创建扩展码文本构建器

第一步是实例化 `ExtCodetextBuilder`。该对象收集多个文本段并生成 QR 码符号能够解释的单一字符串。

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*为什么这很重要*：QR 码支持 **扩展码文本**，这意味着您可以在同一个条码中嵌入多种编码模式（普通、ECI 等）。构建器抽象了 QR 规范所需的底层格式化。

## 步骤 2：添加普通文本段

普通文本是默认模式，适用于 ASCII 字符。首先添加它可以为忽略 ECI 的扫描仪提供可读的回退。

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

如果省略此步骤，QR 码将仅包含 ECI 段，某些旧版读取器可能无法正确解码。

## 步骤 3：为非 ASCII 字符添加 ECI 编码段

要包含 ASCII 范围之外的字符——如西里尔字母、中文或表情符号——必须指定 ECI（扩展通道解释）编码。这里我们使用 UTF‑8 对俄语单词 “Привет” 进行编码。

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*为什么可行*：QR 规范定义了 ECI 值，告知扫描仪使用哪种字符集。若没有 ECI 标记，原始字节会被解释为 ISO‑8859‑1，导致输出乱码。

## 步骤 4：获取合并后的扩展码文本字符串

在添加完所有所需段后，调用 `get_extended_codetext()` 获取条码生成器期望的最终字符串。

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

打印的值看起来像是一系列控制字符后跟实际文本，但您无需手动解析它。

## 步骤 5：使用扩展码文本生成 QR 码

现在创建 `BarcodeGenerator`，将符号设置为 QR（唯一支持扩展码文本的常见二维符号），并提供合并后的字符串。

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*提示*：如果尝试在 Code‑128 或 DataMatrix 上使用相同过程，SDK 将抛出异常，因为这些格式无法解释 ECI 标记。

## 步骤 6：保存 QR 码图像

最后，将条码写入 PNG 文件。这就是您 **保存 QR 码图像** 以供后续使用的地方。

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

在调用 `save` 之前，请确保 `output` 文件夹已存在，或使用 `os.makedirs('output', exist_ok=True)` 创建它。

### 完整可运行示例

将所有步骤组合在一起，即可得到一个可立即运行的独立脚本：

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**预期输出**（控制台）：

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

使用任何 QR 扫描仪打开 `qr_extended.png` 将显示 `HelloWorldПривет`。能够识别 ECI 的扫描仪会正确呈现西里尔字符；其他扫描仪则仅显示 ASCII 部分。

## 常见问题与边缘情况

| Question | Answer |
|----------|--------|
| *我可以使用其他编码如 Shift‑JIS 吗？* | 可以。将 `CodetextEncodingType.UTF_8` 替换为 `CodetextEncodingType.SHIFT_JIS` 并提供相应的文本。 |
| *如果合并后的数据超出 QR 码容量怎么办？* | QR 码有版本限制（最大 177 × 177 模块）。如果构建器抛出大小异常，可提升纠错级别或将数据拆分到多个 QR 码中。 |
| *我需要设置特定的 QR 版本吗？* | SDK 会自动选择最小的适配数据的版本。如有需要，可使用 `qr_generator.set_qr_version(10)` 强制指定版本。 |
| *图像会是透明的吗？* | 默认情况下 SDK 会生成带白色背景的 PNG。如需透明，请在 `save` 前使用 `qr_generator.set_background_color(Color.Transparent)`。 |

## 结论

在本教程中，您学习了如何使用 `ExtCodetextBuilder` 在 QR 码中 **编码非 ASCII 字符**，以及随后使用 `BarcodeGenerator` **保存 QR 码图像**。该过程包括构建扩展码文本字符串、添加普通和 ECI 编码段、生成 QR 符号，最后写入图像文件。

接下来您可以探索：

* 添加更多 ECI 段（不同语言或表情符号）。
* 调整 QR 纠错级别以提升可靠性。
* 将生成的 PNG 嵌入 PDF 或网页中。

祝编码愉快，尽情创建多语言 QR 码吧！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，帮助您进一步学习。每个资源都包含完整的可运行代码示例和逐步解释，助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose.Barcode 在 Python 中生成 QR 码图像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [使用 Aspose.Barcode Python 生成 Code128 条码 – 完整指南](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [使用 Python 条码库显示产品名称 – 步骤指南](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}