---
category: general
date: 2026-10-28
description: 学习如何使用 ExtCodetextBuilder 在 Python 中创建扩展代码文本。包括普通和 ECI 编码的数据、一步一步的代码示例以及最佳实践技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: zh
lastmod: 2026-10-28
og_description: 使用 ExtCodetextBuilder 在 Python 中创建扩展码文本。本教程展示了普通和 ECI 编码数据的处理、完整可运行的代码以及常见陷阱。
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: 在Python中创建扩展代码文本——完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: 如何在 Python 中使用 ExtCodetextBuilder 创建扩展代码文本
url: /zh/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 ExtCodetextBuilder 创建扩展码文本

如果您需要为条形码或 Data‑Matrix 应用 **创建扩展码文本**，本指南将向您展示如何在 Python 中实现。您将看到如何组合普通文本、为 Unicode 字符添加 ECI（Extended Channel Interpretation）段，以及获取一个已正确格式化、可直接用于编码的字符串。

本教程涵盖了从安装所需库到处理不支持的 ECI 值等边缘情况的全部内容。完成后，您将拥有一个可复用的模式，可直接嵌入任何需要 **创建扩展码文本** 的项目中。

## 您将学到

* `ExtCodetextBuilder` 在构建混合编码字符串时的作用。  
* 如何在同一个 builder 实例中 **添加普通码文本** 和 **添加 ECI 码文本**。  
* 如何验证最终输出并排查常见陷阱。  
* 其他字符集的变体（例如 ISO‑8859‑1、Shift‑JIS）。  

### 前置条件

* Python 3.8 或更高版本。  
* `extcodetext` 包（或提供 `ExtCodetextBuilder` 的类似库）。使用以下方式安装：

```bash
pip install extcodetext
```

* 对 Unicode 和 ECI 值有基本了解——ECI 3 对应 UTF‑8，ECI 4 对应 ISO‑8859‑1，等等。

> **专业提示:** 随手保留一张 ECI 编号参考表。它可以防止声明的编码与实际字节序列之间的意外不匹配。

## 理解 ExtCodetextBuilder

`ExtCodetextBuilder` 是一个小工具，用于连接多个文本片段并自动插入所需的 ECI 标记。ECI 标记告诉后续的条码编码器后续字节应使用哪种字符集。如果没有该标记，非 ASCII 字符将被误解。

构建器分为三个简单阶段：

1. **创建** builder 实例。  
2. **追加** 普通或 ECI 编码的片段。  
3. **检索** 合并后的扩展码文本字符串。

下面我们将通过具体代码逐步演示每个阶段。

## 步骤 1：创建 ExtCodetextBuilder 实例

第一行代码构造了用于保存所有片段的对象。目前无需任何配置。

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*原因说明*: 实例化 builder 会分配内部缓冲区。所有后续的 `add_*` 调用都在该缓冲区上操作，确保您指定的顺序。

## 步骤 2：追加普通（未编码）数据

普通数据指属于默认字符集（通常是 ASCII）的字符。此类片段请使用 `add_plain_codetext`。

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*解释*: 字符串 `"ABC123"` 仅包含 ASCII 字符，因此不需要 ECI 标记。该方法仅将原始字节追加到内部缓冲区。

## 步骤 3：追加需要前置 ECI 的数据

当需要嵌入 Unicode 字符（如西里尔字母、日文或表情符号）时，必须告知编码器使用哪种字符集。这通过 `add_eci_codetext(eci, text)` 完成。第一个参数是数值型 ECI，第二个参数是实际文本。

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*为何使用 ECI 3*: 根据 ISO/IEC 18004 规范，ECI 3 对应 UTF‑8。插入此标记后，条码读取器会将后续字节按 UTF‑8 解码，从而保留西里尔字符。

### 处理其他编码

如果需要 ISO‑8859‑1（西欧）可以使用 `add_eci_codetext(4, "¡Hola!")`。对于 Shift‑JIS（日本）则使用 ECI 值 20：

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

始终确认目标条码库支持所选的 ECI 值；不受支持的 ECI 会导致编码失败。

## 步骤 4：检索合并后的扩展码文本字符串

在添加完所有片段后，调用 `get_extended_codetext()` 获取最终字符串。该字符串已包含所有必要的 ECI 转义序列。

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**预期输出**（为清晰起见，以 Python `repr` 形式显示）：

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*拆解*：

* `ABC123` – 普通 ASCII 段。  
* `\x1B\x1D\x03` – UTF‑8 的 ECI 转义序列（ESC GS 0x03）。  
* `Привет` – UTF‑8 编码的西里尔单词。

具体的转义字节可能因库实现而异，但逻辑顺序始终为 *普通 → ECI 标记 → Unicode 文本*。

## 完整可运行示例

将所有内容整合在一起，下面是一个可直接复制粘贴到名为 `create_extended_codetext.py` 的文件中并立即运行的独立脚本。

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

运行脚本后会打印合并后的字符串，可直接供任何接受扩展码文本输入的条码编码器使用。

## 常见陷阱及规避方法

| 症状 | 可能原因 | 解决办法 |
|---|---|---|
| `UnicodeEncodeError` 在调用 `add_eci_codetext` 时出现 | 提供的字符串包含在所选 ECI 中无法表示的字符 | 确认 ECI 与字符串的实际编码匹配（例如，对任何 UTF‑8 文本使用 ECI 3）。 |
| 最终输出缺少 ECI 标记 | 误将非 ASCII 数据使用 `add_plain_codetext` 添加 | 对任何超出 ASCII 范围的字符改用 `add_eci_codetext`。 |
| 条码扫描仪显示乱码 | 扫描仪不支持所选的 ECI 值 | 选择普遍支持的 ECI（UTF‑8 被广泛支持），或在目标语言允许的情况下回退到 ISO‑8859‑1。 |
| `get_extended_codetext` 返回空字符串 | 调用方法前未添加任何片段 | 确保至少执行一次 `add_*` 调用。 |

### 边缘情况：空字符串

调用 `add_plain_codetext("")` 或 `add_eci_codetext(3, "")` 是安全的；builder 会直接忽略空片段。但重复的空调用可能导致不必要的 ECI 标记。通过在添加前检查字符串长度来防止此类情况。

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## 为动态数据扩展模式

在实际应用中，您通常会根据用户输入或数据库记录构建扩展码文本。下面的代码片段展示了一个循环，处理 `(type, value)` 元组列表，其中 `type` 为 `"plain"` 或 `"eci"`。

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

这种方式易于扩展：您可以从 JSON、CSV 或 API 读取片段定义，而无需更改核心构建逻辑。

## 测试输出

一个简短的单元测试可确保 builder 按预期工作。使用 `pytest`：

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

运行 `pytest` 应通过，确认 ECI 标记出现在正确的位置。

## 您可能感兴趣的相关概念

* **条码编码库** – 如 `python-barcode`、`zxing` 绑定等，可直接接受扩展码文本字符串。  
* **ECI 表参考** – ISO/IEC 18004 发布了完整的数值 ECI 列表，可将其存为 Python 字典以供查找。  
* **纠错级别** – 生成 QR 码时，将扩展码文本与适当的纠错级别（L、M、Q、H）结合，以实现稳健扫描。  

## 结论

现在，您已经了解如何使用 `ExtCodetextBuilder` 在 Python 中 **创建扩展码文本**。该过程简明如下：

1. 实例化 builder。  
2. 根据需要追加普通和 ECI 编码的片段。  
3. 检索最终字符串并将其提供给条码生成器。

遵循上述模式，您即可处理任意 ASCII 与 Unicode 数据的混合，避免常见的编码错误，并生成可在各种扫描器上使用的条码就绪字符串。尝试不同的 ECI，将 builder 集成到数据管道中，您将拥有满足所有扩展码文本需求的坚实基础。

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}