---
category: general
date: 2026-09-19
description: 在 C# 中建立 PDF417 條碼，學習如何產生條碼圖像、設定條碼尺寸，並儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: zh-hant
lastmod: 2026-09-19
og_description: 在 C# 中建立 PDF417 條碼，並了解如何產生條碼圖像、設定條碼尺寸，以及將其儲存為 PNG 檔案。
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: 在 C# 中建立 PDF417 條碼並匯出 PNG – 步驟教學
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: 如何在 C# 中建立 PDF417 條碼並匯出 PNG
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 PDF417 條碼並匯出 PNG

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼**，本指南將示範如何產生條碼影像、調整其尺寸，並將其儲存為 PNG 檔案。您將看到一個完整、可執行的範例，使用 Aspose.BarCode 函式庫，您可以直接將程式碼複製到自己的專案中。

產生條碼影像是票務系統、庫存追蹤以及行動登機證等常見需求。完成本教學後，您將了解 **如何產生條碼影像**、**如何設定條碼尺寸**，以及 **如何建立條碼 PNG** 檔案，以符合您的視覺品質標準。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼亦可在 .NET Framework 4.7+ 上執行）。
* 開發環境，例如 Visual Studio 2022 或 VS Code。
* 有效的 **Aspose.BarCode for .NET** 函式庫授權（免費試用版可用於本範例）。
* 基本的 C# 語法熟悉度。

Install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：設定專案並匯入命名空間

建立新的主控台應用程式或將程式碼加入現有專案。於檔案頂部匯入所需的命名空間：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

這些命名空間讓您可以存取 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉。

## 步驟 2：建立 PDF417 條碼 – 基本產生器設定

第一步是以 `Pdf417` 編碼類型與欲編碼的文字實例化 `BarcodeGenerator`。此物件代表您稍後將要呈現的條碼。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*為什麼這很重要*：`EncodeTypes.Pdf417` 告訴函式庫使用 PDF417 符號，這是一種堆疊式線性條碼，可儲存大量資料。第二個參數（「Sample」）是條碼被掃描時顯示的內容。

## 步驟 3：設定條碼尺寸 – 微調密度與版面配置

PDF417 條碼由多列多欄的模組組成。調整 X‑dimension（模組寬度）以及列/欄的數量，可控制影像的視覺密度與整體尺寸。

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*為什麼這很重要*：  
* **X‑dimension** 決定每個微小方塊（模組）的寬度。較小的數值會產生更緊湊的條碼，但對低解析度掃描器可能較難辨識。  
* **Columns** 與 **Rows** 影響資料容量與實體形狀。增加欄數會使條碼變寬，增加列數會使條碼變高。您可依註解中顯示的上限進行測試。

**小技巧**：若條碼在高 DPI 螢幕上看起來過於密集，可將 `XDimension.Pixels` 提升至 3 或 4。相反地，對於小標籤，您可以將其設為 1 像素，並減少欄數。

## 步驟 4：產生條碼影像 – 渲染至記憶體位圖

設定好產生器後，您可以將條碼渲染為影像物件。若僅需直接儲存檔案，此步驟為可選，但取得位圖後可進一步處理（例如加入商標或繪製邊框）。

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` 會回傳 `System.Drawing.Image`，您若需要可使用 GDI+ 進行操作。

## 步驟 5：建立條碼 PNG – 儲存最終影像檔案

最後，將影像以 PNG 格式寫入磁碟。PNG 保留無損品質，對掃描應用而言相當理想。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*為什麼這很重要*：`Save` 方法會為您處理編碼與檔案 I/O。使用 `BarCodeImageFormat.Png` 可確保輸出為可攜、無損的影像，能在瀏覽器與行動裝置上正常顯示。

### 完整可執行範例

以下是完整程式碼，您可貼入 `Program.cs` 並執行。將 `YOUR_DIRECTORY` 替換為您機器上已存在的資料夾路徑。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

執行程式後會產生如下圖所示的 PNG 檔案：

![產生的 PDF417 條碼範例](https://example.com/placeholder-image.png "使用自訂尺寸產生並儲存為 PNG 的 PDF417 條碼")

*替代文字*：**使用 C# 產生的 PDF417 條碼範例，顯示自訂尺寸並儲存為 PNG** – 這符合 **create PDF417 barcode** 的影像可及性需求。

## 常見變體與邊緣案例

| 情況 | 建議調整 |
|-----------|------------------------|
| **非常小的標籤**（例如 1 cm × 2 cm） | 設定 `XDimension.Pixels = 1` 並將 `Columns` 減少至 2‑3。驗證掃描器的可讀性。 |
| **高解析度列印**（300 dpi 或以上） | 將 `XDimension.Pixels` 提升至 3‑4，並視需要增加 `Rows` 以提升資料容量。 |
| **需要不同的影像格式**（JPEG、BMP） | 將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 |
| **嵌入 PDF** | 使用 `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` 取代 PNG。 |
| **動態資料**（使用者輸入） | 將靜態的 `"Sample"` 字串換成變數，例如 `userInput`。確保文字長度不超過 PDF417 限制（約 1 800 個字元）。 |

## 疑難排解清單

* **空白影像** – 確認輸出目錄是否存在且應用程式具有寫入權限。  
* **條碼無法掃描** – 增加 `XDimension.Pixels` 或增加欄/列數；低對比度背景亦可能導致失敗。  
* **尺寸異常** – 再次檢查 `Columns` 與 `Rows` 的數值；函式庫會遵守註解中顯示的最大限制。

## 後續步驟

既然您已能 **建立 PDF417 條碼**，可考慮探索以下相關主題：

* **如何產生條碼影像** 於其他格式，例如用於網頁可縮放圖形的 SVG。  
* **如何設定條碼尺寸** 於 QR Code 與 DataMatrix 符號。  
* **如何建立條碼 PNG**，使用自訂顏色或透過 `System.Drawing` 嵌入商標。

這些延伸功能讓您能構建完整的條碼產生服務，支援行動應用、網站入口與桌面工具等多種情境。

---

*您已學會如何使用 C# 建立 PDF417 條碼、客製化其尺寸、渲染條碼影像，並將其儲存為 PNG 檔案。將此處示範的模式套用至其他條碼類型與影像格式，以擴展您的自動化能力。*

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，建立在此處示範的技術之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 使用 Aspose 產生 PDF417 條碼影像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何使用 Aspose 建立 PDF417 條碼 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [如何在 C# 儲存條碼 – 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}