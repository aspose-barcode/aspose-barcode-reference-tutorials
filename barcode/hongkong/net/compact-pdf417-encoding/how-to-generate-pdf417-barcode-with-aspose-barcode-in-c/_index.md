---
category: general
date: 2026-10-24
description: 學習如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼，並透過緊湊設定與條碼 XDimension 控制。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: zh-hant
lastmod: 2026-10-24
og_description: 使用 Aspose.BarCode 在 C# 中產生 PDF417 條碼。遵循此完整指南以建立緊湊的 PDF417 圖像、控制 XDimension，並設定欄位。
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: 使用 Aspose.BarCode 產生 PDF417 條碼 – C# 步驟教學
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本指南將為您展示一個完整、可直接執行的解決方案。您將看到 Aspose.BarCode 如何簡化此流程，同時讓您能細緻控制 **compact PDF417**、**barcode XDimension** 以及 **PDF417 columns**。

產生條碼是庫存系統、票務平台與文件工作流程的常見需求。完成本教學後，您將擁有一個自包含的 C# 程式，可產生清晰的 PNG 格式 PDF417 條碼影像，隨時可嵌入任何 UI 或列印於標籤上。

## 您需要的環境

- .NET 6.0 SDK 或更新版本（此程式碼亦相容 .NET Framework 4.6+）
- Visual Studio 2022 或您偏好的任何 C# 編輯器
- 有效的 Aspose.BarCode for .NET 授權（開發階段可使用免費試用版）
- 基本的 C# 語法熟悉度

> **專業提示：** 若您正在評估 Aspose.BarCode，請從官方網站下載試用版，並將 NuGet 套件 `Aspose.BarCode` 加入專案。試用版會在產生的影像上加上小浮水印，套用授權後即會移除。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在解決方案資料夾中開啟終端機並執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會取得最新的穩定版（截至 2026 年 10 月，版本 23.12）。加入套件後即可還原 `Aspose.BarCode.Generation` 命名空間，供您 **產生 PDF417 條碼** 影像使用。

## 步驟 2：建立基本的 C# 主控台專案

如果尚未有專案，請建立：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

開啟 `Program.cs`。此骨架已包含 `Main` 方法，我們將在此放入條碼產生程式碼。

## 步驟 3：初始化條碼產生器

首先，匯入必要的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

接著，在 `Main` 內部實例化 `BarcodeGenerator`，使用 PDF417 符號與您想要編碼的資料：

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

此字串包含 Unicode 字元，以示範 Aspose.BarCode 能正確處理非 ASCII 輸入。若僅需 ASCII，請將文字換成任意純文字字串。

## 步驟 4：調整條碼 XDimension（模組大小）

**barcode XDimension** 決定最小條紋（模組）的寬度。以像素設定可讓您對最終影像尺寸做到像素級的精準控制：

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

設定為 `2` 像素即可產生緊湊影像，同時不影響掃描可靠度。若需較大的條碼可提高數值，若版面極為密集則可降低。

## 步驟 5：設定緊湊式 PDF417 選項

兩個 PDF417 專屬設定會顯著影響視覺佔用：

| 設定 | 說明 | 緊湊輸出時的典型值 |
|------|------|-------------------|
| `Columns` | 資料欄位的數量 | `3` |
| `Truncate` (緊湊模式) | 省略右側的空白區域並減少列數 | `true` |

套用方式如下：

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

將 **PDF417 columns** 設為 `3` 並將 `Truncate = true` 結合，可產生 *緊湊 PDF417* 條碼，能在標準標籤上保持良好適配，同時大多數掃描器仍能讀取。

## 步驟 6：儲存條碼影像

最後，將條碼寫入磁碟。範例會儲存為 PNG，但 Aspose.BarCode 亦支援 BMP、JPEG、GIF、TIFF 與 SVG 等格式：

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png` 常數告訴函式庫產生無損的 PNG，這對後續處理或列印最為理想。

## 完整、可執行的原始碼

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

執行程式後會在專案根目錄產生 `CompactPdf417.png`。使用任何影像檢視器開啟，即可看到緊密排列的 PDF417 條碼，編碼內容為 *Åspóse.Barcóde©*。

![使用 Aspose.BarCode 產生的 PDF417 條碼截圖](placeholder-image.png "產生的 PDF417 條碼")

*圖片替代文字：使用 Aspose.BarCode 產生的 PDF417 條碼截圖* – 此替代文字包含主要關鍵字，以提升可及性與 SEO。

## 驗證結果

1. 開啟 PNG 檔案。條碼應由三個垂直資料欄位組成，且版面緊湊（右側無額外靜止區）。
2. 使用支援 PDF417 的智慧手機條碼掃描程式掃描影像。解碼文字必須與原始輸入字串相符。
3. 若掃描失敗，可嘗試將 `XDimension.Pixels` 提升至 `3` 或 `4`。較大的模組有助於低解析度裝置的可讀性。

## 常見變化與邊緣情況

### 1. 更改影像格式

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG 為向量格式，無論放大多少都能保持條碼清晰——非常適合網頁使用。

### 2. 編碼大量資料

PDF417 可儲存約 1.1 KB 文字。當資料量超過三欄的容量時，函式庫會自動增加列數。若想保持條碼緊湊，可採取以下措施：

- 縮短資料長度（例如使用識別碼取代完整訊息）
- 增加 **PDF417 columns** 數量（例如 `generator.Parameters.Barcode.Pdf417.Columns = 5;`）

### 3. 使用授權以移除試用版浮水印

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

將授權檔案放置於執行檔旁。完成授權後，產生的影像將不再顯示浮水印。

### 4. 處理例外情況

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

常見失敗情形包括寫入權限不足或不支援的影像格式。

## 為何這些設定很重要

- **barcode XDimension** – 控制每根條紋的視覺粗細。過小會導致條碼無法辨識，過大則浪費空間。
- **PDF417 columns** – 欄位較少會產生較窄的條碼，但會增加列數。

## 接下來您應該學習什麼？

以下教學與本指南示範的技巧密切相關，並提供完整可執行的程式碼範例與步驟說明，協助您精通更多 API 功能，或在自己的專案中探索其他實作方式。

- [如何使用 Aspose 產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [在 C# 中使用緊湊設定產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [如何在 C# 中儲存條碼並產生 PDF417（使用 Aspose）](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}