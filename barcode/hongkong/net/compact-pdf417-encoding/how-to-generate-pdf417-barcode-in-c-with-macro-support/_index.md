---
category: general
date: 2026-10-21
description: 了解如何使用 Aspose.BarCode 在 C# 中產生 PDF417 條碼。詳細步驟包括 PDF417 條碼設定、宏 PDF417
  條碼的建立，以及儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: zh-hant
lastmod: 2026-10-21
og_description: 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼。請跟隨本逐步教學設定 PDF417 條碼參數、建立宏
  PDF417 條碼，並匯出為 PNG。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: 如何在 C# 中產生 PDF417 條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中生成支援巨集的 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生支援宏的 PDF417 條碼

如果你需要在 C# 中產生 PDF417 條碼，本指南會提供一個完整、可直接執行的解決方案。無論你是要建置物流標籤系統或是編碼大型資料區塊，你都會看到如何設定 PDF417 條碼參數、建立宏 PDF417 條碼，並將結果儲存為 PNG 圖片。

產生 PDF417 條碼不需要低階位元操作。透過使用 Aspose.BarCode 提供的 **barcode generator C#** 類別，你可以專注於業務邏輯，而讓程式庫負責編碼、錯誤更正與圖像渲染。

## 需要的環境

- **.NET 6.0** 或更新版本（此程式碼亦相容 .NET Framework 4.6 以上）
- **Aspose.BarCode for .NET** NuGet 套件（`Install-Package Aspose.BarCode`）
- 開發環境，例如 Visual Studio 2022 或 Visual Studio Code
- 具備寫入 PNG 圖片儲存資料夾的權限

上述先決條件可確保範例能順利編譯與執行，且不需額外設定。

## 產生 PDF417 條碼的步驟概覽

以下為此流程的簡要路線圖：

1. **建立 `BarcodeGenerator` 實例**，使用 `EncodeTypes.MacroPdf417`。
2. **調整條碼基本外觀**（模組大小、顏色等）。
3. **設定 PDF417 專屬參數**，包含宏相關欄位。
4. **以 `BarCodeImageFormat PNG` 儲存產生的條碼影像**。

每個步驟都會詳細說明，並提供完整的程式碼片段，你可以直接複製到 Console 應用程式中。

## 步驟 1：設定開發環境

建立新的 Console 專案，並加入 Aspose.BarCode 參考：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

開啟 `Program.cs`，加入所需的命名空間：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些匯入讓你可以使用 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat`。

## 步驟 2：建立 Macro PDF417 條碼產生器

實作的第一行會建立 **Macro PDF417 條碼** 物件。`EncodeTypes.MacroPdf417` 列舉會告訴程式庫使用 PDF417 的宏變體。

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **為什麼重要：** 使用 `EncodeTypes.MacroPdf417` 會啟用宏欄位（`FileID`、`SegmentID` 等），讓你能將大型資料分割成多個條碼影像，同時保留順序。

## 步驟 3：調整條碼基本外觀

在調整 PDF417 專屬參數之前，先設定模組（像素）寬度。`2` 的數值可產生清晰且易於掃描的影像，同時不會產生過大的檔案。

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

如果你的 UI 需要不同的配色，也可以在此變更前景/背景顏色。

## 步驟 4：設定 PDF417 專屬參數

**PDF417 條碼設定** 透過 `generator.Parameters.Barcode.Pdf417` 取得。以下顯示最重要的宏欄位：

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### 各屬性說明

| Property | Purpose | Typical range |
|----------|---------|---------------|
| `Columns` | 控制每列包含多少資料欄位。欄位越多可減少列數，但會增加寬度。 | 1 – 30 |
| `MacroPdf417FileID` | 用於將同一邏輯檔案的所有段落分組的 32 位元識別碼。每個段落必須相同。 | 任意正整數 |
| `MacroPdf417SegmentID` | 目前段落的零基索引。每產生一個條碼後遞增。 | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | 組成完整檔案的總段落數。必須產生所有段落。 | ≥ 1 |
| `MacroPdf417FileName` | 可選的描述性名稱（最多 255 個字元），有助於除錯。 | 英數字字串 |

> **專業提示：** 大多數標籤印表機建議將 `Columns` 設為 3 到 7 之間。較大的數值可能在低解析度裝置上超出可列印寬度。

## 步驟 5：將條碼儲存為 PNG 圖片

最後，使用 `BarCodeImageFormat PNG` 將條碼寫入磁碟。PNG 保留無損品質，對於可靠掃描至關重要。

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

程式執行完畢後，你會在專案資料夾中看到 `MacroPdf417.png`。開啟該檔案即可看到乾淨的 Macro PDF417 條碼，已可直接列印。

### 預期輸出

產生的影像大致如下（僅示意）：

![Macro PDF417 條碼範例](macro-pdf417-barcode.png "由 C# 程式碼產生的 Macro PDF417 條碼")

*圖片的 alt 文字為「由 C# 程式碼產生的 Macro PDF417 條碼」，符合可及性與 SEO 要求。*

## 常見問題與除錯

| Issue | Symptom | Fix |
|-------|---------|-----|
| **`EncodeTypes` 設定錯誤** | 條碼顯示為 QR code 或純文字。 | 確保使用 `EncodeTypes.MacroPdf417`（而非 `EncodeTypes.Pdf417`）。 |
| **段落 ID 不匹配** | 掃描器回報「缺少段落」。 | 依序遞增 `MacroPdf417SegmentID`，並確保所有檔案的 `SegmentsCount` 一致。 |
| **模組大小過大** | 條碼寬度超過標籤尺寸。 | 減少 `XDimension.Pixels` 或降低 `Columns`。 |
| **檔案路徑錯誤** | 儲存時拋出 `UnauthorizedAccessException`。 | 寫入你擁有權限的資料夾，例如 `Environment.CurrentDirectory`。 |
| **缺少 NuGet 套件** | 編譯錯誤：找不到 `BarcodeGenerator`。 | 在建置前執行 `dotnet add package Aspose.BarCode`。 |

提前解決這些問題，可在將條碼產生整合至更大工作流程時節省時間。

## 擴充範例

現在你已能產生單一 Macro PDF417 條碼，接下來可考慮以下步驟：

- **批次產生**：對資料區塊集合進行迴圈，在每次迭代時更新 `MacroPdf417SegmentID`。
- **不同影像格式**：若下游系統偏好，可將 `BarCodeImageFormat.Png` 改為 `Jpeg` 或 `Bmp`。
- **嵌入 PDF**：使用 Aspose.PDF 將 PNG 放入 PDF 報告中以供分發。
- **掃描驗證**：使用硬體掃描器或支援 Macro PDF417 的行動應用程式測試產生的條碼。

這些變化在保留核心 **PDF417 條碼設定** 的同時，讓輸出符合專案需求。

## 結論

現在你已了解如何使用 Aspose.BarCode 在 C# 中 **產生 PDF417 條碼**，從建立帶有 `EncodeTypes.MacroPdf417` 的 `BarcodeGenerator`、設定宏欄位，到將結果儲存為 `BarCodeImageFormat PNG`。完整且可執行的程式碼示範了建議的做法，說明了每個設定的意義，並指出可能遇到的常見問題。

歡迎自行嘗試不同的欄位數、顏色或輸出格式，並將產生器整合至自己的應用程式，以實現可靠的高密度資料編碼。

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [如何在 C# 使用 Aspose.BarCode 建立 Macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 中儲存條碼並產生 PDF417（使用 Aspose）](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}