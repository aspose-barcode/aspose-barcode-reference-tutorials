---
category: general
date: 2026-08-12
description: 快速在 C# 中建立微型 PDF417 圖像。學習如何使用 C# 產生 PDF417 條碼，提供完整程式碼、設定選項與除錯技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 image
- how to generate PDF417 barcode C#
- barcode generator C#
- PDF417 column settings
- barcode image format PNG
language: zh-hant
lastmod: 2026-08-12
og_description: 使用此詳細教學在 C# 中建立微型 PDF417 圖像。遵循步驟生成 PDF417 條碼（C#）並自訂輸出。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 在 C# 中建立微型 PDF417 圖像 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create micro PDF417 image in C# quickly. Learn how to generate PDF417
    barcode C# with full code, options, and troubleshooting tips.
  headline: Create micro PDF417 image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- imaging
title: 在 C# 中建立微型 PDF417 圖像 – 逐步指南
url: /zh-hant/net/compact-pdf417-encoding/create-micro-pdf417-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立微型 PDF417 圖像 – 步驟指南

如果您需要在 .NET 應用程式中**建立微型 PDF417 圖像**，本教學將示範如何僅用幾行 C# 代碼完成。您將看到產生 PDF417 條碼的完整 C# 程式碼，以及如何調整尺寸、欄位數量和檔案格式。

本指南涵蓋從安裝所需函式庫、處理 Unicode 字元，到將結果儲存為 PNG 檔案的全部步驟。完成後，您將擁有一個可重複使用的方法，能產生高品質的微型 PDF417 條碼，適用於庫存標籤、票證或行動掃描解決方案。

## 先決條件

* .NET 6.0 SDK 或更新版本（此程式碼亦相容於 .NET Core 與 .NET Framework）
* Visual Studio 2022 或任何相容 C# 的 IDE
* **Aspose.BarCode** NuGet 套件（或任何支援 `EncodeTypes.MicroPdf417` 的相容條碼函式庫）

您可以使用 .NET CLI 加入套件：

```bash
dotnet add package Aspose.BarCode
```

> **專業提示：** 使用最新的穩定版函式庫，以獲得錯誤修正與新編碼功能。

## 步驟 1：建立條碼產生器實例

第一步是以 `MicroPdf417` 編碼類型和您想要編碼的資料實例化 `BarcodeGenerator`。函式庫會自動處理 UTF‑8 字元，您可以加入帶重音的字母或符號。

```csharp
using Aspose.BarCode.Generation;

// Data to encode – Unicode characters are supported out of the box
string data = "Åspóse.Barcóde©";

// Create a MicroPdf417 barcode generator
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417, data);
```

**為何重要：** `EncodeTypes.MicroPdf417` 會產生緊湊的 2‑D 條碼，適合小標籤，同時保有錯誤更正功能。於建構時傳入資料可讓產生器提前驗證內容。

## 步驟 2：設定 X‑維度（模組寬度）

X‑維度決定每個條碼模組（像素）的寬度。較小的值會產生更緊密的圖像，但在低解析度掃描器上可能無法辨識。常見的起始值為 2 像素。

```csharp
// Set module width to 2 pixels (adjustable per printer DPI)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**邊緣情況：** 若目標為高解析度印表機（≥300 dpi），可將像素值提升至 3‑4，以提升可讀性，同時不會使整體圖像變大。

## 步驟 3：選擇欄位數量

Micro PDF417 允許您指定矩陣的欄位數量（1‑4）。欄位越多，條碼會變寬但變短，當垂直空間受限時此特性相當有用。

```csharp
// Use 4 columns to keep the barcode compact vertically
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

**調整時機：**  
* 針對狹窄標籤（例如腕帶標籤）使用 **1‑2 欄**。  
* 當有較多水平空間且希望條碼較短時使用 **3‑4 欄**。

## 步驟 4：設定輸出檔案路徑

定義產生的圖像要儲存的位置。使用 `Path.Combine` 建立跨平台的路徑。

```csharp
using System.IO;

string outputDirectory = @"C:\Barcodes";
Directory.CreateDirectory(outputDirectory); // Ensure the folder exists
string outputPath = Path.Combine(outputDirectory, "MicroPdf417.png");
```

**提示：** 將條碼儲存在專屬資料夾，以保持專案整潔，並簡化之後的批次處理。

## 步驟 5：將條碼儲存為 PNG 檔案

最後，將條碼寫入磁碟。PNG 保留無損品質，對於可靠的掃描至關重要。

```csharp
// Save the barcode image in PNG format
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

如果需要其他格式（例如用於網路傳輸的 JPEG），請將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。

### 預期輸出

執行程式後，您會在 `C:\Barcodes` 中找到 `MicroPdf417.png`。開啟檔案會看到清晰的矩形條碼，編碼的字串為 **Åspóse.Barcóde©**。使用 PDF417 讀取器掃描此圖像會回傳原始文字，證實**建立微型 PDF417 圖像**的過程成功。

## 完整可重複使用的方法

以下是一個可直接放入任何 C# 類別的單一方法。它將上述步驟抽象化，讓您傳入自訂資料、欄位數量與輸出位置。

```csharp
using Aspose.BarCode.Generation;
using System.IO;

public static class BarcodeHelper
{
    /// <summary>
    /// Generates a micro PDF417 barcode image.
    /// </summary>
    /// <param name="data">Text to encode (Unicode supported).</param>
    /// <param name="columns">Number of columns (1‑4). Default is 4.</param>
    /// <param name="pixelWidth">Module width in pixels. Default is 2.</param>
    /// <param name="outputPath">Full file path, including file name and extension.</param>
    public static void CreateMicroPdf417Image(
        string data,
        int columns = 4,
        int pixelWidth = 2,
        string outputPath = "MicroPdf417.png")
    {
        // Validate column range
        if (columns < 1 || columns > 4)
            throw new ArgumentOutOfRangeException(nameof(columns), "Columns must be between 1 and 4.");

        // Initialize generator
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

        // Apply settings
        generator.Parameters.Barcode.XDimension.Pixels = pixelWidth;
        generator.Parameters.Barcode.Pdf417.Columns = columns;

        // Ensure directory exists
        string directory = Path.GetDirectoryName(outputPath);
        if (!string.IsNullOrEmpty(directory))
            Directory.CreateDirectory(directory);

        // Save as PNG (change format if needed)
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

**方法使用方式：**

```csharp
BarcodeHelper.CreateMicroPdf417Image(
    data: "Åspóse.Barcóde©",
    columns: 4,
    pixelWidth: 2,
    outputPath: @"C:\Barcodes\MyMicroPdf417.png");
```

此封裝版本讓在多個專案中**如何產生 PDF417 條碼 C#**變得簡單。

## 常見問題與故障排除

| 問題 | 原因 | 解決方案 |
|-------|-------|-----|
| 掃描器無法讀取條碼 | X‑dimension 太低，未符合印表機 DPI | 將 `XDimension.Pixels` 提升至 3‑4，以適應高解析度印表機 |
| 文字被截斷 | 輸入超過 Micro PDF417 容量（≈ 150 個字元） | 使用一般 PDF417 (`EncodeTypes.Pdf417`) 以處理較長資料 |
| Unicode 字元顯示為 � | 函式庫版本不支援 UTF‑8 | 更新至最新的 Aspose.BarCode 套件 |
| 檔案未建立 | 輸出目錄不存在或權限不足 | 在儲存前呼叫 `Directory.CreateDirectory`，並確保寫入權限 |

## 擴充範例

* **變更圖像格式：** 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。
* **新增邊距：** `generator.Parameters.Barcode.Margins.All = 5;` 會加入 5 像素的白色邊框。
* **套用顏色：** `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Blue;` 會變更條碼的前景色。

這些擴充功能讓您能微調**建立微型 PDF417 圖像**的工作流程，以符合品牌需求或特定掃描環境。

## 結論

您現在已了解如何在 C# 中**建立微型 PDF417 圖像**，從資料編碼、模組寬度、欄位選擇到檔案輸出。可重複使用的方法示範了**如何產生 PDF417 條碼 C#**的最佳實踐，處理邊緣情況並提供實務專案的客製化切入點。

接下來，您可以探索相關主題，例如**產生標準 PDF417 條碼**、**在 PDF 報告中嵌入條碼**，或**優化行動相機的條碼可讀性**。嘗試不同的欄位數與像素寬度，以找出最適合您標籤尺寸與掃描器能力的平衡。祝編程愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在本篇示範的技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊型 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何產生 PDF417 條碼 – 緊湊型 PDF417 編碼](/barcode/english/net/compact-pdf417-encoding/)
- [建立條碼圖像 C# – GS1 DataMatrix 範例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}