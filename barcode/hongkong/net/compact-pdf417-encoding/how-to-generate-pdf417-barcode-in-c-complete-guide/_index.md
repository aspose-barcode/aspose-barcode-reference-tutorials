---
category: general
date: 2026-09-26
description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 條碼。請依照此一步一步的教學設定欄位、啟用緊湊模式，並儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: zh-hant
lastmod: 2026-09-26
og_description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 條碼。本指南將示範如何設定列數、啟用緊湊模式，並將結果匯出為 PNG
  圖像。
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: 在 C# 中產生 PDF417 條碼 – 逐步教學
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: 如何在 C# 中產生 PDF417 條碼 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生 PDF417 條碼 – 完整指南

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學提供一個即用的解決方案。您將會看到如何設定條碼尺寸、欄位數量與緊湊模式，然後將結果儲存為高品質的 PNG 檔案。

產生條碼是庫存系統、票務平台與文件編碼的常見需求。完成本指南後，您將擁有一個獨立的 C# 程式，可使用 Aspose 的 **pdf417 barcode generator C#** 函式庫產生緊湊的 PDF417 條碼。

## 您需要的環境

- .NET 6.0 SDK 或更新版本（程式碼亦可在 .NET Framework 4.7+ 上執行）
- 有效的 Aspose.BarCode for .NET 授權（免費評估版可用於測試）
- 如 Visual Studio 2022、Rider 或 VS Code 等 IDE 或編輯器
- 具備 C# 主控台專案的基本知識

> **專業提示：** 若使用免費評估版，產生的圖像會包含小型 Aspose 水印。購買授權後可移除水印並解鎖完整功能。

## 步驟 1：設定 Aspose.BarCode 函式庫

建立新的主控台專案，並加入 Aspose.BarCode NuGet 套件。

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

此套件提供 `BarcodeGenerator` 類別，是 **pdf417 barcode generator C#** 工作流程的核心。

## 步驟 2：撰寫完整的條碼產生程式

開啟 `Program.cs`，將其內容取代為以下程式碼。此程式示範所有必要步驟，從初始化產生器到儲存圖像。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### 每行程式碼的意義說明

| 行 | 目的 |
|------|---------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | 建立 PDF417 產生器並設定要編碼的文字。PDF417 支援大量資料與 Unicode，適合複雜的識別碼。 |
| `XDimension.Pixels = 2` | 控制視覺密度。較小的數值產生較細的條，較大的數值在低解析度螢幕上提升可讀性。 |
| `Pdf417.Columns = 3` | 覆寫自動欄位計算。固定欄位在必須將條碼放入預定空間時很有用。 |
| `Pdf417.Truncate = true` | 啟用緊湊模式，移除不必要的填充，減少整體尺寸。 |
| `Save(..., BarCodeImageFormat.Png)` | 將條碼寫入 PNG 檔案，這是一種無損格式，適合進一步處理或嵌入 PDF 中。 |

## 步驟 3：執行程式並驗證輸出

建置並執行專案：

```bash
dotnet run
```

您應該會在主控台看到確認檔案位置的訊息，且名為 **CompactPdf417.png** 的檔案會出現在專案資料夾中。

![Generated PDF417 barcode example](images/compact-pdf417.png){.img-responsive alt="Generated PDF417 barcode example"}

*此圖顯示一個緊湊的 PDF417 條碼，編碼的字串為 “Åspóse.Barcóde©”。*  

若在影像檢視器中開啟 PNG，您會看到三欄堆疊的資料區塊，每條寬 2 像素。使用標準 PDF417 讀取器掃描條碼即可還原原始文字，證實產生器如預期運作。

## 常見問題與避免方法

| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| 條碼顯得模糊 | XDimension 設定過低，無法符合目標 DPI | 將 `XDimension.Pixels` 提升至 3 或 4，或使用 `generator.Save(..., BarCodeImageFormat.Tiff)` 以更高解析度渲染 |
| Unicode 字元遺失 | 輸入字串未以 UTF‑8 編碼 | 確保來源檔案以 UTF‑8 編碼儲存；當字串型別為 `string` 時，產生器會自動處理 Unicode。 |
| Truncate 產生例外 | 資料大小超過所選欄位數的最大容納量 | 可將 `Pdf417.Columns` 增加，或將 `Pdf417.Truncate = false` 以讓產生器自行分配足夠空間。 |
| 授權未套用 | 評估版會加入水印 | 在建立產生器之前，透過 `Aspose.BarCode.License` 套用有效的授權檔案。 |

## 擴充此解決方案

取得基本的 **generate PDF417 barcode** 流程後，您可以探索其他功能：

- **錯誤更正等級** – 調整 `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` 以提升對損壞的容錯能力。
- **顏色自訂** – 使用 `generator.Parameters.Barcode.ForegroundColor` 與 `BackgroundColor` 以符合品牌指引。
- **嵌入 PDF** – 結合 Aspose.PDF 與 Aspose.BarCode，將條碼直接放入 PDF 文件中。
- **批次產生** – 迭代一系列識別碼，在一次執行中產生多個 PNG 檔案。

上述所有選項皆在 Aspose.BarCode API 參考文件中有說明，且遵循前述相同的模式。

## 結論

您現在已了解如何使用 Aspose.BarCode 在 C# 中 **產生 PDF417 條碼**，設定欄位、啟用緊湊模式，並將結果匯出為 PNG 圖像。完整範例可直接執行，亦可依需求套用於更大型的專案，如票務系統、庫存標籤或安全文件編碼。

接下來，您可以嘗試 **pdf417 barcode generator C#** 的進階設定，如錯誤更正與顏色自訂，或將條碼整合至使用 Aspose.PDF 的 PDF 報告中。嘗試不同的 `XDimension` 值與欄位數，找出最適合您特定使用情境的尺寸與掃描可靠性平衡。祝開發順利！

## 接下來您可以學習什麼？

- [在 C# 中產生 PDF417 條碼 – 含緊湊版面的完整指南](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Aspose 條碼範例：在 C# 中產生 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [如何在 C# 中儲存條碼 – 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}