---
category: general
date: 2026-09-23
description: C# 條碼產生器教學示範如何使用 Aspose.BarCode 函式庫產生具有自訂長寬比的條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: zh-hant
lastmod: 2026-09-23
og_description: C# 條碼產生器指南將一步步教您如何產生條碼圖像、調整長寬比，並使用 Aspose.BarCode 匯出 PNG 檔案。
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: 使用 C# 條碼產生器產生高品質條碼
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: 如何使用 C# 條碼產生器產生 DataBar 條碼
url: /zh-hant/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器產生 DataBar 條碼

如果您需要一個 **c# barcode generator** 能產生 DataBar 堆疊全方向符號，本指南提供完整、可直接執行的解決方案。您將會看到如何產生條碼影像、控制 X‑dimension，並在不離開 IDE 的情況下變更長寬比。

產生條碼是庫存系統、運送標籤及銷售點應用程式的常見需求。完成本教學後，您即可建立任意長寬比的 PNG 檔案，並了解如何將程式碼套用到其他條碼類型。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本已安裝  
* Visual Studio 2022（或您偏好的任何 C# 編輯器）  
* 參考 **Aspose.BarCode** NuGet 套件 – 為 `BarcodeGenerator` 類別提供功能的函式庫  

您不需要額外的圖形函式庫；Aspose.BarCode 會在內部處理影像編碼。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在專案資料夾中開啟終端機並執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此指令會將函式庫的最新穩定版加入您的專案檔，使 `BarcodeGenerator` 類別可供使用。

## 步驟 2：定義輸出資料夾

選擇一個用來儲存產生之 PNG 檔案的資料夾。使用絕對路徑或相對路徑皆可，但相對路徑能保持專案的可移植性。

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

以程式方式建立目錄可避免因資料夾不存在而產生執行時錯誤。

## 步驟 3：以範例資料實例化 C# 條碼產生器

`BarcodeGenerator` 建構子需要兩個參數：條碼類型與資料字串。若要產生 DataBar 堆疊全方向符號，請使用 `EncodeTypes.DatabarStackedOmniDirectional`。

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

資料字串遵循 GS1 應用識別碼（Application Identifier）格式。`EncodeTypes` 列舉包含超過 150 種條碼標準；您只要變更列舉值即可切換至其他類型。

## 步驟 4：設定條碼的 X‑dimension（像素大小）

X‑dimension 控制最窄條的寬度。像素值為 2 時，可產生清晰、高解析度的影像，適用於大多數螢幕。

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

調整 X‑dimension 為可選項，但能讓您細緻控制條碼的視覺密度。

## 步驟 5：產生長寬比為 15 的條碼並儲存為 PNG

`AspectRatio` 屬性屬於 `DataBar` 子物件。變更此值會在垂直方向上拉伸或壓縮條碼，同時保留編碼資料。

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 方法會將條碼寫入指定的檔案路徑。`BarCodeImageFormat.Png` 列舉確保無損壓縮。

![c# 條碼產生器輸出範例](generated_barcode_example.png)

*圖片說明：長寬比為 15 的條碼產生結果。*

## 步驟 6：將長寬比改為 30 並產生第二張影像

重複使用相同的 `BarcodeGenerator` 實例可避免重新分配物件。只需更新 `AspectRatio` 後再次呼叫 `Save` 即可。

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

現在您擁有兩個 PNG 檔案，唯一差異在於垂直縮放。此技巧在需要相同資料對應不同標籤尺寸時相當有用。

## 常見變化與邊緣情況

### 切換至其他條碼類型

若需要 QR code、Code 128 或 PDF417，請在建構子中更換列舉值：

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

其他所有設定步驟（X‑dimension、儲存）皆保持相同。

### 處理不支援的字元

`BarcodeGenerator` 會根據所選符號驗證輸入字串。若提供非法字元，會拋出 `ArgumentException`。請將建立程式碼包在 try‑catch 區塊中，以提供友善的錯誤訊息：

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### 匯出至其他影像格式

Aspose.BarCode 支援 BMP、JPEG、TIFF 與 SVG。請相應變更 `Save` 的第二個參數：

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### 高解析度列印輸出

在高 DPI 列印機上列印時，請提升 X‑dimension，並可選擇設定 `Resolution` 屬性：

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

這些設定會產生較大的檔案，但能在實體媒介上保持清晰的邊緣。

## 預期輸出

執行完整程式後，會在 `GeneratedBarcodes/` 目錄下產生以下檔案：

* `DatabarAspectRatio15.png` – 標準高度的 DataBar 條碼  
* `DatabarAspectRatio30.png` – 垂直拉伸版  

兩張影像皆包含相同的編碼 GS1 資料，您可使用任何條碼掃描應用程式驗證。

## 完整原始碼

將以下程式碼複製到新的主控台專案（`dotnet new console`）中並執行。程式會在主控台印出狀態訊息，並將 PNG 檔寫入磁碟。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

執行程式會產生類似以下的主控台輸出：

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## 結論

您現在擁有一個 **c# barcode generator**，能產生 DataBar 堆疊全方向符號、調整 X‑dimension，並以自訂長寬比匯出 PNG 檔案。同樣的模式亦適用於 Aspose.BarCode 支援的其他條碼符號，讓您輕鬆將條碼產生整合至庫存、運送或銷售點解決方案中。

若想進一步探索，可嘗試：

* 產生 QR code 或 PDF417 符號（`how to generate barcode` 用於行動應用程式）  
* 匯出為 SVG 以取得可縮放的網頁圖形  
* 使用 Aspose.PDF 將產生的影像直接嵌入 PDF 發票  

嘗試不同的 `AspectRatio` 值、X‑dimension 大小與輸出格式，以符合精確的需求

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並以完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何調整條碼尺寸 – 使用 Aspose.BarCode for .NET 調整 Codablock F 長寬比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}