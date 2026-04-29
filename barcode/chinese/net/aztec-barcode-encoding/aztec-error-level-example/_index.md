---
date: 2026-01-09
description: 学习如何使用 Aspose.BarCode for .NET 创建具有可自定义错误纠正级别的 Aztec 条码。分步指南并附有代码示例。
linktitle: Aztec Error Level Example
second_title: Aspose.BarCode .NET API
title: 如何在 .NET 中创建带错误纠正的 Aztec 条码
url: /zh/net/aztec-barcode-encoding/aztec-error-level-example/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中创建带错误纠正的 Aztec 条码

在本分步教程中，您将学习如何使用 Aspose.BarCode for .NET 库 **创建 Aztec 条码** 图像，并设置不同的错误纠正级别。无论是用于包装、票务还是移动扫描，控制错误级别都能帮助您在数据容量和抗损坏性之间取得平衡。我们将逐一演示每个配置选项，提供完整代码示例，并解释每个设置的意义。

## 快速回答
- **使用的库是什么？** Aspose.BarCode for .NET  
- **可以自定义错误级别吗？** 可以 – 任意整数，范围 0 % 到 100 %  
- **推荐使用的 IDE 是？** Visual Studio（任意版本）或带 .NET 支持的 VS Code  
- **需要许可证吗？** 评估阶段可使用临时许可证；生产环境必须购买正式许可证  
- **支持的输出格式？** PNG、JPEG、BMP、GIF 等  

## 什么是带错误纠正的 Aztec 条码？
Aztec 条码是一种二维矩阵码，能够在紧凑的正方形中存储大量数据。错误纠正会添加冗余信息，使得即使条码部分受损或被遮挡仍能被读取。通过调整错误纠正级别，您可以在更高的数据容量（较低错误级别）和更强的抗损坏性（较高错误级别）之间进行选择。

## 为什么选择 Aspose.BarCode for .NET？
Aspose.BarCode 提供流畅的 API，抽象了底层编码细节，让您专注于业务逻辑。它支持广泛的条码标准，提供丰富的自定义选项（尺寸、颜色、边距），并兼容 .NET Framework、.NET Core 以及 .NET 5/6+。这使其成为企业级应用中可靠性和灵活性兼备的理想选择。

## 前置条件

- 具备 C# 基础以及 .NET 生态系统的基本了解。  
- 已安装 Visual Studio、Visual Studio Code 或任意支持 C# 的 IDE。  
- Aspose.BarCode for .NET 库 – 从 [此链接](https://releases.aspose.com/barcode/net/) 下载。  
- （可选）用于无障碍试用的临时许可证 – 在 [此处](https://purchase.aspose.com/temporary-license/) 获取。

## 导入命名空间

首先，将所需的 Aspose.BarCode 命名空间引入项目：

```csharp
using Aspose.BarCode.Generation;
```

## 步骤 1：设置条码生成器

创建 `BarcodeGenerator` 实例，指定 **Aztec** 类型，并提供要编码的数据。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecErrorLevelExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde© is a powerful library to generate & recognize 1D & 2D barcodes");
```

> **小贴士：** 将 `"Your Directory Path"` 替换为您拥有写入权限的绝对或相对路径。

## 步骤 2：定义 X‑Dimension

X‑Dimension 控制条码中最小模块（像素）的宽度。将其设为 4 像素可生成清晰、易扫描的图像。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## 步骤 3：选择 Aztec 符号模式

Aztec 支持多种符号模式。使用 `FullRange` 可让库根据您的数据和错误纠正设置自动选择最佳尺寸。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
```

## 步骤 4：设置错误纠正容量

现在调整错误纠正级别。本示例生成两张条码——一张错误级别为 5 %，另一张为 50 %——以展示视觉差异。

```csharp
// Set error correction capacity to 5%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 5;
gen.Save($"{path}AztecErrorLevel5.png", BarCodeImageFormat.Png);

// Set error correction capacity to 50%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 50;
gen.Save($"{path}AztecErrorLevel50.png", BarCodeImageFormat.Png);
```

运行代码后，指定文件夹中会生成两个 PNG 文件。50 % 版本包含更多冗余数据，因而对损坏的容忍度更高，但符号会稍大一些。

## 常见问题与解决方案

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 条码图像模糊 | X‑Dimension 对所选输出尺寸过低 | 增大 `XDimension.Pixels`（例如设为 6 或 8） |
| 保存操作抛出 *AccessDenied* | 路径无效或不可写 | 确认 `path` 变量指向可写文件夹 |
| 扫描仪无法读取条码 | 错误级别对数据量而言过高 | 降低 `AztecErrorLevel` 或缩短编码文本 |

## 常见问答

**问：Aztec 条码中的错误纠正有什么作用？**  
答：错误纠正确保即使条码部分受损、划伤或被遮挡，仍能被读取。更高的级别会增加冗余，从而提升可靠性。

**问：我可以自定义生成的 Aztec 条码外观吗？**  
答：可以。除了 X‑Dimension 和错误级别，您还可以修改颜色、边距，甚至使用其他 Aspose.BarCode 参数嵌入徽标。

**问：Aspose.BarCode for .NET 是否兼容其他条码格式？**  
答：完全兼容。相同的 `BarcodeGenerator` 类支持 QR Code、DataMatrix、PDF417、Code128 等多种格式。

**问：使用 Aspose.BarCode for .NET 是否必须购买许可证？**  
答：评估期间可使用临时许可证。生产环境请从 [此链接](https://purchase.aspose.com/buy) 购买正式许可证。

**问：在哪里可以找到官方文档？**  
答：完整的 API 参考位于 [此处](https://reference.aspose.com/barcode/net/)。

## 结论

现在，您已经掌握了使用 Aspose.BarCode for .NET **创建带自定义错误纠正级别的 Aztec 条码** 图像的方法。通过调节 X‑Dimension、符号模式和错误级别，您可以生成满足应用对可靠性和尺寸要求的条码。欢迎尝试不同的数据字符串和错误百分比，观察条码的变化。

如果遇到任何问题，可前往 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 与社区交流，官方文档也提供了更深入的高级自定义指南。

---

**最后更新：** 2026-01-09  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
