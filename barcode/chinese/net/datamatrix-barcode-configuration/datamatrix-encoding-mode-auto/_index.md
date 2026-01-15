---
date: 2026-01-15
description: 使用 Aspose.BarCode for .NET 的逐步条码教程指南，教您在 C# 中读取 DataMatrix 条码并生成条码图像。
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: 读取 DataMatrix 条码 C# – 生成 DataMatrix 模式（自动）
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 读取 DataMatrix 条形码 C# – 生成 DataMatrix 模式（Auto）

在当今快速发展的数字世界中，能够 **读取 DataMatrix 条形码 C#** 快速且可靠，对于库存跟踪到安全文档处理等各类场景至关重要。本教程将手把手演示如何使用 Aspose.BarCode for .NET 在 *Auto* 模式下生成 DataMatrix 条形码，并展示如何在 C# 中读取该条形码。无论你是在跟随 **条形码教程指南**，还是仅需一个可靠的代码示例，阅读完本指南后，你将获得一个可直接嵌入自己项目的完整解决方案。

## 快速答疑
- **“Auto” 模式有什么作用？** 它让 Aspose.BarCode 自动为你的数据选择最佳的编码方案。  
- **需要哪个库？** Aspose.BarCode for .NET（提供免费试用）。  
- **可以在同一个应用中读取条形码吗？** 可以 – 使用 `BarCodeReader` 并指定 `DecodeType.DataMatrix`。  
- **生产环境需要许可证吗？** 生产使用需购买商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是读取 DataMatrix 条形码 C#？
在 C# 中读取 DataMatrix 条形码即将黑白模块组成的二维矩阵解码回原始文本或数据。Aspose.BarCode 提供了简洁的 API，屏蔽了底层图像处理细节，让你专注于业务逻辑。

## 为什么使用 Aspose.BarCode 生成条形码图像 C#？
- **可靠性：** 支持所有 DataMatrix 标准，并自动选择最优编码。  
- **灵活性：** 完全控制尺寸、ECI 编码和图像格式。  
- **跨平台：** 兼容 .NET Framework、.NET Core 以及 .NET 5+ 应用。

## 前置条件

1. **.NET 环境** – 从 [.NET 网站](https://dotnet.microsoft.com/download/dotnet) 安装最新的 .NET 运行时。  
2. **Aspose.BarCode for .NET** – 从 [官方网站](https://releases.aspose.com/barcode/net/) 下载库。

## 导入命名空间

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

现在命名空间已经就绪，接下来让我们一步步浏览代码。

## 步骤 1：设置目录路径

```csharp
string path = "Your Directory Path";
```

将 `"Your Directory Path"` 替换为你希望保存生成的 PNG（或其他格式）文件的文件夹路径。

## 步骤 2：在 Auto 模式下创建 DataMatrix 条形码

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

`DataMatrixEncodeMode.Auto` 设置让库自行决定提供文本的最佳编码方式。你可以将示例文本替换为任何需要 **生成条形码图像 C#** 的字符串。

## 步骤 3：读取条形码（读取 DataMatrix 条形码 C#）

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

此代码片段解码我们刚生成的图像，并将原始文本打印到控制台，演示了从生成到读取的完整闭环。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **未检测到条形码** | 图像分辨率过低 | 增加 `XDimension.Pixels`（例如设为 6） |
| **出现乱码** | ECI 编码错误 | 将 `ECIEncoding` 设置为匹配你的数据（UTF‑8、ASCII 等） |
| **`ReadBarCodes` 抛出异常** | 位图在读取前被释放 | 保持 `Bitmap` 实例存活至读取完成后再释放 |

## 常见问答

**问：DataMatrix 编码模式 “Auto” 是什么？**  
答：它让 Aspose.BarCode 自动为提供的数据选择最优的编码方法，简化了 **如何生成 datamatrix 条形码** 的过程。

**问：我可以自定义生成条形码的尺寸吗？**  
答：可以 – 调整 `generator.Parameters.Barcode.XDimension.Pixels` 即可改变模块大小。

**问：Aspose.BarCode for .NET 适合商业使用吗？**  
答：完全适合。可从 [官方网站](https://purchase.aspose.com/buy) 购买许可证。

**问：是否提供免费试用？**  
答：提供，可通过 [此链接](https://releases.aspose.com/) 获取免费试用版。

**问：DataMatrix 条形码有哪些编码选项？**  
答：Aspose.BarCode 支持 UTF‑8、ASCII 以及其他 ECI 编码；通过 `ECIEncoding` 设置所需的编码。

## 结论

现在你拥有了一个完整的、可用于生产的示例，能够 **读取 DataMatrix 条形码 C#**、在 Auto 模式下生成条形码并验证结果——全部基于 Aspose.BarCode for .NET。尝试不同的文本、尺寸和 ECI 设置，以满足你的特定场景，并参考官方 [文档](https://reference.aspose.com/barcode/net/) 进行更深入的定制。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-15  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

---