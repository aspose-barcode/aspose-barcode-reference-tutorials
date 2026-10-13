---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 为 GS1 coupon supplement 创建 barcode 自定义空间并提升
  barcode 可读性。请按照我们的分步指南操作。
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 coupon supplement 空间配置
og_description: 了解如何使用 Aspose.BarCode for .NET 为 GS1 coupon supplement 创建 barcode
  自定义空间并提升 barcode 可读性。包括分步代码和技巧。
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: 为 GS1 coupon supplement 创建 barcode 自定义空间 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: 如何为 GS1 coupon supplement 创建 barcode 自定义空间
url: /zh/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1优惠券补充空间配置

在本教程中，您将使用 Aspose.BarCode for .NET **create barcode custom space**，用于 GS1 Coupon Supplement Space。调整补充空间在需要 **increase barcode readability**（针对低分辨率扫描仪）或遵守零售商规定的边距时至关重要。阅读完本指南后，您将了解补充空间为何重要、如何以编程方式设置它，以及如何生成具有不同像素值的图像。

## 快速答案

- **补充空间控制什么？** 它定义了优惠券数据与条形码其余部分之间的空白区域（以像素为单位）。  
- **使用哪种条形码类型？** `EncodeTypes.UpcaGs1DatabarCoupon`。  
- **我可以更改空间大小吗？** 是的——将 `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` 设置为任意整数值。  
- **此功能需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些输出格式？** PNG、JPEG、BMP、GIF、TIFF 等，更多格式可通过 `BarCodeImageFormat` 获得。  

## GS1优惠券补充空间是什么？

GS1 Coupon Supplement Space 是出现在 GS1‑Databar 优惠券条形码中的定义的空白区域。零售系统使用此空间来提高扫描可靠性，并符合行业规范对补充数据周围最小边距的要求。

## 为什么要配置补充空间？

补充空间直接 **increases barcode readability**，并帮助您满足严格的零售商指南。通过添加额外像素，您可以降低低分辨率扫描仪误读的可能性，确保在不同标签尺寸下扫描的一致性，并为在印刷布局中平衡条形码提供视觉灵活性。

## 先决条件

在我们深入使用 Aspose.BarCode for .NET 配置 GS1 Coupon Supplement Space 之前，请确保您具备以下条件：

1. **Visual Studio** – .NET 开发的主要 IDE。  
2. **Aspose.BarCode for .NET** – 从 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 下载库。  
3. **.NET Framework or .NET 5+** – 需要熟悉 C# 和 .NET 运行时。  

环境准备就绪后，让我们继续实现步骤。

## 导入命名空间

`Aspose.BarCode.Generation` 命名空间包含 `BarcodeGenerator` 类及相关设置。

```csharp
using Aspose.BarCode;
```

## 步骤 1：定义路径

选择一个用于保存生成图像的文件夹。路径必须以适合您操作系统的目录分隔符结尾。

```csharp
string path = "Your Directory Path";
```

## 步骤 2：生成 GS1 优惠券补充空间配置

以下代码片段创建条形码，设置 X 维度，并调整补充空间。

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

在本示例中，我们：

1. **Create** 一个 `BarcodeGenerator` 实例，类型为 `UpcaGs1DatabarCoupon`。  
2. **Set** X‑dimension 为 2 像素，它决定最窄条的宽度。  
3. **Adjust** 将 `SupplementSpace.Pixels` 属性设置为 30 px，生成图像，然后再使用 50 px 重复。  

欢迎尝试其他像素值，以匹配您的打印工作流。

## 常见问题与技巧

- **Invalid path** – 确保 `path` 变量以适合您操作系统的反斜杠 (`\`) 或正斜杠 (`/`) 结尾。  
- **Insufficient permissions** – 以管理员身份运行 Visual Studio，或选择应用程序具有写入权限的文件夹。  
- **Incorrect data format** – 数据字符串必须遵循 GS1 语法（`(8110)` 表示补充标识符）。  

## 这对您的业务为何重要

Aspose.BarCode 支持 **over 60 barcode symbologies**，并且能够渲染最高达 **10,000 × 10,000 pixels** 的图像而不会耗尽内存。对于大规模零售部署，这意味着您可以在批处理模式下生成高分辨率的 GS1 优惠券，并在典型服务器硬件上将每张图像的处理时间保持在一秒以内。

## 常见问题

**Q: GS1 Coupon Supplement Space 在条形码中的作用是什么？**  
A: 它在补充数据周围添加强制性的空白边距，提高扫描仪的可靠性，并满足零售商指定的最小宽度要求。

**Q: 我可以使用 Aspose.BarCode for .NET 自定义 GS1 Coupon Supplement Space 的宽度吗？**  
A: 是的，将 `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` 设置为任意整数值；库会立即将更改应用到生成的图像中。

**Q: 在哪里可以找到 Aspose.BarCode for .NET 的更多文档和支持？**  
A: 请参阅 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 并访问 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 获取社区帮助。

**Q: Aspose.BarCode for .NET 适合初学者和有经验的开发者吗？**  
A: 当然。该 API 提供简洁的方法用于快速任务，也提供高级选项用于精细的条形码生成。

**Q: 我可以获取 Aspose.BarCode for .NET 的临时许可证来评估其功能吗？**  
A: 是的，可从 [Aspose temporary license website](https://purchase.aspose.com/temporary-license/) 请求试用许可证。

## 结论

通过遵循上述步骤，您现在了解如何 **create barcode custom space** 用于 GS1 Coupon Supplement Space，这是一项提升 **increase barcode readability** 并满足零售标准的关键技术。将代码集成到您现有的扫描解决方案中，尝试不同的像素值，并探索 Aspose.BarCode for .NET 提供的其他条形码类型。

---

**最后更新：** 2026-09-28  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相关教程

- [使用 .NET API 生成 Aspose.BarCode Databar 条形码 – 行列配置](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码的分步指南](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}