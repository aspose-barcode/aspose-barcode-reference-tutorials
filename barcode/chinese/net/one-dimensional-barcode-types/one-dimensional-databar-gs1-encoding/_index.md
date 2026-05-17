---
date: 2026-03-07
description: 学习如何在 .NET 中使用 Aspose.BarCode 创建一维 DataBar GS1 编码条形码。本指南展示了如何设置 GS1、配置条形码生成器以及快速生成条形码。
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 创建一维 Databar GS1 编码
url: /zh/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 创建一维 Databar GS1 编码

在本教程中，您将使用 Aspose.BarCode .NET 库**创建符合 GS1 标准的一维 Databar** 条形码。无论您需要严格的 GS1 验证还是更灵活的条码，我们都会一步步演示——从安装库到处理编码异常——帮助您在自己的应用程序中生成可靠的条码。

## 快速答案
- **“创建一维 Databar” 是什么意思？** 指生成一种线性（1‑D）Databar 系列的条形码，常用于零售和物流。  
- **如何设置 GS1 验证？** 在 `DataBar` 参数上将 `IsAllowOnlyGS1Encoding` 设置为 `true`。  
- **我需要许可证吗？** 开发阶段可使用免费试用版；生产环境必须使用商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **在哪里下载库？** 请前往官方 Aspose 发布页面（见前置条件）。

## 什么是“一维 Databar”？
一维 Databar（亦称 RSS）是一种紧凑的线性条形码，可编码数字、日期或 AI（Application Identifier）字符串。配合 GS1 编码后，条码遵循全球通用的数据结构，特别适用于零售、医疗和供应链等场景。

## 为什么在 .NET 中使用 Aspose.BarCode？
Aspose.BarCode 提供流式 API、完整的 GS1 支持，并且可以细致调节条码的每一个视觉属性。它消除了底层编码的猜测，让您专注于业务逻辑。

## 前置条件

1. **Aspose.BarCode for .NET** – 从 [here](https://releases.aspose.com/barcode/net/) 下载并安装。  
2. **Your Directory Path** – 将示例中的 `"Your Directory Path"` 替换为您拥有写入权限的文件夹路径。

## 导入命名空间

在 C# 文件顶部添加所需的 `using` 语句：

```csharp
using Aspose.BarCode;
using System;
```

## 步骤 1：初始化条码生成器

创建 `BarcodeGenerator` 实例并指定 Databar Expanded 符号集：

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## 步骤 2：如何设置 GS1 – 生成严格 GS1 验证的条码

启用仅 GS1 编码，分配符合 GS1 标准的代码文本，并保存图像：

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## 步骤 3：使用 Aspose 生成条码 – 可变编码（关闭 GS1 检查）

如果需要**不**强制执行 GS1 规则的条码，只需关闭检查：

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## 步骤 4：条码生成器 GS1 检查 – 处理异常

当 `IsAllowOnlyGS1Encoding` 为 `true` 而代码文本不符合 GS1 标准时，Aspose 会抛出异常。下面的示例展示了如何捕获并记录该异常：

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### 常见陷阱与技巧
- **陷阱：** 在启用 GS1 检查的情况下提供非 GS1 字符串会导致条码生成中止。  
- **专业提示：** 在将 AI 字符串赋给 `CodeText` 之前先进行验证，以避免运行时错误。  
- **技巧：** 使用绝对路径或 `Path.Combine` 来安全地跨平台构建文件名。

## 结论

现在，您已经掌握了如何使用 Aspose.BarCode for .NET **创建一维 Databar** 条形码并进行 GS1 编码、如何切换 GS1 检查以及如何处理相关异常。欢迎通过 `Parameters.Barcode` 对象进一步探索条码大小、颜色、边距等样式选项。

如果遇到问题，官方文档和社区论坛都是极好的资源：

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## 常见问题

### 1. 什么是条码中的 GS1 编码？
GS1 编码是一种标准化的数据结构（例如产品标识符），用于在条码内部组织信息，确保零售商、制造商和物流供应商之间的互操作性。

### 2. 我可以自定义生成条码的外观吗？
可以。Aspose.BarCode 允许您通过 `Parameters.Barcode` 设置调整尺寸、颜色、边距，甚至添加可读文本。

### 3. 在哪里可以找到 Aspose.BarCode 的更多资源和文档？
您可以在 [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) 查看完整的文档和示例，这是学习和排查问题的宝贵资源。

### 4. Aspose.BarCode 有试用版吗？
有，您可以从 [here](https://releases.aspose.com/) 获取 Aspose.BarCode for .NET 的免费试用版。

### 5. 如何购买 Aspose.BarCode for .NET 的许可证？
请访问 Aspose 网站的 [purchase page](https://purchase.aspose.com/buy) 进行购买。

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}