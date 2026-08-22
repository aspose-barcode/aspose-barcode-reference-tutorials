---
category: general
date: 2026-08-22
description: 條碼產生器 C# 教學示範如何產生條碼 PNG 檔案、建立 DataBar 條碼，並在幾個步驟內調整條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: zh-hant
lastmod: 2026-08-22
og_description: 條碼產生器 C# 指南將一步步教你如何產生條碼 PNG、建立 DataBar 條碼，並有效調整條碼高度。
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: 條碼產生器 C# – 建立 DataBar 條碼並調整高度
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# 條碼產生器建立 DataBar 全向條碼
url: /zh-hant/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 barcode generator C# 產生 DataBar Omni‑directional 條碼

如果你需要一個 **barcode generator C#** 能產生高品質 PNG 圖像，本指南將為你提供完整說明。你將學習如何產生 barcode PNG 檔案、建立 DataBar Omni‑directional 條碼，並在不離開 IDE 的情況下調整條碼高度。

以程式方式產生條碼可省去使用圖形編輯器的手動步驟。完成本教學後，你將擁有兩個 PNG 檔案——一個條碼高度為 30 像素，另一個為 60 像素——可直接用於發票、標籤或庫存系統。

**Prerequisites**

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.7+ 上執行）
- 參考 `Aspose.BarCode` NuGet 套件（或任何提供類似 API 的函式庫）
- 具備 C# 與 Visual Studio 或你慣用的 IDE 基本知識

---

## 步驟 1：設定 barcode generator C# 專案

建立 **barcode generator C#** 實例是第一步。建構子接受兩個參數：條碼類型 (`EncodeTypes.DatabarOmniDirectional`) 與資料內容。在此範例中，資料內容遵循 GS1 應用識別碼格式，用於 14 位元 GTIN。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**為什麼這很重要：** `EncodeTypes.DatabarOmniDirectional` 列舉告訴函式庫渲染可從任意方向讀取的 DataBar，這對小型零售標籤而言非常理想。

---

## 步驟 2：定義模組尺寸 (X‑dimension)

X‑dimension 控制單一條碼模組的寬度。設定為 2 像素可產生清晰、易讀的圖像，同時保持檔案尺寸較小。

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**提示：** 若空間受限需要更緊湊的條碼，可將值降低至 1 像素，但請使用掃描器測試可讀性。

---

## 步驟 3：產生第一個條碼高度為 30 像素的 PNG

條碼高度決定條紋的高度。30 像素的高度是標準標籤的常見預設值。

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

檔案 `DatabarBarHeight30Pixels.png` 現在包含一個 **generate barcode PNG**，可直接在網頁中使用或隨需列印。

---

## 步驟 4：將條碼高度調整為 60 像素並儲存第二個 PNG

變更條碼高度只需將相同屬性賦予新值即可。此示範了產生器的 **adjust barcode height** 功能。

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

現在你已擁有 `DatabarBarHeight60Pixels.png`，適用於需要遠距離掃描的大型包裝。

**預期輸出**

- `DatabarBarHeight30Pixels.png` – 緊湊的 DataBar Omni‑directional 條碼，30 像素高。
- `DatabarBarHeight60Pixels.png` – 同樣的條碼，將高度加倍以提升可見度。

兩個影像皆為 PNG 檔案，保留無損品質，且在需要時支援透明度。

---

## 如何以不同格式產生 barcode PNG 檔案

雖然本教學以 PNG 為例，`Save` 方法亦接受其他格式，如 `Jpeg`、`Bmp` 與 `Svg`。若要 **how to generate barcode** 為其他格式，只需將 `BarCodeImageFormat.Png` 替換為相應的列舉值：

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

當需要可無失真縮放的向量圖時，選擇 SVG 會很方便。

---

## 常見陷阱：在 **create DataBar barcode** 圖像時

| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| 條碼看起來模糊 | 目標解析度下 X‑dimension 設定過低 | 將 `XDimension.Pixels` 提升至 3 或 4 |
| 掃描器無法讀取條碼 | 條碼高度對掃描器光學系統太短 | 使用至少 30 像素的高度，或遵循掃描器規格 |
| 資料字串被拒絕 | GS1 格式不正確 | 確保字串以正確的應用識別碼開頭，例如 GTIN‑14 的 `(01)` |

提前處理這些問題可節省在生產流程中整合條碼的時間。

---

## 進階提示：重複使用同一個產生器產生多個條碼

若需為一批產品 **generate barcode PNG**，可重複使用相同的 `BarcodeGenerator` 實例，僅更新 `CodeText` 屬性：

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

此模式可減少物件建立的開銷，讓程式碼保持簡潔。

---

## 結論

現在你已擁有完整的 **barcode generator C#** 工作流程，能 **creates DataBar barcodes**、**generates barcode PNG** 檔案，並透過單一屬性變更 **adjust barcode height**。此範例涵蓋從專案設定到處理例外情況的所有步驟，讓你能自信地將條碼產生整合至任何 .NET 應用程式。

**下一步**

- 探索其他條碼符號 (`EncodeTypes.QR`, `EncodeTypes.Code128`) 以擴充解決方案。
- 將產生器與 ASP.NET Core 結合，透過 API 端點即時提供條碼。
- 嘗試顏色選項 (`generator.Parameters.Barcode.ForeColor`) 以符合品牌需求。

祝程式開發順利，願你的掃描永遠快速！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [使用 Aspose.BarCode .NET API 產生一維 Databar 2D 條碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}