---
category: general
date: 2026-09-16
description: 在 C# 中建立郵政條碼，並學習如何設定寬度與調整條碼高度，以實現完美掃描。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: zh-hant
lastmod: 2026-09-16
og_description: 使用此逐步指南在 C# 中建立郵政條碼，說明如何設定寬度及調整條碼高度，以確保郵件掃描的可靠性。
og_image_alt: C# generated postal barcode image with custom width and height
og_title: 在 C# 中建立自訂寬度與高度的郵政條碼
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: 在 C# 中建立自訂寬度與高度的郵政條碼
url: /zh-hant/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中使用自訂寬度與高度建立郵政條碼

如果您需要在 C# 中**建立郵政條碼**圖像，本指南將示範如何產生 Planet 與 RM4SCC 條碼並設定精確尺寸。閱讀完前兩句後，您將了解用於**設定寬度**與**變更條碼高度**的確切 API 呼叫，從而產生符合郵政服務規範且可掃描的條碼。

您將學會：
* 如何為 Planet 與 RM4SCC 格式實例化條碼產生器。  
* 用於以像素設定**寬度**（X‑dimension）的精確屬性。  
* 如何為特定條碼類型**變更條碼高度**。  
* 產生的 PNG 檔案儲存位置以及其外觀。

唯一的先決條件是參考提供 `BarcodeGenerator` 類別的 `Aspose.BarCode`（或類似）函式庫。除條碼 SDK 本身外，無需其他 NuGet 套件。

---

## 使用自訂尺寸建立郵政條碼

首先，加入必要的 `using` 指令並建立一個簡易的主控台程式。完整且可執行的範例將於逐步說明之後呈現。

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**為什麼這樣有效：**  
* `EncodeTypes.Planet` 與 `EncodeTypes.RM4SCC` 告訴產生器遵循哪種郵政標準。  
* `XDimension.Pixels` 控制每個條碼模組（最小的黑白單元）的**寬度**。  
* `BarHeight.Pixels` 讓您**變更條碼高度**，適用於不會自動計算高度的格式，例如 RM4SCC。

執行程式會在可執行檔的工作目錄中產生兩個 PNG 檔案：
* `PostalPlanetBarWidth4.png` – 寬度為 4 px 模組的 Planet 條碼。  
* `PostalRM4SCCHeight100.png` – 寬度為 4 px、固定高度 100 px 的 RM4SCC 條碼。

---

## 設定郵政條碼寬度的方法

設定寬度的**步驟**對所有支援的郵政格式皆相同：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` 為表示單一模組像素大小的整數。  
* 郵政條碼的常見值為 **4 px**，但您可為更高解析度的列印提升此數值。

**小技巧：** 在使用 DPI 可控的印表機列印時，將像素寬度乘上印表機的 DPI 系數，以維持實體尺寸。

---

## 變更 RM4SCC 郵政條碼的高度

只有部份郵政符號（例如 RM4SCC）需要明確設定高度。使用**變更條碼高度**屬性：

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` 為條碼影像的總高度，而非單一模組的高度。  
* 將 `BarHeight` 設為 **100 px** 可產生較高且易於閱讀的條碼，符合多數郵政服務的指導方針。

**邊緣情況：** 若設定的高度過小，條碼可能無法被掃描器辨識。大量部署前務必先以實體列印測試。

---

## 完整來源檔案，快速複製貼上

以下是完整程式碼，您可直接複製到新的主控台專案中。無需其他程式碼。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**預期輸出**（主控台）：

```
Both postal barcodes have been saved.
```

兩個 PNG 檔案會出現在輸出資料夾中，分別顯示清晰的郵政條碼，可直接列印或嵌入使用。

---

## 常見問題與故障排除

| Question | Answer |
|----------|--------|
| *如果我需要為每個條碼設定不同的 X‑dimension（寬度）怎麼辦？* | 建立獨立的 `BarcodeGenerator` 實例，並在呼叫 `Save` 前為每個實例指派不同的 `XDimension.Pixels` 值。 |
| *為什麼 Planet 條碼會忽略 `BarHeight`？* | Planet 格式會自動根據 X‑dimension 計算高度，因此設定 `BarHeight` 不會產生任何效果。 |
| *我可以輸出 SVG 而非 PNG 嗎？* | 可以。將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Svg`。 |
| *列印時影像模糊該怎麼辦？* | 提升 X‑dimension（例如至 6 px），並使用產生器的 `Resolution` 設定以較高 DPI 產生影像。 |

---

## 結論

您現在已了解如何在 C# 中**建立郵政條碼**圖像，並使用 `BarcodeGenerator` API 精確**設定寬度**與**變更條碼高度**。此範例同時涵蓋自動尺寸（Planet）與手動尺寸（RM4SCC）格式，為任何郵政自動化專案奠定堅實基礎。

接下來，您可能想探索：
* 在條碼下方加入可讀文字（`CodeTextParameters`）。  
* 匯出至其他格式，例如 SVG 或 PDF，以支援向量列印。  
* 將產生器整合至 Web API，按需提供條碼服務。

歡迎自行嘗試不同的尺寸、編碼與輸出格式，以符合您的郵寄工作流程。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [在 C# 中建立郵政條碼圖像 – 完整逐步指南](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [在 C# 中建立郵政條碼 – 完整產生器範例](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [C# 條碼產生器範例 – 設定寬度與高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}