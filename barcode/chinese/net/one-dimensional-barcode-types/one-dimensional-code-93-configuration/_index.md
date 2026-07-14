---
date: 2026-02-25
description: 学习如何使用 Aspose.BarCode for .NET 生成条形码图像并保存为 PNG——完整的 Aspose 条形码示例。
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 生成 Code 93 条形码图像
url: /zh/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成条形码图像 – 一维 Code 93 使用 Aspose.BarCode

## 介绍

在当今数字化时代，条形码已成为我们生活中不可或缺的一部分，简化了库存管理、产品标签和销售点跟踪等流程。**生成条形码图像**通常是将这些标识符集成到应用程序中的第一步。Aspose.BarCode for .NET 提供了强大且易于使用的 API，只需几行 C# 代码即可创建高质量的 Code 93 条形码。无论您是构建仓库系统、零售应用还是自定义报表工具，本教程将带您完整了解 **aspose barcode example**，展示如何生成、定制并 **保存条形码 PNG** 文件。

## 快速答疑
- **本教程涵盖什么内容？** 创建并保存带有校验和处理的 Code 93 条形码图像。  
- **使用哪个库？** Aspose.BarCode for .NET（最新稳定版）。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需商业许可证。  
- **可以更改输出格式吗？** 可以——通过修改 `BarCodeImageFormat`，可保存为 PNG、JPEG、BMP 等。  
- **最低要求是什么？** .NET Framework 4.6+ 或 .NET Core 3.1+，以及 Visual Studio。

## 什么是 Code 93 条形码？
Code 93 是一种高密度的字母数字符号系统，支持完整的 ASCII 字符集。它因体积小且内置校验和而常被选用，能够在扫描时帮助确保数据完整性。

## 为什么使用 Aspose.BarCode 生成条形码图像？
- **完全控制** 编码类型、校验和、尺寸和图像格式。  
- **无外部依赖** ——库可在任何 .NET 平台上运行。  
- **卓越的渲染质量**，适用于屏幕显示和高分辨率打印。  
- **完善的文档** 与大量示例，加速开发。

## 前置条件

在开始编写代码之前，请确保您具备以下条件：

1. **Visual Studio**（任意近期版本）。  
2. 已安装 **Aspose.BarCode for .NET** ——可从官方下载页面获取。  
3. 对 **C#** 和 .NET 项目结构有基本了解。

准备就绪后，接下来进入逐步指南。

## 导入命名空间

首先，导入所需的命名空间，以便访问条形码生成类。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 步骤 1：设置目录路径

定义生成的条形码图像保存位置。将占位符替换为机器上有效的文件夹路径。

```csharp
string path = "Your Directory Path";
```

## 步骤 2：创建一维 Code 93 条形码

实例化 `BarcodeGenerator`，使用 `Code93Extended` 类型并传入要编码的数据。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## 步骤 3：启用校验和（可选）

Code 93 默认包含校验和。您可以通过 `IsChecksumEnabled` 属性进行切换。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## 步骤 4：保存条形码图像（保存条形码 PNG）

生成图像并将其以 PNG 文件保存到前面指定的文件夹中。

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## 步骤 5：异常处理 – 生成不带校验和的条形码

如果需要创建**不带**校验和的条形码，必须处理可能出现的异常。

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### 常见问题及解决方案
- **路径无效** ——确保目录存在且应用程序拥有写入权限。  
- **不支持的字符** ——Code 93 支持完整 ASCII 集，但控制字符可能导致错误。  
- **未设置许可证** ——未提供有效许可证时，库以评估模式运行，可能会添加水印。

## 常见问答（FAQs）

### 问：在哪里可以找到 Aspose.BarCode for .NET 的文档？
答：您可以在 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 查看文档。

### 问：如何下载 Aspose.BarCode for .NET？
答：您可以从 [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/) 下载。

### 问：Aspose.BarCode for .NET 是否提供免费试用？
答：是的，您可以在[此处](https://releases.aspose.com/)获取免费试用版。

### 问：如何购买 Aspose.BarCode for .NET 的许可证？
答：请在 [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy) 页面购买。

### 问：在哪里可以获得 Aspose.BarCode for .NET 的支持或提问？
答：您可以在 [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13) 论坛获取支持和讨论。

---

**最后更新：** 2026-02-25  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}