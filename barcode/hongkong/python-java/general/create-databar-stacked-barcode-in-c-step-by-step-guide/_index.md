---
category: general
date: 2026-08-06
description: 快速在 C# 中建立 DataBar 堆疊條碼。學習設定 X 尺寸、調整長寬比，並使用 DataBar 堆疊全向產生器匯出 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: zh-hant
lastmod: 2026-08-06
og_description: 在 C# 中使用 Aspose.BarCode 建立 DataBar 堆疊條碼。本教學說明如何設定 X 尺寸、變更長寬比，並儲存 PNG
  圖片。
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: 使用 C# 建立 DataBar 堆疊條碼 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 使用 C# 建立 DataBar 堆疊條碼 – 逐步指南
url: /zh-hant/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 databar stacked barcode – 步驟說明指南

如果您需要在 C# 中**建立 databar stacked barcode**影像，本指南將會示範如何使用 Aspose.BarCode 函式庫完成。您將學會設定 X 維度、變更條碼的長寬比，並將結果儲存為 PNG 檔案——只需簡短的幾個步驟。

在必須為零售掃描或物流追蹤編碼 GS1‑128 資料時，產生 DataBar Stacked 條碼是常見需求。以下各節將從專案設定說明到驗證輸出，完整涵蓋所有細節，讓您能將此解決方案整合至任何 .NET 應用程式中。

## 前置條件

* **.NET 6.0**（或更新版本）已安裝 – 程式碼以現代 SDK 為目標。
* **授權**版的 **Aspose.BarCode for .NET**。免費評估版可用於測試，但會加上浮水印。
* 如 **Visual Studio 2022** 或 **VS Code**（搭配 C# 擴充套件）的開發環境。
* 具備 **C#** 語法的基本認識，以及對 GS1 應用識別碼（Application Identifiers）的概念。

> **專業提示：** 若使用 NuGet 套件管理員，指令 `dotnet add package Aspose.BarCode` 會自動解決所有相依性。

## 步驟 1：建立新 Console 專案

在終端機或套件管理員主控台中執行以下指令：

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 指令會產生最小的 **Program.cs** 檔案。加入 **Aspose.BarCode** 套件後，即可使用 `BarcodeGenerator` 類別。

## 步驟 2：初始化 DataBar Stacked Omnidirectional 產生器

開啟 **Program.cs**，將預設內容取代為以下程式碼。第一行會建立一個針對 **DataBar Stacked Omnidirectional** 符號設定的 **BarcodeGenerator**，並提供 GS1‑128 負載。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**為什麼重要：** `EncodeTypes.DatabarStackedOmniDirectional` 列舉值告訴函式庫產生 **databar stacked barcode**，即 DataBar 全向族的堆疊變體。此符號最多可容納 14 個數字字元，非常適合 GTIN‑14 代碼。

## 步驟 3：設定 X 維度（模組寬度）

X 維度決定最小條紋（模組）的寬度。若設定過小，低解析度印表機可能無法清晰呈現；若設定過大，則可能超出標籤空間。

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **提示：** `Pixels` 屬性在螢幕測試時相當方便。若是以列印為主的情境，請改用 `generator.Parameters.Barcode.XDimension.Millimeters`。

## 步驟 4：調整長寬比並儲存第一張影像

**長寬比** 會影響堆疊條碼的高寬比例。DataBar Stacked Omnidirectional 類型支援 10 至 30 的比例。我們將產生兩張影像以說明視覺差異。

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`generator.Save` 會將 **PNG** 檔寫入目前工作目錄。`BarCodeImageFormat.Png` 列舉確保無損壓縮，適合後續處理或嵌入 PDF 中。

## 步驟 5：將長寬比改為 30 並儲存第二張影像

現在將長寬比改為 **30**，以提升堆疊條紋的高度。這會使條碼變高，但不會改變 X 維度。

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

執行程式後會產生兩個 PNG 檔案：

* **DatabarAspectRatio15.png** – 緊湊的條碼，適用於小尺寸標籤。
* **DatabarAspectRatio30.png** – 較高的條碼，可提升在低對比表面上的掃描可靠度。

您可以使用任何檢視器開啟影像，確認條紋正確堆疊且編碼資料與原始 GS1 字串相符。

## 步驟 6：驗證編碼值（可選）

若需確認條碼確實對應輸入字串，可使用相同函式庫進行解碼：

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

解碼器應輸出 `(01)12345678901231`，證明 **create databar stacked barcode** 的過程已正確保留資料。

## 常見問題與避免方法

| 問題 | 發生原因 | 解決方式 |
|-------|----------------|-----|
| 條碼顯示模糊 | X 維度設定過低，導致輸出解析度不足 | 將 `XDimension.Pixels` 提高，或在列印時使用 `Millimeters` |
| 掃描器回報「找不到符號」 | 長寬比超出支援的 10‑30 範圍 | 將長寬比維持在 10 至 30 之間；15 與 30 為安全預設值 |
| PNG 含有浮水印 | 使用 Aspose.BarCode 的免費評估授權 | 購買完整授權，或僅將試用版用於測試 |
| 第二張影像解碼失敗 | 解碼器設定了錯誤的符號類型 | 在讀取堆疊條碼時使用 `DecodeType.DatabarStackedOmniDirectional` |

## 往後步驟

既然您已能 **create databar stacked barcode** 影像，接下來或許想要：

* **將 PNG 嵌入 PDF 發票**，使用如 **Aspose.PDF** 的 PDF 函式庫。
* **在 Web API 中即時產生條碼**——直接從 ASP.NET Core 控制器回傳 PNG 位元組。
* **嘗試其他 DataBar 變體**（例如 `DatabarExpanded`、`DatabarLimited`），只需變更 `EncodeTypes` 列舉。
* **調整顏色**，透過設定 `generator.Parameters.Barcode.ForeColor` 與 `BackColor` 以符合品牌設計。

上述每個主題皆建立在本教學的核心概念之上：初始化 `BarcodeGenerator`、設定視覺參數，並以 `BarCodeImageFormat` 儲存結果。

---

### 結論

本教學示範了如何使用 Aspose.BarCode 在 C# 中 **create databar stacked barcode** 影像。您學會了設定 **X 維度**、調整 **條碼長寬比**，並使用 `BarcodeGenerator` 匯出為 **PNG** 檔案。透過可選的解碼步驟，亦可驗證編碼的 GS1 資料是否正確。將這些模式套用於您的庫存、運輸或 POS 應用程式，並探索函式庫提供的各種客製化選項。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以步驟說明的完整程式碼範例，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [單維 Databar 條碼高度調整](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [產生條碼影像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}