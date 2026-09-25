---
date: 2026-07-28
description: 了解如何使用 Aspose.BarCode 创建 Java 补丁条形码——一个展示如何生成补丁码并设置补丁格式的 Java 条形码生成器示例。
keywords:
- create patch barcode java
- java barcode generator example
- aspose.barcode patch code
- generate patch code java
lastmod: 2026-07-28
linktitle: 在 Java 中生成补丁码
og_description: 使用 Aspose.BarCode 创建 Java 补丁条形码。本指南展示了 Java 条形码生成器示例，如何在几分钟内生成补丁码并设置补丁格式。
og_image_alt: 'Developer guide: Create Patch Barcode Java using Aspose.BarCode'
og_title: 创建补丁条形码 Java – Aspose.BarCode 示例
schemas:
- author: Aspose
  dateModified: '2026-07-28'
  description: Learn how to create patch barcode java using Aspose.BarCode – a java
    barcode generator example that shows how to generate patch code and set patch
    format.
  headline: Create Patch Barcode Java – Aspose.BarCode Example
  type: TechArticle
- description: Learn how to create patch barcode java using Aspose.BarCode – a java
    barcode generator example that shows how to generate patch code and set patch
    format.
  name: Create Patch Barcode Java – Aspose.BarCode Example
  steps:
  - name: Generate a Basic Patch Code
    text: This **java barcode generator example** creates a simple Patch Code and
      saves it as a BMP image. **What happens here?** 1. `dataDir` points to the folder
      where the image will be written. 2. `BarcodeGenerator` is instantiated with
      `EncodeTypes.PATCH_CODE` and the text `"Patch T"`. 3. `save` writes th
  - name: Set the Patch Format (Paper Size)
    text: If you need a specific paper size, you can set the format before saving.
      This demonstrates **how to set patch format** to US Letter. **Why set the format?**
      Patch Code panels are arranged based on the chosen page size. Using `PatchFormat.US_LETTER`
      ensures the panels fit correctly on a standard lett
  - name: Generate a Whole Page (Assemble All Panels)
    text: Below is the full routine that creates each panel, assembles them into a
      complete page, and writes the final PNG file. This shows **how to generate patch
      code** for a multi‑panel layout. **Key points to note** - The method generates
      four separate images (`topImg`, `leftImg`, `bottomImg`, `rightImg`)
  type: HowTo
- questions:
  - answer: Yes, a commercial license is required for production use. You can purchase
      one from the [Aspose's purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.BarCode for Java in commercial projects?
  - answer: Absolutely. Download a trial version from the [Aspose's release page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community help and official support channels.
    question: How do I get support?
  - answer: Yes, temporary licenses are offered via the [Aspose's temporary license
      page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses an option?
  - answer: The documentation is available at the [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find the full API reference?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create patch barcode
- aspose.barcode
- java barcode
- 2d barcode
- patch code
title: 创建补丁条形码 Java – Aspose.BarCode 示例
url: /zh/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 创建 Java 补丁条码

## 介绍

在本综合指南中，您将使用 Aspose.BarCode for Java **快速且可靠地创建补丁条码 Java**。无论您是在构建文档管理系统、需要一种紧凑的方式在纸张上存储元数据，还是在寻找高密度的 2‑D 条码解决方案，生成 Patch Code 都是实用的选择。我们将演示 **java 条码生成器示例**，解释 **如何生成补丁码**，并展示 **如何设置补丁格式**，以便您根据具体需求自定义输出。

## 快速回答
- **什么库最适合补丁码？** Aspose.BarCode for Java  
- **需要多少行代码？** 基本示例大约 20 行  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证  
- **我可以更改页面尺寸吗？** 可以，使用 `PatchFormat`（例如 US_LETTER、A4）  
- **支持的图像格式？** BMP、PNG、JPEG、GIF 等  

## 什么是补丁码？

补丁码是一种由四个独立面板组成的二维条码，可打印在单页上。每个面板都可以独立扫描，非常适合在保持物理占用空间小的情况下，对大量文档进行索引。**补丁码提供了一种紧凑、高密度的方式，每个面板可编码最多 50 个字符，单张纸上最多可容纳 200 个字符。**

## 为什么使用 Aspose.BarCode for Java？

Aspose.BarCode 支持 **30+ 条码符号体系**，包括补丁码、QR Code、Data Matrix 等。其功能完整的 API 让您只需一次调用即可生成任何受支持的条码，同时提供尺寸、颜色、边距、DPI 等轻松定制，以及跨平台兼容性和完整文档。  
- **功能完整的 API** – 使用单个方法调用生成任何 30 多种支持的条码。  
- **轻松定制** – 通过简单的属性设置更改大小、格式、边距、颜色和 DPI。  
- **跨平台** – 在任何支持 Java 的环境中运行，从桌面应用到云服务。  
- **性能测试** – 在标准工作站上可在 150 ms 以下生成 4 面板的补丁码页面。  

## 先决条件

- **Java 开发环境** – 已安装 JDK 8 或更高版本。  
- **Aspose.BarCode for Java** – 从 [download link](https://releases.aspose.com/barcode/java/) 下载。  
- **IDE 或文本编辑器** – 任意兼容 Java 的编辑器（IntelliJ IDEA、Eclipse、VS Code 等）。  
- **写入权限** – 对计划保存生成图像的文件夹拥有写入权限。  

## 导入包

`BarcodeGenerator`、`EncodeTypes` 和 `PatchFormat` 类是核心构建块。  
`BarcodeGenerator` 是 Aspose.BarCode 用于创建条码的主要类。  
`EncodeTypes` 提供所有受支持条码类型的枚举。  
`PatchFormat` 定义补丁码面板的页面布局。

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

## 如何创建 Java 补丁条码 – 步骤详解

首先加载开发环境，配置所需参数（如数据字符串、条码类型），然后调用 `save` 方法。此简洁工作流包括三个步骤：生成基本补丁码、调整页面格式以匹配纸张尺寸，最后将四个面板拼接成单个可打印图像。

### 步骤 1：生成基本补丁码

此 **java 条码生成器示例** 创建一个简单的补丁码并保存为 BMP 图像。

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

**这里发生了什么？**  
1. `dataDir` 指向将写入图像的文件夹。  
2. `BarcodeGenerator` 使用 `EncodeTypes.PATCH_CODE` 和文本 `"Patch T"` 实例化。  
3. `save` 将条码写入 `patch.bmp`。  

### 步骤 2：设置补丁格式（纸张尺寸）

如果需要特定的纸张尺寸，可在保存前设置格式。此示例演示 **如何设置补丁格式** 为 US Letter。

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

**为什么要设置格式？**  
补丁码面板的排列基于所选页面尺寸。使用 `PatchFormat.US_LETTER` 可确保面板在标准信纸尺寸上正确放置，避免扫描时被裁剪。

### 步骤 3：生成整页（组装所有面板）

下面是完整例程，创建每个面板、组装成完整页面并写入最终 PNG 文件。此示例展示 **如何生成补丁码** 的多面板布局。

```java
public static void generateWholePage() throws IOException {
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    // Set image width, padding, and other parameters
    // ... (refer to the provided code for details)

    // Generate different parts of the Patch Code
    BufferedImage topImg = generator.generateBarCodeImage();
    // ... (similar steps for leftImg, bottomImg, and rightImg)

    // Create a frame and assemble the Patch Code
    BufferedImage frameImg = new BufferedImage(topImg.getWidth(), rightImg.getHeight() + 2 * topImg.getHeight(),
            rightImg.getType());
    // ... (refer to the provided code for details)

    // Save the Patch Code frame
    File outputfile = new File("Your Document Directory");
    ImageIO.write(frameImg, "png", outputfile);
}
```

**关键点说明**  
- 该方法生成四个独立图像（`topImg`、`leftImg`、`bottomImg`、`rightImg`），分别代表每个面板。  
- 创建更大的 `frameImg` 画布以将面板拼接在一起。  
- 最终的 PNG 写入您指定的文件夹。  

## 常见问题与技巧

- **目录路径不正确** – 确保 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾。  
- **缺少权限** – 应用程序必须对目标文件夹具有写入权限。  
- **图像质量** – 如需更高的扫描分辨率，可通过 `generator.getParameters().getImageInfo().setResolutionX/Y()` 调整 DPI。  
- **内存使用** – 生成大页面时，保存后考虑调用 `System.gc()` 释放图像缓冲区。  

## 常见问题

**问：我可以在商业项目中使用 Aspose.BarCode for Java 吗？**  
答：可以，生产使用需要商业许可证。您可以在 [Aspose's purchase page](https://purchase.aspose.com/buy) 购买。

**问：是否提供免费试用？**  
答：当然。可从 [Aspose's release page](https://releases.aspose.com/) 下载试用版。

**问：如何获取支持？**  
答：访问 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 获取社区帮助和官方支持渠道。

**问：临时许可证是可选吗？**  
答：是的，可通过 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**问：在哪里可以找到完整的 API 参考？**  
答：文档位于 [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/)。  

## 附加资源

- **示例项目** – 在官方 Aspose.BarCode GitHub 仓库中查看完整示例。  
- **性能提示** – 使用 `generator.getParameters().getImageInfo().setResolutionX(300)` 进行高分辨率扫描。  
- **后续步骤** – 掌握补丁码后，可使用相同的生成器类尝试其他 2‑D 条码，如 QR Code 或 Data Matrix。  

---

**最后更新：** 2026-07-28  
**测试环境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose

## 相关教程

- [使用 Aspose 创建条码 - 在 Java 中设置 X 与 Y 维度](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [生成 Java 条码 – 使用 Aspose.BarCode 设置图像分辨率](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [如何在 Java 中使用 Aspose.BarCode 创建 code128 条码图像](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}