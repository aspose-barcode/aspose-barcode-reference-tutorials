---
category: general
date: 2026-09-26
description: 學習如何在 C# 中建立郵政條碼圖像。本指南將示範如何產生 Planet 條碼，並設定條碼高度以取得自訂輸出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: zh-hant
lastmod: 2026-09-26
og_description: 快速使用 C# 建立郵政條碼圖像。跟隨本教學生成 Planet 條碼、設定條碼高度，並產生高品質 PNG 檔案。
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: 使用 C# 建立自訂高度的郵政條碼圖像 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何在 C# 中建立具有自訂高度的郵政條碼圖像
url: /zh-hant/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立自訂高度的郵政條碼圖像

如果您需要為郵寄標籤 **建立郵政條碼圖像**，本教學將向您展示完整步驟。您將學習如何產生 Planet 條碼、調整條碼高度，並將結果儲存為 PNG 檔案——全部使用 Aspose.BarCode for .NET 函式庫。

產生條碼圖像不需要外部設計工具。完成本指南後，您即可產生 Planet 與 RM4SCC 標準的預設高度與自訂高度條碼，隨時整合至任何運輸工作流程。

## 前置條件

* .NET 6.0 或更新版本已安裝  
* Visual Studio 2022（或任何 C# IDE）  
* 透過 NuGet 加入 Aspose.BarCode for .NET（`Install-Package Aspose.BarCode`）  

不需要額外設定；函式庫會在內部處理圖像渲染。

## 步驟 1：設定專案並匯入命名空間

建立新的主控台應用程式，並加入所需的 `using` 陳述式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

這些命名空間會公開 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉，您將使用它們來 **產生 Planet 條碼** 以及其他郵政格式。

## 步驟 2：使用預設條碼高度建立 Planet 條碼

第一個範例使用函式庫的預設條碼高度建立 Planet 條碼。此範例示範在套用任何自訂尺寸前的基礎輸出。

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**為何重要：** 預設高度適用於大多數標籤印表機，但某些工作流程需要較高的條碼以提升掃描可靠度。上述程式碼提供一張參考圖像，可與自訂高度版本作比較。

## 步驟 3：為 Planet 條碼套用自訂條碼高度

若要手動 **設定條碼高度**，請將像素值指派給 `BarHeight.Pixels`。以下程式碼片段會建立一個 100 像素高的 Planet 條碼。

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**專業提示：** 選擇與印表機 DPI 相符的條碼高度。以 300 dpi 印表機為例，100 像素的條碼大約等於 0.33 英吋，這通常是郵政掃描器的建議高度。

## 步驟 4：使用預設高度產生 RM4SCC 條碼

RM4SCC 是另一種常見的郵政符號。其流程與 Planet 範例相同，只是使用 `EncodeTypes.RM4SCC`。

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

此步驟證實相同的 **條碼產生器自訂高度** 邏輯可於不同郵政格式中運作。

## 步驟 5：為 RM4SCC 條碼套用自訂高度

最後，使用與 Planet 條碼相同的方式調整 RM4SCC 條碼的條碼高度。

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## 預期輸出

執行完整程式後，會在專案的輸出目錄產生四個 PNG 檔案：

| 檔案名稱 | 條碼高度 | 符號類型 |
|---|---|---|
| `PostalPlanetBarHeightDefault.png` | 預設 | Planet |
| `PostalPlanetBarHeight100Pixels.png` | 100 px | Planet |
| `PostalRM4SCCBarHeightDefault.png` | 預設 | RM4SCC |
| `PostalRM4SCCBarHeight100Pixels.png` | 100 px | RM4SCC |

每張圖像皆呈現清晰、高對比度的條碼，適合列印於郵寄標籤。您可使用任何圖像檢視器開啟 PNG 檔案，以驗證條碼尺寸。

## 常見問題與特殊情況

**如果需要以毫米而非像素設定條碼高度該怎麼辦？**  
函式庫以像素為單位，因為它直接對應位圖解析度。請使用印表機的 DPI 將毫米轉換為像素：  
`pixels = (mm / 25.4) * DPI`。將計算後的值指定給 `BarHeight.Pixels`。

**呼叫 `Save` 後還能變更條碼高度嗎？**  
不能。條碼圖像會在呼叫 `Save` 時即時渲染。請在呼叫 `Save` 前調整所有參數。

**較高的條碼是否需要更大的 X‑dimension？**  
提升 `XDimension` 會使每個模組變寬，能改善低解析度印表機的可讀性。但同時也會增加條碼總寬度。請測試兩者以找出最適合標籤尺寸的平衡點。

**相同程式碼能在 .NET Framework 4.8 上執行嗎？**  
可以。Aspose.BarCode 支援 .NET Framework 4.6.2 及以上版本，您可在較舊的執行環境中使用，無需修改。

## 完整原始碼，快速複製貼上

以下為完整、可執行的程式碼，已整合上述所有步驟。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

執行程式後，主控台會確認每張圖像已儲存。您現在可以將這些 PNG 檔案嵌入郵寄標籤範本、列印，或傳送至第三方物流 API。

## 結論

現在您已了解如何使用 Aspose.BarCode 在 C# 中 **建立郵政條碼圖像** 檔案。本指南說明了產生 Planet 條碼、調整條碼高度，以及將相同技巧套用至 RM4SCC 條碼。透過控制 `XDimension` 與 `BarHeight.Pixels`，您可獲得符合郵政服務要求的精確視覺效果。

接下來，您可以探索相關主題，例如 **產生追蹤用 QR Code**、**在 PDF 發票中嵌入條碼**，或 **批次處理多張條碼圖像**。調整條碼高度僅是其中一項功能；您亦可自訂顏色、加入可讀文字，或匯出為 SVG 供網頁使用。

祝程式開發順利，願您的郵件掃描毫無問題！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，進一步延伸所示技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [在 C# 中建立郵政條碼圖像 – 步驟指南](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [建立郵政條碼圖像 – 輕鬆變更條碼高度](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [如何在 C# 中使用自訂尺寸產生郵政條碼](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}