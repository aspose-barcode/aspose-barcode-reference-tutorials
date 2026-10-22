---
category: general
date: 2026-10-21
description: 學習如何在 C# 中產生條碼圖像，以及如何使用 Aspose.BarCode 將條碼檔案匯出為 PNG，以獲得快速、可靠的結果。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: zh-hant
lastmod: 2026-10-21
og_description: 如何在 C# 中產生條碼圖像以及將條碼檔案匯出為 PNG。請跟隨本完整教學，使用 Aspose.BarCode 建立 Planet
  與 RM4SCC 條碼。
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: 如何在 C# 中產生條碼圖像並匯出 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中產生條碼圖像並匯出
url: /zh-hant/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼影像並匯出

如果您需要在 .NET 應用程式中 **產生條碼** 影像，本指南將示範建立 Planet 與 RM4SCC 條碼的完整步驟，並說明 **如何匯出條碼** 為 PNG 檔案。您將取得可直接執行的程式範例、每個設定的說明，以及常見問題的技巧。

本教學涵蓋：

* 新增 Aspose.BarCode NuGet 套件
* 設定模組寬度與可選的條碼高度
* 將產生的條碼儲存至磁碟
* 驗證輸出檔案

> **先決條件** – .NET 6+ SDK、Visual Studio 2022（或任何 IDE），以及下載 Aspose.BarCode 套件所需的網路連線。

## 您將完成的目標

閱讀完本篇文章後，您將能夠：

* 產生 **Planet** 條碼，且自動計算條碼高度。
* 產生 **RM4SCC** 條碼，且自動計算條碼高度。
* 覆寫預設高度，產生 100 像素高的條碼。
* 將每個條碼匯出為 PNG 檔案，存放於您指定的資料夾。

## 步驟 1：安裝 Aspose.BarCode

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此套件提供 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉，供下列程式碼使用。

## 步驟 2：設定輸出資料夾

建立一個資料夾，用來存放 PNG 檔案。資料夾路徑可以是絕對路徑，也可以是相對於專案根目錄的路徑。

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **小技巧：** 使用 `Path.Combine` 可避免硬編碼路徑分隔符，且在 Windows、macOS 與 Linux 上皆可正常運作。

## 步驟 3：產生自動高度的條碼

若未指定條碼高度，Aspose.BarCode 會自動選擇適合編碼資料的尺寸。以下程式碼以 4 像素的模組寬度，建立 Planet 與 RM4SCC 兩種條碼。

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**為什麼這樣可行：**  
* `EncodeTypes.Planet` 與 `EncodeTypes.RM4SCC` 告訴產生器使用哪種符號系統。  
* `XDimension.Pixels` 定義單一條碼模組的寬度；設定為 4 px 可產生清晰且易於掃描的影像。  
* 由於未設定 `BarHeight`，函式庫會自動計算最佳高度。

## 步驟 4：產生固定 100 像素高度的條碼

若設計上需要特定的條碼高度，可覆寫自動計算：

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**為什麼可能需要固定高度：**  
運輸標籤的設計規範常會要求條碼尺寸必須精確，以確保與條碼掃描器的相容性。設定 `BarHeight.Pixels` 可保證所有產生的影像高度一致。

## 步驟 5：驗證匯出的檔案

程式執行完畢後，`Barcodes` 資料夾會包含四個 PNG 檔案：

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

使用影像檢視器開啟任一檔案，或將其嵌入 PDF 以確認顯示正確。若掃描器無法讀取條碼，請提高 `XDimension.Pixels` 的數值或再次檢查輸入字串長度。

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

您應該會看到類似以下的輸出：

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## 常見問題與特殊情況

| 問題 | 答案 |
|----------|--------|
| **我可以匯出成 PNG 以外的格式嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp`、`Gif` 或 `Tiff` 即可。 |
| **如果我的資料包含符號系統不支援的字元該怎麼辦？** | 產生器會拋出 `ArgumentException`。請先驗證輸入，或改用支援該字元集的符號系統。 |
| **如何變更前景色／背景色？** | 在呼叫 `Save` 前設定 `Parameters.Barcode.ForeColor` 與 `Parameters.Barcode.BackColor`。 |
| **有沒有辦法在記憶體中產生條碼而不是寫入磁碟？** | 呼叫 `GenerateBarCodeImage()` 可取得 `System.Drawing.Image` 物件，之後即可自行處理或串流。 |

## 專業提示：批次處理

當需要一次產生大量條碼（例如郵寄清單）時，可將產生邏輯包在 `foreach` 迴圈中：

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

此模式可輕鬆擴展至數千筆條碼，同時保持程式碼簡潔。

## 結論

現在您已掌握 **如何在 C# 中產生條碼** 影像，以及 **如何使用 Aspose.BarCode 將條碼匯出為 PNG**。完整範例示範了 Planet 與 RM4SCC 符號系統的自動與固定高度產生方式，為任何條碼相關專案奠定堅實基礎。

**下一步**

* 探索其他符號系統，如 Code128、QR 或 DataMatrix。  
* 嘗試顏色客製化（`ForeColor`、`BackColor`）。  
* 使用 PDF 函式庫將產生的 PNG 整合至發票或運送標籤的 PDF 中。  

祝編程愉快，讓您的條碼順利掃描！

## 接下來應該學什麼？

以下教學與本篇內容緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式範例與逐步說明，協助您掌握更多 API 功能，並探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [在 C# 中建立 GS1 條碼影像 – 快速產生條碼教學](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [如何在 C# 中使用 Aspose.BarCode 產生條碼影像](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}