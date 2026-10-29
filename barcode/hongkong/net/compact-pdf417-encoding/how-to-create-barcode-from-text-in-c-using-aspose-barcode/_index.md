---
category: general
date: 2026-10-28
description: 使用 Aspose.BarCode 在 C# 中從文字建立條碼。了解如何產生 PDF417 條碼圖像、設定欄位、調整 X 尺寸，並啟用緊湊模式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: zh-hant
lastmod: 2026-10-28
og_description: 使用 Aspose.BarCode 在 C# 中從文字建立條碼。本教學示範如何產生 PDF417 條碼影像，並自訂大小、列數及緊湊模式。
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: 使用 C# 從文字產生條碼 – 步驟說明指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: 如何在 C# 中使用 Aspose.BarCode 從文字建立條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 從文字建立條碼

如果您需要在 .NET 應用程式中**從文字建立條碼**，本指南提供即時可執行的解決方案。您將看到如何**產生 PDF417 條碼**影像、控制模組寬度、欄位數量，並在不離開 IDE 的情況下啟用緊湊模式。

本教學涵蓋產生 **generate barcode C#** 程式碼所需的一切，從函式庫安裝到儲存最終 PNG 檔案。完成後，您即可在報告、票證或庫存標籤中嵌入高密度 PDF417 條碼。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝  
* Visual Studio 2022（或任何支援 .NET 的編輯器）  
* 具備下載 Aspose.BarCode for .NET NuGet 套件的網路連線  

上述項目足以在 Windows、Linux 或 macOS 上編譯並執行範例。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

產生條碼的函式庫是 **Aspose.BarCode for .NET**。使用 .NET CLI 安裝它：

```bash
dotnet add package Aspose.BarCode
```

此套件會新增 `Aspose.BarCode` 命名空間，其中包含本教學中廣泛使用的 `BarcodeGenerator` 類別。

## 步驟 2：建立主控台專案並加入程式碼

建立新的主控台專案，並將產生的 `Program.cs` 替換為以下程式碼。此程式示範如何**從文字建立條碼**，並將其儲存為**PDF417 條碼影像**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### 為何每一行都很重要

* **`EncodeTypes.Pdf417`** 選擇 PDF417 符號，適合以二維格式編碼大量資料。  
* **`XDimension.Pixels = 2`** 減少模組寬度，使條碼更緊密，較適合空間受限的情況。  
* **`Pdf417.Columns = 3`** 控制垂直資料欄位的數量；較低的欄位數會產生較高但較窄的條碼。  
* **`Pdf417.Truncate = true`** 啟用緊湊模式，裁剪右側未使用的欄位。此設定是將一般 PDF417 轉換為**緊湊 PDF417 條碼影像**的關鍵。  

## 步驟 3：建置並執行專案

在專案目錄中執行以下指令：

```bash
dotnet build
dotnet run
```

程式執行完畢後，您會看到一則顯示檔案位置的主控台訊息。使用任何影像檢視器開啟 `CompactPdf417.png` 以驗證結果。

**預期輸出** – 一張高對比度的 PNG，顯示編碼字串 `Åspóse.Barcóde©` 的緊湊 PDF417 條碼。使用標準條碼讀取器掃描此影像會回傳原始文字，證實 **generate pdf417 barcode** 成功。

## 步驟 4：為不同情境自訂條碼

雖然範例使用固定的欄位數與 X‑dimension，但您可以依需求調整產生器：

| 情境 | 調整方式 |
|----------|------------|
| 較大的資料負載 | 增加 `Pdf417.Columns` 或手動設定 `Pdf417.Rows` |
| 更高的掃描可靠性 | 將 `XDimension.Pixels` 提升至 3 或 4 |
| 不同的影像格式 | 將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Bmp` |
| 透明背景 | 設定 `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

這些選項讓您能夠建立符合行動應用程式、桌面報告或 Web 服務需求的 **generate barcode C#** 解決方案。

## 步驟 5：處理邊緣情況與最佳實踐

* **Unicode 支援** – 產生器會自動編碼 Unicode 字元，但若從檔案讀取字串，請確保來源字串為 UTF‑8 編碼。  
* **大量文字** – PDF417 最多可編碼 1,850 個英數字元。若超過此上限，函式庫會拋出例外；請將資料分割成多個條碼或改用容量更高的符號。  
* **錯誤處理** – 將產生程式碼包在 `try/catch` 區塊中，以捕捉 `BarCodeException` 並提供友善的錯誤訊息。  
* **效能** – 在迴圈中產生大量條碼時，重複使用同一個 `BarcodeGenerator` 實例，僅在每次迭代間更新 `CodeText`，可提升效能。  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## 完整程式碼清單

以下為完整、獨立的程式，您可以直接複製到 `Program.cs` 中。無需其他檔案。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

執行此程式會產生下圖所示的 **pdf417 條碼影像**。

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="從文字建立條碼的範例，顯示緊湊 PDF417 條碼影像"}

*圖片說明：此 PNG 檔顯示編碼字串 “Åspóse.Barcóde©” 的緊湊 PDF417 條碼。*  

## 結論

您現在已了解如何在 C# 中**從文字建立條碼**，並產生具自訂尺寸與緊湊模式的 **PDF417 條碼影像**。此範例示範了 **generate barcode C#** 的基本步驟、Unicode 資料處理，以及針對不同部署情境調整視覺參數的方法。

接下來，您可以探索相關主題，例如 **generate QR code in C#**、**add barcode to PDF documents**，或 **embed barcodes in ASP.NET Core APIs**。這些皆建立在本篇所涵蓋的 `BarcodeGenerator` 基礎之上。

祝開發順利，並盡情將條碼整合至您的 .NET 解決方案！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以相同技術為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [在 C# 中產生 PDF417 條碼 – 建立 PDF417 條碼 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [如何在 C# 中建立 PDF417 條碼影像 – 完整指南](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}