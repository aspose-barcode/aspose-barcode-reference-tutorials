---
category: general
date: 2026-09-19
description: C# 條碼產生器範例，示範如何使用 Aspose.BarCode 產生欄列佈局的條碼
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: zh-hant
lastmod: 2026-09-19
og_description: 條碼產生器範例示範如何使用 Aspose.BarCode 於 C# 中產生具欄與列佈局的條碼。
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: 條碼產生器範例 – 使用 C# 建立 DataBar Expanded Stacked 條碼
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 DataBar Expanded Stacked 建立條碼產生器範例
url: /zh-hant/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器範例 – 使用 C# 建立 DataBar Expanded Stacked 條碼

如果您需要一個可在 .NET 專案中使用的 **barcode generator example**，本指南將完整示範如何使用 Aspose.BarCode 函式庫在 C# 中產生條碼。您將看到如何為 DataBar Expanded Stacked 條碼設定欄位式佈局與列式佈局，並取得可直接執行的程式碼產生 PNG 影像。  
本教學涵蓋從安裝 NuGet 套件到儲存最終影像的全部步驟，讓您可以直接將程式碼複製到自己的解決方案中，無需額外搜尋。

## 您將學會

* 如何在 C# 專案中安裝並參考 Aspose.BarCode。  
* 如何建立一個 **barcode generator example**，以編碼長資料字串。  
* 如何在相同條碼類型上設定 4 欄佈局與 3 列佈局。  
* 如何將產生的影像儲存為 PNG 檔案。  

閱讀完本篇文章後，您將擁有兩個可直接使用的 PNG 檔案：`ExpandedStackedCols4.png`（四欄）與 `ExpandedStackedRows3.png`（三列）。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7.2 上執行）。  
* Visual Studio 2022、VS Code，或您偏好的任何 C# IDE。  
* 具備網際網路連線以下載 **Aspose.BarCode** NuGet 套件。  

不需要其他外部服務。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在專案資料夾中開啟終端機，執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新穩定版的 Aspose.BarCode 加入您的專案檔案。套件還原完成後，您即可在 C# 原始碼檔案中引用其命名空間。

## 步驟 2：加入必要的 using 指令

建立一個新的 C# 主控台應用程式（或將程式碼加入現有專案），並在檔案頂部加入以下 `using` 陳述式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些指令讓您能存取在 **barcode generator example** 中使用的 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉。

## 步驟 3：建立具有 4 欄佈局的 barcode generator example

範例的第一部分會建立一個使用四欄排列的 DataBar Expanded Stacked 條碼。以下程式碼遵循原始片段的每一步，同時加入說明每行程式碼必要性的註解。

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**為什麼這樣可行**

* `EncodeTypes.DatabarExpandedStacked` 告訴 Aspose.BarCode 產生 DataBar Expanded Stacked 符號，適用於零售應用。  
* 將 `DataBar.Columns` 設為 `4` 會強制產生器將符號分為四個垂直區段，提升窄標籤的可讀性。  
* `Save` 將條碼寫入磁碟；`BarCodeImageFormat.Png` 參數確保無失真的影像品質。

執行此程式碼塊會在應用程式的工作目錄產生 `ExpandedStackedCols4.png`。該檔案包含高解析度的條碼，可被任何標準 DataBar 讀取器掃描。

## 步驟 4：重新初始化產生器以使用不同佈局

為示範列式佈局，您需要一個全新的 `BarcodeGenerator` 實例。重新初始化可確保先前的欄設定不會影響新配置。

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## 步驟 5：設定條碼使用 3 列佈局

DataBar API 亦支援列排列。設定 `Rows` 屬性即可定義符號包含多少水平切片。

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**為什麼會選擇列而非欄**

當標籤高度受限而寬度充足時，列佈局較為實用。三列佈局可在垂直方向壓縮條碼，同時保留所需的資料量。

## 完整原始檔案

以下是一個完整、獨立的 `Program.cs`，您可直接編譯執行。它同時包含欄與列的範例，僅執行一次即可產生兩個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### 預期輸出

執行程式後，您會在主控台看到兩條訊息，確認檔案已建立：

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

兩個 PNG 檔案皆會顯示編碼字串 `"Long data string"` 的 DataBar Expanded Stacked 條碼。使用標準條碼掃描器掃描任一影像皆會回傳原始資料。

## 常見問題與邊緣情況

| Question | Answer |
|----------|--------|
| **我可以更改影像格式嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Tiff`，依需求而定。 |
| **如果資料字串較短怎麼辦？** | DataBar 格式會自動調整符號大小；您無需變更佈局設定。 |
| **如何設定條碼尺寸（寬度/高度）？** | 在呼叫 `Save` 前，使用 `generator.Parameters.Image.Width` 與 `generator.Parameters.Image.Height`。 |
| **是否可以加入可讀的說明文字？** | 設定 `generator.Parameters.Barcode.CodeText`，並啟用 `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`。 |
| **支援哪些 .NET 版本？** | Aspose.BarCode 支援 .NET Standard 2.0、.NET 5/6 以及 .NET Framework 4.6.1 以上版本。 |

處理上述變化可使 **barcode generator example** 足夠穩健，適合投入生產環境使用。

## 專業提示

* **僅在佈局相同時重複使用產生器物件。** 如步驟 4‑5 所示，為每個佈局建立新實例，可避免屬性意外遺留。  
* **使用 `generator.Validate()` 驗證產生的條碼**，若需確保符合 ISO/GS1 標準。  
* **批次處理：** 將欄與列的邏輯包在迴圈中，遍歷佈局設定清單。當需要多種變化時，可減少程式碼重複。

## 結論

本 **barcode generator example** 示範了如何 **generate barcode C#** 產生同時具備 4 欄與 3 列 DataBar Expanded Stacked 條碼的程式碼。您現在擁有完整可執行的程式、對關鍵屬性（`Columns`、`Rows`）的了解，以及擴充解決方案的實用技巧。  
接下來，您可以探索相關主題，如 **customizing barcode colors**、**embedding barcodes in PDF documents** 或 **generating QR codes with Aspose.BarCode**。這些主題皆基於本篇所涵蓋的相同 API 原則。  
歡迎自行嘗試不同的資料字串、影像格式與佈局組合。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [C# 條碼產生器範例 – 設定欄、列與匯出影像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [使用 .NET API 產生 Aspose.BarCode Databar 條碼 – 列與欄配置](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [C# 條碼產生器範例 – 設定寬度與高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}