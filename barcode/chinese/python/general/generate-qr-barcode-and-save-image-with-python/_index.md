---
category: general
date: 2026-11-27
description: 使用 Aspose.Barcode 在 Python 中生成 QR 条码，并快速学习如何将条码图像保存到磁盘。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: zh
lastmod: 2026-11-27
og_description: 使用 Aspose.Barcode 在 Python 中生成 QR 条码并即时保存条码图像。按照完整示例创建、定制和存储 QR 码。
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: 使用 Python 生成 QR 条码并保存图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: 使用 Python 生成二维码并保存图像
url: /zh/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Python 生成 QR 条码并保存图像

如果您需要在 Python 应用程序中 **生成 QR 条码**，本指南将展示如何使用 Aspose.Barcode 库实现。您还将学习如何正确 **保存条码图像** 到本地文件夹、获取库版本信息以及处理扩展的 codetext 段。

创建 QR 码是票务系统、移动支付和产品追踪等场景的常见需求。完成本教程后，您将拥有一个可直接运行的脚本，能够生成 QR 条码图像文件并打印版本信息，以便调试或合规使用。

## 前置条件

开始之前，请确保您已经：

* 安装了 Python 3.8 或更高版本。
* 安装了 `aspose-barcode` 包。使用 `pip install aspose-barcode` 进行安装。
* 对将存放条码图像的目录拥有写入权限。

无需额外的外部服务；整个过程均在本地完成。

## 第一步：使用 `ExtCodetextBuilder` 构建扩展的 codetext

扩展的 codetext 允许在同一个 QR 码中混合普通文本和 ECI（扩展通道解释）段。这在需要嵌入不同字符集（例如欧元符号）时非常有用。

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**此步骤的重要性：**  
`ExtCodetextBuilder` 负责组装 QR 编码器将要处理的最终字符串。如果不构建扩展的 codetext，条码只能包含普通 ASCII 字符，无法表示特定语言的符号。

## 第二步：获取组合后的扩展 codetext 字符串

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

输出示例：

```
Extended codetext: ABC123[ECI3]€123
```

方括号中的 `[ECI3]` 标记告诉 QR 编码器在后续字符中切换到指定的字符集。

## 第三步：使用扩展 codetext 生成 QR 条码

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**说明：**  
`BarcodeGenerator` 接收两个参数：条码类型（`QR`）和要编码的数据（`extended_codetext`）。生成器会准备渲染所需的所有内部结构。

## 第四步：保存生成的条码图像

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**为何推荐这种方式：**  
直接调用 `save` 会根据文件扩展名推断图像格式并写入磁盘。该方法支持 PNG、JPEG、BMP 和 TIFF，能够满足不同下游使用者的需求。

### 验证已保存的图像

使用任意图像查看器打开文件 `output/qr_extended.png`。您应该看到一个 QR 码，扫描后返回字符串 `ABC123€123`。大多数现代手机 QR 扫描器会自动处理 ECI 段。

## 第五步：查询 Aspose.BarCode 版本信息（可选但有用）

了解 Aspose.BarCode 库的确切版本有助于报告错误或验证兼容性。

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

典型输出：

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## 完整脚本 – 复制、粘贴并运行

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

运行脚本后会生成 QR 码图像，并在控制台打印扩展 codetext 与版本信息。

## 常见变体和边缘情况

| 情况 | 推荐调整 |
|-----------|------------------------|
| **不同字符集** | 将传递给 `add_eci_codetext` 的 ECI 标识符改为相应值。UTF‑8 使用 `5`。 |
| **更高的错误纠正级别** | 在调用 `save` 之前设置 `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H`。 |
| **自定义图像尺寸** | 使用 `barcode.parameters.image_width` 和 `barcode.parameters.image_height` 控制像素大小。 |
| **非 PNG 输出** | 将 `output_path` 中的文件扩展名改为 `.jpg` 或 `.bmp`，库会自动选择相应的编码器。 |

## 专业技巧

* **如果输出文件夹可能不存在，使用代码自动创建：**

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **生成后通过 `aspose.barcode.BarcodeReader` 验证 QR 码**，确保编码数据符合预期，尤其是在使用 ECI 段时。

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **性能技巧** – 在循环中大量生成 QR 码时，复用同一个 `BarcodeGenerator` 实例。通过重设 `code_text` 属性而不是每次创建新对象来提升效率。

## 结论

现在您已经掌握了如何使用 Aspose.Barcode 在 Python 中 **生成 QR 条码**、构建混合普通文本和 ECI 段的扩展 codetext，并正确 **保存条码图像** 到磁盘。脚本还演示了如何获取库版本信息以便排查问题。

接下来您可以进一步探索：

* 为 QR 码添加徽标叠加或自定义颜色。
* 使用 Aspose.PDF 将 QR 条码直接嵌入 PDF 文档。
* 为大批量数据实现批量生成自动化。

欢迎尝试不同的数据负载、错误纠正级别和图像格式。祝编码愉快！


## 接下来您可以学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}