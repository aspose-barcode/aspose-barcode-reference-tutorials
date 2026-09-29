---
category: general
date: 2026-09-29
description: 如何使用 C# 設定 GS1 DataBar Omni‑Directional 條碼的寬度以及變更高度。請參考逐步說明及完整程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: zh-hant
lastmod: 2026-09-29
og_description: 如何在 C# 中設定 GS1 DataBar Omni‑Directional 條碼的寬度以及變更高度。了解精確的 API 呼叫，並查看完整可執行範例。
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: 如何設定 GS1 DataBar 條碼的寬度 – C# 教學
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: 如何在 C# 中設定 GS1 DataBar Omni‑Directional 條碼的寬度與高度
url: /zh-hant/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中設定 GS1 DataBar Omni‑Directional 條碼的寬度與調整高度

設定 GS1 DataBar Omni‑Directional 條碼的寬度是當您需要為掃描設備提供精確尺寸時的常見任務。在本教學中，您還會學習 **如何變更高度**，讓條碼完美符合您的版面配置。指南將一步步帶您完成整個流程，從專案設定到可直接執行的程式碼範例。

我們將涵蓋：

* 必要的 NuGet 套件與 .NET 版本。
* 為何 X‑dimension（模組寬度）對條碼可讀性至關重要。
* **設定寬度** 與 **變更高度** 的精確 API 呼叫方式。
* 最小模組寬度與高解析度渲染等邊緣案例處理。
* 完整的複製貼上範例，產生兩個不同條碼高度的 PNG 檔案。

## 前置條件

在開始之前，請確保您具備以下條件：

| Requirement | Reason |
|------------|--------|
| .NET 6.0 SDK 或更新版本 | 範例使用現代 C# 功能，且可在 Windows、Linux 或 macOS 上執行。 |
| Visual Studio 2022（或任何 C# IDE） | 提供 Aspose.Barcode API 的 IntelliSense 支援。 |
| **Aspose.Barcode for .NET** NuGet 套件 | 包含 `BarcodeGenerator`、`EncodeTypes` 以及影像格式支援。使用 `dotnet add package Aspose.Barcode` 安裝。 |
| 具寫入權限的資料夾（用於儲存 PNG 檔案） | 產生器會將輸出影像寫入磁碟。 |

## 如何設定條碼的寬度

**設定寬度** 的步驟是透過設定條碼參數的 `XDimension` 屬性來完成。`XDimension` 代表模組寬度（最小的條或空白），單位可以是像素、點或毫米。正確設定可確保條碼符合掃描器規格。

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### 為何 X‑dimension 重要

* **掃描器容差** – 大多數掃描器要求最小模組寬度；過小的值會導致讀取錯誤。  
* **列印解析度** – 以 300 dpi 列印時，2 px 模組約等於 0.17 mm，屬於 GS1 DataBar 推薦範圍。  
* **影像尺寸** – 較大的 X‑dimension 會增加條碼總寬度，可能影響版面限制。

### 設定寬度的可靠技巧

* **絕不要將 XDimension 設為低於 1 px** – 函式庫會自動限制此值，但產生的條碼可能無法辨識。  
* **配合目標 DPI** – 若渲染至高解析度格式（例如 600 dpi 的 TIFF），請相應提升 XDimension。  
* **使用實體掃描器測試** – 變更寬度後，務必在實際使用的掃描設備上驗證條碼。

## 如何變更條碼的高度

在確定寬度之後，您可以透過 `BarHeight` 屬性控制垂直尺寸。以下程式碼示範 **如何將高度** 從 30 px 變更為 60 px，並分別儲存兩張影像。

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### 了解條碼高度

* **視覺平衡** – 較高的條柱在低對比背景下可提升可讀性，但會增加影像的垂直佔用。  
* **法規限制** – 某些標準（例如零售標籤）規定最大條柱高度，請依需求調整。  
* **長寬比** – 調整高度不會影響模組寬度，您可以獨立微調兩者。

### 高度調整的邊緣案例處理

| Situation | Recommended approach |
|-----------|----------------------|
| Height < 10 px | 增加至至少 10 px；過短的條柱可能被掃描器忽略。 |
| Very tall bars (≥ 100 px) | 確認輸出介質（紙張、標籤）能容納額外空間。 |
| Need proportional scaling | 計算 `BarHeight = XDimension * desiredRatio` 以保持視覺一致性。 |

## 完整、可執行的範例

以下程式碼結合了 **設定寬度** 與 **變更高度** 的步驟。將程式碼複製到新的 Console 專案，還原 Aspose.Barcode NuGet 套件後執行。兩個 PNG 檔案會出現在 `bin/Debug/net6.0` 資料夾中。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**預期輸出**

執行程式後會產生兩個 PNG 檔案：

* `DatabarBarHeight30Pixels.png` – 條碼高度 30 px，模組寬度 2 px。  
* `DatabarBarHeight60Pixels.png` – 同一條碼的垂直尺寸加倍。

使用任何影像檢視器開啟任一檔案，即可看到乾淨的 GS1 DataBar Omni‑Directional 符號，已準備好供掃描。

## 常見問題解答

| Question | Answer |
|----------|--------|
| *Can I use millimetres instead of pixels?* | 可以。設定 `generator.Parameters.Barcode.XDimension.Millimeters` 與 `BarHeight.Millimeters`。函式庫會依影像 DPI 轉換為裝置像素。 |
| *What if I need a different barcode type?* | 將 `EncodeTypes.DatabarOmniDirectional` 替換為其他 `EncodeTypes` 值（例如 `EncodeTypes.QR`）。寬度與高度屬性仍然適用。 |
| *Is there a way to generate SVG instead of PNG?* | 在 `Save` 呼叫中使用 `BarCodeImageFormat.Svg`。寬度/高度設定仍然有效。 |
| *Do I need to call `generator.Dispose()`?* | `BarcodeGenerator` 實作 `IDisposable`。在 Console 應用程式中可使用 `using` 區塊包住，但對於短暫範例而言不是必須的。 |

## 結論

您現在已掌握 **如何設定 GS1 DataBar Omni‑Directional 條碼的寬度** 以及 **如何變更高度**，並能使用 Aspose.Barcode API 在 C# 中完成。完整範例示範了建立產生器、配置 `XDimension` 與 `BarHeight`，以及以不同垂直尺寸儲存 PNG 檔案的流程。

接下來您可以：

* 嘗試其他 `EncodeTypes`（例如 QR、Code128）。  
* 以 TIFF 等高解析度格式列印。  
* 將產生器整合至 Web API，實時回傳條碼。

祝您開發順利，條碼永遠掃得乾淨！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並探索在實際專案中的其他實作方式。

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}