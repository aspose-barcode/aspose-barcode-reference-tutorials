---
category: general
date: 2026-09-07
description: 快速在 C# 中建立 Planet 條碼 PNG。了解如何使用 Aspose.BarCode 產生填滿與空白條紋的 Planet 條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: zh-hant
lastmod: 2026-09-07
og_description: 快速在 C# 中建立 Planet 條碼 PNG。跟隨本指南了解如何使用 Aspose.BarCode 產生帶有實心與空白條的 Planet
  條碼圖像。
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: 在 C# 中建立星球條碼 PNG – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# 建立行星條碼 PNG – 步驟指南
url: /zh-hant/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 建立 Planet 條碼 PNG – 步驟說明指南

如果您需要在 C# 中 **建立 planet 條碼 PNG** 檔案，本指南將向您展示完整步驟。無論您是要建置郵務服務整合或物流儀表板，您都將學會使用 Aspose.BarCode 函式庫 **產生 planet 條碼** 圖片，且支援實心與空心條的兩種樣式。

在本教學中您將會：

* 設定圖像的輸出資料夾。  
* 為 Planet 符號配置 `BarcodeGenerator`。  
* 產生使用預設實心條樣式的 PNG。  
* 產生使用空心條以提供視覺對比的 PNG。  

不需要任何外部服務——所有操作皆在本機於 .NET 6 或更新版本上執行。

## 前置條件

在開始之前，請確保您已具備以下條件：

| 需求 | 為什麼重要 |
|-------------|----------------|
| .NET 6 SDK（或更新版） | 為 C# 主控台應用程式提供執行環境。 |
| Visual Studio 2022 或 VS Code | 任意可編譯 C# 專案的 IDE。 |
| Aspose.BarCode for .NET（NuGet 套件 `Aspose.BarCode`） | 提供用於產生 Planet 條碼的 `BarcodeGenerator` 類別。 |
| 具備資料夾寫入權限 | PNG 檔案將儲存於此位置。 |

使用以下指令安裝 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立新主控台專案

在終端機中執行以下指令：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

此指令會產生一個名為 **PlanetBarcodeDemo** 的最小 C# 主控台應用程式。

## 步驟 2：定義輸出目錄

第一段程式碼決定產生的 PNG 檔案將儲存於何處。使用絕對路徑或相對路徑皆可；只要確保資料夾已存在，或讓程式自行建立即可。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*為什麼要這麼做？* 將輸出與原始程式碼分離，可保持專案整潔，並避免意外覆寫。

## 步驟 3：產生實心條 Planet 條碼

Planet 條碼由同心圓組成（預設為實心）。我們會設定 X 維度（每條的像素寬度），然後將影像儲存為 PNG。

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**說明**

* `EncodeTypes.Planet` 告訴 Aspose 使用 Planet 符號，這是郵務服務常用的條碼。  
* `XDimension.Pixels = 4` 可產生清晰、適合列印的尺寸，無需手動縮放。  
* `Save` 方法會寫入 PNG 檔案；您也可以透過變更 `BarCodeImageFormat` 來選擇 JPEG 或 BMP。

## 步驟 4：產生空心條 Planet 條碼

有時需要使用空心（透明）條的視覺效果，例如條碼覆蓋在彩色背景上時。將 `FilledBars` 設為 `false` 即可產生此樣式。

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**說明**

* `FilledBars = false` 會停用實心圓，只保留輪廓。  
* 其他設定（X 維度、資料字串）保持相同，確保兩張影像代表相同的資料。

## 步驟 5：執行程式並驗證輸出

編譯並執行：

```bash
dotnet run
```

您應該會在主控台看到確認已儲存檔案的訊息，且 `Barcodes` 資料夾將包含：

* `PostalPlanetFilledBars.png` – 經典的實心條 Planet 條碼。  
* `PostalPlanetEmptyBars.png` – 使用空心條呈現相同資料的條碼。

在任何影像檢視器中開啟 PNG。兩張影像皆編碼數字字串 **123456**，且可被標準郵務條碼讀取器掃描。

## 常見問題與邊緣案例處理

### 如果需要不同的資料格式該怎麼辦？

Planet 條碼接受最多 12 位的數字字串。若傳入非數字值，Aspose 會拋出 `ArgumentException`。請在建立產生器之前驗證輸入：

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### 如何在不改變條寬的情況下調整影像尺寸？

可使用 `Resolution` 屬性，或在儲存後對產生的位圖進行縮放：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### 我可以產生其他影像格式嗎？

可以。將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`、`Bmp` 或 `Gif`。此 API 支援所有常見的點陣圖格式。

### 顏色自訂呢？

在 `Barcode` 參數上設定 `BarColor` 與 `BackColor`：

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

這些選項同時適用於實心與空心條版本。

## 生產環境使用的專業技巧

* **Cache the generator**：當需要以相同設定產生大量條碼時，請快取產生器——重複初始化物件會增加額外開銷。  
* **Dispose**：若在迴圈中大量建立 `BarcodeGenerator` 物件，請記得釋放（它們實作 `IDisposable`）。  
* **Validate the output folder**：提前驗證輸出資料夾，以避免在受寫保護的目錄上拋出執行時例外。

## 結論

您現在已了解如何在 C# 中 **建立 planet 條碼 PNG** 檔案，並懂得 **產生 planet 條碼** 圖片的實心與空心條兩種樣式。完整且可執行的範例示範了如何設定輸出目錄、配置 `BarcodeGenerator`，以及將結果儲存為 PNG 檔案。

接下來，您可以探索：

* 在條碼下方加入 **可讀文字**（`planetFilled.Parameters.Caption.Visible = true`）。  
* 使用 Aspose.PDF 將產生的 PNG 整合至 **PDF 發票**。  
* 切換至其他郵務符號，如 **IMB** 或 **ITF**（`EncodeTypes.IMB`、`EncodeTypes.ITF`）。  

隨意嘗試不同的條寬、顏色與影像解析度，以符合您的特定應用需求。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與步驟說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [在 C# 中建立 Planet 條碼影像 – 如何產生郵務條碼](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [在 C# 中建立 Planet 條碼 – 完整步驟說明指南](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [使用 Aspose.BarCode for .NET 產生 PNG 條碼：一維實心條設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}