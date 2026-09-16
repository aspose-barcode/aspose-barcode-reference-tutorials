---
category: general
date: 2026-09-16
description: 了解如何設定寬度、如何製作空白條，以及在使用 Aspose.BarCode 產生 Planet 條碼時如何填充條。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: zh-hant
lastmod: 2026-09-16
og_description: 如何在使用 Aspose.BarCode 生成 Planet 條碼時設定寬度、製作空白條與填充條——完整的逐步指南。
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: 如何在 C# 中設定寬度並產生 Planet 條碼
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何設定寬度並在 C# 中產生 Planet 條碼
url: /zh-hant/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定寬度並在 C# 中產生 Planet 條碼

如果您需要 **設定寬度** 以產生 Planet 條碼，本指南將展示完整流程。您還會看到 **如何製作空白** 條、**如何填充條**，以及使用 Aspose.BarCode for .NET **產生 Planet 條碼** 的確切步驟。

在建立郵寄標籤應用程式或郵務服務整合時，產生郵件樣式的 Planet 條碼是常見需求。完成本教學後，您將擁有一個可直接執行的主控台程式，能同時產生實心條圖像與空白條圖像，兩者皆使用相同的資料字串。

## 前置條件

- .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 執行）
- Visual Studio 2022 或任何相容 C# 的 IDE
- Aspose.BarCode for .NET NuGet 套件 (`Aspose.BarCode`)  
  安裝方式如下：

```bash
dotnet add package Aspose.BarCode
```

不需要額外的設定；此函式庫會在內部處理影像編碼。

## 步驟 1：建立主控台專案並加入函式庫

在終端機中執行以下指令：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

這會建立一個 `Program.cs` 檔案，我們將在其中撰寫條碼邏輯。

## 步驟 2：撰寫程式碼 – 設定寬度並產生 Planet 條碼

開啟 `Program.cs`，並將其內容取代為以下完整範例：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### 為何每個步驟都很重要

- **設定寬度**：`XDimension.Pixels` 屬性直接影響每條條碼的實體大小。選擇 2 到 6 像素之間的值，可在螢幕可讀性與列印品質之間取得平衡。
- **製作空白條**：將 `FilledBars = false` 設為 false，會讓產生器僅繪製條碼的輪廓。此樣式適用於「亮字在暗底」列印，或希望保留紙張紋理的情況。
- **填充條**：預設的 `FilledBars = true` 會產生實心黑條，這是大多數郵件掃描器的標準。
- **產生 Planet 條碼**：使用 `EncodeTypes.Planet` 會選擇美國郵政服務 (USPS) 所要求的 Planet 條碼特定編碼。

## 步驟 3：建置並執行程式

在專案資料夾中執行以下指令：

```bash
dotnet run
```

您應該會看到類似以下的主控台輸出：

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

兩個 PNG 檔案會出現在專案目錄中：

- `PostalPlanetFilledBars.png` – 實心黑條（預設樣式）
- `PostalPlanetEmptyBars.png` – 條碼輪廓（空白樣式）

使用任何影像檢視器開啟它們，以驗證條寬符合 4 像素設定，且空白版本顯示未填充的條。

## 常見問題與邊緣情況

| Question | Answer |
|----------|--------|
| *我可以使用其他影像格式嗎？* | 可以。依需求將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。 |
| *如果條碼寬度超過標籤範圍怎麼辦？* | 將 `XDimension.Pixels` 降低（例如調整為 `2`），或提升標籤印表機的模組寬度。 |
| *我需要手動設定 `Height` 嗎？* | 函式庫會根據編碼自動計算高度。若需自行設定，可使用 `Parameters.Barcode.BarHeight` 覆寫。 |
| *所有印表機都支援空白條樣式嗎？* | 大多數現代熱感印表機皆支援實心與空白兩種樣式，但若使用舊版設備，請先進行測試列印以確認。 |
| *如何在條碼下方加入可讀文字說明？* | 使用 `Parameters.Caption` 來啟用並設定說明文字；將 `CaptionAbove` 設為 `false` 即可將說明放在條碼下方。 |

## 專業技巧

- **重複使用相同的產生器** 僅在所有參數保持一致時才可。儲存後再變更 `FilledBars` 不會影響已儲存的影像，因此如範例所示重新實例化可確保從乾淨的狀態開始。
- **批次產生**：將程式碼包在迴圈中，於每次迭代更改 `data`，即可為大量郵寄產生一系列 Planet 條碼。
- **效能**：若需產生數千條條碼，建議只建立一個 `BarcodeGenerator` 實例，依需求調整 `XDimension` 與 `FilledBars`，並重複使用該物件以減少記憶體配置。

## 結論

您現在已了解 **如何設定寬度**、**如何製作空白條**、**如何填充條**，以及使用 Aspose.BarCode 在 C# 中 **產生 Planet 條碼** 的完整步驟。此完整且可執行的範例會產生實心條與空白條的 PNG 檔案，隨時可整合至任何郵寄標籤工作流程。

接下來，您可以探索相關主題，例如 **如何在同一標籤上加入 QR Code**、**自訂條碼顏色**，或 **將條碼嵌入 PDF 文件**。上述皆建立在本教學所涵蓋的相同基礎上。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此技術為基礎。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [在 C# 中建立 Planet 條碼影像 – 如何產生郵件條碼](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [如何在 Java 中建立帶空白條的 Code128 條碼](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [如何在 Java 中使用 Aspose.BarCode 產生條碼影像](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}