---
category: general
date: 2026-09-23
description: 如何在 C# 中使用 Aspose.BarCode 調整條碼大小。學習生成條碼 C# 程式碼、客製化尺寸，並高效匯出條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: zh-hant
lastmod: 2026-09-23
og_description: 如何在 C# 中使用 Aspose.BarCode 調整條碼大小。請參考本指南生成條碼 C# 程式碼、調整尺寸，並匯出條碼圖像。
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: 如何在 C# 中調整條碼大小 – 完整的 Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: 使用 Aspose.BarCode 在 C# 中調整條碼大小 – 逐步指南
url: /zh-hant/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 調整條碼大小 – 步驟指南

如果您需要在 .NET 應用程式中 **調整條碼大小**，本教學會展示您可以直接複製貼上並立即執行的完整程式碼。您將學會如何 **產生條碼 C#** 程式碼、調整條碼高度，以及 **匯出條碼影像** 檔案，且全程不離開 IDE。

建立條碼在庫存系統、運送標籤與銷售點終端機中相當常見。完成本指南後，您將能 **建立 Databar 條碼** 圖片，且高度可依需求自行設定，並了解控制尺寸、解析度與檔案格式的關鍵屬性。

## Prerequisites

- .NET 6 或更新版本（此範例亦支援 .NET Framework 4.6+）  
- Aspose.BarCode for .NET NuGet 套件（`Install-Package Aspose.BarCode`）  
- 基本的 C# 語法與 Visual Studio（或任何 C# IDE）熟悉度  

不需要額外的函式庫；Aspose.BarCode 內部已處理渲染、縮放與影像匯出。

## Step 1: Set up the project and import Aspose.BarCode

建立一個新的 Console 專案（或整合至現有專案），並加入 Aspose.BarCode 命名空間：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Pro tip:** 使用最新的 Aspose.BarCode 版本（截至 2026 年 9 月）可取得錯誤修正與新條碼符號支援。

## Step 2: Initialize a DataBar Omni‑directional barcode generator

**條碼產生器範例** 先指定符號系統 (`EncodeTypes.DatabarOmniDirectional`) 與資料內容。資料遵循 GS1 應用識別碼格式 `(01)12345678901231`。

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

此物件保留所有稍後會修改的參數，例如 X‑dimension、條碼高度與影像格式。

## Step 3: Define common size parameters

在匯出之前，先設定 X‑dimension（最窄條的寬度）與初始條碼高度。X‑dimension 以像素為單位；`2` 的數值在大多數螢幕解析度下表現良好。

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Why this matters:** `BarHeight` 屬性直接影響條碼的視覺大小。變更它即是 **調整條碼大小** 的核心。

## Step 4: Export the first barcode image (30 px height)

現在可以 **匯出條碼影像** 為 PNG 檔案。`Save` 方法會自動使用目前的參數渲染條碼。

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

產生的檔案如下所示：

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="如何調整條碼範例 – 30 像素高度"}

## Step 5: Change the bar height to create a larger barcode

為了動態示範 **調整條碼大小**，調整 `BarHeight` 屬性後重新 **儲存**。此操作 **不需要** 建立新的 `BarcodeGenerator` 實例，只要修改現有物件即可。

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Step 6: Export the resized barcode image (60 px height)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

現在您擁有兩個 PNG 檔案——一個 30 px、另一個 60 px——展示相同資料在不同尺寸下的呈現方式。

### Expected output

| 檔案名稱                     | 條碼高度 (px) | 視覺結果 |
|-------------------------------|----------------|---------------|
| `DatabarBarHeight30Pixels.png`| 30             | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="30 像素 DataBar Omni‑directional 條碼"} |
| `DatabarBarHeight60Pixels.png`| 60             | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="60 像素 DataBar Omni‑directional 條碼"} |

兩張圖片皆為符合 GS1‑128 標準的 DataBar 條碼，可直接掃描。

## Step 7: Optional – Adjust additional visual settings

雖然主要目標是 **調整條碼大小**，您也可能想微調以下設定：

| 屬性 | 說明 | 典型值 |
|----------|-------------|----------------|
| `XDimension.Pixels` | 最窄條的寬度 | 1–4 |
| `BarHeight.Pixels`  | 整個條碼的高度 | 20–200 |
| `Resolution` | 點陣圖輸出的 DPI | 72, 150, 300 |
| `ForeColor` / `BackColor` | 前景與背景顏色 | `Color.Black`, `Color.White` |

範例：

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

這些微調不會影響 **resize** 邏輯，但能讓您完整掌控最終影像品質。

## Common pitfalls and how to avoid them

| 問題 | 徵狀 | 解決方案 |
|-------|---------|-----|
| 條碼高度未變化 | 儲存的影像看起來相同 | 確保在每次 `Save` 呼叫 *之前* 修改 `barcode.Parameters.Barcode.BarHeight.Pixels`。 |
| 條碼變得無法辨識 | 掃描器回報「無法讀取」 | 對 DataBar Omni‑directional 保持 `XDimension` ≥ 2 px，過細的條會影響掃描。 |
| PNG 檔案模糊 | 以低 DPI 匯出 | 將 `barcode.Parameters.ImageResolution.DpiX/Y` 設為至少 150，以取得列印品質的影像。 |
| 檔案不小心被覆寫 | 新影像取代舊檔 | 使用唯一的檔名或在檔名中加入高度值，如上例所示。 |

## Full, runnable example

將以下完整程式碼複製到新的 Console 應用程式（`Program.cs`）中。程式碼即可編譯執行，並在專案輸出資料夾產生兩個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

執行程式後會產生：

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

檢查輸出資料夾，即可看到兩個 PNG 檔案。它們皆可直接列印、嵌入 PDF，或傳送至遠端裝置使用。

## Conclusion

本指南說明了如何在 C# 中使用 Aspose.BarCode **調整條碼大小**，示範完整的 **條碼產生器範例**，並展示如何在不同高度 **匯出條碼影像** 檔案。您現在已掌握：

1. **建立 Databar 條碼** 物件並自訂資料。  
2. 調整 `BarHeight`（即調整大小的核心）。  
3. 以任意尺寸匯出 PNG 檔案。  

接下來您可以探索更多客製化——不同的符號系統、配色方案，或 SVG 等向量格式。相同的模式 (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) 亦適用於 Aspose.BarCode 支援的任何條碼類型，讓您能自信地將 **調整條碼大小** 的知識應用於整個應用程式。

---

**Next steps**

- 嘗試調整其他符號系統（QR、Code128）的尺寸，觀察高度與寬度的互動。  
- 使用 `BarCodeImageFormat.Svg` 產生可於網頁使用的可縮放向量圖形。  
- 將產生的影像整合至 PDF 報表，使用 Aspose.PDF 或 iTextSharp。  

祝程式開發順利，盡情體驗程式化條碼產生所帶來的彈性！

## What Should You Learn Next?

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生並調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何使用 Aspose.BarCode 產生條碼 – Code 39 設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}