---
category: general
date: 2026-07-24
description: 條碼產生器 C# 教學，示範如何產生條碼圖像、設定欄位、設定列數，以及僅用幾行程式碼建立 Databar 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: zh-hant
lastmod: 2026-07-24
og_description: 條碼產生器 C# 教學將一步步帶領您生成條碼圖像、設定欄列，並以清晰的程式碼範例建立 Databar 條碼。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: 條碼產生器 C# – 快速建立 DataBar 堆疊條碼
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 條碼產生器 C# – 建立 DataBar 擴展堆疊圖像
url: /zh-hant/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – DataBar Expanded Stacked 完整指南

有沒有想過如何使用 **barcode generator c#** 在幾秒鐘內產生清晰、可掃描的條碼圖像？或許你曾對著空白專案發呆，不知道欄位（columns）或列（rows）該放在哪裡，甚至不知道該如何 *generate barcode image* 而不頭疼。好消息，你來對地方了。在本教學中，我們會建立一個小型主控台應用程式，產生 DataBar Expanded Stacked 條碼，微調版面配置，並將結果儲存為 PNG——全部使用 **barcode generator c#** 函式庫。

我們會涵蓋所有你需要知道的內容：安裝套件、設定欄位與列（是的，我們會回答 *how to set columns* 與 *how to set rows*），最後示範如何 **create databar barcode** 物件，讓你可以直接放入發票、票券或任何需要機器可讀標籤的地方。無需外部文件，只要複製貼上、執行，即可在資料夾中看到兩個 PNG 檔案。

## What You’ll Need

- .NET 6.0 SDK 或更新版本（程式碼同樣支援 .NET Core、.NET Framework 與 .NET 5+）
- 全新主控台專案 (`dotnet new console`) – 若喜歡圖形介面，也可以使用 Visual Studio。
- Aspose.BarCode for .NET NuGet 套件（即 **barcode generator c#** 背後的函式庫）。使用以下指令安裝：

```bash
dotnet add package Aspose.BarCode
```

就這樣。套件還原完成後即可開始。

## Barcode Generator C# – Setting Up the Project

首先，將必要的命名空間匯入，並建立一個輔助方法，以保持主程式的簡潔。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Why This Structure Works

- **Separation of concerns** – 每個輔助方法只負責單一設定（欄位或列），讓程式碼更易讀、易重用。
- **Explicit parameters** – 以參數 `columns` 或 `rows` 傳入，無需修改方法本體即可使用不同數值。
- **Immediate feedback** – `Console.WriteLine` 會告訴你檔案到底儲存到哪裡，對於在終端機執行時特別方便。

## How to Set Columns for DataBar Expanded Stacked

`DataBar.Columns` 屬性就是決定條碼垂直切片數量的旋鈕。預設值為 `4`，但依據編碼資料量或掃描器需求，你可能需要 `2` 或 `6`。以下是僅示範欄位設定的程式片段：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** 增加欄位數會使條碼整體寬度等比例成長。若要將圖像嵌入 PDF 或網頁，請確保容器能容納額外寬度，否則掃描器可能讀取錯誤。

## How to Set Rows for DataBar Expanded Stacked

列的設定方式相同，只是會影響條碼的高度。預設列數為 `3`。若標籤的垂直空間受限，可降至 `2`。相反地，更多列數在低解析度印表機上可提升可讀性。

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** 若將列數設定為低於編碼資料所需的最小值，執行時會拋出例外。函式庫會拋出 `ArgumentException` 並附上清楚訊息，讓你立即知道設定無效。

## Generate Barcode Image – Saving as PNG

上述兩個輔助方法最終皆呼叫 `Save`。`BarCodeImageFormat.Png` 列舉值告訴 Aspose.BarCode 輸出無損 PNG 檔，這是大多數掃描情境的理想選擇，因為它能保留銳利邊緣。若想改用其他格式（如 JPEG 用於網頁、BMP 用於舊系統），只要換掉列舉值即可，其他程式碼不需變動。

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

產生的 PNG 會長這樣（請想像圖像，以下為替代文字說明）：

> **Alt text for the generated images:** *DataBar Expanded Stacked 條碼，左側為 4 欄，右側為 3 列，呈現高對比黑色於透明背景上。*

## Create DataBar Barcode – Full Working Example

把所有步驟整合起來，以下是一個可直接貼入 `Program.cs` 的精簡範例。它示範了欄位與列的設定，並在儲存後快速檢查檔案是否存在。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Expected Output

執行程式 (`dotnet run`) 後，應該會在主控台看到類似以下的訊息：

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

在任何影像檢視器開啟兩個 PNG 檔案，你會發現左側檔案有四個垂直模組（欄位），右側檔案則是三個垂直模組（列）。兩者皆可被標準 DataBar 讀取器順利掃描。

## Common Pitfalls & How to Avoid Them

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | 欄位設定為 0 或大於 8（函式庫上限為 8） | 請使用 **1** 至 **8** 之間的數值 |
| 條碼在 PDF 中顯示模糊 | PNG 以預設 DPI（96）儲存後被放大 | 在儲存前加入 `generator.Parameters.ImageResolution = 300;` |
| 掃描器在僅設定列時失敗 | 列已變更但欄位仍保留預設值，導致與資料長度不符 | 同時調整列與欄，或省略手動設定讓函式庫自動調整尺寸 |

## Next Steps

現在你已掌握 **generate barcode image**、**set columns**、**set rows** 與 **create databar barcode** 的技巧，接下來可以：

- 使用 `Aspose.PDF` 或 `iTextSharp` 把 PNG 嵌入 PDF。
- 若需要更小的佔用空間，可改用 `EncodeTypes.DatabarLimited`。
- 嘗試顏色設定，例如 `generator.Parameters.Barcode.ForeColor = Color.Blue`。
- 在同一專案中加入 QR Code 或其他符號——Aspose.BarCode 支援超過 150 種條碼類型。

如有任何問題，歡迎在下方留言或參考官方 Aspose.BarCode 文件（API 參考相當完整，且提供大量即時範例程式碼）。祝開發順利，願你的掃描器永不錯過任何標記！

## What Should You Learn Next?

以下教學與本指南緊密相關，能幫助你進一步掌握 API 功能並探索其他實作方式：

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}