---
category: general
date: 2026-10-08
description: 使用 C# 建立空白的 Planet 條碼，並學習如何使用 Aspose.BarCode 產生郵政條碼。附有逐步程式碼與技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: zh-hant
lastmod: 2026-10-08
og_description: 使用 Aspose.BarCode 在 C# 中建立空白的 Planet 條碼，並了解如何為郵件應用程式產生郵政條碼圖像。
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: 建立空白星球條碼 – C# 郵政條碼指南
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: 在 C# 中建立空白的 planet 條碼，產生郵遞條碼
url: /zh-hant/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 建立空白 Planet 條碼，產生郵政條碼

如果您需要為郵件系統 **建立空白 Planet 條碼**，本指南將向您展示如何使用 Aspose.BarCode for .NET 完成此操作。您還將學習 **如何產生郵政條碼** 圖片，例如 Planet 與 RM4SCC，客製化條寬，並控制 filled‑bars（實心條）選項。

產生郵政條碼不需要額外的圖形函式庫。Aspose.BarCode SDK 提供單一 API，負責編碼、影像渲染與影像格式選擇。完成本教學後，您將擁有三個可直接使用的 PNG 檔案：

* `PostalPlanetEmptyBars.png` – 空條 Planet 條碼  
* `PostalPlanetFilledBars.png` – 預設實心條 Planet 條碼  
* `PostalRM4SCCFilledBars.png` – 實心條 RM4SCC 條碼  

您可以將這些檔案放入任何郵件標籤範本、列印於信封上，或傳遞給第三方服務。

## 前置條件

* .NET 6.0 或更新版本（程式碼亦相容 .NET Framework 4.7+）。  
* Visual Studio 2022 或任何 C# IDE。  
* Aspose.BarCode for .NET – 透過 NuGet 安裝：

```bash
dotnet add package Aspose.BarCode
```

不需要其他相依性。

## 使用 Aspose.BarCode 建立空白 Planet 條碼

Planet 符號屬於美國郵政服務 (USPS) 條碼系列。預設情況下 SDK 會繪製 **實心** 條。若要 **建立空白 Planet 條碼**，只需停用 `FilledBars` 旗標。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**為什麼這樣有效：**  
`EncodeTypes.Planet` 告訴產生器使用 Planet 符號。`XDimension.Pixels` 控制每條的實體寬度，這對於需要特定模組尺寸的郵政掃描器相當重要。將 `FilledBars` 設為 `false` 會讓渲染器僅繪製每條的輪廓，產生某些郵寄標準所要求的 *空白* 外觀。

### 預期輸出

您會在目標資料夾中找到 `PostalPlanetEmptyBars.png`。此影像顯示 Planet 條碼，每條都是輪廓而非實心矩形。

![空白 Planet 條碼範例](empty-planet.png){: .align-center alt="建立空白 Planet 條碼 – 空條 Planet 條碼範例"}

## 產生實心版郵政條碼影像

大多數郵政工作流程使用預設的實心條版本。同一套 API 只需幾行程式碼即可產生實心 Planet 條碼與 RM4SCC 條碼。

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**為什麼可能需要 RM4SCC：**  
RM4SCC 是較新的 USPS 條碼，編碼方式與 Planet 相同但密度更高。部分運輸商要求使用 RM4SCC 以取得大量郵寄折扣。上述程式碼示範了如何在不改變整體流程的情況下 **產生郵政條碼**，同時支援兩種標準。

### 預期輸出

* `PostalPlanetFilledBars.png` – 經典實心條 Planet 條碼。  
* `PostalRM4SCCFilledBars.png` – 實心條 RM4SCC 條碼，外觀相似但間距更緊。

兩個檔案皆可在任何影像檢視器中開啟，以驗證條紋圖樣。

## 調整條寬以因應不同列印解析度

郵政掃描器常規定最小模組寬度（例如 0.013 英吋）。若您的印表機解析度為 300 dpi，4 像素的模組即相當於 0.013 英吋。請調整 `XDimension.Pixels` 數值以符合您的硬體規格：

| 目標模組（英吋） | DPI | 所需像素 (`XDimension`) |
|-------------------|-----|--------------------------|
| 0.013             | 300 | 4                        |
| 0.013             | 600 | 8                        |
| 0.015             | 300 | 5                        |

**專業提示：** 務必測試 a

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 C# 建立 Planet 條碼 PNG – 步驟說明指南](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [在 C# 中產生郵政條碼 – 完整指南（含 Planet 條碼）](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [如何使用 Aspose.BarCode 在 C# 中產生郵政條碼](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}