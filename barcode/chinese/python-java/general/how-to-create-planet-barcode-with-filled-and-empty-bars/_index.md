---
category: general
date: 2026-09-29
description: 使用 Aspose.Barcode 在 C# 中创建星球条形码（包含实心和空心条）——一步步指南
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: zh
lastmod: 2026-09-29
og_description: 快速在 C# 中创建行星条码。了解如何渲染实心条、切换为空心条，并使用 Aspose.Barcode 调整 X 维度。
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: 创建带有实线和空线的星球条形码 – C# 教程
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何创建带有实心和空心条的星球条码
url: /zh/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建带填充和空白条的 planet 条形码

如果您需要在 C# 中**创建 planet 条形码**图像，本指南将准确演示如何生成填充条和空白条两种版本。您将了解如何设置条宽（X‑dimension），切换 `FilledBars` 属性，并将结果保存为 PNG 文件——全部使用 Aspose.Barcode 库。

生成邮政条形码是运输系统、邮件列表应用和物流仪表板的常见需求。完成本教程后，您将拥有两个可直接使用的 PNG 文件，可嵌入报告、电子邮件或打印件中。

## 前提条件

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 或更高版本 | 为 C# 示例提供运行时环境。 |
| Visual Studio 2022（或任意 C# IDE） | 让您能够编译并运行代码。 |
| **Aspose.Barcode for .NET** NuGet 包 | 提供 `BarcodeGenerator` 类和 `EncodeTypes.Planet`。使用 `dotnet add package Aspose.Barcode` 安装。 |
| 对磁盘文件夹的写入权限 | `Save` 方法会将 PNG 文件写入您指定的路径。 |

## 步骤 1：设置项目并导入命名空间

创建一个新的控制台项目（或将代码添加到现有项目），并引用 Aspose.Barcode 命名空间。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

这些 `using` 指令让您能够访问本教程所需的 `BarcodeGenerator`、`EncodeTypes` 和图像格式枚举。

## 步骤 2：使用默认（填充）条创建 Planet 条形码

第一个条形码使用库的默认渲染方式，即填充条。

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**为什么这样有效：**  
`EncodeTypes.Planet` 告诉 Aspose.Barcode 使用 **Planet** 符号，它是美国邮政服务使用的邮政条形码。`XDimension` 属性控制每条的宽度；将其设为 4 像素可生成在标准标签打印机上打印良好的条形码。默认情况下，`FilledBars` 为 `true`，因此条是实心的。

## 步骤 3：使用空白条创建 Planet 条形码

要使用*空白*条生成相同的数据，只需切换 `FilledBars` 标志，其他设置保持不变。

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**为什么这很重要：**  
某些邮件系统需要 **empty‑bars** 样式，以在条形码打印在深色背景或使用对比配色时提升可读性。将 `FilledBars = false` 设置后，生成器仅绘制条的轮廓，内部保持透明。

## 预期输出

运行程序后，文件夹 `C:\Barcodes`（或您选择的路径）中会包含两个 PNG 文件：

| File | Visual description |
|------|---------------------|
| `PlanetFilledBars.png` | 条为白色背景上的实心黑色矩形。 |
| `PlanetEmptyBars.png`  | 条为黑色轮廓；每条内部透明（显示背景）。 |

两个图像均编码相同的数字字符串 `"123456"`，且使用 4 像素的条宽，确保它们除填充样式外外观一致。

## 常见变体和边缘情况

### 更改条宽

如果您的标签打印机需要不同的条宽，请修改 `XDimension.Pixels` 的值。对于高分辨率打印机，**2** 或 **3** 像素可能更合适；对于低分辨率打印机，**5** 或 **6** 像素可以提升扫描可靠性。

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### 使用不同的图像格式

Aspose.Barcode 支持 PNG、JPEG、BMP、GIF 和 TIFF。将 `BarCodeImageFormat.Png` 替换为其他枚举值，以匹配后续工作流。

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### 在循环中生成多个条形码

当需要批量生成 Planet 条形码（例如用于邮件列表）时，可将生成逻辑放入 `foreach` 循环，并在每次迭代中更改数据字符串。

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### 处理无效输入

Planet 符号仅接受 **5‑8** 位的数字字符串。提供无效值会抛出 `ArgumentException`。可使用简单的验证方法进行防护。

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## 专业提示：使用扫描器模拟器验证条形码

Aspose.Barcode 包含 `BarcodeReader` 类，您可以使用它确认生成的图像能够解码回原始数据。

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

如果输出对两个文件均显示 `"123456"`，则条形码生成正确。

## 结论

现在，您已经了解如何在 C# 中使用 **Aspose.Barcode** 库创建 **planet 条形码** 图像，支持填充条和空白条两种样式，控制 **Planet 条形码 XDimension**，并以 PNG 格式保存结果。可根据需求调整条宽、切换图像格式，或对一系列值进行循环，以适配任何邮政编码工作流。

接下来，您可以探索：

* **在条形码下方添加可读文本**（`barcodeGenerator.Parameters.Caption.Show = true`）。
* **使用 Aspose.PDF 将条形码嵌入 PDF 文档**。
* **生成其他邮政符号**，例如 **USPS POSTNET** 或 **Intelligent Mail**。

欢迎随意尝试这些参数，并将代码集成到您的运输或邮件系统中。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能，并在项目中探索替代实现方案。

- [在 C# 中创建 Planet 条形码 – 完整分步指南](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [在 C# 中创建 planet 条形码 – 完整编程指南](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [C# 条形码生成器 – 创建 Planet 条形码和 RM4SCC 示例](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}