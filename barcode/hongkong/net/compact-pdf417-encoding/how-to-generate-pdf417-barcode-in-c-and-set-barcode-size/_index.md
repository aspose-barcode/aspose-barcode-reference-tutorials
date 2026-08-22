---
category: general
date: 2026-08-22
description: 學習如何在 C# 中使用 Aspose.BarCode 生成 PDF417 條碼，設定條碼大小、調整列數，並啟用緊湊模式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: zh-hant
lastmod: 2026-08-22
og_description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 條碼。本指南說明如何設定條碼尺寸、控制列數，以及啟用緊湊模式以獲得更小的圖像。
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: 在 C# 中產生 PDF417 條碼 – 設定大小、欄位與緊湊模式
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: 如何在 C# 中產生 PDF417 條碼並設定條碼尺寸
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生 PDF417 條碼並設定條碼尺寸

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本指南將一步步說明完整流程。您將會看到如何使用 Aspose.BarCode **產生 PDF417**、**設定條碼尺寸**，以及產出可嵌入報表或行動應用程式的緊湊 PNG。

產生條碼不需要額外的圖形編輯器。完成本教學後，您將擁有一個功能完整的 C# 方法，能產生符合精確尺寸需求的 PDF417 圖片，供後續處理使用。

## 您將學會

* 安裝並參考 Aspose.BarCode 套件。  
* 建立 PDF417 條碼產生器並指定要編碼的文字。  
* 透過設定 X‑dimension 與欄位數 **設定條碼尺寸**。  
* 啟用緊湊（截斷）模式以縮小符號。  
* 將結果儲存為 PNG 檔案。  
* 排除常見問題，如條碼無法辨識或影像過大等。

### 前置條件

* .NET 6.0 或更新版本（亦支援 .NET Framework 4.6+）。  
* 具備 C# 與 Visual Studio（或任意 C# IDE）的基本知識。  
* 有效的 Aspose.BarCode 授權（免費評估版可用於測試）。

> **專業提示：** 若需在迴圈中大量產生條碼，請重複使用同一個 `BarcodeGenerator` 實例，僅變更 `CodeText` 屬性。這樣可減少記憶體配置。

## 使用 Aspose.BarCode 產生 PDF417 條碼

第一步是為 PDF417 符號建立 `BarcodeGenerator` 實例。此物件是所有條碼操作的入口。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*為什麼這很重要*：`EncodeTypes.Pdf417` 告訴函式庫使用 PDF417 標準，該標準支援大量資料與錯誤更正。建構子同時接受要編碼的資料，省去之後再指定 `CodeText` 的步驟。

## 設定條碼尺寸與欄位數

PDF417 符號由多列多欄的矩形模組組成。控制模組寬度（X‑dimension）與欄位數即可微調整體尺寸。

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*說明*：  
* **X‑dimension**（`Pixels`）決定每個模組的寬度。數值較小會產生更緊密的條碼，數值較大則提升低解析度掃描器的可讀性。  
* **Columns** 控制水平佈局。欄位較少會使條碼變高，欄位較多則變寬。請同時調整這兩個設定，以取得所需的 **設定條碼尺寸**。

## 啟用緊湊模式以產生較小的條碼

PDF417 提供「緊湊」或「截斷」模式，可移除不必要的留白，減少佔用空間。當螢幕空間受限時特別有用。

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*為什麼要啟用截斷？*  
當 `Truncate` 為 `true` 時，產生器會省略停止圖樣以及部分不需要的錯誤更正碼字。如此產出的影像大約縮小 15‑20 %，同時在一般使用情境下不會影響資料完整性。

## 將條碼儲存為 PNG 圖片

完成尺寸與模式設定後，將條碼寫入磁碟。PNG 為無損格式，可確保模組邊緣保持銳利。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

檔案 `CompactPdf417.png` 會包含一個符合先前設定尺寸的清晰 PDF417 符號。

### 預期輸出

開啟儲存的 PNG 應會看到一個垂直方向的 PDF417 條碼，包含三個欄位、每個模組寬度為 2 px，總尺寸約 **120 × 240 px**（寬 × 高）。使用任何標準 PDF417 讀取器掃描此影像，即可得到原始文字 “Sample text for PDF417”。

## 常見陷阱與避免方式

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 條碼無法辨識 | X‑dimension 對掃描器太小 | 將 `XDimension.Pixels` 提升至 3 或 4 |
| 影像寬度過大，佔用 UI 空間 | 設定的欄位過多 | 減少 `Pdf417.Columns` 或啟用 `Truncate` |
| 拋出 `ArgumentOutOfRangeException` | 欄位數為負或零 | 確認 `Columns` 為正整數（最小 1） |
| PNG 檔案為空 | 輸出路徑不存在或無寫入權限 | 檢查目錄是否存在且程式具有寫入權限 |

> **專業提示：** 在呼叫 `Save()` 前使用 `barcodeGenerator.ValidateParameters()`，可提前捕捉設定錯誤。

## 完整可執行範例

以下是一個自包含的主控台程式，整合了上述所有步驟。將程式碼複製到新的 C# 專案、還原 Aspose.BarCode NuGet 套件後執行，即可看到結果。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**執行程式** 後會在執行目錄產生 `CompactPdf417.png`。使用行動應用程式（例如「Barcode Scanner」）掃描該影像，即可驗證編碼文字與來源字串相符。

## 後續步驟與相關主題

* **提升錯誤更正等級** – 調整 `Pdf417.ErrorLevel` 以因應噪聲較大的掃描環境。  
* **變更方向** – 若需水平布局，將 `Pdf417.Rotate` 設為 `RotationAngle.Rotate90`。  
* **將條碼嵌入 PDF** – 結合 Aspose.PDF 與 Aspose.BarCode，直接將影像放入文件。  
* **產生其他 2‑D 條碼** – 同一個 `BarcodeGenerator` 類別支援 DataMatrix、QR、Aztec 等，只要把 `EncodeTypes.Pdf417` 換成目標符號即可。

掌握 **產生 PDF417 條碼** 的技巧後，您可以自動化票證、庫存標籤與安全資料傳輸，應用於各種 .NET 場景。

## 結論

現在您已了解如何在 C# 中 **產生 PDF417 條碼**、精確 **設定條碼尺寸**、配置欄位、啟用緊湊模式，並將結果儲存為 PNG。將這些設定套用於任何 UI 限制或掃描需求，亦可延伸至其他條碼格式。祝您開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並探索在專案中的其他實作方式。

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}