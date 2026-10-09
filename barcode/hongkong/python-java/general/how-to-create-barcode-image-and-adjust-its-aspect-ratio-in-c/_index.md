---
category: general
date: 2026-10-08
description: 學習如何在 C# 中建立條碼圖像，並了解如何調整 DataBar 堆疊全方向條碼的長寬比。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: zh-hant
lastmod: 2026-10-08
og_description: 在 C# 中建立條碼圖像，並學習如何調整 DataBar 堆疊全方向條碼的長寬比，附完整程式碼範例。
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: 在 C# 中建立條碼圖像 – 一步一步教學
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中建立條碼圖像並調整其長寬比
url: /zh-hant/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立條碼圖像並調整其長寬比

如果您需要 **程式化建立條碼圖像**，本指南提供完整、可直接執行的解決方案。您將會看到 **如何為 DataBar 堆疊全方向條碼調整長寬比**，這在零售與物流應用中常見。

在本教學中，您將學會：
* 為 DataBar 堆疊全方向符號初始化 Aspose.BarCode `BarcodeGenerator`。  
* 以像素設定 X‑dimension（模組寬度）以控制條紋粗細。  
* 套用兩種不同的長寬比，並將每個結果儲存為 PNG 檔案。  
* 驗證輸出並了解長寬比為何重要。

不需要任何外部工具——只要有 Aspose.BarCode for .NET 套件以及 .NET 6（或更新）開發環境即可。

## 如何使用 Aspose.BarCode 建立條碼圖像

第一步是以所需的符號與資料字串建立產生器。`EncodeTypes.DatabarStackedOmniDirectional` 列舉會告訴 Aspose.BarCode 產生 DataBar 堆疊全方向條碼，此符號廣泛用於 GS1‑128 應用。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**為什麼重要：** `BarcodeGenerator` 物件是所有條碼產生工作的入口點。提前指定符號與原始資料，可確保產生的圖像符合 GS1 標準。

## 設定 X‑dimension（模組寬度）

X‑dimension 定義最窄條紋（模組）的寬度。較大的 X‑dimension 會產生較粗的條碼，對低解析度印表機特別有幫助。

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼重要：** 調整 X‑dimension 是視覺調校的一環。它不會影響編碼資料，但會影響不同裝置的掃描可靠度。

## 調整長寬比 – 第一種方式（15）

長寬比控制 DataBar 條碼的高寬比例。`DataBar.AspectRatio` 屬性接受整數值；數值越大條紋越高。

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**為什麼重要：** 長寬比 15 是零售掃描器的常見預設值。產生的 PNG（`DatabarAspectRatio15.png`）會呈現較高的外觀，有助於手持設備的掃描成功率。

## 調整長寬比 – 第二種方式（30）

對於特定標籤格式，您可能需要更高的條碼。只要在再次呼叫 `Save` 前，將長寬比指派為新的整數值即可。

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼重要：** 透過示範 **如何調整長寬比**，您可以在同一資料來源下產生多張條碼圖像，而不必重新建立產生器。這可減少記憶體使用並加速批次處理。

### 預期輸出

執行程式後，您會在執行目錄中找到兩個 PNG 檔案：

| 檔案名稱                     | 長寬比 | 視覺說明 |
|-------------------------------|--------|----------|
| `DatabarAspectRatio15.png`    | 15     | 標準高度，適用於大多數 POS 掃描器。 |
| `DatabarAspectRatio30.png`    | 30     | 條紋較高，適合大型標籤或低解析度印表機。 |

兩張圖像皆編碼相同的 GTIN `(01)12345678901231`，但視覺比例會依您設定的長寬比而異。

## 常見問題與邊緣案例處理

### 如果需要不同的 X‑dimension 該怎麼辦？

您可以將 `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` 設為任意大於零的整數。對於高解析度輸出（例如 300 dpi），3‑4 像素的值通常能產生較清晰的結果。

### 如何選擇適當的長寬比？

最佳比例取決於掃描環境：
* **低矮標籤** – 使用較小的比例（例如 10‑15），使條碼更緊湊。  
* **大型運輸容器** – 較高的比例（例如 25‑35）可提升遠距離可讀性。  
* **法規要求** – 某些標準規定最小高度；請參考 GS1 規範取得精確數值。

### 可以用相同的程式碼產生其他條碼格式嗎？

可以。將 `EncodeTypes.DatabarStackedOmniDirectional` 替換為其他 `EncodeTypes` 值（例如 `EncodeTypes.Code128`），其餘程式碼—X‑dimension、長寬比（若適用）以及儲存方式—皆保持不變。

### 若要以其他格式產生圖像怎麼做？

`BarCodeImageFormat` 支援 PNG、JPEG、BMP、GIF 與 TIFF。只要修改 `Save` 的第二個參數，例如：

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## 專業提示：重複使用產生器進行批次處理

當需要大量產生條碼且視覺設定相同時，僅需實例化一次產生器，僅更新 `CodeText` 屬性，然後重複呼叫 `Save`。這樣可避免重複分配內部緩衝區的開銷。

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## 結論

現在您已掌握如何在 C# 中使用 Aspose.BarCode **建立條碼圖像**，以及如何 **調整 DataBar 堆疊全方向符號的長寬比**。透過控制 X‑dimension 與長寬比，您可以產生符合任何掃描或版面需求的條碼，同時保持實作簡潔且易於維護。

### 往後的步驟

* 透過切換 `EncodeTypes` 值，探索 **Code128** 或 **QR Code** 等其他符號。  
* 結合條碼產生與 PDF 建立（例如使用 Aspose.PDF），直接將條碼嵌入發票。  
* 嘗試根據標籤尺寸動態選擇長寬比——將 **如何調整長寬比** 的模式擴展為完整的標籤設計引擎。

歡迎自行調整範例、分享成果，或在留言區提出後續問題。祝開發順利！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索替代實作方式。

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}