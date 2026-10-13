---
category: general
date: 2026-10-02
description: 快速在 C# 中建立堆疊資料條碼。學習設定 XDimension、調整長寬比，並使用條碼產生器匯出 PNG 圖片。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: zh-hant
lastmod: 2026-10-02
og_description: 在 C# 中建立堆疊資料條碼，提供完整程式範例。調整 XDimension、變更長寬比，僅需幾行程式即可儲存 PNG 檔案。
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: 在 C# 中建立堆疊式資料條碼 – 快速教學
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: 在 C# 中建立堆疊資料條碼 – 逐步指南
url: /zh-hant/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立堆疊式 DataBar 條碼 – 步驟說明指南

如果您需要在 .NET 專案中**建立堆疊式 DataBar 條碼**，本教學將逐步說明。您將會看到如何設定 X‑dimension、切換長寬比，並以 PNG 檔案儲存結果——全部使用 Aspose.BarCode 函式庫。

產生堆疊式 DataBar 條碼不需要複雜的圖形流程。完成本指南後，您將擁有兩張可直接使用的 PNG 圖片，示範不同的長寬比，並了解這些參數對掃描可靠性的影響。

## 您需要的環境

- .NET 6.0 或更新版本（程式碼亦相容 .NET Framework 4.6+）
- Visual Studio 2022 或任何 C# IDE
- **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- 具備寫入 PNG 檔案之資料夾的寫入權限

## 步驟 1：設定專案並匯入命名空間

建立一個新的主控台應用程式（或將程式碼加入現有專案），並匯入所需的命名空間：

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **為什麼這很重要：** `Aspose.BarCode.Generation` 提供 `BarcodeGenerator` 類別，而 `Aspose.BarCode` 包含用於儲存影像的 `BarCodeImageFormat` 列舉。

## 步驟 2：為堆疊式全方向 DataBar 初始化產生器

`EncodeTypes.DatabarStackedOmniDirectional` 會選擇堆疊式 DataBar 符號。資料字串必須符合 GS1 應用識別碼 (AI) 格式；此處使用一個虛擬的 GTIN‑14 值。

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **為什麼這很重要：** 所選的編碼類型告訴函式庫產生*堆疊*條碼，這在垂直空間受限的高密度標籤上至關重要。

## 步驟 3：以像素定義模組 (X‑dimension) 大小

X‑dimension 控制最小條紋（即「模組」）的寬度。2 像素的值對大多數螢幕解析度的輸出而言相當適合。

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **為什麼這很重要：** 掃描器將模組寬度視為基本測量單位。過小會導致印刷模糊，過大則浪費空間。

## 步驟 4：以長寬比 15 儲存第一張影像

`AspectRatio` 屬性影響每個堆疊區段的高寬比例。長寬比 15 是零售應用的常見預設值。

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **為什麼這很重要：** 較低的長寬比會產生較平坦的條碼，對某些標籤材質而言較易掃描。PNG 格式保留無損品質，適合測試使用。

## 步驟 5：將長寬比改為 30 並儲存第二張影像

提升長寬比會使每個堆疊區段變得更高，這可提升在低對比度背景上的掃描可靠性。

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **為什麼這很重要：** 不同零售商或物流夥伴可能要求特定的條碼尺寸。提供兩個版本可讓您快速比較掃描效能。

## 完整、可執行的範例

以下是完整程式碼，您可以直接複製貼上至 `Program.cs`。安裝 Aspose.BarCode NuGet 套件後，即可編譯執行，無需其他修改。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### 預期輸出

執行程式後會在執行目錄產生兩個檔案：

| 檔案名稱 | 長寬比 | 視覺說明 |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | 較短且較平坦的堆疊條碼 |
| `DatabarAspectRatio30.png`    | 30           | 較高且較細長的堆疊條碼 |

![Create stacked databars barcode example](placeholder-image.png){alt="建立堆疊式 DataBar 條碼範例"}

## 常見問題與邊緣情況

| 問題 | 答案 |
|----------|--------|
| **我可以使用不同的 X‑dimension 嗎？** | 可以。典型值介於 1 到 4 像素。較大的值會使條碼尺寸增大，但在低解析度印表機上可能提升可讀性。 |
| **如果需要不同的符號集該怎麼辦？** | 將 `EncodeTypes.DatabarStackedOmniDirectional` 替換為其他 `EncodeTypes` 值，例如 `DatabarStacked`（非全方向）或 `DatabarLimited`。 |
| **如何變更輸出格式？** | 在 `Save` 呼叫中使用 `BarCodeImageFormat.Jpeg`、`Gif` 或 `Bmp`。 |
| **GTIN‑14 格式是必須的嗎？** | DataBar 符號需要以適當的 AI 為前綴的數字字串（例如 `(01)` 代表 GTIN‑14）。請依您的使用情境調整資料。 |
| **DPI 設定怎麼處理？** | 產生器會遵循 `Resolution` 屬性。若需高解析度列印，請相應設定 `barcodeGen.Parameters.ImageResolution.DpiX` 與 `DpiY`。 |

## 專業技巧

- **批次產生：** 將儲存邏輯包在迴圈中，並提供 GTIN 清單，以自動產生數千個條碼。
- **驗證：** 在儲存前使用 `barcodeGen.Validate()` 以提前捕捉格式錯誤的資料。
- **效能：** 重複使用同一個 `BarcodeGenerator` 實例（僅變更參數）比每張影像重新建立物件更快。

## 後續步驟

既然您已能以自訂長寬比**建立堆疊式 DataBar 條碼**，接下來可探索以下方向：

- 在條碼下方加入可讀文字 (`barcodeGen.Parameters.Barcode.CodeText`)。
- 匯出為 **PDF** 以製作可列印的標籤紙 (`BarCodeImageFormat.Pdf`)。
- 將產生器整合至 Web API，隨時提供條碼服務。
- 嘗試其他 **次要關鍵字** 如 *C# barcode generator* 與 *barcode aspect ratio*，以針對特定硬體微調實作。

祝程式開發順利，盡情體驗 Aspose.BarCode 為您的 C# 條碼專案帶來的彈性！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [在 C# 中建立堆疊式 DataBar 條碼 – 步驟說明指南](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [C# 中的堆疊式全方向 DataBar 條碼 – 完整指南](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [如何使用 C# 及 Aspose.BarCode 建立 DataBar PNG 圖片](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}