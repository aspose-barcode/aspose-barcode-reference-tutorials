---
category: general
date: 2026-08-03
description: 在 C# 中建立條碼 PNG，並學習如何調整 DataBar 圖像的長寬比。跟隨此完整範例，內含程式碼與技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: zh-hant
lastmod: 2026-08-03
og_description: 在 C# 中建立條碼 PNG，並了解如何調整 DataBar 條碼的長寬比。本指南提供可直接執行的程式碼與實用技巧。
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: 在 C# 中建立條碼 PNG – 完整範例與長寬比控制
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: 在 C# 中建立條碼 PNG – 逐步指南
url: /zh-hant/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立條碼 PNG – 步驟指南

如果您需要 **在 C# 中建立條碼 PNG**，本教學會一步一步示範。您將產生一個堆疊式全向 DataBar 條碼，將其儲存為 PNG 檔案，並學習 **如何調整長寬比** 以符合不同的掃描環境。

本指南涵蓋您所需的一切：必要的套件、完整可執行的程式碼，以及每個設定為何重要的說明。完成後，您將得到兩個 PNG 檔案——一個長寬比為 15，另一個為 30——可直接用於測試或正式環境。

## 前置條件

開始之前，請確保您已具備：

- .NET 6.0 SDK 或更新版本
- Visual Studio 2022（或任何 C# IDE）
- 已加入 **Aspose.BarCode** 的 NuGet 參考（提供 `BarcodeGenerator` 的函式庫）
- 有寫入 PNG 檔案所在目錄的權限

您可以使用以下指令加入 Aspose.BarCode 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立專案並匯入命名空間

建立一個新的主控台應用程式，並匯入產生條碼與檔案 I/O 所需的命名空間。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**為什麼這很重要：** 匯入 `Aspose.BarCode.Generation` 後即可使用 `BarcodeGenerator`。將程式碼寫在 `Main` 內，使範例自成一體且易於執行。

## 步驟 2：為堆疊式全向 DataBar 建立條碼產生器

以 `EncodeTypes.DatabarStackedOmniDirectional` 類型以及範例 GS1‑128 資料字串實例化 `BarcodeGenerator`。

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**為什麼這很重要：** 選擇此編碼類型可產生高密度 DataBar，能被大多數現代掃描器讀取。資料字串遵循 GS1 應用識別碼 (01) 格式，常用於商品識別。

## 步驟 3：以像素定義 X‑dimension（模組寬度）

設定模組寬度，以控制條碼的整體尺寸，同時不影響可讀性。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼這很重要：** X‑dimension 設為 2 像素，可讓條碼既不會太小而無法被掃描，也不會太大而佔用過多標籤空間。

## 步驟 4：以長寬比 15 儲存第一個 PNG

調整 DataBar 的長寬比，然後將影像儲存為 PNG 檔案。

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**為什麼這很重要：** 長寬比決定堆疊 DataBar 的高寬比例。15 是常見的預設值，能在可讀性與標籤高度之間取得平衡。

## 步驟 5：將長寬比改為 30 並儲存第二個 PNG

對同一個產生器實例修改為較大的長寬比，然後儲存第二張影像。

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**為什麼這很重要：** 提高長寬比會使條碼在垂直方向上拉長，對低解析度裝置或在窄幅媒介上列印的標籤，可提升掃描可靠性。

## 預期輸出

執行程式後會產生兩個 PNG 檔案：

| 檔案名稱                           | 長寬比 | 大約尺寸（像素）                |
|------------------------------------|--------|---------------------------------|
| `DatabarAspectRatio15.png`         | 15     | 200 × 300（寬 × 高）            |
| `DatabarAspectRatio30.png`         | 30     | 200 × 600（寬 × 高）            |

兩張影像皆包含清晰且可掃描的 DataBar 條碼，編碼的 GS1 識別碼為 `(01)12345678901231`。

## 常見問題與邊緣案例

### 如何變更其他視覺屬性？

您可以透過 `generator.Parameters.Barcode` 物件調整前景色、背景色，或加入可讀文字。例如：

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### 若需要其他影像格式該怎麼做？

將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif` 即可。PNG 仍是條碼影像的最佳無損選擇。

### 長寬比會影響掃描速度嗎？

較高的長寬比會增加條碼高度，對於難以辨識短堆疊符號的裝置，可提升掃描可靠性。但過高的條碼可能無法放入小尺寸標籤，請以目標硬體進行測試。

### 能否在迴圈中產生多筆條碼？

可以。為每筆資料字串建立新的 `BarcodeGenerator` 實例，或在同一實例上更新 `CodeText` 與 `DataBar.AspectRatio` 後重複使用。此作法可減少物件分配的開銷。

## 專業小技巧

- **重複使用產生器**：只變更 `CodeText` 或 `AspectRatio`，即可避免重新實例化物件，提升批次處理效能。
- **驗證輸出**：使用手持掃描器或行動應用程式確認產生的 PNG 能正確讀取，才上線投入正式環境。
- **檔名命名**：如範例所示，將長寬比寫入檔名，方便在測試期間追蹤不同變體。

## 結論

現在您已掌握如何在 C# 中 **建立條碼 PNG**，以及如何 **精確調整堆疊式全向 DataBar 的長寬比**。完整範例示範了初始化、X‑dimension 設定、長寬比調整與影像儲存，全部集中於一個可直接執行的程式。

接下來，您可以探索其他條碼類型、嘗試顏色變化，或將產生器整合至更大的報表或庫存系統。祝開發順利！

## 接下來該學什麼？

以下教學與本指南的技巧密切相關，提供完整可執行的程式碼範例與逐步說明，協助您深入掌握其他 API 功能，或在專案中嘗試不同的實作方式。

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}