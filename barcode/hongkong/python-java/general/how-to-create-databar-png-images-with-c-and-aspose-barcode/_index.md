---
category: general
date: 2026-08-19
description: 使用 Aspose.BarCode 在 C# 中建立 databar PNG 檔案。了解如何產生 databar 圖像、設定 databar
  參數，並儲存 PNG 輸出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: zh-hant
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 在 C# 中建立 DataBar PNG 檔案。本教學將逐步說明如何產生 DataBar 圖像、設定
  DataBar 參數（如 X 尺寸與長寬比），以及將高品質 PNG 檔案儲存供列印或網頁使用。
og_image_alt: create databar PNG example
og_title: 在 C# 中建立 DataBar PNG 圖像 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: 如何使用 C# 與 Aspose.BarCode 建立 DataBar PNG 圖像
url: /zh-hant/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 與 Aspose.BarCode 建立 databar PNG 圖片

如果您需要在 .NET 應用程式中 **建立 databar PNG** 檔案，本指南將逐步說明。您將看到一個完整、可執行的範例，產生堆疊全方向 DataBar 條碼、設定關鍵參數，並以不同長寬比儲存兩個 PNG 檔案。

產生 DataBar 圖片不只是呼叫單一方法。您還必須 **設定 databar 參數**，例如 X‑dimension（模組寬度）與長寬比，以符合列印或掃描規格。完成本教學後，您將了解 **如何產生 databar** 圖形，並能在實務情境中可靠運作。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 執行）
- Visual Studio 2022 或任何相容 C# 的 IDE
- 有效的 **Aspose.BarCode for .NET** 授權（免費評估版可用於測試）
- 基本的 C# 語法熟悉度

> **專業提示：** 若您尚未取得授權，可從 Aspose 入口網站申請暫時的評估金鑰。API 行為相同，僅會顯示浮水印。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在 Visual Studio 中開啟您的專案，於解決方案上點右鍵，選取 **Manage NuGet Packages**。搜尋 `Aspose.BarCode` 並安裝最新的穩定版。

```bash
dotnet add package Aspose.BarCode
```

此指令會將 `Aspose.BarCode` 程式集加入您的專案，並使 `BarcodeGenerator` 類別可用。

## 步驟 2：為堆疊全方向 DataBar 初始化條碼產生器

`BarcodeGenerator` 建構子接受兩個參數：條碼類型與原始資料字串。若要產生堆疊全方向 DataBar，請使用 `EncodeTypes.DatabarStackedOmniDirectional`。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**為何重要：** `EncodeTypes.DatabarStackedOmniDirectional` 常數告訴函式庫產生可從任何方向讀取的條碼，這對零售貨架標籤而言相當理想。

## 步驟 3：以像素設定 X‑dimension（模組寬度）

X‑dimension 控制最小條紋元素的大小。以像素設定可讓您精確掌握最終影像尺寸。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**2 像素**的數值在大多數標籤印表機上兼具可讀性與緊湊性。如需較大或較小的模組，可自行調整此數值。

## 步驟 4：設定第一個長寬比並儲存 PNG

長寬比會影響堆疊 DataBar 的高度。長寬比為 **15** 時會產生相對較短的條碼，而 **30** 則會使其較高。

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 方法會將產生的條碼寫入 PNG 檔案。PNG 為無損格式，可保留條碼掃描器所需的清晰邊緣。

## 步驟 5：變更長寬比並儲存第二個 PNG

您只需變更長寬比，即可重複使用相同的 `BarcodeGenerator` 實例產生不同變化。

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

現在您擁有兩個 PNG 檔案 — `DatabarAspectRatio15.png` 與 `DatabarAspectRatio30.png`，它們的視覺密度各不相同。

## 步驟 6：驗證輸出結果

在任何影像檢視器中開啟產生的 PNG 檔案。您應該會看到清晰、高對比度的 DataBar 條碼。使用智慧手機條碼掃描器掃描圖像，可確認兩種長寬比皆能正確解碼為原始 GTIN 值 `12345678901231`。

![create databar PNG example](databar_example.png)

*上圖顯示兩個 PNG 檔案並排比較。左側圖像使用長寬比 15，右側使用長寬比 30。*

## 常見變形與邊緣情況

| Scenario | What to change | Reason |
|----------|----------------|--------|
| **不同資料** | Replace the string `(01)12345678901231` with any valid GS1 Application Identifier and data | 允許您編碼產品編號、序號等 |
| **更高解析度** | Increase `XDimension.Pixels` to 3 or 4 | 當條碼需以較大尺寸列印或遠距離掃描時需要 |
| **其他 DataBar 類型** | Use `EncodeTypes.DatabarStacked` or `EncodeTypes.DatabarExpanded` | 選擇最適合您標籤版面的類型 |
| **透明背景** | Pass `BarCodeImageFormat.Png` with `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | 適用於將條碼覆蓋於彩色標籤上 |

> **注意：** 設定過小的 X‑dimension（< 1 像素）可能會產生模糊的條碼，導致

## 接下來您應該學習什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [使用 Aspose.BarCode 建立一維 Databar GS1 編碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [使用 .NET API 產生 Aspose.BarCode Databar 條碼 – 行與列配置](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}