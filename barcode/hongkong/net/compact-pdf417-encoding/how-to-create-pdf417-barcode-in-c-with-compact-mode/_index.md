---
category: general
date: 2026-09-10
description: 在 C# 中快速建立 PDF417 條碼。了解如何啟用緊湊模式、設定欄位，並使用 BarcodeGenerator 產生 PNG 圖片。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: zh-hant
lastmod: 2026-09-10
og_description: 在 C# 中啟用緊湊模式、設定欄位，並將 PDF417 條碼儲存為 PNG。請遵循完整的逐步指南。
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: 在 C# 中建立 PDF417 條碼 – 緊湊模式教學
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中使用緊湊模式建立 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用緊湊模式建立 PDF417 條碼

如果你需要在 .NET 應用程式中 **建立 PDF417 條碼**，本教學會一步一步示範如何完成。你將會看到如何 **啟用緊湊模式**、設定欄位數量，並使用 BarcodeGenerator C# 函式庫將結果儲存為 PNG 圖片。

產生條碼是庫存追蹤、票券系統與行動掃描應用的常見需求。完成本教學後，你將擁有一個可自行執行的完整範例，能產生符合生產需求的緊湊 PDF417 條碼。

## 前置條件

在開始之前，請確保你已具備：

* 已安裝 .NET 6.0 或更新版本（此程式碼亦相容於 .NET Framework 4.7+）
* 最近版本的 **BarcodeGenerator** 函式庫（例如 Aspose.BarCode for .NET）
* 如 Visual Studio 2022 或 VS Code 等 IDE 或編輯器
* 有寫入 PNG 檔案的資料夾寫入權限

除條碼函式庫本身外，無需額外的 NuGet 套件。

## 步驟 1：建立 PDF417 條碼產生器

第一步是以 `EncodeTypes.Pdf417` 列舉值與欲編碼的文字，實例化 `BarcodeGenerator` 物件。此物件負責整個產生流程。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*為什麼這很重要*：`EncodeTypes.Pdf417` 告訴函式庫使用 PDF417 符號，而第二個參數則提供實際的資料內容。你可以將 `"Compact mode"` 替換成任何需要編碼的字母數字字串。

## 步驟 2：設定 X 維度（模組寬度）

X 維度控制條碼中每個小方格（模組）的寬度。較小的數值會產生更緊密的圖像，適合空間受限的情況。

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

對大多數螢幕掃描器而言，`2` 像素是一個在可讀性與緊湊度之間的良好平衡。

## 步驟 3：定義欄位數量

PDF417 可以將資料排列成列與欄的格子。調整欄位數會改變條碼的長寬比例。

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

將 **how to set columns** 設為 `3` 會產生一條短而寬的條碼，適合貼在標籤上。你可以依資料量與目標掃描器，嘗試 `1` 到 `30` 之間的值。

## 步驟 4：啟用緊湊模式

緊湊模式會移除不必要的填充列，使條碼在不失去資料完整性的前提下變得更小。這是產生 **緊湊 PDF417** 的關鍵步驟。

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

當 `Truncate` 為 `true` 時，函式庫會自動計算儲存資料所需的最少列數，因而讓最終圖像看起來「緊湊」。

## 步驟 5：將產生的條碼儲存為 PNG 圖片

最後，將條碼寫入檔案。PNG 能保留掃描所需的清晰邊緣。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

將 `YOUR_DIRECTORY` 替換為你的應用程式可寫入的絕對或相對路徑。執行後，你會在該目錄找到名為 `CompactPdf417.png` 的檔案，內含條碼圖像。

### 完整原始碼

將所有步驟整合起來，即可得到一個可直接執行的程式：

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

執行此程式會在可執行檔所在的同一資料夾產生 `CompactPdf417.png`。使用任何圖像檢視器開啟，你應該會看到一個密集且高對比度的 PDF417 條碼，已可供掃描。

## 在其他情境下啟用緊湊模式

* **批次產生** – 大量產生條碼時，只需在產生器上一次設定 `Truncate`，然後重複使用於每筆新資料。
* **不同影像格式** – 若需其他檔案類型，可將 `Save` 方法的參數改為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。
* **動態欄位數** – 若編碼字串長度不固定，可根據字串長度與掃描器解析度計算最佳欄位數。

## 針對特定使用情境設定欄位數

* **標籤列印** – 使用較低的欄位數（例如 `2`‑`5`），讓條碼足夠短以適應窄標籤。
* **行動掃描** – 較高的欄位數（`10`‑`15`）會產生較高的條碼，手機相機較易對焦。
* **錯誤更正取捨** – 欄位數增多會減少列數，可能影響條碼內建的錯誤更正能力。請以目標掃描器測試，找出最佳平衡點。

## 常見問題與專業提示

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| 條碼無法辨識 | X 維度過低（例如 `1` 像素） | 將 `XDimension.Pixels` 提升至至少 `2` |
| 圖片過大 | 欄位數設定過高，導致短資料產生過多列 | 減少 `Pdf417.Columns` 或啟用 `Truncate` |
| PNG 檔案為空白 | 輸出資料夾不存在或缺乏寫入權限 | 確認資料夾已建立且程式具有寫入權限 |
| 掃描器回報「資料損毀」 | 在使用大量欄位時未啟用 Truncate | 啟用 `Truncate` 或降低欄位數 |

## 驗證結果

你可以使用任何 PDF417 掃描應用程式（市面上有許多免費的 Android/iOS 版）驗證條碼。於應用程式中開啟 `CompactPdf417.png`，確認解碼文字與原始資料（「Compact mode」）相符。若文字不符，請再次檢查 `Truncate` 旗標與欄位設定。

## 往後的步驟

* **整合至 ASP.NET Core** – 直接在控制器動作中回傳 PNG，而非先寫入磁碟。
* **加入可讀文字** – 使用 `barcodeGenerator.Parameters.Barcode.CodeTextParameters` 在條碼下方顯示編碼字串。
* **探索其他符號** – 同一個 `BarcodeGenerator` 類別支援 QR、Code128、DataMatrix 等。只要切換 `EncodeTypes` 即可嘗試。

---

### 結論

現在你已掌握如何在 C# 中 **建立 PDF417 條碼**，同時 **啟用緊湊模式**、**設定欄位數**，並使用 **barcode generator C#** API 產生符合實際尺寸限制的條碼。將這些步驟套用到任何需要緊湊高密度條碼的 .NET 專案，並依需求擴展至其他條碼格式。祝程式開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，提供完整的程式碼範例與逐步說明，協助你精通更多 API 功能並探索替代實作方式。

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}