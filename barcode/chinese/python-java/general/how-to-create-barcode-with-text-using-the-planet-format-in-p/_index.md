---
category: general
date: 2026-11-27
description: 学习如何在 Python 中创建带文本的条形码并生成星球条形码——一步步指南，输出高分辨率 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: zh
lastmod: 2026-11-27
og_description: 使用 Python 创建带文本的条形码并生成星球条形码。按照本完整指南输出高分辨率 PNG。
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: 在 Python 中创建带文本的条形码 – 轻松生成 Planet 条形码
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: 如何在 Python 中使用 Planet 格式创建带文本的条形码
url: /zh/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Planet 格式创建带文本的条形码

如果您需要为邮件系统**创建带文本的条形码**，本教程将准确展示如何操作。您将看到一个简洁的端到端示例，生成 Planet 条形码，调整分辨率，并将结果保存为 PNG 图像。

生成条形码是物流、库存和票务应用的常见需求。在本指南中，您不仅会学习**如何生成条形码**文件，还会了解每个配置步骤的重要性以及如何避免常见陷阱。

## 您将学习的内容

* 使用自定义文本设置 Planet 条形码生成器。
* 调整 X 维度以提升图像清晰度。
* 将条形码保存为 PNG 文件，可用于打印或在网页上显示。
* 将示例扩展到其他条形码类型或输出格式。

**先决条件**

* Python 3.8 或更高版本。
* `aspose-barcode` 包（或任何提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的兼容库）。
* 对 Python 脚本的基本了解。

您可以使用以下方式安装所需的包：

```bash
pip install aspose-barcode
```

---

## 第一步：创建带文本的条形码 – 初始化生成器

您首先需要创建一个 `BarcodeGenerator` 实例，以指定使用的符号系统和要编码的文本。对于 Planet 条形码，`EncodeTypes.Planet` 枚举值指示库遵循 USPS Planet 规范。

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**为什么这很重要：**  
`BarcodeGenerator` 对象封装了条形码的所有设置。在构造时提供文本可确保编码值在后续过程保持不变，从而避免后期出现意外不匹配。

---

## 第二步：调整设置 – 如何生成更高分辨率的条形码

低分辨率的条形码在标签打印机上打印时可能会模糊。X 维度（模块宽度）控制每根条的大小。将其设置为 4 像素可生成清晰的高分辨率图像，适用于大多数现代打印机。

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**说明：**  
* `gen.parameters.barcode.x_dimension.pixels` 直接映射到单个模块的实际宽度。  
* **4** 的数值表示每根条宽四像素，约等于 300 dpi 时的 0.127 mm——在 USPS Planet 条形码推荐范围内。  

**专业提示：** 如果需要不同的 DPI，请相应计算像素宽度（例如，150 dpi 为 2 像素，600 dpi 为 8 像素）。

---

## 第三步：保存图像 – 生成 Planet 条形码为 PNG

现在生成器已配置好，您可以将条形码渲染为图像文件。PNG 为无损格式，确保精确的模块图案得以保留。

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**结果：**  
运行脚本会生成名为 `PostalPlanetBarHeightNone.png` 的文件，其中包含编码字符串 “123456” 的 Planet 条形码。图像尺寸大约为 200 × 100 像素，具体取决于您选择的 X 维度。

---

## 可选：可视化验证条形码

您可以使用任意图像查看器快速打开生成的 PNG，以确认条形码清晰且可读文本出现在图案下方。

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

如果图像显得模糊，请返回**第 2 步**并增加 X 维度，直至条纹清晰可辨。

---

## 常见变体和边缘情况

| 情况 | 调整 |
|-----------|------------|
| **不同的文本长度** | Planet 条形码支持最多 12 位数字字符。如果超出此长度，库会抛出异常。 |
| **替代输出格式** | 将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp` 以满足其他使用场景。 |
| **自定义前景/背景颜色** | 使用 `gen.parameters.barcode.barcode_color = Color.Blue` 和 `gen.parameters.barcode.back_color = Color.White`。 |
| **无可读文本** | 将 `gen.parameters.barcode.hide_code_text = True` 设置为生成不带底部文字的条形码。 |
| **批量生成** | 遍历字符串列表，为每个字符串创建新的 `BarcodeGenerator`，并保存为唯一命名的文件。 |

这些变体使您能够**生成 planet 条形码**文件，以满足各种业务需求。

---

## 完整脚本 – 可直接运行

以下是完整的、独立的脚本，您可以复制、粘贴并执行。它包含所有导入、错误处理和注释。

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**脚本说明**

* `create_planet_barcode` 函数封装了三个核心步骤，使代码可复用。
* 输入验证确保遵循 Planet 规范（仅限数字，最多 12 位）。
* 该函数会自动创建输出文件夹，无需手动管理目录。
* 生成后，脚本使用 Pillow（`PIL`）打开图像，以便即时验证。

---

## 结论

您现在已经掌握了在 Python 中**创建带文本的条形码**和**生成 planet 条形码**文件的方法。本指南涵盖了初始化、分辨率调优和文件输出，以及可选的自定义和常见边缘情况。  

接下来您可以：

* 将 `EncodeTypes.Planet` 替换为其他符号系统（例如 `EncodeTypes.Code128`），以复用相同模式。
* 将该函数集成到按需返回条形码图像的 Web 服务中。
* 通过批量处理实验，生成数千个用于批量邮件的条形码。

欢迎根据项目需求调整脚本，并在评论中分享您的成果。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都提供完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 Python 中生成条形码 – 完整分步指南](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [在 Python 中创建条形码 PNG – 分步指南](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [如何使用 Python 创建 Planet 条形码 PNG](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}