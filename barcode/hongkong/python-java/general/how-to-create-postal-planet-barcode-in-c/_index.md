---
category: general
date: 2026-11-23
description: 使用 C# 及 Aspose.BarCode 建立郵政 Planet 條碼。了解如何產生 Planet 條碼、設定 X 尺寸，並儲存實條或空條。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: zh-hant
lastmod: 2026-11-23
og_description: 使用 C# 建立郵政行星條碼，並學習如何使用 Aspose.BarCode 產生行星條碼。遵循完整範例以產生實心與空心條。
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: 如何在 C# 中建立郵政星球條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中建立郵政星球條碼
url: /zh-hant/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立郵政 Planet 條碼

如果您需要在 .NET 應用程式中 **建立郵政 Planet 條碼**，本教學將示範如何使用 Aspose.BarCode 函式庫 **產生 Planet 條碼**。您將會看到如何設定 X‑dimension、在實心與空心條之間切換，以及將影像儲存為 PNG 格式。

產生 Planet 條碼是郵政服務常見的需求，因為它需要高密度、機器可讀的符號。完成本教學後，您將擁有兩個 PNG 檔案——一個實心條、一個空心條——即可整合至任何郵寄工作流程。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本。
* 已配置 .NET 開發環境的 Visual Studio 2022（或任何 C# 編輯器）。
* 具備 **Aspose.BarCode for .NET** 的有效 NuGet 授權。使用以下指令安裝套件：

```bash
dotnet add package Aspose.BarCode
```

不需要額外的外部服務；函式庫會在本機完成所有編碼工作。

## 步驟 1 – 建立郵政 Planet 條碼

第一步是為 **Planet** 符號實例化 `BarcodeGenerator`，並提供要編碼的資料。資料字串必須為數字，且根據郵政規範最多 12 位。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

建立產生器會配置所有內部結構以供渲染。`EncodeTypes.Planet` 列舉值會選擇正確的郵政格式編碼演算法。

## 步驟 2 – 設定 X‑dimension 以提升可視性

X‑dimension 定義單一模組（最小條形元素）的寬度。設定為 4 像素即可在不放大整體影像的情況下提供清晰的視覺呈現。

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

在低解析度媒介上列印條碼時，調整 X‑dimension 是必要的。相同的設定也會用於空心條版本，以保持兩張影像的一致性。

## 步驟 3 – 儲存實心條的條碼

預設情況下，產生器會渲染 **實心條**（純黑模組）。只需一次方法呼叫即可將 PNG 檔寫入磁碟。

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

將 `YOUR_DIRECTORY` 替換為您實際想要輸出檔案的路徑。`BarCodeImageFormat.Png` 列舉確保無損壓縮，適合後續處理。

## 步驟 4 – 為空心條建立另一個 Planet 條碼產生器

若要產生 **空心條**（白色模組、黑色背景）的版本，需要第二個 `BarcodeGenerator` 實例。重新使用相同的資料字串可確保兩張影像代表相同的郵遞編碼。

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

建立獨立的產生器可將 `FilledBars` 屬性隔離，讓您在不影響第一張影像的情況下切換視覺樣式。

## 步驟 5 – 設定產生器以渲染空心條

`FilledBars` 旗標會切換渲染模式。將其設為 `false` 即告訴函式庫以空心（透明）方式繪製條形，同時保持背景為實心。

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

將 X‑dimension 保持與實心版相同，可確保兩個 PNG 檔的尺寸一致，簡化列印樣板中的版面計算。

## 步驟 6 – 儲存渲染空心條的條碼

最後，將空心條影像寫入磁碟。仍使用相同的 PNG 格式，若需要也可改為 JPEG 或 BMP，只要更改 `BarCodeImageFormat` 的值即可。

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

此時您會得到兩個檔案：

* `PostalPlanetFilledBars.png` – 實心黑條。
* `PostalPlanetEmptyBars.png` – 黑色背景上的空心條。

兩者皆符合 Planet 符號的郵政規範。

## 完整原始程式碼

將所有步驟整合，即可得到一個簡潔的主控台應用程式，直接執行即可。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

編譯並執行程式：

```bash
dotnet run
```

主控台會印出 *Barcodes generated successfully.*，兩個 PNG 檔案會出現在專案資料夾中。

## 預期輸出

以下為實心條圖像的視覺示例。空心條的對應圖與之相同，只是條形為透明。

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*圖片替代文字:* **已建立的郵政 Planet 條碼（實心條）範例**（包含主要關鍵字）。

兩張影像預設皆為 150 × 150 像素，若需不同解析度，可透過 `ImageWidth` 與 `ImageHeight` 參數調整整體大小。

## 可選變化

### 變更影像格式

若下游系統偏好 JPEG，請將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。JPEG 會產生壓縮雜訊，僅在檔案大小是關鍵限制時使用。

### 放大條碼

透過調整 `Resolution` 屬性，可在保持模組寬度不變的前提下放大條碼：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

較高的 DPI 值可提升雷射印表機的列印品質。

### 使用自訂背景色

可使用以下程式碼設定背景色：

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

此功能適合視覺測試，但在正式的郵件標籤中應避免使用，因為郵政標籤必須為白色背景。

## 常見問題

**這能在 .NET Core 上運作嗎？**  
可以。Aspose.BarCode 函式庫以 .NET Standard 2.0 為目標，兼容 .NET 5、.NET 6 與 .NET Core 3.1。

**如果資料字串包含非數字字符會怎樣？**  
Planet 條碼僅接受數字輸入。若提供字母或符號，會拋出 `BarcodeException`。請在建立產生器前先驗證輸入。

**能否在記憶體中產生條碼而不寫入磁碟？**  
可以使用 `GenerateBarCodeImage` 方法取得 `System.Drawing.Image` 物件，然後直接串流至回應或資料庫。

## 結論

現在您已掌握如何在 C# 中 **建立郵政 Planet 條碼**，以及如何 **產生實心與空心兩種樣式的 Planet 條碼**。本教學涵蓋了完整工作流程——從初始化產生器、設定 X‑dimension、切換 `FilledBars` 旗標，到儲存 PNG 檔案。您可以自行實驗影像格式、DPI 設定與背景顏色，以配合特定的郵寄系統需求。

接下來，您可以探索其他郵政符號，例如 **POSTNET** 或 **Intelligent Mail**，使用相同的 Aspose.BarCode API。只要將參數改為 `EncodeTypes.Postnet`，即可套用本教學的相同模式，打造完整的條碼產生套件。

## 接下來您可以學習什麼？

以下教學與本指南的技巧密切相關，能協助您進一步掌握 API 功能並探索其他實作方式：

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}