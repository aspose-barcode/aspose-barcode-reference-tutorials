---
category: general
date: 2026-08-22
description: 学习在 Python 中生成 DataMatrix 条码并使用 Aspose.BarCode 编码俄文文本——一步一步的指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: zh
lastmod: 2026-08-22
og_description: 在 Python 中生成 DataMatrix 条码并使用 Aspose.BarCode 对俄文文本进行编码。遵循完整示例并立即运行。
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: 在Python中生成DataMatrix条码 – 完整的Aspose.BarCode教程
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: 如何使用 Aspose.BarCode 在 Python 中生成 DataMatrix 条码
url: /zh/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.BarCode 生成 DataMatrix 条码

如果您需要在 Python 中 **生成 DataMatrix 条码** 并 **对俄文文本进行编码**，本指南将展示完整的步骤。您将看到一个可直接运行的示例，构建扩展的 codetext、配置条码并在单个脚本中保存图像。

创建包含非 ASCII 字符的条码时，常会遇到字符集和数据编码的问题。通过使用 Aspose.BarCode 的 `ExtCodetextBuilder`，您可以安全地在 DataMatrix 符号中嵌入 UTF‑8 文本（如西里尔字母）。该结果可被任何支持 DataMatrix 标准的扫描仪读取。

在本教程中，您将：

* 安装所需的 Aspose.BarCode 包。
* 构建混合普通数据和俄文文本的扩展 codetext。
* **生成 DataMatrix 条码** 并使用扩展字符串。
* 调整条码参数，如模块大小。
* 将条码保存为 PNG 文件。

无需任何外部服务；所有操作均在本机本地完成。

## 前提条件

开始之前，请确保您具备：

* 已安装 Python 3.8 或更高版本。
* 有效的 Aspose.BarCode for Python 许可证（免费试用版可用于开发）。
* 基本的 Python 脚本编写经验。

您可以通过 pip 安装 Aspose.BarCode 库：

```bash
pip install aspose-barcode
```

## 第一步：构建扩展 codetext 字符串

首要任务是创建一个包含普通产品标识符和俄文短语的单一字符串。`ExtCodetextBuilder` 允许您在保留各段编码信息的前提下拼接不同的 codetext 部分。

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**此步骤的重要性** – DataMatrix 符号存储的是原始字节。当需要混合不同字母表时，必须告诉编码器每个段使用的字符集。`add_eci_codetext` 方法会在俄文文本前插入 ECI 指示符，确保扫描仪将这些字节解释为 UTF‑8。若未使用 ECI，西里尔字符将显示为乱码。

## 第二步：创建 DataMatrix 条码生成器

准备好扩展 codetext 后，实例化一个指定 `EncodeTypes.DATA_MATRIX` 类型的 `BarcodeGenerator`。

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**为何选择 DataMatrix？** – DataMatrix 是一种二维条码，可存储最多 2,335 个字母数字字符或 1,556 字节。它非常适合小件商品、工业部件以及需要嵌入多语言文本的场景。

## 第三步：（可选）配置条码参数

Aspose.BarCode 提供了众多参数。对于大多数使用场景，默认设置即可生成可读的符号。但您可能需要控制每个模块（矩阵中最小的方块）的大小，以满足打印需求。

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

其他有用的参数包括错误纠正级别、边距和背景颜色。仅在目标扫描环境对容差有特定要求时才进行调整。

## 第四步：保存条码图像

最后，将条码写入文件。`save` 方法支持 PNG、JPEG、BMP 以及多种矢量格式。

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

打开 `extended_codetext.png`，您将看到清晰的 DataMatrix 符号。使用标准 DataMatrix 读取器扫描后，会得到两部分内容：

1. **ABC123** – 普通标识符。
2. **Привет** – 俄文问候语，已正确解码为 UTF‑8。

## 完整、可运行的示例

下面是完整脚本，您可以复制粘贴到名为 `generate_datamatrix.py` 的文件中。将 `YOUR_DIRECTORY` 替换为系统中实际存在的文件夹路径。

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

在命令行运行脚本：

```bash
python generate_datamatrix.py
```

您应看到类似以下的控制台输出：

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## 验证结果

确认条码正确编码俄文短语的步骤：

1. 在图像查看器中打开 PNG 文件。
2. 使用任意 DataMatrix 扫描应用（许多移动应用均支持）或硬件扫描仪。
3. 解码后的字符串应显示为 `ABC123Привет`（或根据扫描器 UI 将两部分分开显示）。

如果俄文字符出现乱码，请再次确认扫描仪支持 ECI UTF‑8。大多数现代读取器都支持，但旧设备可能需要显式配置。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 西里尔字符乱码 | 缺少 ECI 指示符 | 使用 `add_eci_codetext` 并将 `eci_encoding=3` |
| 条码对打印机太小 | 默认模块尺寸对低 DPI 打印机过细 | 增大 `x_dimension`（例如 `3.0` 或 `4.0`） |
| 文件未保存 | 目录路径无效 | 确认 `YOUR_DIRECTORY` 存在且可写 |
| 扫描仪无法读取 | 数据密度过高 | 减少编码数据量或提升错误纠正级别 (`generator.parameters.barcode.error_correction_level`) |

## 扩展示例

您可以将此模式用于其他语言或数据类型：

* **编码日文或阿拉伯文** – 将 `eci_encoding` 改为相应的值（例如 ISO‑8859‑5 为 5，ISO‑8859‑7 为 6）。  
* **添加多个 ECI 段** – 多次调用 `add_eci_codetext`，每次使用不同的编码。  
* **改为生成 QR 码** – 将 `EncodeTypes.DATA_MATRIX` 替换为 `EncodeTypes.QR`。  

其他步骤保持不变，因为 `ExtCodetextBuilder` 已抽象了底层字节处理。

## 结论

现在，您已经掌握了如何在 Python 中使用 Aspose.BarCode 的扩展 codetext 功能 **生成 DataMatrix 条码** 并 **对俄文文本进行编码**。完整脚本仅用几行代码就完成了字符集协商、条码创建和图像输出。

接下来，您可以探索其他条码符号（PDF417、Aztec），或将生成器集成到返回 PNG 图像的 Web 服务中。同样的原理——构建扩展 codetext 并选择合适的 `EncodeTypes`——在整个 Aspose.BarCode 套件中均适用。

祝编码愉快，尽情享受多语言条码生成的强大功能！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步说明。

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}