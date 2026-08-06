---
category: general
date: 2026-08-06
description: 如何為 Databar Expanded Stacked 條碼設定欄位，並學習如何產生條碼圖像、設定列以及於 C# 中儲存條碼檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set columns
- how to generate barcode
- how to set rows
- barcode save file
language: zh-hant
lastmod: 2026-08-06
og_description: 如何設定 Databar Expanded Stacked 條碼的欄位，並快速學習如何產生條碼影像、設定列，以及使用 Aspose.Barcode
  儲存條碼檔案。
og_image_alt: Screenshot showing how to set columns for a Databar Expanded Stacked
  barcode in C#
og_title: 如何為 Databar Expanded Stacked 條碼設定欄位 – C# 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set columns for a Databar Expanded Stacked barcode and learn
    how to generate barcode images, set rows, and save the barcode file in C#.
  headline: How to set columns for a Databar Expanded Stacked barcode – complete C#
    guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何設定 Databar Expanded Stacked 條碼的欄位 – 完整 C# 指南
url: /zh-hant/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定 Databar Expanded Stacked 條碼的列數 – 完整 C# 指南

如果您需要 **how to set columns** for a Databar Expanded Stacked 條碼，本教學會向您展示確切的步驟。無論您是建立零售標籤系統或物流應用程式，控制列與行都能讓您微調條碼尺寸與掃描可靠性。此外，您還會看到 **how to generate barcode** 圖像、調整行數，以及正確 **barcode save file** 到磁碟。

本指南將帶您完成：

* 安裝 Aspose.Barcode for .NET 程式庫。  
* 為 Databar Expanded Stacked 類型建立條碼產生器。  
* 設定列數、行數和圖像格式。  
* 將產生的 PNG 檔案儲存至指定目錄。  

不需要先前使用 Aspose.Barcode 的經驗——只需一個基本的 C# 開發環境。

## 前置條件

在開始之前，請確保您已具備以下條件：

* .NET 6.0 SDK 或更新版本已安裝。  
* Visual Studio 2022（或任何支援 .NET 的 IDE）。  
* 已加入 **Aspose.Barcode** 的 NuGet 參考（`dotnet add package Aspose.Barcode`）。  

所有程式碼片段均可於預設的 Console 專案範本編譯。

## 步驟 1：為 Databar Expanded Stacked 建立條碼產生器

第一步是使用 `EncodeTypes.DatabarExpandedStacked` 列舉實例化 `BarcodeGenerator`。此操作會設定預設佈局（stacked），並為後續設定做好準備。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the Databar Expanded Stacked type.
        // The text "Databar Expanded Stacked long" is the data encoded in the barcode.
        BarcodeGenerator barcodeGeneratorCols = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

**為什麼這很重要：** 產生器保存所有渲染參數。選擇 `DatabarExpandedStacked` 即告訴函式庫使用 stacked 佈局，這是唯一支援列與行調整的佈局。

## 如何設定 Databar Expanded Stacked 條碼的列數

現在產生器已建立，您可以控制列數。`DataBar.Columns` 屬性接受 1 到 4 之間的整數。將其設定為 **4** 會產生最寬的條碼，同時仍符合 stacked 佈局。

```csharp
        // Step 2: Configure the generator to use 4 columns.
        barcodeGeneratorCols.Parameters.Barcode.DataBar.Columns = 4;
```

**實用提示：** 僅在標籤上有足夠空白時才使用最大列數。過多列數在小標籤上可能導致掃描問題。

## 如何產生條碼圖像並儲存

在設定列數後，您需要渲染條碼並將圖像寫入磁碟。`Save` 方法接受檔案路徑與圖像格式列舉。

```csharp
        // Step 3: Save the barcode image as PNG.
        barcodeGeneratorCols.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
```

資料夾 `output` 必須已存在，否則呼叫會拋出例外。若需要，您可以使用 `Directory.CreateDirectory("output");` 程式化建立它。

## 如何設定 Databar Expanded Stacked 條碼的行數

行數的設定方式與列數類似，但會影響條碼模組的垂直堆疊。`DataBar.Rows` 屬性接受 1 到 5 的值。本範例使用 **3** 行。

```csharp
        // Step 4: Create a second generator for the same barcode type.
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the generator to use 3 rows.
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        // Step 6: Save the row‑adjusted barcode.
        barcodeGeneratorRows.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼行數重要：** 增加行數會提升條碼高度，對於需要更多資料模組而不想加寬條碼的高密度標籤非常有用。

## 條碼儲存檔案選項與最佳實踐

`Save` 方法支援多種圖像格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。PNG 為無損格式，適用於大多數掃描設備。若需要較小的檔案大小且能接受輕微壓縮痕跡，可選擇 JPEG：

```csharp
barcodeGeneratorCols.Save("output/DatabarCols4.jpg", BarCodeImageFormat.Jpeg);
```

**特殊情況：** 儲存為 JPEG 時，請確保品質參數設定適當（預設為 90）。品質過低會使小模組模糊，導致條碼無法辨識。

## 完整、可執行的範例

將所有步驟整合起來，以下是一個單一檔案，您可以直接複製到新的 Console 專案中並立即執行：

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists.
        Directory.CreateDirectory("output");

        // ------------------------------
        // How to set columns (4 columns)
        // ------------------------------
        BarcodeGenerator colsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        colsGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colsGenerator.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to output/DatabarCols4.png");

        // ------------------------------
        // How to set rows (3 rows)
        // ------------------------------
        BarcodeGenerator rowsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowsGenerator.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to output/DatabarRows3.png");

        // ------------------------------
        // How to generate barcode (additional format)
        // ------------------------------
        rowsGenerator.Save("output/DatabarRows3.jpg", BarCodeImageFormat.Jpeg);
        Console.WriteLine("Saved JPEG version to output/DatabarRows3.jpg");
    }
}
```

**預期輸出：** 執行程式後，`output` 資料夾會包含三個檔案：

* `DatabarCols4.png` – 具有 4 列的條碼（寬）。  
* `DatabarRows3.png` – 具有 3 行的條碼（高）。  
* `DatabarRows3.jpg` – 3 行條碼的 JPEG 版本。

在圖像檢視器中開啟任一 PNG 檔案，您應該會看到清晰的 Databar Expanded Stacked 條碼，已可供掃描。

## 常見問題與疑難排解

| Question | Answer |
|----------|--------|
| *如果圖像模糊怎麼辦？* | 確認您使用 PNG 以獲得無損輸出。若需要 JPEG，請提升品質設定（`new JpegOptions { Quality = 95 }`）。 |
| *我可以更改條碼文字嗎？* | 可以——將 `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Your Text")` 的第二個參數替換為您想要的文字。 |
| *列與行可以同時使用嗎？* | 可以同時設定；只需在呼叫 `Save` 前同時設定 `DataBar.Columns` 與 `DataBar.Rows`。 |
| *目錄深度有上限嗎？* | 路徑必須符合作業系統的規範。使用 `Path.Combine` 可確保跨平台安全。 |

## 結論

您現在已了解如何 **how to set columns** for a Databar Expanded Stacked 條碼、如何 **how to set rows**，以及如何 **how to generate barcode** 圖像，並可將其 **barcode save file** 為 PNG 或 JPEG 格式。完整範例展示了從函式庫安裝到最終檔案驗證的每一步驟。

接下來，您可以探索：

* **how to generate barcode** 搭配 QR Code 的錯誤更正等級。  
* **barcode save file** 的向量格式選項，如 SVG 或 PDF。  
* 將產生的條碼整合至 ASP.NET Core MVC 視圖，以實現動態標籤列印。

隨意嘗試不同的列/行組合、圖像格式與條碼內容，以符合您專案的規格。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [如何產生條碼 – Code 39 設定與 Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [如何產生 Aztec 條碼，使用自訂長寬比，透過 Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}