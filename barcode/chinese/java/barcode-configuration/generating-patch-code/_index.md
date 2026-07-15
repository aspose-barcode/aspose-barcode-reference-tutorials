---
date: 2026-02-15
description: 学习如何使用 Aspose.BarCode 在 Java 中创建补丁条码——一个 Java 条码生成器示例，展示如何生成补丁码并设置补丁格式。
linktitle: Generating a Patch Code in Java
second_title: Aspose.BarCode Java API
title: 创建补丁条码 Java – 使用 Aspose.BarCode 生成补丁码
url: /zh/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Java 中创建 Patch 条形码

## 介绍

在本综合指南中，您将 **快速且可靠地使用 Aspose.BarCode for Java 创建 patch barcode java**。无论您是在构建文档管理系统、需要一种紧凑的方式在纸张上存储元数据，还是在寻找高密度的 2‑D 条形码解决方案，生成 Patch Code 都是实用的选择。我们将演示一个 **java barcode generator example**，解释 **how to generate patch code**，并展示 **how to set patch format**，帮助您根据具体需求自定义输出。

## 快速答案
- **哪种库最适合 Patch Code？** Aspose.BarCode for Java
- **需要多少行代码？** 基本示例约 20 行
- **是否需要许可证？** 开发阶段可使用免费试用版；生产环境需商业许可证
- **可以更改页面尺寸吗？** 可以，使用 `PatchFormat`（例如 US_LETTER、A4）
- **支持的图像格式？** BMP、PNG、JPEG、GIF 等

## 什么是 Patch Code？
Patch Code 是一种由四个独立面板组成的二维条形码，可打印在同一页上。每个面板都可以独立扫描，非常适合在保持物理占用面积小的前提下，对大量文档进行索引。

## 为什么使用 Aspose.BarCode for Java？
- **功能完整的 API** – 支持所有主流条形码类型，包括 Patch Code。
- **轻松自定义** – 通过简单的属性调用即可更改尺寸、格式、边距等。
- **跨平台** – 适用于任何支持 Java 的环境，从桌面应用到 Web 服务均可。
- **文档完善** – 丰富的示例和 API 参考帮助您快速上手。

## 前提条件

在开始之前，请确保您具备以下条件：

- **Java 开发环境** – 已安装 JDK 8 或更高版本。
- **Aspose.BarCode for Java** – 从 [download link](https://releases.aspose.com/barcode/java/) 下载。
- **IDE 或文本编辑器** – 任意支持 Java 的编辑器（IntelliJ IDEA、Eclipse、VS Code 等）。
- 对计划保存生成图像的文件夹拥有 **写入权限**。

## 导入包

首先，导入所需的类。下面的代码片段展示了全部需要的导入语句：

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

## 如何在 Java 中创建 Patch 条形码 – 步骤详解

下面提供了一个清晰的编号步骤，将每个代码块与具体操作对应。您可以直接复制这些代码片段，只需将占位符文件夹路径替换为实际路径即可运行。

### 步骤 1：生成基本的 Patch Code

此 **java barcode generator example** 创建一个简单的 Patch Code 并保存为 BMP 图像。

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

**这里发生了什么？**
1. `dataDir` 指向图像将要写入的文件夹。
2. 使用 `EncodeTypes.PATCH_CODE` 和文本 `"Patch T"` 实例化 `BarcodeGenerator`。
3. `save` 将条形码写入 `patch.bmp`。

### 步骤 2：设置 Patch 格式（纸张尺寸）

如果需要特定的纸张尺寸，可在保存前设置格式。以下示例演示 **how to set patch format** 为 US Letter。

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

**为什么要设置格式？**  
Patch Code 面板的排列基于所选页面尺寸。使用 `PatchFormat.US_LETTER` 可确保面板在标准信纸尺寸上正确布局。

### 步骤 3：生成完整页面（组装所有面板）

下面的完整例程会创建每个面板，将它们组装成一整页，并写入最终的 PNG 文件。这一步展示了 **how to generate patch code** 用于多面板布局的实现方式。

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
- 该方法生成四个独立图像（`topImg`、`leftImg`、`bottomImg`、`rightImg`），分别对应每个面板。
- 创建更大的 `frameImg` 画布用于拼接这些面板。
- 最终的 PNG 文件会写入您指定的文件夹。

## 常见问题与技巧

- **目录路径不正确** – 确保 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾。  
- **缺少权限** – 应用程序必须对目标文件夹拥有写入权限。  
- **图像质量** – 如需更高的扫描分辨率，可通过 `generator.getParameters().getImageInfo().setResolutionX/Y()` 调整 DPI。  
- **内存使用** – 生成大页面时，保存后可调用 `System.gc()` 释放图像缓冲区。

## 常见问答

**Q: 可以在商业项目中使用 Aspose.BarCode for Java 吗？**  
A: 可以，生产环境需要购买商业许可证。您可在 [Aspose's purchase page](https://purchase.aspose.com/buy) 购买。

**Q: 有免费试用版吗？**  
A: 当然。可从 [Aspose's release page](https://releases.aspose.com/) 下载试用版本。

**Q: 如何获取技术支持？**  
A: 访问 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 获取社区帮助及官方支持渠道。

**Q: 临时许可证可以吗？**  
A: 可以，临时许可证可通过 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 申请。

**Q: 哪里可以查阅完整的 API 参考？**  
A: 请访问 [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/)。

## 其他资源

- **示例项目** – 在官方 Aspose.BarCode GitHub 仓库中探索完整示例。  
- **性能技巧** – 使用 `generator.getParameters().getImageInfo().setResolutionX(300)` 可获得高分辨率扫描效果。  
- **后续步骤** – 掌握 Patch Code 后，可使用同一生成器类尝试 QR Code、Data Matrix 等其他 2‑D 条形码。

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.BarCode for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}