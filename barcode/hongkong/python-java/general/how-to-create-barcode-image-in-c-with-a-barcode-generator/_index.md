---
category: general
date: 2026-10-02
description: 使用條碼產生器在 C# 中建立條碼圖像，控制條碼像素大小並調整條碼高度，以自訂條碼尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: zh-hant
lastmod: 2026-10-02
og_description: 使用條碼產生器在 C# 中建立條碼影像。學習設定條碼像素大小、調整條碼高度，以及自訂條碼尺寸。
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: 在 C# 中建立條碼圖像 – 條碼產生器與自訂尺寸指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 如何使用條碼產生器在 C# 中建立條碼圖像
url: /zh-hant/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器建立條碼圖像

如果您需要以程式方式 **建立條碼圖像** 檔案，本指南將向您展示一個完整、可直接執行的 C# 解決方案。透過使用條碼產生器，您可以控制 **條碼像素大小**、**調整條碼高度**，以及在不離開 IDE 的情況下定義 **自訂條碼尺寸**。

您將學會產生兩個 PNG 檔案——一個條碼高度為 30 px，另一個為 60 px——同時保持模組寬度不變。此步驟適用於庫支援的任何條碼類型，您可以將其套用於 QR Code、Code 128 或其他符號。

## 您需要的環境

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.8 編譯）
- 條碼函式庫的參考（例如 Aspose.BarCode for .NET 或任何相容的 `BarcodeGenerator` 類別）
- 基本的 C# 知識
- 具有寫入權限的資料夾，以儲存 PNG 檔案

## 步驟 1：初始化條碼產生器以 **建立條碼圖像**

首先，匯入所需的命名空間並實例化 `BarcodeGenerator`。建構函式接受條碼類型（`EncodeTypes.DatabarOmniDirectional`）以及您想要編碼的資料字串。

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

建立產生器是任何 **barcode generator c#** 工作流程的基礎。它會配置內部繪圖畫布並為渲染準備資料。

## 步驟 2：定義 **條碼像素大小** 與初始條碼高度

最終圖像的視覺品質取決於兩個參數：

| 參數 | 說明 |
|-----------|---------|
| `XDimension.Pixels` | 單一模組的寬度（最小的黑/白元件）。 |
| `BarHeight.Pixels` | 目前圖像中條碼的高度。 |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

在變更高度的同時保持 **條碼像素大小** 不變，可讓您建立符合品牌指南或掃描需求的 **自訂條碼尺寸**。

## 步驟 3：儲存第一個 PNG 檔案（30 px 高度）

現在將圖像寫入磁碟。`Save` 方法接受檔案路徑與欲輸出的圖像格式。

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

產生的檔案是一個 **條碼圖像**，條碼高度為 30 px，模組寬度為 2 px，非常適合緊湊的標籤。

## 步驟 4：**調整條碼高度** 以產生較大的版本

若要產生第二個視覺尺寸不同的圖像，只需變更 `BarHeight.Pixels` 屬性。這說明了在不重新建立產生器的情況下，**調整條碼高度** 是多麼簡單。

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

在保持 **條碼像素大小** 不變的同時變更高度，可確保條碼保持清晰，且整體長寬比保持一致。

## 步驟 5：儲存第二個 PNG 檔案（60 px 高度）

最後，將較大的版本寫入磁碟。

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

您現在已經擁有兩個並排儲存的 **自訂條碼尺寸**：

- `DatabarBarHeight30Pixels.png` – 30 px 條碼高度
- `DatabarBarHeight60Pixels.png` – 60 px 條碼高度

兩張圖像皆使用相同的 2 px **條碼像素大小**，確保不同尺寸間的視覺一致性。

## 為何這些設定很重要

- **條碼像素大小**（`XDimension`）會影響掃描器的可讀性。2 px 的寬度是常見的預設值，能在檔案大小與掃描可靠性之間取得平衡。
- **條碼高度**決定標籤上條碼的高度。有些零售掃描器需要最低高度；另一些則允許較高的條碼以符合美觀需求。
- 在只調整 `BarHeight` 時保持產生器實例持續存在，可減少記憶體分配並加速批次處理。

## 邊緣情況與最佳實踐建議

| 情況 | 建議做法 |
|-----------|----------------------|
| **不同的圖像格式**（JPEG、BMP） | 在 `Save` 呼叫中更改 `BarCodeImageFormat.Jpeg` 或 `.Bmp`。JPEG 檔案較小，但可能產生壓縮雜訊。 |
| **高解析度輸出**（例如 300 DPI） | 將 `XDimension.Pixels` 成比例提升（例如 4 px），並調整 `BarHeight.Pixels` 以維持相同的實體尺寸。 |
| **動態資料字串** | 將產生器的建立封裝在接受資料字串為參數的方法中，然後重複使用相同的 `barcode` 實例進行多次儲存。 |
| **執行緒安全的批次產生** | 為每個執行緒實例化獨立的 `BarcodeGenerator`，或使用執行緒本地池以避免競爭條件。 |
| **檔案系統權限錯誤** | 確認 `outputFolder` 已存在且程式具有寫入權限；妥善處理 `IOException`。 |

## 完整程式碼清單

以下是完整、獨立的程式，您可以直接複製、貼上並執行。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### 預期輸出

執行程式後，`YOUR_DIRECTORY` 資料夾會包含兩個 PNG 檔案：

- **DatabarBarHeight30Pixels.png** – 適用於小型標籤的緊湊條碼。
- **DatabarBarHeight60Pixels.png** – 適合高可視性應用的較大版本。

兩個檔案皆可在任何圖像檢視器中開啟、列印，或嵌入 PDF 中。

## 結論

您現在已了解如何在 C# 中使用 **barcode generator c#** 來 **建立條碼圖像** 檔案，控制 **條碼像素大小**、**調整條碼高度**，並產生符合特定掃描或品牌需求的 **自訂條碼尺寸**。此範例展示了一個簡潔、可重複使用的模式，能擴展至批次處理或不同符號。

### 接下來可以探索的內容

- [如何在 C# 中建立可調整高度的條碼圖像](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [如何在 C# 中產生自訂尺寸的條碼集合並儲存圖像](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [使用條碼產生器範例在 C# 中建立條碼圖像](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}