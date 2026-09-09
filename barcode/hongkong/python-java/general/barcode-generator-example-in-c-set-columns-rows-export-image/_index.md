---
category: general
date: 2026-07-15
description: C# 條碼產生器範例，示範如何設定欄位、設定列，並快速匯出條碼影像。請依照此步驟指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: zh-hant
lastmod: 2026-07-15
og_description: C# 條碼產生器範例示範如何設定欄位、設定列以及匯出條碼圖像。只需數分鐘即可了解完整工作流程。
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: C# 條碼產生器範例 – 欄、列與圖像匯出
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: C# 條碼產生器範例 – 設定欄、列及匯出圖像
url: /zh-hant/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 條碼產生器範例 – 完整教學

有沒有想過如何在 C# 中建立 **barcode generator example**，讓你可以調整欄位、列，然後將結果匯出為影像？你並不孤單。許多開發者在需要快速產生支援自訂版面配置的 DataBar Expanded Stacked 條碼時，常會卡住。於本教學中，我們將一步一步解決此問題，示範 **how to set columns**、**how to set rows**，最後 **export barcode image** 檔案——全部使用乾淨、可投入生產的程式碼。

完成本指南後，你將擁有一個完整、可執行的程式，能產生條碼影像、調整版面，並將兩個 PNG 檔案儲存至磁碟。沒有神祕的函式庫，沒有隱藏的設定——只有純粹的 C# 與可靠的 barcode SDK。

---

## 先決條件

在開始之前，請確保你具備以下條件：

- **.NET 6.0**（或任何較新 .NET 版本）。此程式碼亦可在 .NET Framework 上編譯，但 .NET 6+ 提供最新的執行時改進。
- 一個支援 DataBar Expanded Stacked 的 **barcode generation library**。在範例中，我們將使用 **Aspose.BarCode for .NET**，它提供免費試用且 API 簡潔易用。
- 開發環境—Visual Studio 2022、Rider 或 VS Code 均可。
- 對將儲存 PNG 檔案的資料夾具寫入權限。

如果尚未取得此函式庫，請從 NuGet 取得：

```bash
dotnet add package Aspose.BarCode
```

那一行指令會把所有必需的套件拉下來，包含稍後會用到的 `BarcodeGenerator` 類別與 `BarCodeImageFormat` 列舉。

---

## 步驟 1：建立專案骨架

建立一個新的主控台應用程式，並加入必要的 `using` 指示詞：

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

以下是 **完整** 的 `Program.cs` 檔案骨架：

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** 保持 `Main` 方法簡潔；稍後我們會將繁重的工作交給輔助方法。這樣可讓程式碼更易於測試與重用。

---

## 步驟 2：建立 Barcode Generator Example

現在我們將構建核心的 **barcode generator example**，用以產生 DataBar Expanded Stacked 條碼。這是本教學的核心。

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

為什麼要將它拆成獨立方法？這樣可將 **barcode generator example** 的邏輯隔離，若日後需要以不同資料產生多個條碼時，可重複使用。

---

## 步驟 3：設定欄位

DataBar Expanded Stacked 格式可以以欄位導向的版面呈現。預設情況下 SDK 會選擇合適的值，但你常需要配合特定的標籤尺寸。以下示範 **how to set columns** 為四欄：

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Why columns matter:** 每個欄位會增加垂直空間，對於在窄標籤上列印時可能相當關鍵。將其設定為 `4` 可取得平衡且易讀的條碼，同時不影響掃描可靠性。

在主流程中我們會呼叫此方法：

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## 步驟 4：設定列

有時你需要更緊湊的版面，特別是列印在短而寬的標籤上。這時 **how to set rows** 就派上用場。從欄位導向切換至列導向的配置，可縮小條碼佔用的空間。

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

呼叫方式如下：

```csharp
SetRows(generator, 3);
```

> **Edge case note:** 不能同時設定欄位 *與* 列——若對 `Rows` 指定非零值，SDK 會優先使用列。因此在切換版面時，請確保將另一屬性清為 `0`：

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## 步驟 5：匯出條碼影像

版面配置完成後，最後一步是 **export barcode image** 檔案。SDK 支援 PNG、JPEG、BMP 等格式。PNG 為無損格式，適用於大多數標籤印表機。

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

將所有程式碼整合於 `Main`：

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### 預期輸出

執行程式後，你應該會在 `YOUR_DIRECTORY` 中看到兩個 PNG 檔案：

- **DatabarCols4.png** – 以四個垂直欄位呈現的條碼。
- **DatabarRows3.png** – 相同資料，但以三個水平列排列。

兩張影像皆為 300 × 150 px（依 `CreateGenerator` 設定），可直接列印或嵌入 PDF 中。

---

## 常見問題與技巧

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **File path errors** | 使用未指向正確目錄的相對路徑可能拋出 `DirectoryNotFoundException`。 | 使用 `Path.Combine(Environment.CurrentDirectory, "output", "file.png")`，或確保資料夾已存在（使用 `Directory.CreateDirectory`）。 |
| **Rows vs. Columns conflict** | 同時設定兩個屬性會導致 SDK 忽略欄位設定。 | 切換版面時，請明確將另一屬性設為 `0`。 |
| **Unsupported barcode type** | 並非所有條碼函式庫都支援 DataBar Expanded Stacked。 | 確認你的函式庫版本包含 `EncodeTypes.DatabarExpandedStacked`。 |
| **Image quality too low** | 預設 DPI 可能不足以應付高解析度印表機。 | 將 `generator.Parameters.Image.ResolutionX/Y` 調整為 `300` 或更高。 |

---

## 擴充 Barcode Generator Example

現在你已擁有完整的 **barcode generator example**，或許會想知道還能做什麼。

1. **Add colors** – 將 `generator.Parameters.Barcode.ForegroundColor` 設為 `Color.Blue`。
2. **Encode different data** – 傳入變數字串，而非硬編碼的 `"Databar Expanded Stacked long"`。
3. **Batch processing** – 迭代產品代碼的 CSV 檔案，為每筆產生 PNG。
4. **Integrate with a web API** – 提供一個端點，回傳條碼的 base64 編碼字串。

上述每個擴充功能皆遵循相同模式：先設定 `BarcodeGenerator` 實例，然後依需求呼叫 `Save` 或 `Export`。

---

## 結論

我們已完整示範了 C# 的 **barcode generator example**，說明 **how to set columns**、**how to set rows**，以及 **export barcode image** 檔案的作法。程式碼自給自足，使用 Aspose.BarCode 即可直接執行，並展示了可讀性與可維護性的最佳實踐。

歡迎自行嘗試——更換資料字串、調整影像尺寸，或改用其他條碼符號。此處學到的概念——初始化產生器、設定版面參數與匯出——幾乎適用於 SDK 支援的所有條碼類型。

對於建立 barcode image C# 程式有任何疑問，或需要特定標籤印表機的協助嗎？歡迎在下方留言，祝開發愉快！

---

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技術。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索替代實作方式。

- [建立 DotCode 條碼影像 – 列與欄 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [建立條碼影像 C# – 設定 Codablock F 列與欄](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [建立條碼影像 C# – GS1 DataMatrix 範例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}