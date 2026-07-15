---
category: general
date: 2026-07-15
description: 如何使用 Aspose.Barcode 在 Python 中生成二维码图像。学习逐步创建二维码，包括扩展码文本、ECI 编码和 Unicode
  支持。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: zh
lastmod: 2026-07-15
og_description: 如何使用 Aspose.Barcode 在 Python 中生成 QR 码图像。本指南将带您了解使用扩展代码文本、ECI 编码和 Unicode
  字符创建 QR 码的过程。
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: 如何在 Python 中生成二维码图像 – Aspose.Barcode 完整教程
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: 使用 Aspose.Barcode 在 Python 中生成二维码图像 – 完整指南
url: /zh/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Barcode 在 Python 中生成 QR 码图像 – 完整指南

是否曾经想过 **如何在 Python 中生成 QR 码图像** 而不必搜寻大量库？你并不孤单。许多开发者需要一种可靠的方法在 QR 码中嵌入多语言文本——比如俄语、阿拉伯语或表情符号——而内置库往往力不从心。

事实上，Aspose.Barcode for Python 让这件事变得异常轻松。在本教程中，我们将逐步演示完整流程，从安装包到构造混合普通 ASCII 与 ECI 编码 Unicode 的扩展 codetext 字符串。完成后，你将拥有一个可直接使用的 QR 码图像保存在磁盘上。

## 本指南涵盖内容

- 为 Python（兼容 Python 3.8+）安装 **Aspose.Barcode**
- 构建 **扩展 codetext**，将普通段落与 Unicode 段落组合
- 使用 **ECI 编码** 正确渲染俄语字符
- 配置 `BarcodeGenerator` 生成 QR 码
- 将输出图像保存为 PNG 格式
- 提示、常见陷阱以及后续思路（如添加徽标或调整纠错级别）

无需任何 Aspose 经验；只需一个基本的 Python 环境和对 QR 码的好奇心。

---

## 前置条件

在开始之前，请确保你具备以下条件：

1. **Python 3.8 或更高版本** 已安装在机器上。  
2. **虚拟环境**（可选但推荐），用于保持依赖整洁。  
3. 能使用 **pip** 安装 `aspose-barcode` 包。  
4. 对将要保存生成 PNG 的文件夹拥有写入权限。

如果上述任意一点不熟悉，请先停下来完成相应设置——准备好后，接下来的步骤将轻而易举。

---

## 第一步：安装 Aspose.Barcode for Python

获取库的第一道门槛是安装它。Aspose 在 PyPI 上发布包，只需一条 `pip` 命令即可完成：

```bash
pip install aspose-barcode
```

> **小贴士**：如果你在虚拟环境中操作，能够保持全局 site‑packages 干净。如果遇到权限错误，可在命令前加 `--user` 或使用 `sudo`（不过在现代环境中很少需要）。

安装完成后，可通过以下方式验证：

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

如果版本信息正常打印，说明已准备就绪。

---

## 第二步：创建 **扩展 Codetext Builder** 实例

Aspose.Barcode 提供 `ExtCodetextBuilder` 类用于组合复杂的 QR 负载。可以把它看作一个小型文本编辑器，能够为每个段落自动添加正确的控制字符。

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

为何要使用 Builder？直接拼接原始字节容易出错；Builder 能保证正确的 ECI（Extended Channel Interpretation）切换，从而让 QR 扫描器能够正确解码每种语言。

---

## 第三步：清空构建器（可选但更整洁）

如果你重复使用同一个 Builder 实例，调用 `clear()` 可以清除之前的所有数据。这是防止残留段落泄漏到下一个 QR 码中的安全网。

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

首次运行脚本时可以省略此行，但保留它可以让代码具备幂等性——在函数被多次调用时尤为有用。

---

## 第四步：添加普通（未编码）段落

大多数 QR 码以简单的 ASCII 字符串开头——可能是标识符或 URL。`add_plain_codetext` 方法正是用于添加此类内容，不会附加任何 ECI 标记。

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

本例中使用 `"HelloWorld"` 作为占位符。请根据实际需求替换为产品 SKU、短消息等。

---

## 第五步：添加 **ECI 编码** 段落（UTF‑8 = 26）

下面进入多语言部分。ECI 值 **26** 对应 UTF‑8，这是事实上的 Unicode 标准。将 `26` 与俄语短语一起传入，即可指示 QR 扫描器在读取后续字符前切换到 UTF‑8。

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

如果需要其他编码，可将 `26` 替换为相应的 ECI 值（例如 `27` 表示 ISO‑8859‑1）。Builder 会自动插入正确的控制字符。

---

## 第六步：获取合并后的扩展 Codetext

所有段落添加完毕后，提取最终字符串供 QR 生成器使用。该字符串包含不可见的控制序列，但仍可打印出来用于调试。

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

控制台输出会出现乱码（因为嵌入了控制字节），这完全正常。关键是 Builder 已经正确地将普通和 Unicode 部分拼接在一起。

---

## 第七步：配置条形码生成器

现在将扩展 codetext 交给 Aspose 的 `BarcodeGenerator`。将符号类型设为 `QR`，并把合并后的字符串赋给 `code_text`。

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

此处还可以调节其他属性——如 `resolution`、`error_correction_level` 或 `foreground_color`。这些选项在 Aspose 文档中有详细说明，但对于基础图像，默认值已足够。

---

## 第八步：保存生成的 QR 码图像

最后，将 QR 码写入磁盘。`save` 方法接受文件路径和可选的格式；PNG 是安全的默认选择。

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

使用任意图像查看器打开生成的 `qr_extended.png`。用手机扫描时应能看到两条独立信息：“HelloWorld” 与 “Привет”。大多数现代 QR 读取器会自动处理 ECI 切换。

---

## 完整工作示例

将上述步骤整合，下面是可以直接复制运行的完整脚本：

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**预期输出**（控制台）：

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

打开 `qr_extended.png` → 扫描 → 你将看到 “HelloWorld” 后跟 “Привет”。

---

## 常见问题与边缘情况

### 1. *如果需要超过两个段落怎么办？*  
只需多次调用 `add_plain_codetext` 或 `add_eci_codetext`。Builder 会保持正确的顺序，QR 码将按添加顺序包含每个段落。

### 2. *可以嵌入表情符号吗？*  
可以——表情符号本质上是 Unicode 字符。使用 UTF‑8 ECI（值 26）并传入表情字符串，例如 `builder.add_eci_codetext(26, "🚀")`。支持的扫描器会显示火箭表情。

### 3. *如果 QR 码变得太密集怎么办？*  
QR 码有版本上限。若数据容量超出，Aspose 会自动提升版本以容纳更多数据，但图像尺寸会增大。若想控制大小，可降低纠错级别：

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *是否必须考虑 UTF‑8 之外的字符集？*  
仅在需要兼容旧系统且必须使用特定编码（如 ISO‑8859‑1）时才需要。此时将 `26` 替换为相应的 ECI 值（参见 Aspose 的 ECI 表）。对大多数现代应用而言，UTF‑8 是最安全的选择。

### 5. *如何在中心添加徽标？*  
Aspose.Barcode 支持 `barcode.generator.QRCodeParameters.logo_image`。使用 Pillow 加载图像（`from PIL import Image`），然后赋值：

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

徽标会在保持可扫描性的前提下覆盖在中心（Aspose 会自动调整安静区）。

---

## 生产环境使用的专业建议

- **缓存 Builder**：若频繁生成相同 QR，缓存已构建好的扩展字符串可避免重复拼接。  
- **验证输出**：编写单元测试，使用 `zxing` 或 `pyzbar` 解码生成的 QR，确保 ECI 切换正确。  
- **使用确定性文件名**：例如根据负载哈希生成文件名，防止覆盖已有图像。  
- **注意授权**：Aspose.Barcode 为商业软件。免费评估版适用于开发，生产环境需购买授权。

---

## 后续步骤与相关主题

现在你已经掌握了 **如何生成 QR 码** 的全部流程，下面的教程将进一步扩展相关技术：

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}