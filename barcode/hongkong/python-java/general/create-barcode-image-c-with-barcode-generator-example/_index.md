---
category: general
date: 2026-09-10
description: 使用條碼產生器示例 C#，快速建立條碼圖片，示範如何設定尺寸並儲存為 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: zh-hant
lastmod: 2026-09-10
og_description: 使用簡潔的條碼產生器範例 C# 生成條碼圖像，學習在幾分鐘內設定尺寸與高度，並匯出 PNG 檔案。
og_image_alt: Screenshot of a barcode image created with C# code
og_title: C# 建立條碼圖像 – 步驟式產生器範例
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 使用條碼產生器範例在 C# 中建立條碼圖像
url: /zh-hant/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用條碼產生器範例在 C# 中建立條碼影像

如果您需要 **在 C# 中建立條碼影像** 以供產品標籤、庫存追蹤或行動掃描使用，本教學將示範完整解決方案。您將看到一個 **條碼產生器範例 C#**，只需幾行程式碼即可設定模組寬度、條碼高度，並將 PNG 檔案儲存下來。

本教學涵蓋從安裝必要函式庫到執行可直接編譯的主控台程式的全部步驟。完成後，您將得到兩個條碼 PNG 檔案——一個條碼高度為 30 像素，另一個為 60 像素——可在任何 .NET 應用程式中使用。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* 如 Visual Studio 2022 或 VS Code 等開發環境  
* **Aspose.BarCode** NuGet 套件（程式碼使用此函式庫的 `BarcodeGenerator`）  

您可以使用以下 CLI 指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：建立主控台專案

建立一個新的主控台專案並參考條碼函式庫。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

此指令會產生 `Program.cs` 檔案，您將在其中放入 **條碼產生器範例 C#** 程式碼。

## 第二步：撰寫完整的條碼產生程式

將 `Program.cs` 的內容取代為下方可直接執行的完整範例。程式示範如何 **在 C# 中建立條碼影像**，自訂尺寸並將結果儲存為 PNG 檔案。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 為什麼每一行都很重要

* **EncodeTypes.DatabarOmniDirectional** – 選擇 DataBar Omnidirectional 符號，能編碼數字資料，且在零售業廣泛使用。  
* **XDimension.Pixels = 2** – 設定模組寬度；數值越小條碼越緊湊。  
* **BarHeight.Pixels** – 控制條碼的視覺高度。調整此值即可產生符合不同標籤尺寸的條碼。  
* **Save 方法** – 將條碼寫入 PNG 檔案，該格式保留銳利邊緣，且相容大多數影像函式庫。

## 第三步：建置並執行程式

在專案資料夾中執行以下指令：

```bash
dotnet run
```

程式執行完畢後，您會在 `output` 子資料夾看到兩個 PNG 檔案：

* `DatabarBarHeight30Pixels.png` – 條碼高度 30 像素  
* `DatabarBarHeight60Pixels.png` – 條碼高度 60 像素  

兩張影像編碼相同，但視覺高度不同，說明 **條碼產生器範例 C#** 可依不同標籤需求靈活調整。

## 第四步：驗證產生的條碼

使用任何影像檢視器開啟 PNG 檔案，您應該會看到清晰、高對比度的 DataBar 條碼。若要確認條碼可讀，您可以使用行動掃描應用程式（例如基於 ZXing 的 App）或在桌面使用 **Aspose.BarCode** 的解碼模式：

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

若輸出與 `(01)12345678901231` 相符，即表示產生成功。

## 常見變化與邊緣案例

| 情境 | 調整方式 | 程式碼片段 |
|-----------|------------|--------------|
| **不同符號**（例如 QR、Code128） | 更改 `EncodeTypes` 值 | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **自訂影像格式**（JPEG、BMP） | 使用不同的 `BarCodeImageFormat` 列舉 | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **動態資料**（使用者輸入） | 將硬編碼字串換成變數 | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **資料長度無效** | 捕捉產生器拋出的 `ArgumentException` | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

小技巧：務必先驗證輸入長度是否符合所選符號的規範；Aspose.BarCode 會在資料不符合規格時拋出例外。

## 疑難排解清單

* **找不到目錄** – `SaveBarcode` 輔助方法會自動建立 `output` 資料夾，但請確保應用程式具有寫入權限。  
* **影像尺寸異常** – 請確認在呼叫 `Save` 前已設定 `XDimension.Pixels` 與 `BarHeight.Pixels`。儲存後再變更這些值不會影響已寫入的檔案。  
* **條碼無法辨識** – 使用 DataBar 符號時，請確保編碼字串符合 GS1 格式。缺少括號或應用識別碼錯誤會導致解碼失敗。

## 結論

現在您已掌握如何使用實用的 **條碼產生器範例 C#** 來 **在 C# 中建立條碼影像**。完整程式設定模組寬度、調整條碼高度，並以最少程式碼儲存 PNG 檔案。接下來，您可以探索顏色客製化、多頁 PDF 匯出，或在 ASP.NET Core Web API 中即時產生條碼等進階功能。

**後續步驟**

* 嘗試其他符號（`EncodeTypes.Code128`、`EncodeTypes.QR`），擴充掃描選項。  
* 將產生器整合至 Web 服務，依需求即時回傳條碼影像。  
* 結合 Aspose.PDF，將條碼與產品資訊一起產生 PDF 發票。

祝開發順利，盡情發揮 C# 在條碼影像建立上的彈性！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索其他實作方式。

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}