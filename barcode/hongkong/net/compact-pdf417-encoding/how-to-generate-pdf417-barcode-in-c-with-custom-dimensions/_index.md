---
category: general
date: 2026-09-07
description: 在 C# 中產生 PDF417 條碼，並學習如何設定條碼尺寸以精確控制。請按照此逐步指南建立 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: zh-hant
lastmod: 2026-09-07
og_description: 在 C# 中產生 PDF417 條碼，並學習如何設定條碼尺寸。本教學提供完整可執行的範例。
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: 在 C# 中產生 PDF417 條碼 – 完整指南與尺寸說明
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: 如何在 C# 中以自訂尺寸產生 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生具自訂尺寸的 PDF417 條碼

如果您需要在 .NET 應用程式中**產生 PDF417 條碼**，本指南將會一步步說明如何完成。您將會看到一個完整且可執行的範例，該範例會產生 PNG 圖片，並讓您自行控制條碼尺寸。

產生 PDF417 條碼是庫存系統、登機證與安全文件等常見需求。在本教學中，您還會學習**如何設定條碼尺寸**，以確保輸出符合您的版面需求。

## 前置條件

- .NET 6.0 SDK 或更新版本已安裝  
- Visual Studio 2022（或任何相容 C# 的 IDE）  
- **Aspose.BarCode for .NET** NuGet 套件（或任何支援 PDF417 的相容函式庫）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立 PDF417 條碼產生器

第一步是使用 `EncodeTypes.Pdf417` 類型以及您想要編碼的文字，實例化一個 `BarcodeGenerator`。此產生器物件會保存條碼的所有設定。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**為什麼這很重要：** `EncodeTypes.Pdf417` 列舉告訴函式庫使用 PDF417 符號，該符號支援大量資料與錯誤更正。文字字串可包含 Unicode 字元，讓您無需額外處理即可編碼國際符號。

## 步驟 2：設定條碼尺寸

控制每個模組（最小的黑白方格）的大小會決定整體影像解析度。`XDimension.Pixels` 屬性設定單一模組的像素寬度。

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼這很重要：** 較大的 `XDimension` 會產生較高解析度的影像，適合列印或遠距離掃描。相反地，較小的數值則可減少網路使用的檔案大小。

## 步驟 3：定義 PDF417 版面（欄與列）

PDF417 允許您透過指定欄數與列數來影響矩陣形狀，這會影響可讀性與條碼的實體尺寸。

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**為什麼這很重要：** 調整欄與列可讓條碼適配特定空間或符合掃描器的長寬比需求。若資料未填滿矩陣，函式庫會自動加入填充。

## 步驟 4：將條碼儲存為 PNG 圖片

最後，將產生的條碼寫入檔案。PNG 保留無損品質，適合後續處理。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

執行程式後，`Pdf417Layout.png` 會出現在專案的輸出資料夾中。圖像如下所示：

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*圖片說明文字：產生具自訂尺寸的 PDF417 條碼圖像*  

**為什麼這很重要：** 以 PNG 儲存可確保您設定的模組尺寸完整保留，這對後續的掃描應用至關重要。

## 完整範例（單一程式碼區塊）

以下是完整程式碼，您可以直接複製、貼上並執行，無需其他修改（如需可自行調整輸出路徑）。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### 預期輸出

- **檔案：** `Pdf417Layout.png`（PNG，無損）  
- **尺寸：** 由 `XDimension`（2 px）×（欄數 × 列數）矩陣決定  
- **內容：** 可掃描的 PDF417 條碼，編碼 Unicode 字串 `Åspóse.Barcóde©`

## 常見問題與邊緣情況

### 如果需要更大的列印圖像該怎麼辦？

將 `XDimension.Pixels` 提升至 4 或 5。較大的數值會產生更高解析度的條碼，但同時會增加檔案大小。

### 我可以編碼比範例字串更多的資料嗎？

可以。PDF417 最多可容納 1,850 個字元。只要在 `BarcodeGenerator` 建構式中更換文字參數即可。若資料超過矩陣容量，函式庫會自動新增列。

### 錯誤更正機制如何運作？

PDF417 內建錯誤更正功能。您可以透過以下方式調整其等級：

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

較高的等級會提升容錯能力，但會使條碼變大。

### 若條碼在螢幕上顯示模糊該怎麼辦？

請確保輸出圖像的 DPI 與顯示環境相符。您可以在儲存時設定 DPI：

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## 專業提示

- **專業提示：** 始終使用實際的掃描器測試產生的條碼。不同裝置對模組尺寸與靜區的容忍度各異。  
- **注意：** 非常小的 `XDimension` 值（< 1 px）在高 DPI 螢幕上可能會呈現為不可見的線條。  
- **Web 應用提示：** 以 `Cache-Control: public, max-age=86400` 提供 PNG，可減少重複產生的開銷。

## 結論

現在您已了解如何在 C# 中**產生 PDF417 條碼**，以及如何精確**設定條碼尺寸**以符合任何需求。完整且可執行的範例示範了如何以自訂欄/列版面與模組大小建立 PNG 圖片，供列印或數位發佈使用。

### 後續步驟

- 探索**如何以不同影像格式（JPEG、BMP）產生 PDF417 條碼**。  
- 學習**如何根據使用者輸入或裝置 DPI 動態設定條碼尺寸**。  
- 將條碼產生整合至 ASP.NET Core API，以按需提供條碼服務。

歡迎嘗試其他 PDF417 設定，例如錯誤更正、邊距與顏色。祝程式開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [如何設定 PDF417 條碼的錯誤等級 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [如何在 C# 中儲存條碼 – 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [在 C# 中產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}