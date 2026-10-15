---
category: general
date: 2026-10-12
description: 學習使用 C# 建立微型 PDF417 條碼並將條碼轉換為 PNG。一步一步的完整程式碼與技巧指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: zh-hant
lastmod: 2026-10-12
og_description: 使用 C# 建立微型 PDF417 條碼並將條碼轉換為 PNG。請參考本完整指南，以產生標準版與 GS1 版。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 建立微型 PDF417 條碼並轉換為 PNG – C# 教學
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中建立微型 PDF417 條碼並轉換為 PNG
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立微型 PDF417 條碼並轉換為 PNG

如果您需要在 .NET 應用程式中 **建立微型 PDF417 條碼**，本教學將完整說明步驟。您將看到一個完整、可執行的範例，產生標準 Micro PDF417 條碼與符合 GS1 標準的版本，然後 **將條碼轉換為 PNG**，以供列印或網頁顯示等下游使用。

產生條碼不只是呼叫單一方法——選擇正確的模組大小、欄位數量與編碼格式會影響掃描的可靠性。閱讀完本指南後，您將了解每個設定為何重要，以及如何為自己的專案調整它們。

## 前置條件

| 需求 | 原因 |
|------|------|
| .NET 6.0 SDK or later | 提供 C# 主控台應用程式的執行環境 |
| Visual Studio 2022 (or any C# IDE) | 讓編輯與除錯更為方便 |
| **Aspose.BarCode for .NET** NuGet package | 提供 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 類別 |
| Write permission to the output folder | `Save` 呼叫需要寫入權限以建立 PNG 檔案 |

您可以透過 CLI 新增 Aspose.BarCode 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：設定最小化的主控台專案

建立一個新的主控台專案並參考條碼函式庫。以下的 `Program.cs` 包含所有所需程式碼；不需要其他外部檔案。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### 為何每一行都很重要

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – 前者產生普通的 Micro PDF417 條碼，後者遵循 GS1 標準，嵌入應用程式識別碼 (AI)。請依下游系統是否需要 GS1 資料來選擇。
* **`XDimension.Pixels = 2`** – 控制模組寬度。較小的數值會產生更密集的影像，但在低解析度掃描器上可能無法辨識。兩個像素是大多數標籤印表機的安全預設值。
* **`Pdf417.Columns = 4`** – Micro PDF417 允許限制欄位數，以減少總寬度。四欄可在不犧牲短資料負載的資料容量下保持條碼緊湊。
* **`BarCodeImageFormat.Png`** – PNG 保持無損品質，對條碼清晰度至關重要。因此我們 **將條碼轉換為 PNG** 而非 JPEG。

## 步驟 2：執行程式並驗證輸出

1. 建置專案：`dotnet build`。
2. 執行：`dotnet run`。

您應該會看到類似以下的主控台訊息：

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

使用任何影像檢視器開啟產生的 PNG 檔案。兩張圖片皆顯示清晰、高對比度的條碼，隨時可供掃描。

### 預期的視覺結果

| 條碼類型 | 外觀 |
|----------|------|
| **Micro PDF417** | 具有 4 欄的細小矩形圖案，可被大多數 2‑D 條碼掃描器讀取。 |
| **GS1 Micro PDF417** | 尺寸相同，但編碼 GS1 AI；支援 GS1 的掃描器會回傳 GTIN 與序號。 |

如果掃描器無法讀取影像，請嘗試將 `XDimension.Pixels` 提升至 **3** 或 **4**，或減少標準 Micro PDF417 的欄位數。

## 常見陷阱與避免方法

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 列印後條碼模糊 | 印表機 DPI 設定過低 | 將 PNG 匯出為 300 dpi 或更高，或讓印表機驅動程式處理縮放。 |
| 掃描器回傳「資料無效」 | 缺少或格式錯誤的 GS1 AI | 確保每個 AI 都以括號包住，且符合 GS1 規範（例如 `(01)` 代表 GTIN‑14）。 |
| 未產生影像檔案 | 輸出資料夾缺乏寫入權限 | 以提升的權限執行程式，或選擇如 `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` 之資料夾。 |
| 條碼過大無法貼標籤 | 預設欄位數過高 | 減少 `Pdf417.Columns`（例如 **3**）或增加 `XDimension` 以縮小整體尺寸。 |

## 擴充範例

* **不同的影像格式** – 若工作流程需要，可將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Bmp`。PNG 仍是無損品質的最佳選擇。
* **動態資料** – 將使用者輸入或資料庫值傳入 `BarcodeGenerator` 建構子，即時產生條碼。
* **批次產生** – 將建立邏輯包在迴圈中，從 CSV 檔讀取每列資料，並以唯一檔名儲存每個條碼。

## 結論

您現在已了解如何在 C# 中 **建立微型 PDF417 條碼**，以及 **將條碼轉換為 PNG**，適用於標準與符合 GS1 的情境。完整、可執行的程式碼示範了關鍵設定——X 維度、欄位數與編碼類型——讓您能將此解決方案套用至任何需要緊湊、高品質 2‑D 條碼的 .NET 專案。

*下一步*：探索 Aspose.BarCode 支援的其他符號（例如 QR、DataMatrix），試驗不同的 `XDimension` 值以應對高解析度列印，或將產生的 PNG 整合至即時提供條碼的 Web API。

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，延伸所示技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何在 C# 中建立微型 pdf417 條碼並儲存為 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [在 C# 中建立條碼 PNG – 完整的 GS1 Micro PDF417 指南](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [在 C# 中產生 Micro PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}