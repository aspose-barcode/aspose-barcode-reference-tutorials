---
date: 2026-03-07
description: 学习如何使用 Aspose.BarCode for .NET 在 C# 中创建带有补充数据的 EAN-13 条形码——快速生成条形码 PNG。
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: 使用补充数据创建 EAN-13 条形码 – Aspose.BarCode
url: /zh/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建带补充数据的 EAN-13 条形码 – Aspose.BarCode for .NET

在本实践教程中，您将**创建包含补充 EAN‑2 或 EAN‑5 数据的 EAN-13 条形码**，并了解如何仅用几行 C# 代码**生成条形码 PNG**文件。无论您是在构建零售收银系统、物流应用程序，还是简单的库存工具，添加补充信息的能力都能让您的条形码更加实用。

## 快速解答
- **“补充数据”是什么意思？** 主条形码旁边打印的额外数字（EAN‑2/EAN‑5），通常用于价格或期号。  
- **使用哪种条形码类型？** 以 EAN‑13 为主符号，可选 EAN‑2 或 EAN‑5 补充。  
- **可以输出 PNG 图像吗？** 可以——`Save` 方法可直接导出为 PNG。  
- **开发是否需要许可证？** 免费试用可用于测试；生产环境需要商业许可证。  
- **是否兼容 .NET Core / .NET 6？** 完全兼容——Aspose.BarCode 支持所有现代 .NET 运行时。

## 前提条件

在深入代码之前，请确保您已具备以下条件：

- Visual Studio（或任何兼容 .NET 的 IDE）。  
- Aspose.BarCode for .NET 的副本——在 **[此处](https://releases.aspose.com/barcode/net/)** 下载。  
- 基本的 C# 知识。  
- 一个可写入的文件夹，用于保存生成的 PNG 文件。

## 导入命名空间

首先，添加 Aspose.BarCode 命名空间，以便访问生成器类：

```csharp
using Aspose.BarCode.Generation;
```

> **专业提示：** 如果您使用 .NET Core，请向项目添加 NuGet 包 `Aspose.BarCode`，而不是手动引用 DLL。

## 什么是补充条形码？

补充条形码是打印在主条形码旁边的辅助数字串。  
- **EAN‑2** – 两位数字的补充，常用于杂志的期号。  
- **EAN‑5** – 五位数字的补充，常用于零售商品的价格扩展。

添加这些补充并不会改变主 EAN‑13 数据；它仅提供扫描仪可以读取的额外上下文。

## 为什么使用 Aspose.BarCode 处理补充数据？

- **一行 API** – 在单个对象中配置主条形码及其补充。  
- **完整的尺寸控制** – 调整 X 维度、补充间距和图像格式。  
- **跨平台** – 支持 .NET Framework、.NET Core 和 .NET 5/6+。  

## 步骤指南

### 步骤 1：设置输出目录

定义 PNG 文件的存放位置。将占位符替换为您机器上的实际路径。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：初始化条形码生成器（Barcode Generator C#）

创建 `BarcodeGenerator` 实例，指定 **EAN‑13** 为主类型并提供 13 位负载。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### 步骤 3：调整条形码尺寸

微调条形码的视觉尺寸以及为补充预留的空间。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### 步骤 4：添加 EAN‑2 补充

将补充数据设置为两位数字（例如 “12”）。它将显示在主条形码的右侧。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### 步骤 5：将 EAN‑2 条形码保存为 PNG

导出图像。`BarCodeImageFormat.Png` 参数确保生成高质量的 PNG 文件。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### 步骤 6：切换为 EAN‑5 补充

将 `SupplementData` 更改为五位数字字符串，用于价格扩展。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### 步骤 7：将 EAN‑5 条形码保存为 PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **为什么这样有效：** 同一个 `BarcodeGenerator` 实例被重复使用，因此只需在每次 `Save` 调用前修改 `SupplementData` 属性。这样代码简洁，避免了不必要的对象创建。

## 常见问题与技巧

- **目录路径无效** – 确保文件夹存在且应用程序具有写入权限。  
- **补充长度不正确** – EAN‑2 必须恰好 2 位，EAN‑5 必须 5 位；否则会抛出异常。  
- **图像不可见** – 确认使用 `BarCodeImageFormat.Png`；其他格式（如 JPEG）可能产生压缩伪影，影响扫描仪读取。  

## 常见问答

### 我可以在 .NET Core 项目中使用 Aspose.BarCode for .NET 吗？
是的，Aspose.BarCode for .NET 完全兼容 .NET Core、.NET 5 和 .NET 6。

### 是否提供 Aspose.BarCode for .NET 的免费试用？
是的，您可以通过访问 **[此链接](https://releases.aspose.com/)** 免费试用。

### 在哪里可以获取 Aspose.BarCode for .NET 的临时许可证？
您可以从 **[此链接](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

### Aspose.BarCode 是否支持广泛的条形码类型？
当然——它支持 EAN‑13、QR Code、Code 128、DataMatrix、PDF‑417 等多种类型。

### 我可以自定义生成的条形码外观吗？
可以，您可以使用丰富的 `Parameters` API 修改颜色、字体、边距，甚至添加背景图像。

## 结论

您现在已经了解如何使用 Aspose.BarCode for .NET **创建带有补充 EAN‑2 或 EAN‑5 数据的 EAN-13 条形码**并**生成条形码 PNG**文件。此方法让您对条形码尺寸、补充间距和输出格式拥有完整控制，非常适用于零售、物流以及任何需要额外数字信息的场景。

欲深入了解，请查阅完整参考指南：**[Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)**。

---

**最后更新：** 2026-03-07  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}