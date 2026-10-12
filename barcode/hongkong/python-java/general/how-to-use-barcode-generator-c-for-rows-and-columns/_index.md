---
category: general
date: 2026-09-26
description: 條碼產生器 C# 指南說明在 C# 中建立 Databar Expanded Stacked 條碼時，如何設定行與欄。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: zh-hant
lastmod: 2026-09-26
og_description: 條碼產生器 C# 教學說明如何設定 Databar Expanded Stacked 條碼的列與欄，提供完整程式碼與技巧。
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: 條碼產生器 C# – 逐步設定行與列
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: 如何在 C# 中使用條碼產生器處理列與欄
url: /zh-hant/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 barcode generator 設定列與欄

如果您需要一個 **barcode generator C#**，讓您能控制 Databar Expanded Stacked 條碼的視覺佈局，本教學提供完整、可執行的解決方案。您將學習 **如何設定列** 以及 **如何設定欄**，使產生的圖像符合您所需的精確設計。

以程式方式產生條碼常常感覺像在猜測哪個屬性負責什麼。閱讀完本指南後，您將了解 API 的使用方式，避免常見的陷阱，並擁有一個可直接複製到自己專案的即用程式碼範例。

## 前置條件

* 安裝 .NET 6.0 或更新版本（此程式碼同樣適用於 .NET Core 與 .NET Framework）
* 參考提供 `BarcodeGenerator` 與 `EncodeTypes` 的條碼產生函式庫（例如 Aspose.BarCode、Dynamsoft，或任何相容的 SDK）
* 使用 Visual Studio 或 VS Code 等開發環境 (IDE)
* 具備寫入 PNG 檔案之資料夾的寫入權限

除了條碼 SDK 本身外，無需額外的 NuGet 套件。

## barcode generator C# – 設定列與欄

以下各節將逐步說明每個設定步驟。程式碼片段完整，可直接貼入 console 應用程式的 `Main` 方法中。

### 步驟 1：為 Databar Expanded Stacked 條碼建立產生器

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*為什麼重要：* 實例化 `BarcodeGenerator` 是任何 **barcode generator C#** 工作流程的第一步。建構子會接收編碼類型與將被編碼的資料字串。

### 步驟 2：設定欄 – 將條碼配置為使用 4 欄

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

設定 `Columns` 屬性會改變 DataBar 使用的垂直模組數量。`4` 的值會產生較密集、較緊湊的條碼，適用於水平空間受限的情況。

### 步驟 3：以欄設定儲存條碼影像

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

`Save` 方法會將產生的影像寫入磁碟。請檢查輸出檔案，以確認四欄佈局如預期顯示。

![Barcode generator C# example showing rows and columns settings](./images/barcode-rows-columns.png)

*上圖說明了欄設定的結果。*

### 步驟 4：重新初始化產生器以使用不同佈局

當您需要另一個具有不同視覺排列的條碼時，請建立新實例，而非重複使用先前的物件。這可確保先前的設定（如欄）不會滲入新的配置中。

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### 步驟 5：設定列 – 將條碼配置為使用 3 列

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

`Rows` 屬性控制 DataBar 模組的垂直堆疊。三列佈局是許多掃描設備的預設，但您可以增加列數以提升資料密度。

### 步驟 6：儲存包含列設定的條碼影像

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

開啟 `DatabarRows3.png` 以查看三列排列。如果條碼無法掃描，請再次核對列/欄值是否符合掃描器的規格。

## 完整原始碼 – 可直接複製

以下為結合上述所有步驟的完整程式。請將 `YOUR_DIRECTORY` 替換為您機器上存在的絕對或相對路徑。

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### 預期輸出

執行程式會產生兩個 PNG 檔案：

| File name            | Layout description                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked with **4 columns** |
| `DatabarRows3.png`   | Databar Expanded Stacked with **3 rows**    |

兩張影像均應可被支援 Databar Expanded Stacked 符號的標準條碼閱讀器掃描。

## 常見陷阱與專業提示

| 陷阱                              | 發生原因                               | 修正／提示 |
|----------------------------------|----------------------------------------|-----------|
| 同時使用相同的 `BarcodeGenerator` 實例設定列與欄 | SDK 會保留先前的設定，於欄之後再設定列可能產生意外的混合結果 | 在變更另一維度前，請重新初始化產生器（如步驟 4 所示） |
| 未正確設定 `EncodeTypes`          | SDK 會預設為其他符號，導致條碼無效          | 在需要此特定格式時，務必傳入 `EncodeTypes.DatabarExpandedStacked` |
| 儲存至不存在的資料夾               | `Save` 會在路徑無效時拋出例外               | 確保 `YOUR_DIRECTORY` 已存在，或在呼叫 `Save` 前使用 `Directory.CreateDirectory` |
| 使用超出允許範圍的值（例如 0 欄）   | SDK 會驗證範圍並拋出 `ArgumentOutOfRangeException` | 此符號的有效欄值為 1‑4；有效列值為 1‑3 |

### 專業提示

如果您需要產生大量列與欄不同的條碼，請將設定邏輯封裝於輔助方法中：

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

此做法可減少重複程式碼，讓程式更易於維護。

## 結論

您現在已掌握使用 **barcode generator C#** 來同時控制 Databar Expanded Stacked 條碼之列數與欄數的完整範例。依循上述步驟，即可產生符合掃描硬體精確佈局需求的條碼影像。

接下來您可以探索：

* 調整其他 `DataBar` 屬性，例如 **AspectRatio** 或 **BarHeight**
* 使用相同的 `BarcodeGenerator` 類別產生其他符號（例如 QR、Code128）
* 將產生的 PNG 嵌入 PDF，或直接從 C# 列印

歡迎嘗試不同的列/欄組合，並在留言區分享您的成果。祝編程愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何為 Databar Expanded Stacked 條碼設定欄 – 完整 C# 教學](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked 條碼指南 – 如何在 C# 中產生與調整大小](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator 範例（C#） – 設定欄、列與匯出影像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}