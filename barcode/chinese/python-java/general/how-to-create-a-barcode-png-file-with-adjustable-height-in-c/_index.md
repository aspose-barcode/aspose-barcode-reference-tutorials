---
category: general
date: 2026-08-19
description: 学习如何在 C# 中生成条形码 PNG 文件并调整其高度，涵盖如何生成条形码图像以及轻松更改条形码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: zh
lastmod: 2026-08-19
og_description: 在 C# 中创建条形码 PNG 文件，学习如何生成条形码图像、调整条形码高度以及更改条形码高度以实现最佳扫描。
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: 在 C# 中创建条形码 PNG 文件 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中创建可调高度的条形码 PNG 文件
url: /zh/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建可调高度的条形码 PNG 文件

如果您需要在 C# 中创建 **条形码 PNG 文件**，本指南将一步步演示完整的可运行示例，展示 **如何生成条形码** 图像以及 **如何调整条形码高度** 以适应不同的使用场景。

生成条形码 PNG 文件是库存系统、销售点终端以及任何需要打印或显示机器可读数据的应用程序的常见需求。完成本教程后，您将能够修改条形码高度、保存多个 PNG 文件，并了解高度对扫描可靠性的影响。

## 前置条件

在开始之前，请确保您已具备以下环境：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 包（示例代码使用该库）  

您可以通过命令行添加该包：

```bash
dotnet add package Aspose.BarCode
```

> **小贴士：** Aspose.BarCode 的免费评估版可用于开发和测试。生产环境请获取授权密钥。

## 安装条形码库

第一步是在项目中引用该库。在 C# 文件顶部添加以下 `using` 指令：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

这些命名空间为您提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat`。

## 创建条形码 PNG 文件

现在我们创建一个 `BarcodeGenerator` 实例，用于输出 **条形码 PNG 文件**。示例使用 Databar OmniDirectional 编码方式，您也可以将 `EncodeTypes.DatabarOmniDirectional` 替换为任意受支持的类型。

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

字符串 `"(01)12345678901231"` 符合 GS1 应用标识符格式，表示 14 位 GTIN。请根据自己的产品标识符进行相应调整。

## 设置 X 维度（可选）

X 维度定义单个条形码模块的宽度。使用像素值可以精确控制图像尺寸。

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 像素的值在大多数屏幕显示下表现良好。如果需要在打印时获得更大的条形码，请增大该值。

## 调整条形码高度并保存条形码 PNG 文件

**BarHeight** 属性控制条形的垂直尺寸。修改该属性即可 **调整条形码高度**，而不会影响编码数据。

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

文件 `DatabarBarHeight30Pixels.png` 现在是一个 **条形码 PNG 文件**，高度为 30 像素。  

若要 **更改条形码高度** 并创建第二张图像，只需赋予新值并再次调用 `Save`：

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

这样您就拥有了两张 PNG 文件——一张 30 px，另一张 60 px——演示了如何即时 **调整条形码高度**。

### 为什么条形码高度很重要

* **可读性：** 扫描器需要最小高度才能可靠检测。高度过低的条形码可能被漏检，尤其是在低分辨率摄像头下。  
* **美观性：** 将条形码高度与周围设计元素匹配，可获得更整洁的 UI。  
* **打印限制：** 某些标签打印机的高度槽位是固定的，调整条形码高度可确保其适配。

**最佳实践：** 保持高度为 X 维度的整数倍（例如 X 维度为 2 px 时高度设为 30 px），以维持比例并避免失真。

## 完整示例

下面是完整的、可直接粘贴到控制台应用程序并立即运行的代码。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**预期输出**

运行程序后，执行目录下会生成两个文件：

* `DatabarBarHeight30Pixels.png` – 高度为 30 像素的条形码 PNG 文件  
* `DatabarBarHeight60Pixels.png` – 高度为 60 像素的条形码 PNG 文件  

使用任意图像查看器打开这两张 PNG，您将看到清晰的 Databar OmniDirectional 条形码，已准备好进行扫描。

## 边缘情况与故障排除

| 情况 | 检查要点 | 推荐解决方案 |
|-----------|---------------|-----------------|
| 条形码模糊 | X 维度相对于所选高度过低 | 增大 `XDimension.Pixels`（例如从 2 提升到 3） |
| 扫描器在低高度条形码上失效 | 高度低于扫描器最低要求 | 将 `BarHeight.Pixels` 设置为至少 30 px（或依据扫描器规格） |
| PNG 文件为空或损坏 | 输出路径无效或缺少写入权限 | 使用绝对路径或确保应用拥有写入权限 |
| 需要其他编码方式 | 当前 `EncodeTypes` 不适用 | 将 `EncodeTypes.DatabarOmniDirectional` 替换为其他枚举值（如 `EncodeTypes.Code128`） |

## 常见问题

**问：我可以生成其他图像格式吗（JPEG、BMP）？**  
答：可以。将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp` 等。

**问：如何在网页中嵌入 PNG？**  
答：通过 HTTP 接口提供生成的 PNG，或将其转换为 Base64 字符串并放入 `<img>` 标签的 `src` 属性中。

**问：可以设置背景颜色吗？**  
答：使用 `generator.Parameters.Image.BackgroundColor = Color.White;`（或任意 `System.Drawing.Color`）即可。

## 结论

现在您已经掌握了在 C# 中 **生成条形码 PNG 文件** 并精确 **调整条形码高度** 的方法，以满足扫描或设计需求。通过修改 `BarHeight.Pixels` 属性，您可以即时 **更改条形码高度**，并从同一代码库生成多个 PNG 资源。

接下来，您可以探索前景色、边距以及添加可读文字等其他自定义选项。还可以尝试不同的编码方式（如 `EncodeTypes.Code128`、`EncodeTypes.QR`），以扩展可编码的数据范围。

祝编码愉快，愿您的条形码一次即能成功扫描！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中尝试替代实现方案，每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}