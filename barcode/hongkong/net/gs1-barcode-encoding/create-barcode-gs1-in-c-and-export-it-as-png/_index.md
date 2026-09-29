---
category: general
date: 2026-09-29
description: 在 C# 中建立 GS1 條碼，並使用 BarcodeGenerator 產生條碼 PNG 圖像。遵循一步一步的指南，以高效匯出條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: zh-hant
lastmod: 2026-09-29
og_description: 使用 C# 建立 GS1 條碼並透過 BarcodeGenerator 產生條碼 PNG 檔案。遵循本完整指南，快速匯出條碼圖像。
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: 在 C# 中建立 GS1 條碼 – 幾分鐘內匯出 PNG
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: 在 C# 中建立 GS1 條碼並匯出為 PNG
url: /zh-hant/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 GS1 條碼並匯出為 PNG

如果您需要在 .NET 應用程式中 **建立 GS1 條碼**，本指南會精確說明如何操作。您將看到一個簡潔的解決方案，可產生條碼 PNG 圖片並將條碼圖像匯出至磁碟，全部使用 Aspose.BarCode 的 `BarcodeGenerator` 類別。

產生 GS1 條碼是庫存、運輸與銷售點系統的常見需求。完成本教學後，您將能編寫一個小型 C# 程式，建立符合 GS1 標準的 MicroPDF417 條碼，並將其儲存為高品質的 PNG 檔案。

## 前置條件

在開始之前，請確保您已具備：

* **.NET 6**（或任何更新的 .NET 版本）已安裝。
* **Visual Studio 2022** 或任何支援 C# 的 IDE。
* **Aspose.BarCode for .NET** NuGet 套件 (`Aspose.BarCode`) – 提供本範例中使用的 `BarcodeGenerator` API。
* 基本的 C# 語法熟悉度。

> **專業提示：** 在實驗時使用 Aspose.BarCode 的免費社群版；完整版本會移除所有評估水印。

## 第一步 – 使用 BarcodeGenerator 建立 GS1 條碼

您首先需要為 *MicroPDF417* 格式實例化 `BarcodeGenerator`，並提供一個 GS1 資料字串。GS1 應用識別碼 (AI) 需以括號包住，例如 `(01)` 代表 GTIN‑14，`(21)` 代表序號。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**為什麼這很重要：**  
`EncodeTypes.MicroPdf417` 會在字串包含有效 AI 時自動將輸入視為 GS1 資料。這確保產生的條碼符合 GS1 規範，無需額外設定。

## 第二步 – 設定條碼尺寸以獲得最佳大小

條碼的視覺大小由 **X‑dimension**（單一模組的寬度）控制。調整 `XDimension.Pixels` 可在保持可讀性的同時微調最終圖像尺寸。

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **如何產生條碼 PNG** – X‑dimension 不會影響編碼資料；它僅改變產生圖像的實體尺寸。若需較大的條碼以供高解析度列印，請提升此數值（例如 `3` 或 `4`）。

## 第三步 – 產生條碼 PNG 並匯出條碼圖像

現在您可以將條碼渲染並寫入 PNG 檔案。`Save` 方法接受目標路徑與欲輸出的圖像格式。

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**內部運作原理：**  
`BarcodeGenerator.Save` 會將條碼光柵化為位圖，套用先前設定的 X‑dimension，並將位圖編碼為 PNG 檔案。產生的檔案可直接用於網頁、標籤列印或嵌入 PDF。

## 完整程式碼範例

以下是一個完整、獨立的主控台應用程式，您可以直接複製、貼上並執行。它示範了 **如何產生條碼 PNG** 檔案、**匯出條碼圖像**，並包含基本的錯誤處理。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### 預期輸出

執行程式後，您應該會看到：

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

開啟 PNG 檔案會顯示一個清晰的 **GS1 MicroPDF417** 條碼，編碼內容為 GTIN‑14 `12345678901234` 與序號 `ABC123`。使用任何支援 GS1 的掃描器掃描，即可回傳原始資料字串。

## 常見陷阱與最佳實踐

| 問題 | 為什麼會發生 | 如何避免 |
|------|--------------|----------|
| **AI 格式不正確** | 缺少括號或順序錯誤會導致條碼非 GS1。 | 必須將每個 AI 包在括號內，例如 `(01)`。 |
| **X‑dimension 設定過小** | 條碼在低解析度裝置上難以辨識。 | 大多數印表機請保持 `XDimension.Pixels` ≥ 2；高 DPI 輸出則需提高。 |
| **輸出資料夾不存在** | `Save` 會拋出 `DirectoryNotFoundException`。 | 呼叫 `Save` 前先使用 `Directory.CreateDirectory` 建立資料夾。 |
| **使用錯誤的 EncodeType** | 某些類型（如 `Code128`）預設不支援 GS1 資料。 | 選擇 `EncodeTypes.MicroPdf417` 或其他支援 GS1 的類型。 |
| **缺少 NuGet 參考** | 編譯時出現 `The type or namespace name 'Aspose' could not be found` 等錯誤。 | 透過 NuGet 安裝 `Aspose.BarCode` 套件。 |

## 擴充範例

* **不同的圖像格式** – 如需其他格式，將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Gif` 或 `Bmp`。
* **更高解析度的輸出** – 在儲存前設定 `generator.Parameters.ImageResolution.DpiX` 與 `DpiY`。
* **嵌入 PDF** – 使用 `Aspose.Pdf` 將 PNG 放入 PDF 發票或標籤中。

## 結論

您現在已掌握如何在 C# 中使用 Aspose.BarCode 的 `BarcodeGenerator` **建立 GS1 條碼**、**產生條碼 PNG**，以及 **匯出條碼圖像** 至檔案系統。本指南涵蓋了從以 GS1 資料初始化產生器、調整 X‑dimension，到儲存最終 PNG 檔案的每一步，同時說明常見錯誤並提供擴充想法。

歡迎嘗試其他 GS1 應用識別碼、不同的條碼符號或更高解析度的圖像。當您熟悉這些基礎後，為庫存、運輸或零售產生符合規範的條碼將成為 .NET 工具箱中的日常工作。

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，能進一步深化您的技能。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索替代實作方式。

- [在 C# 中建立 GS1 條碼圖像 – 快速產生條碼 C# 教學](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [在 C# 中建立條碼 PNG – 步驟說明指南](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [在 C# 中建立條碼圖像 – 完整程式設計指南](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}