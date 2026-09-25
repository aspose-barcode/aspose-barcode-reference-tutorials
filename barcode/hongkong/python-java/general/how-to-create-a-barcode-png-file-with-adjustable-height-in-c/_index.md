---
category: general
date: 2026-08-19
description: 學習如何在 C# 中產生條碼 PNG 檔案並調整其高度，涵蓋如何輕鬆產生條碼圖像及變更條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: zh-hant
lastmod: 2026-08-19
og_description: 在 C# 中建立條碼 PNG 檔案，學習如何產生條碼圖像、調整條碼高度，以及更改條碼高度以獲得最佳掃描效果。
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: 在 C# 中建立條碼 PNG 檔案 – 步驟說明指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中建立可調整高度的條碼 PNG 檔案
url: /zh-hant/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立可調整高度的條碼 PNG 檔案

如果你需要在 C# 中建立 **barcode PNG file**，本指南將一步步說明。你將看到完整、可執行的範例，示範 **how to generate barcode** 圖片以及如何 **adjust barcode height** 以因應不同使用情境。

產生 barcode PNG file 是庫存系統、銷售點終端機以及任何需要列印或顯示機器可讀資料的應用程式的常見需求。完成本教學後，你將能夠變更條碼高度、儲存多個 PNG 檔案，並了解高度對掃描可靠性的影響。

## 前置條件

* 已安裝 .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 套件（範例程式碼使用此函式庫）  

你可以從指令列加入此套件：

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Aspose.BarCode 的免費評估版可用於開發與測試。正式環境請取得授權金鑰。

## 安裝條碼函式庫

第一步是在專案中參考此函式庫。於 C# 檔案的最上方加入以下 `using` 指令：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些命名空間讓你可以使用 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat`。

## 建立 barcode PNG 檔案

現在我們建立一個 `BarcodeGenerator` 實例，以產生 **barcode PNG file**。範例使用 Databar OmniDirectional 符號，但你可以將 `EncodeTypes.DatabarOmniDirectional` 替換為任何支援的類型。

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

字串 `"(01)12345678901231"` 符合 GS1 應用程式識別碼的 14 位 GTIN 格式。請依你的產品識別碼調整此資料。

## 設定 X‑dimension（可選）

X‑dimension 定義單一條碼模組的寬度。以像素為單位的數值可讓你精確控制影像大小。

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 像素的數值在大多數螢幕顯示上表現良好。若列印時需要較大的條碼，請將其調高。

## 調整條碼高度並儲存 barcode PNG 檔案

**BarHeight** 屬性控制條紋的垂直尺寸。變更此數值即可 **adjust barcode height**，且不會影響編碼資料。

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

檔案 `DatabarBarHeight30Pixels.png` 現在是一個高 30 像素的 **barcode PNG file**。

若要 **change barcode height** 並建立第二張影像，只需指定新數值再呼叫 `Save` 即可：

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

現在你擁有兩個 PNG 檔案——一個 30 px，另一個 60 px——示範如何即時 **adjust barcode height**。

### 為何條碼高度重要

* **Readability:** 掃描器需要最低高度才能可靠偵測。條碼過短可能被忽略，特別是在低解析度相機下。  
* **Aesthetics:** 將條碼高度與周圍設計元素匹配，可打造更整潔的 UI。  
* **Print constraints:** 某些標籤印表機的高度槽位固定，調整條碼高度可確保能夠放入。  

**Best practice:** 保持高度為 X‑dimension 的倍數（例如 X‑dimension 為 2 px 時，高度為 30 px），以維持比例並避免失真。

## 完整範例

以下是完整、獨立的程式碼，你可以直接貼到主控台應用程式中，即刻執行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**預期輸出**

執行程式會在可執行檔的工作目錄中產生兩個檔案：

* `DatabarBarHeight30Pixels.png` – 高 30 像素的 barcode PNG file  
* `DatabarBarHeight60Pixels.png` – 高 60 像素的 barcode PNG file  

使用任何影像檢視器開啟任一 PNG，你會看到清晰的 Databar OmniDirectional 條碼，已可供掃描。

## 邊緣情況與故障排除

| 情況 | 檢查項目 | 建議修正 |
|-----------|---------------|-----------------|
| 條碼模糊不清 | X‑dimension 對所選高度過低 | 將 `XDimension.Pixels` 提升（例如從 2 增至 3） |
| 掃描器在低高度條碼上失敗 | 高度低於掃描器的最小要求 | 將 `BarHeight.Pixels` 設為至少 30 px（或依掃描器規格） |
| PNG 檔案為空或損毀 | 輸出路徑無效或寫入權限被拒 | 使用絕對路徑或確保應用程式具有寫入權限 |
| 需要不同的符號系統 | 目前的 `EncodeTypes` 不適用 | 將 `EncodeTypes.DatabarOmniDirectional` 替換為其他列舉值（例如 `EncodeTypes.Code128`） |

## 常見問題

**Q: 我可以產生其他影像格式（JPEG、BMP）嗎？**  
A: 可以。將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp` 等。

**Q: 如何在網頁中嵌入 PNG？**  
A: 透過 HTTP 端點提供產生的 PNG，或將其轉換為 Base64 字串，放入 `<img>` 標籤的 `src` 屬性中。

**Q: 有辦法設定背景顏色嗎？**  
A: 使用 `generator.Parameters.Image.BackgroundColor = Color.White;`（或任意 `System.Drawing.Color`）。

## 結論

現在你已了解如何在 C# 中 **generate a barcode PNG file**，並精確 **adjust barcode height** 以符合掃描或設計需求。透過變更 `BarHeight.Pixels` 屬性，你可以即時 **change barcode height**，並從同一段程式碼產生多個 PNG 資產。

接下來，可探索其他自訂選項，如前景色、邊距，以及加入可讀文字。你也可以嘗試不同的符號系統（`EncodeTypes.Code128`、`EncodeTypes.QR`），以擴展可編碼的資料類型。

祝程式開發順利，願你的條碼一次即能成功掃描！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}