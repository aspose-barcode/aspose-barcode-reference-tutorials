---
date: 2026-01-30
description: 学习如何在 C# 中创建 DataMatrix 条码并使用条码阅读器。本指南涵盖使用 Aspose 进行条码生成、读取以及使用 Aspose.BarCode
  for .NET 进行阅读器编程。
linktitle: DataMatrix Reader Programming
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 创建 DataMatrix 条码
url: /zh/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 创建 DataMatrix 条码并读取它

您准备好使用 Aspose.BarCode for .NET 解锁 DataMatrix 条码读取编程的世界了吗？在本教程中，您将 **创建 DataMatrix 条码** 图像，嵌入读取器编程数据，并学习如何在 C# 应用程序中 **使用条码读取器** 功能。完成后，您将拥有一个可直接投放到自己项目中的完整、可生产的示例。

## 快速回答
- **我可以实现什么？** 生成 DataMatrix 条码并读取其读取器编程标志。  
- **使用哪个库？** Aspose.BarCode for .NET（支持 .NET Framework 与 及更高版本中运行。  
- **需要许可证吗？** 免费试用可用于开发；生产环境需商业许可证。  
- **需要多长时间？** 大约 10‑15 分钟即可复制、运行并适配示例。

## 什么是 “创建 DataMatrix 条码” 编程？
创建 DataMatrix 条码即将数据编码为由黑白单元格组成的二维矩阵。当 **IsReaderProgramming条码还会## 为什么使用 Aspose.BarCode for .NET？
Aspose.BarCode 提供了一个统一且文档完善的 API，适用于 **条码生成 Aspose** 和 **使用条码读取器** 场景。它支持最新的 .NET 版本，提供高性能的编码/解码，并且不需要外部本机依赖。

## 前置条件
1. **Visual Studio**（任意近期版本），并已安装 .NET Framework 或 .NET Core SDK。  
2. **Aspose.BarCode for .NET** – 从[下载页面](https://releases.aspose.com/barcode/net/)获取。  
3 **C#** 知识 – 示例仅使用标准 .NET 类。

## 导入命名空间
在 .NET 中，需要将相关命名空间引入作用域，以便编译器找到条码类。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## 如何以编程方式创建 DataMatrix 条码

### 步骤 1：定义目录路径
设置生成的图像将要保存的文件夹。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：初始化 BarcodeGenerator
创建 `BarcodeGenerator` 实例，选择 **EncodeTypes.DataMatrix**，并启用读取器编程。

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

### 步骤 3：生成条码图像
下面的象。

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

### 步骤 4：使用条码读取器验证标志
现在使用 **BarCodeReader** 读取图像，并确认 **IsReaderProgramming** 标志是否存在。

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

## 常见问题与故障排除
- **路径无效** – 确保 `path` 中的文件夹已存在且应用程序拥有写入权限。  
-有效许可证运行时，生成的图像会带有水印。  
- **不受支持的 .NET 版本** – 请确认使用的是受支持的框架（例如 .NET

### Q1: 什么是 DataMatrix 读取器编程？
A1: DataMatrix 读取器编程指的是在 DataMatrix 条码格式中编码数据，使其能够被条码扫描器或软件轻松读取。此编程常用于制造业、医疗保健和物流等行业的数据存储与检索。

### Q2: 为什么选择 Aspose.BarCode for .NET？
A2: Aspose.BarCode for .NET 是一个强大且多条码生成、读取和码类型提供广泛支持，是开发者的首选。

### Q3: 我可以免费使用 Aspose.BarCode 吗？
A3: Aspose.BarCode 提供免费试用版供评估使用。但若用于商业用途，则需购买许可证。您可以通过[此链接](https://purchase.aspose.com/buy)获取许可证。

### Q4: 如何获取 Aspose.BarCode 的临时许可证？
A4: 若需要用于短期项目的临时许可证，可从[此链接](https://purchase.aspose.com/temporary-license/)获取。

### Q5: Aspose.BarCode 与最新的 .NET Framework 兼容吗？
A5: 是的，Aspose.BarCode for .NET 设计为兼容多种 .NET Framework 版本，包括最新的发布版。

## 其他常见问题

**问：如何在 C# 中生成不带读取器编程的 DataMatrix 条码？**  
答：Programming = true;` 这一行，条码将正常条码类型吗？**  
答：可以，`BarCodeReader` 支持多种符号集。将 `DecodeType.DataMatrix` 改为所需的类型（例如 `DecodeType.QR`）。

**问：Aspose.BarCode 是否支持 .NET Core / .NET 5 及以上？**  
答：完全支持。该库兼容 .NET Core 3.1、.更高版本。

**问：有没有办法批量处理多个图像？**  
答：可以将 `BarCodeReader` 逻辑放入循环中，遍历文件路径集合或 `Bitmap` 对象。

## 结论
通过上述步骤，您现在已经掌握了如何 **创建 DataMatrix 条码**、嵌入读取器编程数据，以及如何使用 Aspose.BarCode for .NET 的 **条码读取器** 功将代码集成到更大的库存管理系统中。

欲了解更深入的细节，请查阅官方[文档](https://reference.aspose.com/barcode/net/)或加入[Aspose.BarCode 支持论坛](https://forum.aspose.com/c/barcode/13)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-30  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

---