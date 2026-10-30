---
category: general
date: 2026-10-28
description: 快速在 C# 中建立條碼圖片。學習條碼產生器 C# 使用方法、如何設定像素大小，以及如何調整 DataBar 的長寬比。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: zh-hant
lastmod: 2026-10-28
og_description: 使用條碼產生器在 C# 中建立條碼圖像。按照本指南設定像素大小、調整長寬比，並產生 DataBar 條碼。
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: 在 C# 中建立條碼圖像 – 步驟教學
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: 如何使用條碼產生器在 C# 中建立條碼圖像
url: /zh-hant/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Barcode Generator 於 C# 建立條碼影像

如果您需要在 .NET 應用程式中 **建立條碼影像**，本教學將一步步示範。您將看到完整、可執行的範例，使用 Barcode Generator C# 函式庫產生 DataBar stacked omnidirectional 條碼、設定像素大小，並變更長寬比。

以程式方式產生條碼可免除外部工具，並能直接將影像嵌入 PDF、報表或 UI 控制項。以下步驟同時說明 **如何設定像素大小** 以及 **如何變更長寬比**，這兩項是需要清晰、正確比例條碼時的常見需求。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* 支援 C# 的 IDE（Visual Studio、Rider 或 VS Code）  
* 已在專案中安裝 `BarcodeGenerator` NuGet 套件（例如 `GroupDocs.Barcode` 或 `Aspose.Barcode`）  

您可以使用以下指令加入套件：

```bash
dotnet add package GroupDocs.Barcode
```

> **小技巧：** 請確認套件版本與目標框架相符，以免執行時發生相容性問題。

## 使用 Barcode Generator C# 建立條碼影像

第一步是以欲使用的條碼類型與資料建立產生器。以下範例會產生 **DataBar stacked omnidirectional** 條碼，這是零售掃描情境的理想選擇。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 為何每一行都很重要

* **實例化 `BarcodeGenerator`** – 建構子接受條碼符號 (`EncodeTypes.DatabarStackedOmniDirectional`) 與原始資料字串。選對符號才能讓掃描器正確讀取。  
* **設定 `XDimension.Pixels`** – 此屬性控制最小條紋的寬度。設定為 `2` 時，可產生細緻的影像，且在大多數螢幕上仍保持可讀性。若需在低解析度印表機上印出較大的條碼，可將數值調高。  
* **配置 `AspectRatio`** – DataBar 系列支援多種長寬比，會影響高度與寬度的比例。常見值為 `15` 與 `30`；`15` 產生較短的條碼，`30` 則較高。  
* **`Save` 方法** – 將產生的條碼存為 PNG 檔。若下游系統需要其他格式，可將 `BarCodeImageFormat.Png` 換成 `Jpeg` 或 `Bmp`。

## 如何為不同渲染情境設定像素大小

像素大小決定條碼的視覺密度。若條碼要在高 DPI 螢幕上顯示，可將像素大小提升至 `3` 或 `4`。相反地，對於低解析度熱感印表機，較小的像素大小（例如 `1`）可減少墨水使用量。

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**邊緣情況：** 將像素大小設定低於 `1` 會拋出 `ArgumentOutOfRangeException`。請務必在指派前驗證數值。

## 如何在不重新建立產生器的情況下變更長寬比

變更長寬比只需要更新屬性；**不必** 重新建立 `BarcodeGenerator` 實例。這樣可節省記憶體並提升在需要多種形狀影像時的效能。

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

若需要超過兩種長寬比，可使用陣列迴圈：

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## 預期輸出

執行程式後會產生兩個 PNG 檔（若使用迴圈則會更多）。用任何影像檢視器開啟，您應該會看到清晰的 DataBar 條碼：

* **DatabarAspectRatio15.png** – 短且寬的條碼，適合狹窄標籤空間。  
* **DatabarAspectRatio30.png** – 較高的條碼，可提升斜角掃描器的掃描可靠度。

兩張影像的像素大小皆為 2 px per module，唯一差異在於高度，示範了 **如何在保持其他參數不變的情況下變更長寬比**。

## 常見陷阱與避免方式

| 症狀 | 原因 | 解決方式 |
|------|------|----------|
| 條碼模糊不清 | `XDimension.Pixels` 設定過低，無法符合輸出解析度 | 將像素大小提升至至少 `2`（螢幕顯示）或 `3`（列印） |
| 掃描器無法讀取 | 使用了錯誤的 `EncodeTypes` 符號 | 確認 GTIN‑14 資料與所選符號相符 |
| 設定長寬比時拋出 `ArgumentOutOfRangeException` | 長寬比值不在函式庫支援範圍（有效範圍：15‑30） | 僅使用文件中列出的值，或捕捉例外並回退至預設值 |
| `Save` 後找不到檔案 | 相對路徑指向不存在的目錄 | 改用絕對路徑或先呼叫 `Directory.CreateDirectory` 建立目錄 |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## 往後的步驟 – 延伸條碼工作流程

現在您已能 **建立條碼影像**，接下來可以考慮：

* 使用 `PdfSharp` 或 `iTextSharp` 等函式庫 **將 PNG 嵌入 PDF**。  
* 透過變更 `EncodeTypes` 列舉，**產生其他符號**（QR、Code128、PDF417）。  
* 透過 `barcode.Parameters.Barcode.Image.Color` **套用顏色變換**。  
* 在 ASP.NET Core 端點上 **即時產生影像**，供 Web 應用程式使用。

上述主題皆建立在本教學的核心概念之上，包括 **barcode generator c#** 的使用、像素大小控制與長寬比調整。

## 結論

您現在已掌握如何在 C# 中使用 Barcode Generator **建立條碼影像**、設定像素大小、變更長寬比，並有效產生 DataBar 條碼。完整、可執行的範例可直接複製到任何 .NET 專案，依需求改為其他符號或擴充至實務工作流程。

歡迎嘗試不同的 `XDimension`、長寬比與輸出格式。若遇到問題，請回顧「常見陷阱」表格或參考函式庫官方文件以取得更深入的設定說明。祝開發順利！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索其他實作方式。

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}