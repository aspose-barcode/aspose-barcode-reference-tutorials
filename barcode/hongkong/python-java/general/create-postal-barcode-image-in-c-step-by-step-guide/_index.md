---
category: general
date: 2026-08-03
description: 快速在 C# 中建立郵政條碼圖像。了解如何產生郵政條碼、設定條碼尺寸，並產生 Planet 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: zh-hant
lastmod: 2026-08-03
og_description: 使用完整教學在 C# 中建立郵政條碼圖像；了解如何設定條碼尺寸、產生 Planet 條碼以及產生 RM4SCC 條碼。
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: 在 C# 中建立郵政條碼圖像 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: 在 C# 中建立郵政條碼圖像 – 步驟指南
url: /zh-hant/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立郵政條碼圖像 – 步驟指南

如果您需要在 C# 中 **建立郵政條碼圖像**，本指南將逐步說明。我們將涵蓋 **如何產生郵政條碼**、**如何設定條碼尺寸**，以及 **如何產生 Planet 條碼** 以符合常見的郵政標準。

您將得到兩個即用的 PNG 檔案——一個 Planet 條碼和一個 RM4SCC 條碼——每個皆為 100 px 高。除了 Aspose.BarCode for .NET 函式庫外，無需其他工具。

## 前置條件

* .NET 6 SDK 或更新版本（此程式碼亦適用於 .NET Framework 4.7+）
* Visual Studio 2022 或任何 C# IDE
* NuGet 套件 **Aspose.BarCode**（提供 `BarcodeGenerator` 的函式庫）

## 步驟 1：安裝條碼函式庫

在專案資料夾中開啟終端機並執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，內含產生郵政條碼所需的 `BarcodeGenerator` 與 `EncodeTypes` 列舉。

## 步驟 2：定義輸出資料夾

建立可靠的輸出路徑可避免在資料夾不存在時發生執行時錯誤。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*為何重要*：`Directory.CreateDirectory` 為冪等操作——僅在資料夾尚未存在時才會建立，避免在後續執行時拋出例外。

## 步驟 3：設定通用條碼尺寸

設定 X‑dimension（單根條的寬度）與整體條碼高度，可控制產生圖像的視覺尺寸。

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**如何設定條碼尺寸**：`Parameters.Barcode.XDimension.Pixels` 屬性定義窄條寬度，而 `Parameters.Barcode.BarHeight.Pixels` 定義完整高度。請依照您的郵寄服務規格調整這些數值。

## 步驟 4：產生 Planet 條碼

Planet 是英國廣泛使用的郵政條碼。以下程式碼會產生一個 100 px 高的 Planet 條碼，並以 PNG 格式儲存。

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**為何此程式碼可行**：`EncodeTypes.Planet` 告訴產生器使用 Planet 符號。`Save` 方法會將 PNG 檔寫入指定路徑，保留先前設定的尺寸。

## 步驟 5：產生 RM4SCC 條碼

RM4SCC 是荷蘭的郵政條碼標準。以下程式碼與 Planet 範例相同，示範 **如何產生不同類型的郵政條碼**，且尺寸相同。

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

兩個 PNG 檔案現在皆位於 `Barcodes` 資料夾。開啟後會看到乾淨、100 px 高的條碼，可直接列印或嵌入文件中。

## 完整原始碼

以下為完整、可執行的程式，**建立郵政條碼圖像** 檔案，支援 Planet 與 RM4SCC 兩種標準。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### 預期輸出

執行程式會列印檔案路徑，並產生兩個 PNG 檔案：

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

每張影像皆為 100 px 高，窄條寬度為 4 像素，符合我們設定的尺寸。

## 實用技巧與常見陷阱

* **資料夾權限** – 若程式在受限帳號下執行，請確保目標資料夾具備寫入權限。
* **不同尺寸** – 若要產生較高的條碼，請增加 `barHeightPixels`。若需更細緻的解析度，降低 `xDimensionPixels`，但須保持 ≥ 2 以避免渲染瑕疵。
* **其他郵政符號** – Aspose.BarCode 亦支援 `EncodeTypes.Postnet` 與 `EncodeTypes.AustralianPost`。只要交換 `EncodeTypes` 的值，並保留相同的尺寸邏輯即可。
* **影像格式** – 若不需要無損品質，可使用 `BarCodeImageFormat.Jpeg` 以減小檔案大小。

## 結論

現在您已了解如何在 C# 中 **建立郵政條碼圖像** 檔案，透過設定尺寸、選擇正確的符號，並將結果儲存為 PNG。本教學說明了 **如何產生郵政條碼**，示範了 **產生 Planet 條碼**，並解釋了 **如何設定條碼尺寸** 以確保輸出一致。

接下來，您可以探索 **自訂條碼顏色**、加入 **可讀文字**，或將影像整合至 PDF 發票中。同樣的模式適用於 Aspose.BarCode 支援的任何其他條碼類型，讓您將此解決方案擴展為完整的郵政自動化工作流程。

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在本教學示範的技術之上。每個資源皆提供完整的可執行程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何產生 Java 條碼 – 使用 Aspose 的澳洲郵政條碼](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}