---
category: general
date: 2026-10-15
description: 使用 Aspose.Barcode for Python 从字符串创建条形码。了解如何生成条形码、设置尺寸，并在几分钟内保存为 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: zh
lastmod: 2026-10-15
og_description: 使用 Aspose.Barcode for Python 从字符串创建条形码。本教程将一步步演示如何生成邮政条形码并将其保存为 PNG。
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: 在 Python 中从字符串创建条形码 – Aspose 指南
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: 如何使用 Aspose 在 Python 中从字符串创建条形码
url: /zh/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose 从字符串创建条形码

如果您需要 **快速从字符串创建条形码**，Aspose.Barcode for Python 能让这一过程变得简单直观。在本指南中，您将看到 **如何生成条形码** 图像、调整 X‑dimension（模块宽度），以及将结果保存为 PNG 文件——只需几行代码。

您还将获得一个完整的 **条形码生成器示例**，可以直接复制粘贴到自己的项目中。无需外部脚本或复杂配置，教程基于当前的 Aspose.Barcode 23.10 版本。

## 前提条件

在开始之前，请确保您已经：

- 在机器上安装了 Python 3.8+  
- 拥有有效的 Aspose.Barcode for Python 许可证（免费试用版可用于评估）  
- 在虚拟环境中执行了 `pip install aspose-barcode`  

这些条件可确保代码运行时不会出现导入错误。

## 使用 Aspose.Barcode（Python）从字符串创建条形码

第一步是实例化 `BarcodeGenerator`，并指定所需的符号体系——本例中使用 **Planet** 邮政条形码，以及您想要编码的字符串。

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**为什么这很重要：**  
`EncodeTypes.Planet` 告诉 Aspose 使用 Planet 邮政符号体系，该体系专为多个国家的邮件分拣设计。第二个参数（`"123456"`）是将被编码为条形码的原始字符串。更改此值即可 **从字符串创建条形码**，用于任意邮政编码或跟踪号。

## 如何使用自定义尺寸生成条形码

邮政条形码的模块宽度（X‑dimension）通常需要符合打印规格。Aspose 允许您以像素为单位设置宽度，同时自动计算高度。

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**为何可能需要调整：**  
较大的 X‑dimension 会使条形更粗，在低分辨率打印机上可提升扫描可靠性。相反，较小的数值可减小网页使用时的图像尺寸。此行代码演示了 **如何生成符合精确尺寸要求的条形码** 图像。

## 保存条形码图像

配置好生成器后，只需调用 `save`。该方法接受输出路径和所需的图像格式。

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**您将得到：**  
一个名为 `PostalPlanetAuto.png` 的 PNG 文件，内含编码为 `"123456"` 的 Planet 条形码。您可以使用任意图像查看器打开该文件以验证结果。

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="已生成的邮政条形码 PNG 截图"}

## 完整的条形码生成器示例

下面是包含上述所有步骤的完整可运行脚本。将其复制到名为 `generate_postal_barcode.py` 的文件中，然后执行 `python generate_postal_barcode.py`。

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### 预期输出

运行脚本后会产生：

```
Barcode saved to PostalPlanetAuto.png
```

…并生成一个名为 `PostalPlanetAuto.png` 的文件，效果如下：

![Generated Planet barcode](barcode_example.png){.align-center alt="已生成的 Planet 条形码 PNG"}

## 常见变体和边缘情况

| 情况 | 需要更改的内容 | 原因 |
|-----------|----------------|-----|
| **不同的符号体系**（例如 Code128） | 将 `EncodeTypes.Planet` 替换为 `EncodeTypes.Code128` | 让您 **生成条形码** 用于库存标签，而不仅限于邮政编码。 |
| **更长的数据字符串** | 确保所选符号体系支持该长度；Planet 必须保持 6 位数字。 | 防止运行时出现 `ValueError`。 |
| **更高分辨率** | 将 `x_dimension.pixels` 提升至 6 或 8。 | 为高 DPI 打印生成更粗的条形。 |
| **其他图像格式** | 使用 `BarCodeImageFormat.JPEG` 或 `BarCodeImageFormat.GIF`。 | 当 PNG 不适合您的工作流时可使用。 |
| **在 Web 服务中运行** | 将文件系统的 `save` 调用替换为 `BytesIO` 流并返回字节。 | 在 Flask 或 Django 中实现即时条形码生成。 |

**专业提示：** 在调用 `BarcodeGenerator` 前务必对输入字符串进行验证。无效数据（如 Planet 的错误长度或非数字字符）会抛出异常，导致应用程序崩溃。

## 在 Flask 端点中生成条形码（可选后续步骤）

如果您想将 **条形码生成器示例** 以 REST API 形式公开，可以包装 `create_postal_barcode` 函数：

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

此代码片段展示了如何 **按需生成条形码** 而无需写入磁盘，非常适合微服务场景。

## 结论

现在，您已经掌握了如何在 Python 中使用 Aspose.Barcode **从字符串创建条形码**，以及如何 **生成条形码** 并自定义尺寸，最后将结果保存为 PNG 文件。完整的 **条形码生成器示例** 包含了输入验证、错误处理以及可在更大项目中复用的函数。

接下来，探索其他符号体系（`EncodeTypes.Code128`、`EncodeTypes.QR`）或将生成器嵌入 Flask、Django 等 Web 框架。上述步骤将帮助您深入了解 **aspose barcode python** 库，并在实际项目中 **生成邮政条形码** 图像。

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步提升。每篇资源都提供完整可运行的代码示例，并配有逐步解释，帮助您掌握更多 API 功能并探索替代实现方式。

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}