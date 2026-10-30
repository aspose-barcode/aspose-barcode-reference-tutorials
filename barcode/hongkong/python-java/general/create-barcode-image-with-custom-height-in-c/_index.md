---
category: general
date: 2026-10-28
description: 在 C# 中建立條碼圖像，並學習如何使用 BarcodeGenerator API 調整高度。一步一步的指南，教你自訂條碼高度及變更條碼線條高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: zh-hant
lastmod: 2026-10-28
og_description: 在 C# 中建立條碼影像，並立即了解如何調整高度。請參考此完整範例，使用 BarcodeGenerator 設定自訂條碼高度。
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: 在 C# 中建立自訂高度的條碼圖像 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: 在 C# 中建立自訂高度的條碼圖像
url: /zh-hant/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立自訂高度的條碼影像

如果您需要**建立條碼影像**並控制其尺寸，本指南將會一步步說明。使用 Aspose.BarCode .NET 函式庫，您可以產生 GS1‑Databar Omni‑Directional 條碼，並**調整高度**以符合任何版面需求。

您將會透過一個完整且可執行的程式，示範**c# barcode generator**的使用方式，說明每個屬性的設定，並展示兩種不同的輸出——一個條高為 30 像素，另一個條高為 60 像素。完成後，您即可以程式方式**變更條碼高度**，適用於函式庫支援的任何條碼類型。

## 前置條件

- .NET 6.0 SDK 或更新版本（程式碼亦可於 .NET Framework 4.6+ 執行）
- Visual Studio 2022 或任何能編譯 C# 專案的編輯器
- Aspose.BarCode for .NET NuGet 套件（`Install-Package Aspose.BarCode`）
- 具備基本的 C# 語法知識

> **專業提示：** 若您使用 CI 流程，請將 NuGet 套件加入 `csproj` 檔案，讓建置自動還原。

## Step 1: 設定專案並匯入命名空間

建立一個新的 console 專案，並加入必要的 `using` 陳述式。這些命名空間讓您可以存取 `BarcodeGenerator`、`EncodeTypes` 以及影像格式輔助工具。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **為什麼這很重要：** 匯入正確的命名空間可避免編譯時錯誤，且讓 API 在 IntelliSense 中可被發現。

## Step 2: 為 GS1‑Databar Omni‑Directional 代碼初始化 **c# barcode generator**

建構子接受兩個參數：條碼類型 (`EncodeTypes.DatabarOmniDirectional`) 與資料字串。資料字串必須遵循 GS1 應用識別碼格式，例如 `(01)12345678901231`。

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **說明：** `BarcodeGenerator` 物件是所有條碼相關設定的入口。取得此實例後，您即可調整尺寸、顏色與輸出格式。

## Step 3: 定義共用的 X‑dimension（最窄條的像素寬度）

2 像素的 X‑dimension 是大多數螢幕顯示情境的良好起點。

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **為什麼要設定 X‑dimension？** 它控制條碼的整體寬度。保持一致可確保變更條高時不會扭曲視覺平衡。

## Step 4: **建立條碼影像**，條高為 30 像素

現在我們設定條高，儲存第一張影像，然後再變更條高產生第二張。

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **結果：** 您會得到一個 PNG 檔案，裡面的每根垂直條皆為 30 像素高。X‑dimension 仍為 2 像素，整體寬度不變。

## Step 5: **如何調整高度** – 將條高改為 60 像素

為了示範**自訂條碼高度**，只需將相同屬性賦予新值，再次儲存即可。

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **關鍵洞見：** `BarHeight` 屬性是可變的；您不必重新建立 `BarcodeGenerator` 實例。這讓在迴圈或批次處理中產生多種尺寸變得非常輕鬆。

## Step 6: 驗證輸出

執行 console 程式（`dotnet run`）。執行完畢後，您應該會在專案的輸出資料夾看到兩個 PNG 檔案：

- `DatabarBarHeight30Pixels.png` – 短條 (30 px)
- `DatabarBarHeight60Pixels.png` – 長條 (60 px)

兩張影像編碼的資料相同，但視覺高度不同，這在將條碼整合至表單、產品標籤或 UI 元件且空間限制不同時相當有用。

![建立自訂高度的條碼影像](barcode-example.png){.align-center width="600" alt="建立自訂高度的條碼影像"}

> **提示：** 用任何影像檢視器開啟 PNG 檔案。較高的條碼應正好是較短條碼垂直尺寸的兩倍，而水平間距保持相同。

## Step 7: 常見變化與例外情況

| 情況 | 建議設定 |
|-----------|---------------------|
| **在高解析度標籤印表機上列印** | 使用較大的 X‑dimension（例如 4 px），並相應增加 `BarHeight`。 |
| **在低 DPI 螢幕上顯示** | 將 `XDimension` 保持在 1 px，`BarHeight` 設為 20‑40 px 以確保可讀性。 |
| **產生 QR Code 或 2‑D 條碼** | `BarHeight` 屬性會被忽略；請使用 `EncodeTypes.QR` 並改以調整 `ImageHeight`。 |
| **批次產生多種高度** | 遍歷高度陣列，在迴圈內呼叫 `Save`；不必在每次迭代時重新建立產生器。 |

### 處理無效的高度

若將 `BarHeight` 設為非正值，函式庫會拋出 `ArgumentOutOfRangeException`。可使用簡單檢查來防止此情況：

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## 完整原始碼（可直接複製）

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **為什麼這樣可行：** 所有必要的設定（`EncodeTypes`、`XDimension`、`BarHeight`）皆在每次 `Save` 呼叫前完成。同一個 `BarcodeGenerator` 實例被重複使用，既省記憶體又易於閱讀。

## 結論

您現在已掌握如何在 C# 中**建立條碼影像**檔案，並透過 `BarcodeGenerator` API 精確**變更條碼高度**。只要調整 `BarHeight.Pixels`，即可取得**自訂條碼高度**，無需重新建立產生器，這使得解決方案非常適合動態標籤製作、UI 呈現或批次處理流程。

接下來，您可以探索如**調整寬度**、**加入可讀文字**，或**匯出為 SVG 以供網頁彈性使用**等相關主題。相同的模式——設定屬性、呼叫 `Save`——在這些情境下同樣適用，讓您能自信地擴充此範例。

## 接下來您可以學習什麼？

以下教學與本指南所示技巧密切相關，並在此基礎上進一步延伸。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中變更條碼高度 – 完整指南](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [條碼產生器範例 – 建立 Planet 與 RM4SCC 條碼並自訂高度](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [如何在 C# 中建立 rm4scc 條碼並控制其高度](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}