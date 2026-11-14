---
category: general
date: 2026-11-14
description: 快速學習如何在 C# 中建立 PDF417 條碼。本指南亦示範如何產生 PDF417 以及如何自訂 PDF417 設定，以達到精確控制。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: zh-hant
lastmod: 2026-11-14
og_description: 使用 C# 逐步說明建立 PDF417 條碼。學習如何產生 PDF417 以及如何自訂 PDF417 參數以獲得精確結果。
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: 在 C# 中建立 PDF417 條碼 – 完整指南與自訂版面
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: 如何在 C# 中以自訂佈局建立 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中以自訂佈局建立 PDF417 條碼

如果您需要為票務系統、庫存標籤或行動應用程式掃描 **建立 PDF417 條碼**，本教學將完整說明整個流程。您將看到如何快速產生 PDF417，以及如何自訂 PDF417 的設定（如欄與列），使條碼符合您的設計限制。

產生條碼不需要複雜的圖形函式庫，只要使用 Aspose.BarCode for .NET（或任何相容的 API）即可。完成本指南後，您將擁有可直接嵌入 PDF、網頁，或從應用程式直接列印的即用型 PNG 檔案。

## 前置條件

- .NET 6.0 或更新版本（程式碼亦相容 .NET Framework 4.7+）
- Aspose.BarCode for .NET（NuGet 套件 `Aspose.BarCode`）
- 具備 C# 與 Visual Studio（或任何 IDE）的基本知識

> **專業提示：** 若您使用 CI/CD 流程，請在專案檔案中加入 NuGet 套件參考，以確保建置可重現。

## 步驟 1：安裝條碼函式庫

在終端機中開啟您的專案資料夾，執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此套件包含本教學中會使用到的 `BarcodeGenerator` 類別，無需額外的原生相依性。

## 步驟 2：建立基本的 PDF417 條碼

首要目標是以預設設定 **建立 PDF417 條碼**。以下程式碼會設定產生器、編碼範例字串，並將結果儲存為 PNG 圖片。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**為什麼這樣可行：**  
`EncodeTypes.Pdf417` 告訴函式庫使用 PDF417 符號。建構子會自動建立具有預設欄/列值的 `Barcode` 物件，確保在大多數使用情境下具備可掃描性。

執行程式 (`dotnet run`)。您會在專案資料夾中看到 `Pdf417Default.png`。開啟該圖像即可看到一個可供掃描的標準 PDF417 條碼。

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Create PDF417 barcode example showing default layout"}

## 步驟 3：如何以自訂尺寸產生 PDF417

有時固定尺寸的標籤或 UI 元件需要特定的條碼佔位空間。此時 **如何產生 PDF417** 並自訂欄與列就變得相當重要。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**為什麼您可能需要這樣做：**  
- **寬度受限：** 減少欄數並增加列數會產生較寬但較短的條碼，適合窄標籤。  
- **高度受限：** 增加欄數並減少列數會產生較高且較窄的條碼，適用於垂直空間充足的情況。

`Columns` 與 `Rows` 只能接受文件中規定的範圍值（欄：2‑30，列：1‑90）。若提供超出範圍的值，會拋出 `ArgumentOutOfRangeException`，因此若在 UI 中公開此設定，務必先驗證使用者輸入。

## 步驟 4：進一步自訂 PDF417

除了欄與列之外，PDF417 符號還提供許多可選參數：

| 屬性 | 用途 | 典型值 |
|----------|---------|----------------|
| `ErrorLevel` | 控制錯誤更正能力 | 0‑8（數值越高越健壯） |
| `MacroPdf417` | 啟用 macro PDF417 以支援多段資料 | `true`/`false` |
| `CompactPdf417` | 產生更緊湊的條碼，但會降低錯誤更正能力 | `true`/`false` |
| `SecurityLevel` | 加入安全檢查碼 | 0‑2 |

以下是一個快速範例，將錯誤等級設為最高值 (8)，適用於噪聲較大的環境：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**為什麼這很重要：**  
較高的錯誤更正能讓掃描器即使在條碼部分受損時仍能恢復資料。但同時會使條碼尺寸變大，需在佈局限制與設定之間取得平衡。

## 步驟 5：驗證條碼是否可用

產生 PNG 後，使用任何條碼掃描應用程式測試（大多數智慧型手機都有免費的 PDF417 讀取器）。若掃描器回傳原始文字（`Custom layout text`），則條碼有效。

如果您遇到掃描問題：

1. **檢查尺寸：** 確保欄/列仍在允許的範圍內。  
2. **調整錯誤等級：** 若媒體受損，提升 `ErrorLevel`。  
3. **檢查影像品質：** 若要列印，請以較高 DPI 儲存（`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`）。

## 可重用輔助程式的完整原始碼

以下是一個精簡且可重用的類別，您可以將其放入任何 .NET 專案。它在單一方法中封裝了 **如何產生 PDF417** 與 **如何自訂 PDF417**。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

您可以這樣呼叫此輔助程式：

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

此方法抽象化重複的樣板程式碼，讓您專注於業務邏輯。

## 常見陷阱與避免方式

- **超出範圍的值：** 在指定 `columns` 與 `rows` 前務必先驗證。  
- **影像格式不正確：** 部分舊版掃描器僅接受 BMP 或 JPEG。如有需要，請使用 `BarCodeImageFormat.Bmp`。  
- **列印 DPI 較低：** 預設 DPI 為 96。若需高品質列印，呼叫 `Save` 時請明確設定較高的 DPI（例如 300）。  
- **缺少字型支援：** PDF417 會編碼二進位資料，通常不需要指定字型。但若在影像上疊加文字，請確保目標機器已安裝該字型。

## 結論

您現在已了解如何從頭到尾 **建立 PDF417 條碼**、如何以自訂欄/列設定 **產生 PDF417**，以及如何為錯誤更正與緊湊度 **自訂 PDF417**。遵循可重用的輔助程式模式，您即可按需產生條碼、調整至任何佈局限制，並確保在生產環境中可靠掃描。

**下一步**  

- 使用相同的 `BarcodeGenerator` 類別探索其他符號，如 QR 或 Code128。  
- 將 PNG 輸出與 PDF 產生函式庫（例如 iText7）結合，將條碼嵌入發票。  
- 嘗試 `MacroPdf417` 以進行多段資料傳輸，此功能在物流與運輸應用中相當有用。

祝程式開發順利，願您的條碼一次即能成功掃描！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中產生 PDF417 條碼 – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [如何產生條碼並自訂 PDF417 條碼於 C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [如何在 C# 中建立 PDF417 條碼並匯出 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}