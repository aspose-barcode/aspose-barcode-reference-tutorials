---
category: general
date: 2026-09-26
description: 快速學習如何在 C# 中建立 Planet 條碼。本指南涵蓋實心與空心 Planet 條碼、X 尺寸設定以及圖像匯出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: zh-hant
lastmod: 2026-09-26
og_description: 使用 C# 建立 Planet 條碼，提供完整程式範例。產生實心與空心的 Planet 條碼，設定條寬，並儲存為 PNG。
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: 在 C# 中創建行星條碼圖像 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 BarcodeGenerator 建立 planet 條碼圖像
url: /zh-hant/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarcodeGenerator 建立 Planet 條碼圖像

如果您需要在 .NET 應用程式中**建立 Planet 條碼**圖像，本教學將示範完整步驟。您將學會產生實心與空白的 Planet 條碼、調整條寬，並以 PNG 檔案匯出——全部使用 Aspose.BarCode for .NET 函式庫。

只要了解關鍵的**條碼產生器參數**，產生**Planet 條碼 C#**解決方案就相當簡單。以下各節將逐步說明完整可執行的程式碼、每個設定的意義，並指出常見陷阱，讓您一次成功。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本。
* Visual Studio 2022（或您慣用的 C# IDE）。
* 已在專案中加入 **Aspose.BarCode for .NET** NuGet 套件（`Aspose.BarCode`）。

您可以透過 NuGet 套件管理員主控台加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：設定 BarcodeGenerator

`BarcodeGenerator` 類別是所有條碼產生工作的入口點。它需要兩個參數：條碼類型（`EncodeTypes.Planet`）與要編碼的資料。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*為什麼重要*：以 `EncodeTypes.Planet` 建立產生器，會告訴函式庫使用 **Planet 條碼** 符號，這在某些國家的郵務服務中相當常見。字串 `"123456"` 即為將顯示於條碼中的資料。

## 步驟 2：設定 X‑dimension（條寬）

X‑dimension 控制每根條的實體寬度。螢幕顯示的常見值為 4 像素，您也可以依列印需求自行調整。

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*為什麼重要*：設定 `XDimension.Pixels` 可確保產生的條碼既不會太細（導致掃描失敗），也不會太粗（浪費空間）。此設定稍後也會用於空白條碼。

## 步驟 3：儲存實心 Planet 條碼

使用 `Save` 方法將條碼匯出為 PNG 檔案。`BarCodeImageFormat.Png` 列舉表示產生無損影像，適合後續處理。

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

執行程式後，您會在輸出資料夾中看到 `PostalPlanetFilledBars.png`。開啟檢查，條碼應為實心（已填滿）。

## 步驟 4：建立空白 Planet 條碼的產生器

**空白 planet 條碼**會顯示相同資料，但條是未填滿（白色）的。這在需要將條碼覆蓋於彩色背景的視覺設計時很有用。

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

建構子呼叫與實心版本相同，差異在於接下來要變更的參數。

## 步驟 5：重新使用相同的 X‑dimension

為了保持視覺尺寸一致，將相同的條寬套用到空白條碼。

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

重複使用**條碼產生器參數**可保證兩張圖像並排時完全對齊。

## 步驟 6：切換為未填滿的條

`FilledBars` 旗標決定條是以實心黑色（預設）還是透明白色呈現。

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*為什麼重要*：將 `FilledBars = false` 會切換渲染模式，這正是實心與空白 Planet 條碼的關鍵差別。

## 步驟 7：儲存空白 Planet 條碼

最後，將空白版本匯出為 PNG。

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

執行程式後，會產生兩個檔案：

* `PostalPlanetFilledBars.png` – 實心黑條。
* `PostalPlanetEmptyBars.png` – 透明（未填滿）條。

兩張圖像皆使用相同資料（`123456`）且 X‑dimension 相同，因而在大多數 UI 場景中可互換使用。

## 完整、可執行範例

將以下程式碼全部貼入新建的 Console 專案，即可直接執行：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**預期輸出**

執行程式後，執行檔所在目錄會產生兩個 PNG 檔。使用任意影像檢視器開啟：

* **實心版** – 深色、實心條，標準掃描器易於辨識。
* **空白版** – 條呈白色間隙於黑色背景，適合做覆蓋效果。

## 常見問題與進階小技巧

| 問題 | 為什麼會發生 | 解決方法 |
|------|--------------|----------|
| 條太細 | X‑dimension 保持預設（1 像素） | 將 `XDimension.Pixels` 設為 3‑5 像素以供螢幕使用；列印時可再提升。 |
| 空白條碼全黑 | 未將 `FilledBars` 設為 `false` | 確保在設定 X‑dimension 後執行 `emptyPlanet.Parameters.Barcode.FilledBars = false;` |
| PNG 檔案遺失 | 輸出路徑錯誤或目錄不存在 | 提供完整路徑（`@"C:\Barcodes\PostalPlanetFilledBars.png"`）或先以 `Directory.CreateDirectory` 建立目錄。 |
| 條碼掃描失敗 | 資料字串含有 Planet 符號不允許的字元 | Planet 條碼僅接受數字；可使用 `int.TryParse` 進行驗證。 |

**進階小技巧**：若需將條碼嵌入 PDF，可使用 Aspose.PDF 讀取產生的 PNG，或直接以影像串流方式加入 PDF，無需先寫入磁碟。

## 後續步驟

既然已能**建立 planet 條碼**圖像，您可以進一步探索以下相關主題：

* **Planet 條碼 C#** – 客製化顏色、加入可讀文字，或直接嵌入 PDF。
* **條碼產生器參數** – 微調錯誤更正等級、靜區或旋轉角度。
* **批次產生** – 迭代郵遞區號清單，產出 PNG 壓縮檔。
* **其他格式** – 匯出為 SVG 或 JPEG，以符合網路傳遞需求。

嘗試不同的 `XDimension` 數值與 `FilledBars` 旗標，觀察它們對掃描可靠度與視覺風格的影響。準備好後，可將產生程式碼整合至 Web API 或桌面應用程式，實時自動化產生郵務條碼。

---


## 接下來該學什麼？

以下教學與本指南緊密相關，能幫助您進一步掌握 API 功能並探索其他實作方式：

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}