---
category: general
date: 2026-09-29
description: 學習如何在 C# 中使用 Aspose.BarCode 建立全向 Databar 條碼。調整 X 尺寸、設定長寬比，並儲存 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: zh-hant
lastmod: 2026-09-29
og_description: 使用 Aspose.BarCode 在 C# 中建立全方向 Databar 條碼。了解如何設定 X 尺寸、調整長寬比，並匯出 PNG
  檔案。
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: 使用 C# 建立全方向 DataBar 條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中建立全向 DataBar 條碼
url: /zh-hant/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立全向 DataBar 條碼

如果您需要在 .NET 應用程式中 **建立全向 DataBar 條碼**，本指南將向您展示具體步驟。您將看到如何初始化 DataBar 堆疊全向條碼、設定 X‑dimension、變更長寬比，並使用 Aspose.BarCode 產生 PNG 圖片。

產生 **DataBar 堆疊全向條碼** 是在必須為零售掃描器編碼產品識別碼時的常見需求。在本教學中，您將學習 **設定條碼長寬比**、控制模組大小，並在不離開 IDE 的情況下匯出結果。

## 前置條件

- 安裝 .NET 6.0 或更新版本
- Visual Studio 2022（或任何相容 C# 的 IDE）
- **Aspose.BarCode for .NET** NuGet 套件（版本 23.12 或更新）

您可以透過 NuGet 套件管理員加入此套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：初始化全向 DataBar 條碼

第一步是建立一個 `BarcodeGenerator` 實例，目標為 **DataBar 堆疊全向** 符號。建構函式接受編碼類型與資料字串。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**為什麼這很重要：** `EncodeTypes.DatabarStackedOmniDirectional` 值告訴 Aspose.BarCode 以特定的全向 DataBar 格式呈現，這是雙向掃描所必需的。

## 步驟 2：定義 X‑dimension（模組大小）

X‑dimension 控制單一條碼模組的寬度（以像素為單位）。`2` 像素的值在螢幕顯示與大多數印表機上都表現良好。

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼這很重要：** 一致的 X‑dimension 可確保條碼符合零售掃描器的最小尺寸規範，同時保持圖像檔案大小在可接受範圍。

## 步驟 3：設定第一個長寬比並儲存圖像

**長寬比** 決定 DataBar 的高寬比例。`15` 的長寬比會產生緊湊且較高的條碼，適合狹窄的標籤空間。

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**為什麼這很重要：** 調整長寬比可讓條碼適配不同的標籤版面，同時不影響可讀性。儲存的 PNG 可在任何圖像檢視器中檢視。

## 步驟 4：變更長寬比並產生第二張圖像

有時需要較寬的條碼，例如標籤有較多水平空間時。將比例改為 `30` 會產生較平坦的外觀。

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼這很重要：** 透過公開 **set barcode aspect ratio** 屬性，您可以從單一程式碼基礎產生多種條碼變體，簡化自動化標籤產生流程。

## 預期輸出

執行程式會在應用程式的輸出資料夾產生兩個 PNG 檔案：

| 檔案名稱 | 長寬比 | 視覺說明 |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15 | 高且窄的條碼，適用於狹窄標籤 |
| `DatabarAspectRatio30.png` | 30 | 較寬的條碼，填滿更多水平空間 |

您可以將這些圖像嵌入報告、列印於產品包裝上，或傳送至 Web 服務進一步處理。

![建立全向 DataBar 條碼範例](databar-example.png "建立全向 DataBar 條碼範例")

*此螢幕截圖顯示兩個產生的 PNG 檔案並排顯示。*

## 常見問題與邊緣情況

### 如果需要不同的 X‑dimension 該怎麼辦？

您可以為 `XDimension.Pixels` 指定任意整數值。小於 `1` 的值會被忽略，而大於 `10` 的值可能產生超過印表機邊界的過大模組。每次變更後請測試視覺輸出。

### 如何編碼其他 AI 產生的資料（例如 UPC、EAN）？

將 `BarcodeGenerator` 建構函式中的資料字串替換為相應的應用程式識別碼（AI）。對於 UPC‑A 代碼，使用不帶 AI 前綴的 `"012345678905"`。

### 能否匯出為 PNG 以外的格式？

可以。`Save` 方法接受 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Gif`、`BarCodeImageFormat.Tiff` 與 `BarCodeImageFormat.Bmp`。選擇符合您後續工作流程的格式。

## 專業提示：重複使用產生器進行批次處理

如果需要產生數十個長寬比不同的條碼，請保持 `BarcodeGenerator` 實例持續存在，並在每次 `Save` 前僅修改 `DataBar.AspectRatio`。這可避免為每張圖像重新實例化產生器的開銷。

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## 結論

您現在已了解如何使用 Aspose.BarCode 在 C# 中 **建立全向 DataBar 條碼**。透過初始化 `BarcodeGenerator`、設定 X‑dimension、調整 **set barcode aspect ratio**，並儲存 PNG 檔案，您即可產生符合各種標籤需求的條碼影像。  

接下來，探索相關主題，例如 QR 代碼的 **generate barcode image**、**DataBar 堆疊全向條碼** 驗證，或將產生的 PNG 整合至使用 Aspose.PDF 的 PDF 發票中。嘗試不同的長寬比與模組大小，以找到最適合您特定印刷硬體的配置。

---

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 中使用條碼產生器建立 DataBar 全向條碼](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [C# 中的 DataBar 堆疊全向條碼 – 完整指南](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [如何在 C# 中產生條碼 – 使用 DataBar Expanded 建立條碼影像](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}