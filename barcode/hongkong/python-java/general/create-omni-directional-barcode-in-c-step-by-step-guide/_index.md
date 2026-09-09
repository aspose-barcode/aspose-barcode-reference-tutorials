---
category: general
date: 2026-07-15
description: 使用 Aspose.BarCode 在 C# 中快速建立全方向條碼 – 學習如何在 C# 生成可調整條碼高度與 X 尺寸的條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: zh-hant
lastmod: 2026-07-15
og_description: 使用 Aspose.BarCode 在 C# 中建立全方向條碼。掌握透過調整 XDimension 與 BarHeight 於 C#
  產生完美條碼的技巧。
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: 在 C# 中建立全向條碼 – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: 在 C# 中創建全方位條碼 – 步驟教學
url: /zh-hant/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立全方向條碼 – 步驟指南

有沒有想過如何在 C# 中產生符合 GS1 DataBar Omni‑Directional 符號規範的條碼？你並不孤單。在本教學中，我們將**建立全方向條碼**圖像，從頭開始調整 X‑dimension，並玩轉條碼高度——全部使用 Aspose.BarCode 函式庫。

我們將以真實情境說明：您需要一個緊湊且高密度的條碼用於零售標籤，且希望完全掌控其視覺尺寸。完成後您將擁有兩個 PNG 檔案——一個條碼高度為 30 px，另一個為 60 px——即可直接投入任何列印工作流程。

## 先決條件

- 已在機器上安裝 .NET 6（或任何近期的 .NET 執行環境）。  
- Visual Studio 2022 或 VS Code——您喜愛的 IDE 均可。  
- 免費的 Aspose.BarCode for .NET NuGet 套件（`Aspose.BarCode`）。

不需要其他相依性。如果您從未使用過 NuGet，只需開啟套件管理員主控台並執行以下指令：

```powershell
Install-Package Aspose.BarCode
```

## 建立全方向條碼 – 基礎概念

**GS1 DataBar Omni‑Directional** 符號設計可在任何方向掃描，十分適合貨架邊緣標籤。當您呼叫 `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` 時，函式庫會自行完成繁重工作：編碼資料、套用符號規則，並產生點陣圖像。

> **專業提示：** 總是將原始資料包裝在適當的應用程式識別碼 (AI) 格式，例如 GTIN‑14 的 `"(01)12345678901231"`。這會告訴掃描器這些數字的意義。

## 步驟 1 – 設定條碼產生器 (how to generate barcode c#)

首先我們建立產生器物件。這是使用 Aspose 進行 **how to generate barcode c#** 的基礎。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 列舉值告訴引擎使用哪種符號。第二個參數是已包裝在 GTIN AI 中的原始資料字串。

## 步驟 2 – 調整 X‑Dimension (barcode XDimension)

**barcode XDimension** 控制最小條的寬度。對於大多數標籤印表機而言，2 px 是可讀性與緊湊性的良好平衡。

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

如果需要更細或更粗的外觀，只要更改數值即可。請記住：X‑dimension 是基本單位；所有其他條寬都是此值的倍數。

## 步驟 3 – 建立第一張 30 px 條高的影像 (barcode BarHeight)

現在我們將 **barcode BarHeight** 設為 30 px 並儲存影像。這會產生尺寸適中的條碼，能很好地適配標準標籤。

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` 方法會將 PNG 檔寫入磁碟。若偏好 JPEG 輸出，可改用 `BarCodeImageFormat.Jpeg`。

## 步驟 4 – 將條高提升至 60 px 以適用較大標籤 (barcode BarHeight)

有時需要較大的條碼——例如放置在離掃描器較遠的貨架標籤。讓我們將高度加倍。

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

請注意，我們 **不需要** 重新建立產生器；只要調整參數並重複使用同一物件即可。這樣可節省記憶體並保持程式碼整潔。

## 步驟 5 – 儲存第二張影像 (how to generate barcode c#)

最後，我們儲存第二張 PNG。現在您有兩個檔案，唯一差異在於條高。

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### 預期輸出

- `DatabarBarHeight30Pixels.png` – 高度為 30 px 的全方向條碼。  
- `DatabarBarHeight60Pixels.png` – 相同資料，但條高為 60 px。

在任何影像檢視器中開啟檔案，即可看到清晰、可掃描的條紋，符合 GS1 DataBar Omni‑Directional 規範。

## 常見問題與邊緣情況

### 如果需要不同的 X‑dimension 該怎麼辦？

只要在呼叫 `Save` 前指派新值即可。若需超高密度列印，可降至 1 px，但請先以掃描器測試——有些裝置在低於 2 px 的條寬上會有困難。

### 可以在條碼下方加入可讀文字嗎？

可以。將 `barcodeGenerator.Parameters.Barcode.CodeText` 設為字串，並可選擇將 `barcodeGenerator.Parameters.Barcode.CodeLocation` 調整為 `BarCodeTextLocation.Below`。這在零售環境中需要顯示數字 GTIN 時非常方便。

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### PNG 是列印的最佳格式嗎？

PNG 為無損格式，能保留條碼掃描器所需的銳利邊緣。若下游系統需要其他格式（TIFF、BMP），只要更改 `BarCodeImageFormat` 列舉即可。

## 完整範例 (create omni-directional barcode)

以下是完整、可直接執行的程式。將其複製貼上至新的主控台專案，然後按 **F5**。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

執行程式，檢查輸出資料夾，即可看到如前所述的兩個 PNG 檔案。

## 重點回顧

我們示範了使用 Aspose.BarCode 產生 **how to generate barcode C#** 程式碼，建立 **create omni-directional barcode**。透過調整 **barcode XDimension** 與 **barcode BarHeight**，您可精細控制視覺尺寸，同時不影響掃描可靠性。

## 接下來的步驟

- 嘗試其他 **GS1 DataBar Omni-Directional** 設定，如 `Color` 或 `Margin`。  
- 使用 `Graphics` 在單一畫布上結合多個條碼，以製作複雜的標籤設計。  
- 將產生器整合至 Web API，讓您的電商平台能即時產生條碼。

有任何想法想分享嗎？留下評論，讓我們持續交流。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何產生條碼 – Code 39 設定與 Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼靜區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}