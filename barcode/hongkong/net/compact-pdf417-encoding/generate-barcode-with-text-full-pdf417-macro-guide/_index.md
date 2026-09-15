---
category: general
date: 2026-07-18
description: 使用 Aspose.BarCode for .NET 產生帶文字的條碼。了解如何產生 PDF417 條碼、設定巨集選項，並匯出 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: zh-hant
lastmod: 2026-07-18
og_description: 在 C# 中快速生成帶文字的條碼。本分步教學展示如何生成 PDF417 條碼、設定巨集設定，並儲存為 PNG。
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: 產生帶文字的條碼 – Master PDF417 巨集創建
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: 生成帶文字的條碼 – 完整 PDF417 巨集指南
url: /zh-hant/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生帶文字的條碼 – 完整 PDF417 Macro 教學

有沒有想過 **如何產生同時內嵌自訂文字的 PDF417** 條碼？在本教學中，你將會看到如何使用 Aspose.BarCode for .NET **產生帶文字的條碼**，並一步步說明 Macro PDF417 符號所需的所有設定。內容精簡、直接，提供一個完整可執行的範例，讓你今天就能把它放入專案中使用。

我們將會說明：

* 必要的 NuGet 套件與 using 指令。  
* 如何建立支援 Unicode 字元的條碼產生器。  
* 設定模組大小、欄位數以及 Macro 專屬的 ID。  
* 將結果存成 PNG 檔並驗證輸出。  

完成後，你將擁有一張可直接使用的 Macro PDF417 條碼 PNG 圖片，能嵌入發票、票證或任何需要機器可讀區段的文件中。

---

## 前置條件

在開始之前，請確保你已具備以下項目：

| Requirement | Reason |
|-------------|--------|
| **.NET 6.0** 或更新版本 | Aspose.BarCode 支援 .NET Standard 2.0+，使用 .NET 6 可取得最新執行環境。 |
| **Visual Studio 2022**（或任何 C# IDE） | 方便編輯與除錯。 |
| **Aspose.BarCode for .NET** NuGet 套件 | 真正負責產生條碼的函式庫。使用 `dotnet add package Aspose.BarCode` 安裝。 |
| **寫入權限** 至輸出資料夾 | `Save` 方法需要寫入 PNG 檔。 |

如果上述任一項目你不熟悉，請先處理好，否則程式碼會拋出明顯的例外。

---

## 第一步 – 安裝並匯入函式庫

首先，將 NuGet 套件加入專案：

```bash
dotnet add package Aspose.BarCode
```

接著，將必要的命名空間匯入：

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **小技巧：** 若使用 Visual Studio，右鍵點擊專案 → *Manage NuGet Packages* → 搜尋 *Aspose.BarCode* 並安裝最新的穩定版。

---

## 第二步 – 使用自訂文字建立條碼產生器

*主要* 任務是 **產生帶文字的條碼**，且文字中可能包含「Å」或「©」等特殊字元。建構子接受編碼類型與原始資料字串：

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

為什麼這很重要：`EncodeTypes.MacroPdf417` 告訴 Aspose 我們要使用 Macro 版，讓大型訊息能分割成多個符號。文字字串可以是任意 UTF‑8 序列，Aspose 會在內部自行處理轉換。

---

## 第三步 – 調整基本外觀（模組大小）

條碼的「模組」是最小的黑白方格。設定其像素大小即可在不改變資料密度的前提下調整整體影像尺寸：

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

如果需要較大的列印圖檔，可將此值調高至 4 或 6。只要記得，模組變大會使最終 PNG 檔案尺寸增加。

---

## 第四步 – 設定 Macro PDF417 專屬選項

Macro PDF417 會加入兩個識別碼，讓掃描器能將多個符號串接起來。通常會設定：

| Property | 功能說明 |
|----------|----------|
| `Columns` | 每個符號的資料欄位數（影響寬度）。 |
| `MacroPdf417FileID` | 整個 Macro 檔案的唯一 ID（必須 ≤ 2³¹‑1）。 |
| `MacroPdf417SegmentID` | 目前段落的索引（0‑254）。 |

以下為程式碼範例：

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**邊緣案例說明：** `MacroPdf417FileID` 必須在同一邏輯檔案的所有段落中保持相同。若產生多個段落，請重複使用相同的 ID，否則會得到無法組合的獨立符號。

---

## 第五步 – 將條碼存為 PNG 圖片

所有設定完成後，將影像寫入磁碟：

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save` 方法會自動產生 PNG，並處理 DPI 與色深。執行完畢後，開啟檔案，你會看到類似下圖的結果：

![產生帶文字的條碼範例](/images/barcode-example.png){.center alt="產生帶文字的條碼範例"}

如果看不到條碼，請再次確認資料夾是否存在，以及程式是否具備寫入權限。

---

## 完整、可直接執行的範例

將下列程式碼全部複製到新建的 Console App（`dotnet new console`）中，執行即可。它會在 `C:\Barcodes` 資料夾（請先自行建立）產生 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**預期輸出**（Console）：

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

產生的 PNG 會顯示一個緊湊的 Macro PDF417 符號，內含文字 “Åspóse.Barcóde©”。

---

## 常見問題與注意事項

| Question | Answer |
|----------|--------|
| *Can I use a different image format?* | 絕對可以——將 `BarCodeImageFormat.Png` 改成 `Jpeg`、`Bmp` 或 `Gif`。PNG 為無損格式，我們預設使用它。 |
| *What if I need more than one segment?* | 為每個段落建立新的 `BarcodeGenerator`，保持 `MacroPdf417FileID` 相同，並遞增 `MacroPdf417SegmentID`（0‑254）。 |
| *My text contains emojis—will they work?* | Aspose.BarCode 支援 UTF‑8，大多數表情符號皆可使用。但請確認目標掃描器能解碼；許多工業掃描器僅支援英數字。 |
| *The barcode is too wide for my label.* | 減少 `Columns` 或增大模組大小。欄位較少會產生較窄的符號，但可能需要更高 DPI 的印表機。 |
| *Do I need a license?* | 評估授權可供測試使用，但會加上小水印。正式上線建議購買授權，以移除水印並解鎖全部功能。 |

---

## 往後的步驟

了解 **如何產生 PDF417** 並內嵌自訂文字後，你可能想要：

* 使用 Aspose.BarCode 的 `BarCodeReader` 在行動應用程式中 **解碼** 條碼。  
* 將多個 Macro 段落 **合併** 成單一 PDF 文件，以便批次列印。  
* **探索其他條碼類型**（QR、DataMatrix），其參數設定模式相似。  
* 透過 `Pdf417.ErrorCorrectionLevel` **調整錯誤更正等級**，以因應更惡劣的環境。

以上主題皆建立在剛才學到的核心概念上，切換起來相當順暢。

---

## 結論

我們完整示範了如何使用 Aspose.BarCode for .NET **產生帶文字的條碼**，以及 **如何產生 PDF417 Macro** 符號。透過設定 X‑dimension、欄位數與 Macro ID，你可以全方位掌控尺寸、版面與多段落處理。最終產出的 PNG 可直接列印、嵌入 PDF，或供掃描器使用，無需額外轉換。

試著自行調整參數，讓條碼為你的業務需求服務。若遇到問題，Aspose 官方文件與社群論壇都是極佳的後續資源。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化你在專案中的應用。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能與替代實作方式。

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}