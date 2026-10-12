---
category: general
date: 2026-09-23
description: 学习如何使用 Aspose.BarCode 在 Python 中生成 Code 128 条码并保存条码图像——一步步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: zh
lastmod: 2026-09-23
og_description: 使用 Aspose.BarCode 在 Python 中生成 Code 128 条形码并保存条形码图像。请按照此完整示例创建、定制并将条形码导出为
  PNG 文件。
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: 生成 Code 128 条形码并保存条形码图像 – Python 指南
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: 如何使用 Aspose.BarCode 生成 Code 128 条形码并保存条形码图像
url: /zh/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 生成 Code 128 条形码并保存条形码图像

如果您需要在 Python 项目中 **生成 Code 128 条形码** 并 **保存条形码图像**，本教程将展示完整步骤。使用 Aspose.BarCode 的 `ExtCodetextBuilder`，您可以在单个负载中嵌入普通文本和 Unicode 段，然后将结果渲染为 PNG 文件。

您将看到一个完整可运行的脚本、每行代码的解释，以及处理 ECI 编码或选择正确输出文件夹等常见陷阱的提示。无需查阅外部文档——直接复制、粘贴并运行即可。

## 前置条件

在开始之前，请确保您已具备：

* 已安装 Python 3.8+。
* 已安装 `aspose.barcode` 包（使用 `pip install aspose-barcode` 安装）。
* 对将保存 PNG 的目录拥有写入权限。

该代码适用于 Aspose.BarCode 支持的任何符号系统，但示例聚焦于 **Code 128**，因为它能够高效编码字母数字数据并支持扩展字符集。

## 第一步：导入所需类

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*为什么要这一步？* 导入类后，您即可使用用于扩展码文本的构建器、用于创建图像的写入器以及在调试库更新时可能有用的版本帮助器。

## 第二步：构建扩展码文本

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` 允许您在单个条形码负载中混合普通 ASCII 和 Unicode 数据。ECI（Extended Channel Interpretation）字节 `0x03` 告诉扫描器后续字节采用 UTF‑8 编码，这对于俄语、中文或阿拉伯语等语言至关重要。

## 第三步：为 Code 128 配置条形码写入器

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

将 `encode_type` 设置为 `CODE_128` 可指示写入器渲染 **Code 128 条形码**。`code_text` 属性接收前一步构建的扩展字符串。

## 第四步：将条形码图像保存为 PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

`save` 方法将条形码写入文件。使用 `BarCodeImageFormat.PNG` 可确保无损压缩，并在 Web 与移动应用中拥有广泛兼容性。

## 第五步（可选）：验证 Aspose.BarCode 库版本

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

了解确切的库版本有助于在报告错误或比较不同版本行为时提供依据。

## 预期输出

运行脚本后，控制台输出类似于：

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

生成的 PNG（`extended_codetext.png`）如下所示：

![Python 生成的 Code 128 条形码已保存为 PNG 图像](images/code128_extended.png)

*该图像展示了一个编码了 ASCII 字符串 `ABC123` 和俄语单词 “Пример” 的 Code 128 条形码。*

## 常见问题与边缘情况处理

| Question | Answer |
|----------|--------|
| **Can I use a different symbology?** | Yes. Replace `BarCodeEncodeMode.CODE_128` with any other supported mode such as `QR`, `EAN_13`, or `PDF_417`. |
| **What if my Unicode text contains emojis?** | Emojis are also UTF‑8 characters, so the same `add_eci_codetext` call works. Ensure the target scanner supports the ECI you use. |
| **How do I change the image size?** | Set `writer.x_dimension` and `writer.bar_height` before calling `save`. |
| **What folder should I use for `output_path`?** | Any folder that the Python process can write to. Use `os.makedirs` with `exist_ok=True` to create it automatically. |

## 专业提示

* **避免硬编码路径。** 使用 `os.path.join` 和 `pathlib` 模块中的 `Path` 以实现跨平台兼容。
* **验证条形码。** 保存后，您可以使用 `barcode.BarCodeReader` 读取图像，以确认编码文本与 `extended_codetext` 相匹配。
* **性能技巧。** 若在循环中生成大量条形码，复用同一个 `BarCodeWriter` 实例，并在每次迭代仅更新 `code_text`。

## 结论

现在，您已经掌握了如何使用 Aspose.BarCode 在 Python 中 **生成包含 ASCII 与 Unicode 数据的 Code 128 条形码** 并 **将条形码图像保存为 PNG**。完整脚本涵盖了构建扩展码文本、配置写入器、导出图像以及检查库版本的全部步骤。

接下来您可以进一步探索：

* 添加前景/背景颜色（`writer.back_color`, `writer.fore_color`）。
* 使用 `Aspose.PDF` 将条形码嵌入 PDF。
* 使用 `BarCodeReader` 类解码已保存的图像并自动验证内容。

祝编码愉快，欢迎尝试其他符号系统和图像格式！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方案，每篇资源均提供完整可运行的代码示例和逐步解释。

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}