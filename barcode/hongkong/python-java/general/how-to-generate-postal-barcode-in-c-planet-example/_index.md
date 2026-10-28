---
category: general
date: 2026-10-28
description: 使用 C# 產生 Planet 格式的郵政條碼。此 Planet 條碼範例示範如何設定條碼寬度，並儲存實條與空條。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: zh-hant
lastmod: 2026-10-28
og_description: 使用 C# 產生郵政條碼，提供完整的 Planet 條碼範例。學習設定條碼寬度、產生實心條，以及建立空條圖像。
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: 在 C# 中產生郵政條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中產生郵政條碼 – planet 範例
url: /zh-hant/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生郵政條碼 – Planet 範例

如果您需要在 C# 中產生郵政條碼，本指南將一步步帶您完成完整解決方案。您將看到一個實用的 Planet 條碼範例，能編碼數字字串、設定條碼寬度，並儲存實心與空心條紋圖像。

產生郵政條碼不需要複雜的建置流程。完成本教學後，您即可在任何 .NET 應用程式中整合條碼產生功能、客製化 X‑dimension，並選擇條紋是實心還是空心。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* C# 開發環境（Visual Studio、VS Code 或 Rider）  
* **Aspose.BarCode for .NET** NuGet 套件（版本 23.10 或更新）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

以下程式碼片段假設您已在檔案頂部加入 `using Aspose.BarCode.Generation;`。

## 使用 Planet 符號產生郵政條碼

第一步是建立使用 Planet 符號的 `BarcodeGenerator` 實例。Planet 是多個國家郵政服務使用的郵政條碼格式。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼這很重要：**  
`EncodeTypes.Planet` 告訴函式庫使用 Planet 條碼標準，該標準會將數字資料編碼為一系列條紋與空白。建構子接收您想要編碼的資料字串（此例為 `"123456"`）。

執行程式後，執行檔的工作目錄會產生兩個 PNG 檔案：

* **PostalPlanetFilledBars.png** – 條紋以實心黑色矩形呈現。  
* **PostalPlanetEmptyBars.png** – 條紋以白色矩形加黑色輪廓呈現，適合在深色背景上列印。

## 以像素設定條碼寬度 (X‑dimension)

條碼的視覺大小由 X‑dimension 控制，它定義單一條紋的寬度。調整此值可確保條碼在目標列印解析度下能正確掃描。

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**為什麼要設定它：**  
較大的 X‑dimension 讓低解析度掃描器更容易讀取，而較小的值則可在高密度列印時減少整體圖像大小。預設寬度為 2 像素；4 像素是大多數桌面印表機的常見折衷。

您可以嘗試不同的值：

| 像素 | 常見使用情境 |
|------|--------------|
| 2    | 高密度標籤 |
| 4    | 標準辦公室列印 |
| 6‑8  | 大幅面標示 |

**小技巧：** 改變 X‑dimension 後，務必使用目標掃描器測試產生的條碼。

## Planet 條碼範例 – 實心與空心條紋

Planet 條碼可以以實心（filled）或輪廓（empty）條紋呈現。`FilledBars` 屬性可切換此行為。

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**為什麼可能會選擇空心條紋：**  
空心條紋在深色包裝上可提升對比度，因為每條條紋的白色內部在深色背景下更為顯眼。實心條紋是預設設定，適用於淺色媒介。

**預期輸出：**  

*兩張圖像皆顯示相同的編碼資料（`123456`）。* 唯一的視覺差異在於條紋樣式。以下為文字說明：

* **實心條紋圖像：** 白色背景上垂直的實心黑色條紋。  
* **空心條紋圖像：** 形成相同圖案的黑色輪廓，內部為白色。

您可以使用任何圖像檢視器開啟 PNG 檔案，驗證圖案是否符合 Planet 規範。

## 客製化其他條碼屬性（可選）

上述核心步驟已涵蓋大多數情境，您仍可微調其他設定：

| 屬性 | 說明 | 常見值 |
|------|------|--------|
| `Barcode.Color` | 條紋的前景色 | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | 背景填色 | `System.Drawing.Color.White` |
| `Barcode.CodeText` | 條碼下方顯示的可讀文字 | 與編碼資料相同或自訂標籤 |
| `Barcode.ImageFormat` | 輸出格式（PNG、JPEG、BMP 等） | `BarCodeImageFormat.Png` |

設定自訂前景色的範例：

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

這些可選調整有助於符合企業品牌或特定列印需求。

## 常見陷阱與避免方法

| 問題 | 成因 | 解決方式 |
|------|------|----------|
| 條碼無法辨識 | X‑dimension 對列印機 DPI 而言過小 | 將 `XDimension.Pixels` 提升至 4 或更高 |
| 圖像檔案損毀 | 目標資料夾缺乏寫入權限 | 使用絕對路徑或確保資料夾已存在 |
| 使用錯誤的符號 | 傳入 `EncodeTypes.Code128` 而非 `EncodeTypes.Planet` | 確認 `EncodeTypes` 參數與郵政格式相符 |

**專業小提醒：** 在正式上線前，務必產生測試條碼並使用目標硬體掃描驗證。

## 完整可執行範例

以下是一個自包含的主控台應用程式，整合了所有步驟。將程式碼複製到新的 .NET 主控台專案中，執行後即可在輸出資料夾看到兩個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**驗證步驟：**  

1. 建置專案（`dotnet build`）。  
2. 執行可執行檔（`dotnet run`）。  
3. 在 `bin/Debug/net6.0` 資料夾中找到 `PostalPlanetFilledBars.png` 與 `PostalPlanetEmptyBars.png`。  
4. 開啟每張圖像，您應該會看到一系列垂直條紋，代表該數字字串。

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並探索在專案中實作的其他方式。

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}