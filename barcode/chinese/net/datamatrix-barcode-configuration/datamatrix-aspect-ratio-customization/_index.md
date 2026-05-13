---
date: 2026-01-12
description: 学习如何使用 Aspose.BarCode for .NET 创建具有自定义 DataMatrix 长宽比的条码 PNG。条码生成和尺寸定制的分步指南。
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 创建条码 PNG – DataMatrix 宽高比 – Aspose.BarCode
url: /zh/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建条形码 PNG – DataMatrix 长宽比 – Aspose.BarCode

生成 **条形码 PNG** 并自定义 DataMatrix 长宽比是满足特定布局约束的常见需求。在本教程中，我们将逐步演示如何使用 Aspose.BarCode for .NET **创建条形码 PNG** 文件，说明为何需要调整长宽比，并展示如何为您的应用程序微调输出。

## 快速答复
- **“长宽比”控制什么？** 它定义了 DataMatrix 模块的宽高比例。  
- **我可以输出 PNG、JPEG 或 SVG 吗？** 可以——`Save` 方法支持 PNG、JPEG、BMP、GIF 等格式。  
- **此功能需要许可证吗？** 免费试用可用于开发；生产环境需要完整许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.x、.NET Core 3.1+、 .NET 5/6/7。  
- **有效的长宽比取值范围是多少？** 任意正浮点数；常用值为 0.5 – 2.0。

## 什么是 DataMatrix 条码，为什么要调整其长宽比？
DataMatrix 是一种二维矩阵条码，能够在小空间内存储大量数据。调整 **长宽比** 可水平拉伸或压缩模块，对于将条码放入窄列或宽标签而不影响可读性非常有用。

## 先决条件

在开始自定义 DataMatrix 长宽比之前，请确保已具备以下条件：

1. **Visual Studio** – 任意近期版本均可。  
2. **Aspose.BarCode for .NET** – 在此处下载 [here](https://releases.aspose.com/barcode/net/)。  
3. **NET Framework / .NET Core** – 项目必须针对受支持的版本。

## 导入命名空间

首先，需要在 C# 项目中导入必要的命名空间：

```csharp
using Aspose.BarCode.Generation;
```

> **小贴士：** 将此 `using` 语句放在文件顶部，以便随时使用 `BarcodeGenerator` 类。

## 分步指南

### 步骤 1：设置项目
在 Visual Studio 中创建一个新的控制台或 Windows Forms 项目，并添加对 Aspose.BarCode DLL 的引用。

### 步骤 2：初始化条码生成器
实例化一个 `BarcodeGenerator`，指定 DataMatrix 类型以及要编码的数据：

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 这行代码创建了一个生成器，可生成包含示例文本的 DataMatrix 条码。

### 步骤 3：自定义长宽比并保存 PNG 文件
现在可以更改 **长宽比** 并将每个版本保存为 PNG 图像：

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 第一次调用创建一个正方形比例的条码（`AspectRatio = 1`）。  
- 第二次调用水平压缩条码（`AspectRatio = 0.5`），产生更宽的外观。

现在您拥有两个 **条形码 PNG** 文件，长宽比不同，可用于报表、标签或 UI 元素。

## 常见问题与解决方案
| 问题 | 解决方案 |
|-------|----------|
| **生成的图像模糊** | 在保存之前提高 `Resolution` 参数（`gen.Parameters.ImageResolution = 300`）。 |
| **条码无法扫描** | 确保长宽比保持在 0.5 – 2.0 范围内，并保持足够的空白区（`gen.Parameters.Barcode.CodeTextParameters.Margin`）。 |
| **文件路径错误** | 使用 `Path.Combine` 构建输出路径，并确认文件夹已存在。 |

## 常见问答

**问：我可以使用 Aspose.BarCode for .NET 自定义其他条码类型的长宽比吗？**  
答：可以，许多 2‑D 条码（例如 QR、PDF417）都支持通过各自的参数对象调整长宽比。

**问：Aspose.BarCode for .NET 有免费试用吗？**  
答：有，您可以在此处获取 Aspose.BarCode for .NET 的免费试用 [here](https://releases.aspose.com/).

**问：在哪里可以购买 Aspose.BarCode for .NET 的许可证？**  
答：您可以在 Aspose 网站上购买许可证 [here](https://purchase.aspose.com/buy).

**问：Aspose.BarCode for .NET 是否兼容不同的 .NET Framework 版本？**  
答：是的，它兼容 .NET Framework 4.x、.NET Core 3.1+ 以及最新的 .NET 版本。

**问：我可以使用 Aspose.BarCode for .NET 生成不同格式的条码吗？**  
答：当然可以——PNG、JPEG、BMP、GIF、TIFF、SVG 和 PDF 都开箱即支持。

## 结论

使用 Aspose.BarCode for .NET 自定义 DataMatrix 条码的 **长宽比** 并 **创建条形码 PNG** 文件非常简便。按照上述步骤操作，即可生成完全符合项目布局要求的条码。您还可以探索 `Resolution`、`Margin`、`Color` 等其他参数，以进一步定制输出。

欲深入了解，请查阅官方 [documentation](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)。

---

**最后更新：** 2026-01-12  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}