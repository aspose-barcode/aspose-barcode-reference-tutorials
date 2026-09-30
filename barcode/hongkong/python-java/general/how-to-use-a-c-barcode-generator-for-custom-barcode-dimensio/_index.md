---
category: general
date: 2026-08-22
description: 了解如何使用 C# 條碼產生器變更條碼大小、調整尺寸，並在 DataBar Expanded Stacked 條碼中產生多列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: zh-hant
lastmod: 2026-08-22
og_description: C# 條碼產生器教學，示範如何更改條碼大小、調整尺寸，並使用自訂設定產生多行條碼。
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: C# 條碼產生器指南 – 變更大小、行與列
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何使用 C# 條碼產生器自訂條碼尺寸
url: /zh-hant/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 條碼產生器自訂條碼尺寸

如果你需要一個 **c# barcode generator** 能即時 **變更條碼尺寸**，本指南將一步步說明。 我們會產生 DataBar Expanded Stacked 條碼，透過設定自訂的欄與列來調整寬度與高度，並儲存三個範例圖像。

完成本教學後，你將得到一個完整、可執行的主控台程式，示範 **custom barcode dimensions**、**generate barcode multiple rows** 以及 **adjust barcode dimensions**，且全程不離開 IDE。

## 你需要的條件

| 先決條件 | 原因說明 |
|--------------|----------------|
| .NET 6.0 SDK or later | 提供主控台應用程式的執行環境 |
| Visual Studio 2022 (or VS Code) | 提供具備 IntelliSense 的編輯器 |
| Aspose.Barcode for .NET NuGet package | 提供範例中使用的 `BarcodeGenerator` 類別 |
| Write permission to a folder on disk | 產生器會將 PNG 檔案儲存至此位置 |

使用 NuGet CLI 安裝函式庫：

```bash
dotnet add package Aspose.Barcode
```

或使用 Visual Studio 套件管理員：

```powershell
Install-Package Aspose.Barcode
```

## 步驟 1：建立基本的 C# 條碼產生器

建立一個新的主控台專案並加入必要的 `using` 指令。此步驟會建立一個最小的 **c# barcode generator**，能輸出簡單的 DataBar Expanded Stacked 條碼。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**為什麼這樣可行：** `EncodeTypes.DatabarExpandedStacked` 告訴產生器使用哪種符號。`Save` 方法會將 PNG 檔寫入磁碟。此時條碼使用的是函式庫的預設尺寸。

## 步驟 2：透過調整 columns 變更條碼尺寸

DataBar Expanded Stacked 條碼的寬度由 **columns** 屬性控制。設定此屬性即可讓 **c# barcode generator** 產生較寬或較窄的條碼。

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**說明：** Columns 會影響水平模組數量。欄位越多條碼越寬闊，這在需要為較長的可讀文字留出空間或在寬標籤上列印時特別有用。

## 步驟 3：產生多列條碼以控制高度

高度由 **rows** 屬性決定。透過增加 rows，你可以 **generate barcode multiple rows**，使符號變高——適合高解析度掃描。

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**為什麼 rows 重要：** Rows 會增加垂直模組。較高的條碼在低對比度背景或掃描器焦距變化時，可提升可讀性。

## 步驟 4：結合自訂 columns 與 rows 以完整控制

既然你已了解如何 **adjust barcode dimensions**，現在可以同時設定兩個屬性。此步驟會產生一個具有六個 columns 與十個 rows 的條碼，展示 **c# barcode generator** 的完整彈性。

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**結果：** 檔案 `DatabarCols6Rows10.png` 包含的條碼比預設更寬且更高，證明你可以 **adjust barcode dimensions** 以符合任何版面需求。

## 完整可執行範例

以下為結合所有四個步驟的完整程式。將其複製到 `Program.cs`，執行 `dotnet run`，然後檢查 `C:\Temp\Barcodes\` 資料夾，即可看到四個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### 預期輸出

執行程式會產生四個 PNG 檔案：

| File name                | Visual description |
|--------------------------|--------------------|
| `DefaultDatabar.png`     | 標準寬度與高度 |
| `DatabarCols4.png`       | 較寬條碼（4 個 columns） |
| `DatabarRows3.png`       | 較高條碼（3 個 rows） |
| `DatabarCols6Rows10.png` | 同時較寬與較高（6 個 columns，10 個 rows） |

在影像檢視器中開啟任一 PNG，即可看到 DataBar Expanded Stacked 圖樣已依指定精確調整。

## 常見陷阱與專業提示

- **Invalid column/row values** – 若設定的值超出支援範圍（columns 為 1‑12，rows 為 1‑10），函式庫會拋出 `ArgumentException`。請在指派前先驗證輸入。
- **Directory permissions** – 若輸出資料夾受保護，`Save` 會失敗。可如範例所示使用 `System.IO.Directory.CreateDirectory` 以確保路徑存在。
- **Performance** – 在迴圈中大量產生條碼會消耗 CPU。重複使用同一個 `BarcodeGenerator` 實例，僅在儲存之間修改 `Columns`/`Rows`，以減少物件分配開銷。
- **Scanning considerations** – 過高或過寬的條碼可能超出掃描器視野。調整尺寸後，請以目標硬體進行測試。

## 結論

現在你已擁有一個完整的 **c# barcode generator** 範例，能 **change barcode size**、**custom barcode dimensions**、**generate barcode multiple rows**，以及 **adjust barcode dimensions**，以符合任何應用。透過調整 `Columns` 與 `Rows` 屬性，你可以精確控制 DataBar Expanded Stacked 條碼的視覺佔位。

歡迎嘗試其他符號系統（`EncodeTypes.QR`、`EncodeTypes.Code128`）或輸出格式（`BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Svg`）。相同的模式——建立 `BarcodeGenerator`、設定尺寸屬性，然後呼叫 `Save`——在整個 Aspose.Barcode API 中皆適用。

**下一步**

- 探索 QR 代碼的 **error correction levels**。
- 結合 **custom colors** 與 **background images** 以打造品牌條碼。
- 將產生器整合至 ASP.NET Core 網路服務，以實現即時條碼產生。

祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何調整條碼尺寸 – 使用 Aspose.BarCode for .NET 的 Codablock F 長寬比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}