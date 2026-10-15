---
category: general
date: 2026-10-12
description: 使用 Aspose.BarCode，於數分鐘內於 C# 建立條碼圖像。此一步一步的 C# 條碼產生器範例示範如何設定長寬比並儲存 PNG
  檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: zh-hant
lastmod: 2026-10-12
og_description: 即時使用 C# 建立條碼圖像。遵循此 C# 條碼產生器範例，即可產出具自訂長寬比的高品質 PNG 條碼。
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: 產生條碼圖像 C# – Aspose.BarCode 快速指南
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中使用 Aspose.BarCode 建立條碼圖像
url: /zh-hant/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中建立條碼影像

如果您需要 **快速建立條碼影像 C#**，本教學將帶您完成一個完整、可直接執行的範例。無論您是要建置出貨標籤系統或庫存掃描器，下列步驟都會說明如何設定 DataBar Stacked Omnidirectional 條碼、調整視覺參數，並將結果儲存為 PNG 檔案。

您還會看到一個 **條碼產生器範例 C#**，示範即時變更長寬比，讓您在不重新編寫程式碼的情況下產生多種變體。無需額外文件——只要複製、貼上、執行即可。

## 您需要的環境

在開始之前，請確保您已具備：

* .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.7 以上）
* **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 一個用來寫入產生 PNG 檔案的資料夾（請在程式碼中將 `YOUR_DIRECTORY` 替換為實際路徑）

上述前置條件可確保 **條碼產生器範例 C#** 能在任何現代 Windows、Linux 或 macOS 開發機上執行。

## 如何使用 Aspose.BarCode 在 C# 中建立條碼影像

此流程分為四個簡短步驟：建立產生器、設定模組大小、配置長寬比，最後儲存影像。每一步都會說明 *為何* 需要這樣做，而不只是 *輸入什麼*。

### 步驟 1 – 初始化條碼產生器

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**為何重要：** `BarcodeGenerator` 建構子接受兩個參數：條碼類型（`EncodeTypes.DatabarStackedOmniDirectional`）與原始資料字串。`(01)` 前綴告訴掃描器，接下來的 14 位數字代表 GTIN‑14 識別碼，這是零售與物流常見的需求。

### 步驟 2 – 設定模組（X‑dimension）大小

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為何重要：** X‑dimension 控制最小條（「模組」）的寬度。設定為 `2` 像素可產生清晰、高解析度的條碼，即使放大後仍具可讀性。若需在海報上使用較大的條碼，請按比例增大此數值。

### 步驟 3 – 以長寬比 15 儲存第一張影像

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**為何重要：** DataBar 符號支援 *長寬比*，會影響高度與寬度的比例。`15` 為多數零售應用的預設值，產生緊湊、近似方形的條碼，易於貼在小標籤上。

### 步驟 4 – 將長寬比改為 30 並儲存第二張影像

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**為何重要：** 將長寬比提升至 `30` 會使條碼在垂直方向上拉長，提升在低解析度掃描器或較高標籤上的可讀性。因為重複使用同一個 `BarcodeGenerator` 實例，可避免為每個變體重新分配物件——這是批次處理的高效模式。

## 完整、可執行的範例

以下程式碼可直接貼入 Console 應用程式。它包含必要的 `using` 陳述式、錯誤處理，以及說明每一行功能的註解。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### 預期輸出

執行程式後會產生兩個 PNG 檔案：

| 檔案名稱 | 長寬比 | 常見用途 |
|-----------|--------|----------|
| `DatabarAspectRatio15.png` | 15 | 標準零售標籤 |
| `DatabarAspectRatio30.png` | 30 | 高標籤或低解析度掃描器 |

兩張影像皆包含清晰的 DataBar Stacked Omnidirectional 條碼，編碼的 GTIN‑14 值為 `12345678901231`。您可使用任何影像檢視器開啟 PNG，驗證視覺品質。

![Sample barcode image created with C# using Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="使用 C# 及 Aspose.BarCode 建立的樣本條碼圖像"}

*上述 alt 文字包含主要關鍵字，有助於搜尋引擎與螢幕閱讀器。*

## 其他考量與最佳實踐建議

* **支援的格式** – `BarCodeImageFormat` 支援 PNG、JPEG、BMP、GIF 與 TIFF。PNG 為無損格式，是後續掃描最安全的選擇。
* **顏色客製化** – 可透過 `generator.Parameters.Barcode.ForegroundColor` 與 `BackgroundColor` 變更前景/背景色彩，適用於彩色媒介列印。
* **批次產生** – 若需處理大量庫存，可將儲存邏輯包在 `foreach` 迴圈中，從 CSV 讀取商品資料。重複使用同一個 `BarcodeGenerator` 實例可減少記憶體壓力。
* **錯誤處理** – 完整範例中的 `try/catch` 區塊會捕捉資料字串無效或寫入權限錯誤等常見問題，特別是目標目錄不存在時。
* **效能** – 在第一次 `Save` 前設定 `XDimension.Pixels`，可確保渲染器僅在每次長寬比變更時重新計算位圖大小。

## 結論

現在您已掌握如何使用 Aspose.BarCode **在 C# 中建立條碼影像**、調整 X‑dimension、切換長寬比，並以單一可重用程式碼區塊儲存 PNG 檔案。此 **條碼產生器範例 C#** 包含了在零售或物流應用中產生 DataBar Stacked Omnidirectional 符號時最常見的變化。

## 接下來可以做什麼？

* 探索其他條碼類型，例如 `EncodeTypes.Code128` 或 `EncodeTypes.QR`，擴充您的解決方案。
* 嘗試調整 `generator.Parameters.Barcode.ImageMargin`，為條碼四周加入留白。
* 使用 Aspose.PDF 將產生的 PNG 嵌入 PDF 發票，或直接放入 HTML 報表中。

歡迎依照您的工作流程自行調整程式碼——無論是每個商品產生單一影像，或是一次匯出數千條條碼，此模式皆能有效擴展。

---


## 接下來應該學什麼？

以下教學與本指南的技術緊密相關，能協助您進一步掌握 API 功能並探索其他實作方式：

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}