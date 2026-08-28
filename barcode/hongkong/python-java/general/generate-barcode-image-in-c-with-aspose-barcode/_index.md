---
category: general
date: 2026-08-06
description: 使用 Aspose.BarCode 在 C# 中產生條碼影像。學習如何產生 Databar、調整自訂條碼尺寸，以及以簡單程式碼變更條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: zh-hant
lastmod: 2026-08-06
og_description: 使用 Aspose.BarCode 在 C# 中產生條碼影像。本教學將示範如何建立 Databar Omnidirectional
  條碼、客製化其尺寸，以及有效調整條碼高度。
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: 在 C# 中生成條碼圖像 – 完整 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: 使用 Aspose.BarCode 在 C# 中產生條碼圖像
url: /zh-hant/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中使用 Aspose.BarCode 產生條碼影像

如果您需要以程式方式 **產生條碼影像**，本指南將完整說明操作步驟。無論您是建立零售庫存系統或物流追蹤平台，您都會看到建立 Databar Omnidirectional 條碼、調整其尺寸，並將結果儲存為 PNG 檔案的完整工作流程。

產生條碼影像是常見需求，但開發人員常常想知道 **如何產生符合特定尺寸的 Databar**。在本教學中，您將學會建立 Databar 條碼、客製化其寬度與高度，並在不重新撰寫整個產生器的情況下變更條碼高度。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼可在 .NET Core 與 .NET Framework 上執行）
* Visual Studio 2022（或任何支援 C# 的 IDE）
* 有效的 Aspose.BarCode for .NET 授權（免費評估版可用於測試）
* 具備基本的 C# 語法知識

## 步驟 1：安裝 Aspose.BarCode

將 Aspose.BarCode NuGet 套件加入您的專案：

```bash
dotnet add package Aspose.BarCode
```

此套件包含本教學中會使用的 `BarcodeGenerator` 類別。安裝完成後，請還原專案以取得相依性。

## 步驟 2：建立基本的條碼產生器

第一行程式碼會建立一個 **條碼產生器**，用以產生 Databar Omnidirectional 符號。`EncodeTypes.DatabarOmniDirectional` 列舉告訴函式庫使用哪種符號系統，資料字串則遵循 GS1 應用識別碼語法。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**為什麼這很重要：** `BarcodeGenerator` 物件是所有條碼操作的入口點。選取 `DatabarOmniDirectional` 可確保輸出符合零售掃描的 GS1 標準。

## 步驟 3：設定自訂 X‑dimension（模組寬度）

X‑dimension 控制最窄條的寬度。將其設為較小的像素值可產生緊湊的條碼，較大的值則會增加整體寬度。

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**說明：** 2 像素的 X‑dimension 是高解析度螢幕的常見選擇。如需更緊密或較寬鬆的視覺密度，請調整此數值。

## 步驟 4：產生第一張具特定高度的條碼影像

條碼高度與 X‑dimension 無關。此處將條碼高度設為 **30 px**，然後將影像儲存為 PNG。

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**結果：** 您現在會得到名為 `DatabarBarHeight30Pixels.png` 的檔案，顯示高度為 30 px 的 Databar 條碼。此範例展示了 **自訂條碼尺寸** 的功能，適用於小標籤等特定情境。

## 步驟 5：變更條碼高度以產生較大版本

若相同條碼需顯示於較大的標籤，只需修改高度屬性並重複使用同一個產生器實例。

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼可以重複使用產生器：** 變更 `BarHeight.Pixels` 會更新內部版面配置，而不必重新建立物件，這樣可節省記憶體並保留資料字串不變。這是即時 **變更條碼高度** 的建議做法。

## 步驟 6：驗證輸出結果

使用任意影像檢視器開啟這兩個 PNG 檔案。您應該會看到兩個 Databar Omnidirectional 條碼，編碼相同的 GTIN，但垂直尺寸不同：

* `DatabarBarHeight30Pixels.png` – 高 30 px，適用於緊湊的收據。
* `DatabarBarHeight60Pixels.png` – 高 60 px，適合較大的貨架邊緣標籤。

兩張影像皆保留相同的 X‑dimension，因而條與空白的比例保持一致，僅整體高度隨之調整。

## 常見變化與邊緣情況

| 情況 | 處理方式 |
|-----------|------------------|
| **不同的條碼符號系統** | 將 `EncodeTypes.DatabarOmniDirectional` 替換為其他列舉值（例如 `EncodeTypes.Code128`），其餘程式碼保持不變。 |
| **非像素尺寸** | 若需列印就緒的實體尺寸，可使用 `generator.Parameters.Barcode.XDimension.Millimeters` 或 `BarHeight.Millimeters`。 |
| **透明背景** | 在呼叫 `Save` 之前設定 `generator.Parameters.ImageBackgroundColor = Color.Transparent;`。 |
| **高解析度輸出** | 成比例地增加 `XDimension.Pixels` 與 `BarHeight.Pixels`，或以 `BarCodeImageFormat.Tiff` 儲存以獲得無損品質。 |
| **單一影像內多條條碼** | 建立多個 `BarcodeGenerator` 實例，將每個渲染至 `Bitmap`，再使用 `Graphics.DrawImage` 合成。 |

**專業提示：** 在投入正式環境前，務必使用實體掃描器測試產生的條碼。掃描器可能會因光線與感測器品質不同而對極細條產生不同的解讀。

## 完整原始程式碼供參考

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

將程式碼複製到新的 Console 專案中，執行後您會在輸出資料夾看到兩個 PNG 檔案。

## 常見問與答

**Q: 我可以在未安裝授權的情況下產生條碼嗎？**  
A: Aspose.BarCode 的評估版可在未授權下使用，但會加上小水印。正式環境請使用 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` 以套用購買的授權。

**Q: 變更 X‑dimension 會影響可讀性嗎？**  
A: 會。過小的 X‑dimension 可能導致低解析度印表機無法正確讀取條碼。螢幕渲染建議最小 1 px；列印則建議至少 0.25 mm。

**Q: 若需產生 JPEG 格式的條碼該怎麼做？**  
A: 將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Jpeg`。亦可設定 `generator.Parameters.ImageQuality` 以控制壓縮程度。

## 結論

您現在已掌握如何在 C# 中使用 Aspose.BarCode **產生條碼影像**、**建立 Databar 條碼**、調整 **自訂條碼尺寸**，以及依需求 **變更條碼高度**。完整範例示範了最常見的工作流程，變化表格則讓您能應對實務中的各種邊緣情況。

接下來，您可以探索相關主題，例如 **在 PDF 文件中嵌入條碼**、**批次產生多條條碼**，以及 **使用 QR Code 進行行動支付**。這些情境皆基於本篇所述的相同原則，讓您能自信地延伸應用此知識。

祝程式開發順利，條碼掃描永遠順暢！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技術。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [產生條碼影像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何產生條碼 – 使用 Aspose.BarCode 的 Code 39 設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}