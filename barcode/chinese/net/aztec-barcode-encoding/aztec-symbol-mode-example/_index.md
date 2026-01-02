---
date: 2026-01-02
description: 学习如何在 Aspose.BarCode for .NET 中使用 Aztec 条码生成器——一步步指南，教您如何设置 Aztec 符号模式（Auto、FullRange、Compact、Rune）。
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: 条码生成器 Aztec – 使用 Aspose.BarCode for .NET 掌握 Aztec 符号模式
url: /zh/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – 掌握 Aspose.BarCode for .NET 中的 Aztec 符号模式

## Quick Answers
- **What is the primary class?** `BarcodeGenerator` from `Aspose.BarCode.Generation`.
- **Which Symbol Modes are available?** Auto, FullRange, Compact, and Rune.
- **Do I need a license?** A temporary license works for testing; a full license is required for production.
- **Can I change the code text?** Yes, set `gen.CodeText` before saving.
- **What image formats are supported?** PNG, JPEG, BMP, GIF, TIFF, and more.

## What is a barcode generator aztec?
barcode generator aztec 创建二维 Aztec 码，这是一种紧凑的矩阵条码，能够在小空间内存储大量数据。它非常适用于移动票证、URL 和空间受限的二进制数据。

## Why use Aspose.BarCode for .NET?
- **Full .NET support** – works with .NET Framework, .NET Core, and .NET 5/6.
- **Rich feature set** – multiple symbol modes, error correction, and extensive customization.
- **No external dependencies** – generate barcodes completely in‑process.
- **Cross‑platform** – run on Windows, Linux, and macOS.

## Prerequisites

- A working knowledge of .NET development.  
- Visual Studio installed on your machine.  
- A copy of Aspose.BarCode for .NET. You can download it [here](https://releases.aspose.com/barcode/net/).

Now that you're ready, let’s explore the Aztec Symbol Mode options.

## How to set Aztec Symbol Mode with the barcode generator aztec

### Importing Namespaces

First, add the required namespace at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
```

With the namespace imported, you can start creating Aztec barcodes.

### Step 1: Setting up the Barcode Generator

Initialize the generator with the Aztec encoding type and provide the text you want to encode:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Pro tip:** Use a UTF‑8 compatible string for international characters, as shown above.

### Step 2: Setting the Symbol Mode to Auto

The **Auto** mode lets the library decide the optimal size based on the data length:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

The generated PNG will be saved to the folder you specified.

### Step 3: Setting the Symbol Mode to FullRange

If you want the library to use the full range of Aztec symbol sizes, choose **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Step 4: Setting the Symbol Mode to Compact

For a more compact barcode that still retains good readability, use **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Step 5: Setting the Symbol Mode to Rune

The **Rune** mode is designed for special use‑cases where a different visual style is required:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Common Issues and Solutions

| 问题 | 解决方案 |
|-------|----------|
| Barcode image is blank | Verify that `path` points to an existing writable directory. |
| Unsupported characters | Use only characters supported by the Aztec standard or switch to UTF‑8 encoding. |
| Wrong symbol size | Experiment with `AztecSymbolMode.Auto` to let the library pick the best size. |

## Frequently Asked Questions

**Q: What is the purpose of Aztec Symbol Mode in barcode generation?**  
A: It lets you control the visual density and error‑correction level of the Aztec code, tailoring the barcode to your space and readability requirements.

**Q: Can I change the code text for Aztec barcodes in Aspose.BarCode for .NET?**  
A: Yes, simply assign a new string to `gen.CodeText` before calling `Save`.

**Q: Is there a free trial version of Aspose.BarCode for .NET?**  
A: Yes, you can download a free trial [here](https://releases.aspose.com/).

**Q: Where can I find the full documentation for Aspose.BarCode for .NET?**  
A: The complete API reference is available [here](https://reference.aspose.com/barcode/net/).

**Q: How can I obtain a temporary license for Aspose.BarCode for .NET?**  
A: A temporary license can be requested through [this link](https://purchase.aspose.com/temporary-license/).

## Conclusion

In this guide we covered everything you need to know to use the **barcode generator aztec** with Aspose.BarCode for .NET, from setting up the generator to mastering each Symbol Mode (Auto, FullRange, Compact, Rune). Armed with these examples, you can now embed versatile Aztec barcodes into any .NET application quickly and reliably.

If you have more questions, feel free to join the Aspose.BarCode community on their [support forum](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-02  
**测试环境：** Aspose.BarCode 24.10 for .NET  
**作者：** Aspose