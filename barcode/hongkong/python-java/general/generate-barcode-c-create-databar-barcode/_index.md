---
category: general
date: 2026-07-21
description: 快速使用 Aspose.BarCode 於 C# 產生條碼。學習如何建立 DataBar 條碼、客製化條碼尺寸，並在幾個步驟內匯出條碼影像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: zh-hant
lastmod: 2026-07-21
og_description: 使用 Aspose.BarCode 於 C# 產生條碼。建立 DataBar 條碼，自訂尺寸，即時匯出圖像。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: 產生條碼 C# – 使用自訂尺寸建立 DataBar 條碼
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: 產生條碼 C# – 建立 DataBar 條碼
url: /zh-hant/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生條碼 C# – 建立 DataBar 條碼

想要 **generate barcode C#** 而不必翻閱無盡的文件嗎？您來對地方了。在本指南中，我們將一步步說明如何建立 **DataBar 條碼**、調整其尺寸，最後 **匯出條碼影像**——只需幾行 C# 程式碼。

想像一下，您需要一個能貼在小型貨架標籤上的緊湊產品標籤。DataBar Expanded Stacked 符號正好適合，使用 Aspose.BarCode 您可以精確控制使用多少列或行。準備好了嗎？讓我們開始吧。

## 您將完成的工作

- **建立 DataBar 條碼**（「expanded stacked」變體）從頭開始。  
- **自訂條碼大小**，直接設定列或行。  
- **即時變更條碼尺寸**，無需重新建立產生器。  
- **匯出條碼影像**為 PNG（或任何 Aspose 支援的格式）。  

無需外部服務，無需雜亂設定——只要乾淨、可執行的 C# 程式碼。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.7+ 上執行）。  
- 有效的 Aspose.BarCode for .NET 授權（或可使用試用模式）。  
- 您選擇的 IDE——Visual Studio、Rider 或 VS Code 都可。  

如果您尚未安裝 NuGet 套件，請執行：

```bash
dotnet add package Aspose.BarCode
```

就這樣——沒有其他相依性。

## 步驟 1：設定條碼產生器（如何 **generate barcode C#**）

首先，我們需要一個指向 **DataBar Expanded Stacked** 符號的 `BarcodeGenerator` 實例。此物件是之後產生影像的引擎。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*為什麼這很重要*：`EncodeTypes.DatabarExpandedStacked` 列舉告訴 Aspose 我們需要堆疊版，適合狹窄空間。傳入的文字會成為編碼值；您可以替換為任何應用程式需要的數字字串。

## 步驟 2：**自訂條碼大小** – 設定列數

DataBar 條碼允許您透過指定 **列** *或* **行** 數量來影響視覺密度。我們先從列開始。行數會自動計算以確保條碼有效。

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*專業提示*：列數會影響條碼寬度。列越多 → 條碼越寬，這可提升低解析度印表機的掃描可靠度。

## 步驟 3：**匯出條碼影像**（使用列設定）

現在我們將影像寫入磁碟。您可以選擇 PNG、JPEG、BMP，甚至 SVG。這裡使用 PNG 以獲得清晰、無損的輸出。

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **預期結果** – 開啟 `DatabarCols4.png`，您應該會看到一個整齊堆疊、具四列的 DataBar。它看起來像是一堆密集的垂直條，十分適合小標籤。

## 步驟 4：**變更條碼尺寸** – 改為設定行數

有時您需要較高的條碼而非較寬的。改為使用行控制；Aspose 會自動重新計算列數。

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*為什麼要切換？* 行數會影響條碼高度。行越多 → 符號越高，當您有垂直空間但寬度受限時非常有用。

## 步驟 5：**匯出條碼影像**（使用行設定）

儲存第二個變體。請注意檔名反映了變更；您也可以保留兩張影像以作比較。

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **結果** – `DatabarRows3.png` 現在顯示相同資料的較高版本，仍然可完美掃描。

## 完整範例

將上述全部結合，以下是一個可直接複製貼上並立即執行的獨立主控台應用程式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

執行程式，然後開啟兩個 PNG 檔案。您已經 **generate barcode C#**、**customized barcode size**、**changed barcode dimensions**，以及 **exported the barcode image**——全部在不到一分鐘內完成。

## 常見問題與邊緣情況

- **如果需要其他影像格式該怎麼辦？**  
  將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp`、`Gif` 或 `Svg`。API 會自動處理轉換。

- **可以同時變更行與列嗎？**  
  從技術上說可以同時設定，但 Aspose 會以最後一次設定的屬性為優先。較安全的做法是只設定 *一個* 維度，讓函式庫自動計算另一個，以確保 DataBar 有效。

- **如何設定前景色/背景色？**  
  使用 `barcodeGen.Parameters.Barcode.ForegroundColor` 與 `BackgroundColor`。範例：  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **編碼資料有尺寸限制嗎？**  
  DataBar Expanded Stacked 支援最多 74 個數字字元（或 30 個字母數字混合）。超過此限制會拋出例外。

## 往後步驟

現在您已掌握 **create databar barcode** 基礎，請考慮：

- 在條碼下方加入 **文字註釋**（`barcodeGen.Parameters.CaptionAbove.Text`）。
- 使用 Aspose.PDF 將 PNG 直接嵌入 PDF。
- 透過迴圈 CSV 中的產品 ID，大量產生條碼。

上述每個主題皆以相同的 `BarcodeGenerator` 物件為基礎，您不必從頭開始。

---

**結論**：您現在知道如何 **generate barcode C#**、**customized barcode size**、**changed barcode dimensions**，以及使用 Aspose.BarCode **export barcode image**。盡情嘗試列/行數值、切換影像格式，並將程式碼整合至您的庫存或 POS 系統。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以相同技術為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [產生條碼影像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [產生 DataMatrix 條碼 – Aspose.BarCode 專業指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}