---
category: general
date: 2026-11-17
description: 學習如何儲存條碼、啟用緊湊模式、調整欄位，並使用完整的 C# 範例產生 PDF417 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: zh-hant
lastmod: 2026-11-17
og_description: 在 C# 中生成 PDF417 條碼時，如何儲存條碼、啟用緊湊模式及調整欄位。請參考逐步指南。
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: 如何在 C# 中將條碼儲存為 PNG 並啟用緊湊模式
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: 如何在 C# 中將條碼儲存為 PNG 並啟用緊湊模式
url: /zh-hant/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何將條碼儲存為 PNG 並在 C# 中啟用緊湊模式

如果您需要 **how to save barcode** 以可用於網頁或列印的格式，本指南將向您展示具體步驟。您還將學習如何 **enable compact mode**、**adjust columns**，以及使用 Aspose.BarCode .NET 函式庫 **generate PDF417 barcode**。

本教學涵蓋從專案設定到最終 PNG 檔案的全部內容，讓您可以直接將程式碼複製到自己的解決方案中，無需額外研究。無需外部文件說明；已包含完整、可執行的範例。

## 前置條件

* .NET 6.0 或更新版本已安裝  
* Visual Studio 2022（或任何 C# IDE）  
* `Aspose.BarCode` NuGet 套件（`Install-Package Aspose.BarCode`）  

這三項即為以下程式碼唯一的相依性。

## 步驟 1：建立 PDF417 條碼產生器

在 **generate PDF417 barcode** 時的第一步是實例化 `BarcodeGenerator`，並指定正確的編碼類型與要編碼的資料。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417` 列舉告訴函式庫使用 PDF417 符號，這是一種堆疊式線性條碼，適合編碼大量資料。字串 `"Compact mode"` 會成為條碼下方的可讀文字。

## 步驟 2：設定 X‑dimension（模組寬度）

條碼中的每根條稱為模組。控制模組寬度可讓您在不改變資料的前提下微調條碼的視覺大小。

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

2 像素的 X‑dimension 會產生緊湊的影像，且在大多數裝置上仍能可靠掃描。

## 步驟 3：**How to adjust columns** for the PDF417 code

PDF417 允許您指定條碼使用的欄位數量。較少的欄位會產生較高且較窄的符號，而較多的欄位則會使符號變寬但變矮。

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

此行示範了 **how to adjust columns**。您可以將數值改為 2、4，或任何函式庫支援的數字，視目標媒介的空間而定。

## 步驟 4：**How to enable compact mode** and truncate the symbol

緊湊模式會移除不必要的填充，減少條碼的整體佔用空間。函式庫透過 `Truncate` 屬性提供此功能。

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

請注意此處出現 **enable compact mode** 這個詞彙，且在指南後續同樣以 **how to enable compact mode** 的精確措辭描述相同操作，以符合次要關鍵字需求。

## 步驟 5：**How to save barcode** as a PNG image

將產生的影像儲存下來是最後一步。`Save` 方法會依您指定的格式將條碼寫入檔案系統。

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

將 `YOUR_DIRECTORY` 替換為應用程式可寫入的絕對或相對路徑。執行後，您會在該目錄中找到名為 `CompactPdf417.png` 的檔案，內含緊湊的 PDF417 條碼。

### 預期輸出

開啟已儲存的 PNG 檔案會看到一個垂直緊湊的 PDF417 條碼，具有三個欄位且已去除填充。視覺尺寸約為每個模組 2 px，適合嵌入 HTML `<img>` 標籤或列印於小型標籤上。

## 完整、可執行範例

以下是完整的程式碼，您可以將其複製到新的主控台專案中。它包含所有必要的 `using` 指令，並在單一流程中示範 **how to save barcode**、**enable compact mode**、**how to adjust columns** 與 **generate PDF417 barcode**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

執行此程式會產生前述的 PNG 檔案。主控台輸出會確認已儲存檔案的位置，協助您驗證 **how to save barcode** 步驟已成功。

## 常見問題與邊緣案例

### 如果需要不同的影像格式該怎麼辦？

`Save` 方法接受任何 `BarCodeImageFormat` 列舉值，例如 `Jpeg`、`Bmp` 或 `Gif`。將 `BarCodeImageFormat.Png` 替換為所需的格式，其他程式碼則保持不變。

### 截斷會如何影響資料容量？

啟用 **compact mode**（截斷）會減少列數，可能降低條碼的最大資料容量。若遇到 “Data too large” 例外，請增加欄位數或停用截斷。

### 可以使用動態欄位數嗎？

可以。您可以根據輸入字串的長度計算欄位數：

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

此程式碼片段示範了 **how to adjust columns** 的程式化寫法，確保條碼能符合指定的版面配置。

### X‑dimension 是否只能使用整數像素？

`Pixels` 屬性接受任何正整數。對於高解析度輸出（例如列印），您可能會偏好使用 `Points` 而非 `Pixels`，以達到與裝置無關的尺寸設定。

## 生產環境使用小技巧

* **Pro tip:** 在條碼產生時使用 try‑catch 區塊，以處理當輸入資料超過符號容量時拋出的 `BarCodeException`。  
* **Watch out for:** 檔案系統權限。程序必須對目標目錄具有寫入權限，否則 **how to save barcode** 步驟會因 `UnauthorizedAccessException` 而失敗。  
* **Performance note:** 在迴圈中大量產生條碼時，重複使用單一 `BarcodeGenerator` 實例，僅在每次迭代間更新 `CodeText` 屬性，可提升效能。

## 結論

您現在已了解如何使用 Aspose.BarCode for C# **how to save barcode** 為 PNG 檔案、**enable compact mode**、**how to adjust columns**，以及 **generate PDF417 barcode**。完整範例示範了從初始化產生器到寫入最終影像的所有必要步驟。

接下來您可以探索相關主題，例如在條碼中加入標誌、客製化顏色，或將產生器整合至 ASP.NET Core API。這些延伸功能皆遵循本指南所示的相同模式，讓您能有信心地調整程式碼。

歡迎嘗試不同的欄位數、X‑dimension 與影像格式，以符合專案的精確規格。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}