---
category: general
date: 2026-08-22
description: 如何使用 Aspose.BarCode 在 C# 中生成条形码。学习逐步创建条形码图像（C#），禁用二维组件，并保存为 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: zh
lastmod: 2026-08-22
og_description: 如何使用 Aspose.BarCode 在 C# 中生成条形码。本教程展示了如何使用 DataBar Expanded 在 C# 中创建条形码图像，切换
  2‑D 组件，并保存为 PNG 文件。
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: 如何在 C# 中生成条形码 – 完整指南：创建条形码图像 C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: 如何在 C# 中生成条形码 – 使用 DataBar Expanded 创建条形码图像
url: /zh/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成条形码 – 使用 DataBar Expanded 创建条形码图像 C#

在需要将机器可读数据嵌入应用程序时，生成条形码是常见需求。本文档展示了如何使用 Aspose.BarCode 库在 C# 中创建条形码图像、禁用 2‑D 复合组件，并将结果保存为 PNG 文件。

您将看到完整可运行的示例程序、每个配置选项的说明以及自定义输出的技巧。无需外部文档——只需下面的代码和 .NET 开发环境即可。

## 前置条件

开始之前，请确保您已具备：

* .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* Aspose.BarCode for .NET NuGet 包（`Aspose.BarCode`）  

您可以使用以下命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

库提供了在本教程中始终使用的 `BarcodeGenerator` 类。

## 第一步：创建项目并导入命名空间

新建一个控制台应用程序并导入所需的命名空间：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` 命名空间包含配置和渲染条形码所需的全部类。

## 第二步：初始化 DataBar Expanded 条形码生成器

下面的第一行代码为 **DataBar Expanded** 符号创建了一个 `BarcodeGenerator`，并提供原始数据字符串。数据字符串遵循 GS1 应用标识符格式 `(01)12345678901231`。

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

创建生成器时会分配内部位图画布，您可以在渲染前调整大小和外观。

## 第三步：定义模块宽度（X‑dimension）

X‑dimension 控制最小条形码单元的宽度。以像素为单位设置可以精确控制最终图像尺寸。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 像素的值在屏幕显示时效果良好；若需更高分辨率的打印，可适当增大。

## 第四步：禁用 2‑D 复合组件

DataBar Expanded 可以可选地包含携带额外信息的 2‑D 组件。若要生成**不带**该组件的条形码，请将标志设为 `false`。

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

禁用该组件可降低视觉复杂度并生成更小的 PNG 文件。

## 第五步：保存不含 2‑D 组件的条形码图像

选择输出目录并将图像写入磁盘。`BarCodeImageFormat.Png` 枚举确保生成无损 PNG 文件。

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

调用完成后，`Databar2DComponentDisabled.png` 即为纯净的 DataBar Expanded 条形码。

## 第六步：启用 2‑D 复合组件

如果需要额外的数据层，请重新将标志设为 `true`。同一个生成器实例可以重复使用，避免创建第二个对象。

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## 第七步：保存启用 2‑D 组件的条形码图像

使用相同的设置渲染第二张图像，只是将 2‑D 标志改为启用。

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

此时 `Databar2DComponentEnabled.png` 将展示带有额外 2‑D 图案的条形码。

## 完整源代码

将下面的代码片段全部复制到 `Program.cs` 并运行项目。程序会在您指定的文件夹中生成两张 PNG 文件。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### 预期输出

运行程序后会在控制台打印：

```
Barcode images generated successfully.
```

并创建两个文件：

* `Databar2DComponentDisabled.png` – 不含 2‑D 组件的条形码  
* `Databar2DComponentEnabled.png` – 含 2‑D 组件的条形码  

使用任意图像查看器打开 PNG，即可验证视觉差异。

## 常见变体与边缘情况

| 情况 | 调整方式 |
|-----------|------------|
| **不同的符号类型** | 将 `EncodeTypes.DatabarExpanded` 替换为其他值，例如 `EncodeTypes.Code128`。 |
| **更高分辨率** | 将 `XDimension.Pixels` 提升至 4 或 5，或在 `barcodeGenerator.Parameters.Image` 中设置 `Resolution`。 |
| **其他图像格式** | 使用 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp` 或 `BarCodeImageFormat.Svg`。 |
| **在 Web 应用中运行** | 直接将图像字节流写入 HTTP 响应，而不是保存到磁盘。 |
| **内存管理** | 若目标为 .NET Framework，建议在 `using` 块中使用生成器，以确保释放非托管资源。 |

## 专业技巧

* **复用生成器** – 只更改 2‑D 标志即可避免重新实例化对象，从而节省 CPU 周期。  
* **验证数据** – GS1 数据必须严格符合长度和校验规则；无效输入会抛出 `ArgumentException`。  
* **批量处理** – 对数据字符串集合进行循环，根据需要切换 2‑D 标志，并使用唯一文件名保存每张图像。  

## 结论

现在您已经掌握了在 C# 中生成条形码并通过 DataBar Expanded 完全控制 2‑D 复合组件的技巧。示例演示了生成器的初始化、X‑dimension 的配置、组件的开关以及 PNG 文件的保存。接下来，您可以探索其他符号类型、将图像嵌入 PDF，或在 ASP.NET Core 服务中集成条形码生成。

--- 

*后续步骤*：尝试生成 QR 码、实验不同的图像分辨率，或使用 Aspose.PDF 将生成的 PNG 嵌入 PDF。这些扩展基于相同的 `BarcodeGenerator` API，保持工作流一致。

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，提供完整可运行的代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}