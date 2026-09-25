---
category: general
date: 2026-08-19
description: 快速在 C# 中生成 PDF417 條碼。了解如何使用 Aspose.BarCode 於 C# 生成 PDF417 條碼，並使用緊湊模式及自訂設定。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: zh-hant
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 在 C# 中產生 PDF417 條碼。本教學示範如何在緊湊模式下產生 PDF417 條碼、設定
  X 尺寸，並儲存為 PNG。
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: 在 C# 中產生 PDF417 條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 在 C# 中生成 PDF417 條碼 – 完整指南（緊湊版面）
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 PDF417 條碼 – 完整指南

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學將會完整示範操作步驟。您將會看到一個簡潔、可投入生產環境的範例，能建立緊湊的 PDF417 條碼、調整 X‑dimension，並將結果儲存為 PNG 圖片。

產生 PDF417 條碼在需要將大量資料（例如票證資訊、運送清單或身分證件）編碼為機器可讀格式時相當常見。使用 Aspose.BarCode 可讓此流程變得簡單，且程式碼相容 .NET 6+ 或 .NET Framework 4.7.2 及以上版本。

在本指南中您將會：

* 安裝 Aspose.BarCode NuGet 套件。
* 撰寫一個自包含的 C# 程式，**產生 PDF417 條碼**，使用少量欄位且啟用緊湊（截斷）模式。
* 調整條碼寬度（X‑dimension）以提升渲染銳利度。
* 將條碼儲存為 PNG 檔案。
* 探索變化、邊緣案例與最佳實踐技巧。

## 前置條件

在開始之前，請確保您具備：

* 已安裝 .NET 6 SDK 的 Visual Studio 2022（或任何 C# IDE）。
* 可連網下載 **Aspose.BarCode** NuGet 套件的網路環境。
* 有寫入權限的資料夾，以便儲存 PNG 檔案。

不需要額外的函式庫；Aspose.BarCode 內部已處理影像編碼。

## 步驟 1：加入 Aspose.BarCode 套件

在 Visual Studio 中開啟您的專案，於方案上點右鍵，選取 **Manage NuGet Packages**。搜尋 `Aspose.BarCode` 並安裝最新的穩定版。

```bash
dotnet add package Aspose.BarCode
```

> **專業提示：** 請保持套件為最新版本。新版本通常包含效能提升與對最新 .NET 執行階段的支援。

## 步驟 2：建立最小化的主控台應用程式

如果尚未有專案，請建立一個新的 C# 主控台專案：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

將 `Program.cs` 的內容取代為以下完整範例。此程式示範 **如何在 C# 中產生 PDF417 條碼**，從頭到尾完整流程。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 為何每一行都很重要

* **`EncodeTypes.Pdf417`** – 選取 PDF417 符號集，支援約 1.1 KB 的資料量。
* **`XDimension.Pixels = 2`** – 設定基本條寬。較小的數值會讓條碼更細，較大的數值則提升低解析度裝置的可讀性。
* **`Pdf417.Columns = 3`** – 限制欄位數，迫使產生器使用更多列，產生較高但較窄的條碼。
* **`Pdf417.Truncate = true`** – 啟用緊湊模式，移除停止圖樣，縮小影像大小且不影響資料完整性。
* **`Save(..., BarCodeImageFormat.Png)`** – 輸出 PNG 檔案。您亦可根據下游需求選擇 `Jpeg`、`Bmp` 或 `Svg`。

執行程式：

```bash
dotnet run
```

您應該會在主控台看到確認檔案位置的訊息，且資料夾內會出現 `CompactPdf417.png`。開啟 PNG 後可看到清晰、緊湊的 PDF417 條碼，已正確編碼 Unicode 字串。

## 步驟 3：驗證條碼（可選但建議執行）

為確保條碼可被讀取，您可以使用智慧手機上的任意標準 PDF417 掃描應用程式，或是桌面解碼函式庫。編碼後的文字應與原始 `data` 字串完全相同，包含所有特殊字元。

若遇到解碼問題：

* 將 `XDimension` 提升至 3 或 4 像素。
* 減少欄位數（例如設定 `Columns = 2`）。
* 停用 `Truncate`（`Truncate = false`）以加入停止圖樣。

這些調整會在尺寸與可讀性之間取得平衡，對於低解析度的印表機或掃描器特別有用。

## 步驟 4：探索常見變化

### 4️⃣ 產生高密度 PDF417 以供列印

如果需要在小標籤上放置條碼，請提升欄位數並降低 X‑dimension：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ 變更輸出格式為 SVG 以支援向量縮放

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG 輸出可在不失真的情況下自由縮放，適合回應式網頁使用。

### 6️⃣ 編碼二進位資料（例如 byte 陣列）

若需嵌入二進位負載，請先將其轉換為 Base64 字串：

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

條碼現在攜帶二進位資訊，解碼端必須先還原 Base64 步驟。

## 常見問題

| 問題 | 答案 |
|----------|--------|
| **可以不使用 Aspose 產生 PDF417 嗎？** | 可以，還有 ZXing.Net、Dynamsoft 等其他函式庫，但 Aspose.BarCode 提供更豐富的版面控制（欄位、截斷）與更佳的 Unicode 處理。 |
| **最大資料長度是多少？** | PDF417 最多可編碼 1,108 位元組（≈ 1 KB）的二進位資料。若超過此上限，建議將資料切分至多個條碼。 |
| **緊湊模式符合標準嗎？** | 截斷式 PDF417 為 ISO/IEC 15438 規範的一部份，廣受支援，但請確認目標掃描器明確支援此模式。 |
| **如何變更背景顏色？** | 在儲存前設定 `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` 以及 `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;`。 |

## 結論

您現在已掌握使用 Aspose.BarCode **在 C# 中產生 PDF417 條碼** 的方法，了解如何微調 X‑dimension、啟用緊湊模式，並將結果匯出為 PNG 圖片。完整、可執行的範例可直接複製至任何 .NET 專案，而上述變化示例則讓您能依需求將條碼應用於列印、網頁或二進位負載情境。

接下來可以探索的方向：

* 將條碼產生整合至 ASP.NET Core API，依需求即時回傳影像。
* 在同一標籤上同時結合 PDF417 與 QR Code，實現雙格式掃描。
* 使用 Aspose.BarCode 的 `Reader` 類別解碼產生的影像，並以程式方式驗證資料。

祝您開發順利，盡情體驗 **產生 PDF417 條碼** 解決方案為應用程式帶來的彈性！

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，能協助您進一步掌握 API 功能並探索其他實作方式：

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}