---
category: general
date: 2026-10-02
description: 學習如何在 C# 中建立 Micro PDF417 條碼，並快速產生條碼 PNG 圖像。包括一步一步的程式碼與最佳實踐。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- barcode generation C#
- MicroPdf417 settings
- C# image export
language: zh-hant
lastmod: 2026-10-02
og_description: 在 C# 中建立微型 PDF417 條碼並產生條碼 PNG 圖片。遵循此完整指南，即可製作高品質條碼檔案。
og_image_alt: C# code generating a MicroPdf417 barcode saved as PNG
og_title: 在 C# 中建立微型 PDF417 條碼 – 完整的 PNG 生成指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create micro pdf417 barcode in C# and generate a barcode
    PNG image quickly. Includes step‑by‑step code and best practices.
  headline: How to create micro pdf417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中建立微型 PDF417 條碼並儲存為 PNG
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立微型 PDF417 條碼並儲存為 PNG

如果您需要為標籤、票證或手機掃描**建立微型 PDF417 條碼**，本指南將完整示範如何在 C# 中實作。您也會學習**如何產生條碼 PNG**檔案，以便嵌入網頁或直接從應用程式列印。

我們將逐步說明所有必要設定，從初始化產生器到選擇適當的 X‑dimension 與欄位數。完成本教學後，您將擁有可直接使用的 C# 程式碼片段，產生清晰的 MicroPdf417 條碼 PNG 圖片。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼亦相容於 .NET Core 3.1+）
* Visual Studio 2022 或任何相容 C# 的 IDE
* **Aspose.BarCode for .NET** NuGet 套件（或任何支援 `EncodeTypes.MicroPdf417` 的函式庫）。使用以下方式安裝：

```bash
dotnet add package Aspose.BarCode
```

* 需要對欲儲存 PNG 檔案的資料夾具有寫入權限。

不需要額外的設定；函式庫會自行處理所有低階影像處理。

## 步驟 1：初始化 MicroPdf417 條碼產生器

第一行會建立一個 `BarcodeGenerator` 實例，告訴它必須編碼 MicroPdf417 符號。您傳入的文字可以包含 Unicode 字元，函式庫會自動進行編碼。

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator with the desired text
var generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 barcode type
    "Åspóse.Barcóde©");               // Sample data containing special characters
```

*為什麼這很重要*：選擇 `EncodeTypes.MicroPdf417` 會讓引擎使用緊湊的 MicroPdf417 規格，適合小型標籤，同時仍支援錯誤更正。

## 步驟 2：定義 X‑dimension（模組大小）以像素為單位

X‑dimension 決定最小條的寬度（即「模組」）。設定為 `2` 像素時，條碼密集但仍可辨識。

```csharp
// Set the module size (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*提示*：較大的 X‑dimension 會使整體影像尺寸變大，對低解析度印表機有幫助。大多數螢幕顯示情境建議維持在 2–4 px。

## 步驟 3：設定欄位數（MicroPdf417 最多 4 欄）

MicroPdf417 最多支援四個欄位。欄位數增多會使條碼高度縮短，但影像變寬。

```csharp
// Configure the number of columns (max 4 for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*調整原因*：若標籤寬度受限，請減少欄位數。相反地，若高度受限，則可增加欄位數以縮短條碼。

## 步驟 4：將產生的條碼儲存為 PNG 圖片

最後，將條碼匯出為 PNG 檔案。PNG 能保留精確的像素資料且不會產生壓縮雜訊，非常適合呈現銳利的條碼。

```csharp
using Aspose.BarCode;

// Define the output path (ensure the directory exists)
string outputPath = Path.Combine(
    Environment.CurrentDirectory, "MicroPdf417.png");

// Save as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to: {outputPath}");
```

**預期輸出** – 執行程式後，您會在專案資料夾中看到 `MicroPdf417.png`。開啟該檔案即可看到清晰的 MicroPdf417 條碼，編碼內容為 `Åspóse.Barcóde©`。

## 如何以不同影像格式產生條碼 PNG（可選）

雖然 PNG 是條碼影像最常使用的格式，但相同的 `Save` 方法亦支援 JPEG、BMP 與 TIFF。若要在其他格式**產生條碼 PNG**，只需更改 `BarCodeImageFormat` 列舉即可：

```csharp
// Save as JPEG instead of PNG
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

請記得 JPEG 會使用有損壓縮，可能導致細條模糊。對於任何正式的掃描應用，請使用 PNG。

## 建立條碼影像 C# – 最佳實踐與邊緣情況

以下提供幾項實用技巧，讓您的 **create barcode image c#** 工作流程更健全：

| 情境 | 建議 |
|-----------|----------------|
| **大量資料負載** | 將資料分割為多個 MicroPdf417 符號，並在視覺上串接。 |
| **低解析度印表機** | 將 `XDimension.Pixels` 提升至 3‑4 px，以避免條碼缺失。 |
| **動態輸出資料夾** | 使用 `Path.GetTempPath()` 或透過 `SaveFileDialog` 讓使用者選擇資料夾。 |
| **執行緒安全產生** | 每個執行緒建立新的 `BarcodeGenerator`；此類別本身不具執行緒安全性。 |
| **錯誤處理** | 將產生程式碼包在 `try/catch` 區塊中，以捕捉 `BarCodeException`。 |

```csharp
try
{
    // generation code from steps 1‑4
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## 完整、可執行範例

將上述所有步驟整合起來，以下是一個完整的主控台應用程式範例，您可以直接複製、貼上並執行：

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Initialize generator with MicroPdf417 type and sample text
        var generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2. Set module size (X‑dimension) to 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3. Use the maximum of 4 columns for a compact shape
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4. Define output path and save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory, "MicroPdf417.png");

        // Ensure the directory exists
        Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!);

        // Save the barcode image
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode successfully created at: {outputPath}");
    }
}
```

使用 `dotnet run` 執行程式。主控台會印出完整路徑，PNG 檔案則會出現在執行檔旁邊。

## 結論

您現在已了解如何在 C# 中**建立微型 PDF417 條碼**，以及如何為任何 .NET 專案**產生條碼 PNG**檔案。上述步驟——初始化產生器、設定 X‑dimension 與欄位數、以及匯出為 PNG——涵蓋了可靠條碼產生所需的關鍵設定。

從此您可以探索：

* 透過變更 `EncodeTypes`，使用 **Create barcode image c#** 產生其他條碼類型（QR、Code128、DataMatrix）。
* 使用 `generator.Parameters.Barcode.Image` 加入顏色或背景影像。
* 將條碼產生整合至 ASP.NET Core 端點，即時提供影像服務。

請自行嘗試各項設定，在實際掃描器上測試輸出，並依需求調整程式碼以符合您的工作流程。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，進一步延伸所示技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [在 C# 中建立條碼 PNG – GS1 微型 PDF417 完整指南](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [如何在 C# 中產生微型 PDF417 條碼 – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中使用 Macro PDF417 選項建立 PDF417 條碼影像](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}