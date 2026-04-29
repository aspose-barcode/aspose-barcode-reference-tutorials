---
date: 2026-01-04
description: 了解如何使用 Aspose.BarCode for .NET 生成带起始和终止字符的 Codabar 条码。为开发者提供的逐步条码生成教程。
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: 在 Aspose.BarCode for .NET 中生成带起止字符的 Codabar 条码
url: /zh/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 生成带起止字符的 Codabar 条码

## 介绍

欢迎阅读本完整指南，了解如何使用 Aspose.BarCode for .NET **生成带起止字符的 Codabar 条码** 图像。无论您是在构建零售库存系统、实验室样本追踪器，还是医疗记录解决方案，Codabar 都是一种可靠的数字符号，需要显式的起止符号才能实现准确扫描。接下来几分钟，我们将从前置条件到保存最终 PNG 文件的全部步骤逐一讲解，帮助您立即开始创建 Codabar 条码。

## 快速答案
- **需要哪个库？** Aspose.BarCode for .NET  
- **条码可以保存为何种格式？** PNG (BarCodeImageFormat.Png)  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需商业许可证。  
- **可以更改起止符号吗？** 可以 – 使用 CodabarSymbol.A、B、C 或 D。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 前置条件

在开始之前，请确保您具备以下条件，以便顺利完成本教程：

1. **环境搭建** – 确保机器上已安装可用的 .NET 开发环境。如需指导，请参阅[文档](https://reference.aspose.com/barcode/net/)。  
2. **Aspose.BarCode for .NET 库** – 从官方[下载页面](https://releases.aspose.com/barcode/net/)获取并安装库。  
3. **基本的 .NET 知识** – 熟悉 C# 与 Visual Studio（或其他 IDE）会让步骤更顺畅。  
4. **IDE** – Visual Studio、Rider 或 Visual Studio Code 都可。  

现在我们已经完成前置条件的说明，下面进入实际代码。

## 导入命名空间

要使用 Aspose.BarCode for .NET，请先导入必要的命名空间：

```csharp
using Aspose.BarCode.Generation;
```

## 如何生成 Codabar 条码 – 步骤指南

### 步骤 1：初始化条码生成器

创建 `BarcodeGenerator` 实例，指定 **Codabar** 为编码类型，并提供已包含起止字符的数据字符串（例如 “-12345-”）。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **小贴士：** 短横线（`-`）是 Codabar 的有效起止符号之一。您也可以根据业务需求使用 A、B、C 或 D。

### 步骤 2：设置 X‑Dimension（条码单元宽度）

X‑Dimension 控制最窄条的宽度。根据扫描环境进行调整。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **为什么重要：** 较大的 X‑Dimension 能提升低分辨率打印机的可读性，而较小的数值则可在高密度标签上节省空间。

### 步骤 3：定义起止字符

Codabar 支持四种起止符号（A、B、C、D）。下面给出每种选项的示例。请选择与您系统规范相匹配的符号。

#### 设置起始 A 和结束 A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### 设置起始 B 和结束 B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### 设置起始 C 和结束 C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### 设置起始 D 和结束 D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

您可以为需要的每个符号重复上述配置；下面的示例会分别保存四张图片——每对起止符号对应一张。

### 步骤 4：保存生成的条码图像（PNG）

最后，将条码写入 PNG 文件。这演示了 **save barcode png** 的使用场景，并为测试提供了可直接使用的资源。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

每个文件现在都包含一个带相应起止符号的 **codabar 条码示例**。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| 条码显示扭曲 | X‑Dimension 对所选打印机分辨率过低 | 增大 `XDimension.Pixels`（例如设为 3 或 4） |
| 扫描仪无法读取起止符 | 为目标系统设置了错误的起止符 | 核实所需符号（A‑D），并相应设置 |
| PNG 文件为空或损坏 | 输出路径无效或写入权限不足 | 确认 `path` 指向已存在的文件夹，且应用拥有写入权限 |

## 常见问答

### Q1：什么是 Codabar，为什么起止字符很重要？

A1：Codabar 是一种广泛用于库存、图书馆和医疗行业的数字条码符号。起止字符定义了条码的边界，确保扫描器能够准确识别数据的起始和结束位置。

### Q2：我可以使用 Aspose.BarCode for .NET 自定义 Codabar 条码的外观吗？

A2：可以。除了 X‑Dimension，您还可以修改颜色、添加边距，甚至使用相同的 API 将条码嵌入 PDF 或 SVG 格式。

### Q3：Codabar 条码在数据编码方面有什么限制？

A3：Codabar 主要支持数字（0‑9）和少量特殊字符，不适用于完整的字母数字字符串。

### Q4：Aspose.BarCode for .NET 是否适合商业使用，如何获取许可证？

A4：是的，已具备生产就绪能力。请在[Aspose 购买页面](https://purchase.aspose.com/buy)购买许可证。

### Q5：我可以在哪里获取帮助或讨论 Aspose.BarCode for .NET 相关问题？

A5：加入[Aspose.BarCode for .NET 支持论坛](https://forum.aspose.com/c/barcode/13)，与 Aspose 工程师及其他开发者交流。

---

**最后更新：** 2026-01-04  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}