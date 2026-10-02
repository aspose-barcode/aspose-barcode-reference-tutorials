---
category: general
date: 2026-10-02
description: 學習如何在 C# 中建立 rm4scc 條碼，以及如何以自訂高度產生郵政條碼。包括 Planet 條碼的逐步程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: zh-hant
lastmod: 2026-10-02
og_description: 在 C# 中建立 rm4scc 條碼，並學習如何產生具確切尺寸的郵政條碼。完整程式碼範例與最佳實踐技巧。
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: 使用自訂高度建立 rm4scc 條碼 – C# 教學
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: 如何在 C# 中建立 rm4scc 條碼並控制其高度
url: /zh-hant/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 rm4scc 條碼並控制其高度

如果您需要為郵件系統 **建立 rm4scc 條碼**，本指南將完整說明如何產生郵政條碼並設定精確的條紋高度。您將看到預設（自動調整）方式與明確設定高度的技巧，讓您可以選擇符合設計需求的方法。

在建立運送標籤、批次郵寄軟體，或任何與國家郵政服務整合的解決方案時，產生郵政條碼是一項常見任務。本教學涵蓋：

* **如何產生郵政條碼** 用於 RM4SCC 與 Planet 符號  
* **產生 planet 條碼** 使用相同設定以作比較  
* **如何設定條碼高度** 為固定的像素值  
* 完整、可執行的 C# 程式碼，使用 Aspose.BarCode 函式庫  

閱讀完本文後，您將擁有一個可直接執行的主控台程式，產生四個 PNG 檔案——兩個使用自動高度，兩個使用固定 100 像素的高度。

## 前置條件

在開始之前，請確保您已具備以下條件：

* .NET 6.0 SDK 或更新版本（程式碼亦可於 .NET Framework 4.7+ 執行）。  
* Visual Studio 2022 或任何能編譯 C# 專案的 IDE。  
* **Aspose.BarCode for .NET** NuGet 套件 (`Install-Package Aspose.BarCode`)。  

不需要額外設定；函式庫會在內部處理所有影像渲染。

## 步驟 1：設定專案並匯入命名空間

建立一個新的主控台專案，並加入必要的 `using` 指令。此步驟會為條碼產生做好環境準備。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*此處重要性*：僅宣告一次 `outputFolder` 可避免重複，且日後若需變更目的路徑也更方便。`CreateDirectory` 呼叫確保儲存操作不會因資料夾不存在而失敗。

## 步驟 2：使用預設高度產生郵政條碼

### 2.1 建立 RM4SCC 條碼（自動高度）

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 建立 Planet 條碼（自動高度）

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

兩個呼叫皆未設定 `BarHeight` 屬性，函式庫會根據符號規格計算最佳高度。這是在沒有嚴格版面限制時，最簡單的 **如何產生郵政條碼** 方式。

## 步驟 3：設定條碼高度以達精確版面

當標籤模板需要固定的視覺尺寸時，必須明確設定條紋高度。以下程式碼示範了 **如何設定條碼高度** 為 100 像素，適用於兩種符號。

### 3.1 固定高度 RM4SCC 條碼

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 固定高度 Planet 條碼

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*此處運作原理*：`BarHeight.Pixels` 屬性會覆寫自動計算，強制渲染器使用您指定的像素數。當條碼必須與其他 UI 元件或列印模板對齊時，這是必須的。

## 步驟 4：驗證產生的影像

程式執行完畢後，於 `outputFolder` 開啟四個 PNG 檔案。您應該會看到：

| 檔案名稱 | 高度 | 符號 |
|-----------|--------|-----------|
| `PostalRM4SCC_AutoHeight.png` | 自動計算 (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | 自動計算 (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px**（精確） | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px**（精確） | Planet |

這兩張 “FixedHeight” 影像的條紋高度正好為 100 px，符合 **如何設定條碼高度** 於標準化標籤格式的需求。

## 步驟 5：常見陷阱與最佳實踐建議

* **無效的高度值** – 將 `BarHeight.Pixels` 設為負數會拋出 `ArgumentException`。在指派前務必驗證使用者輸入。  
* **解析度意識** – 螢幕上的視覺大小亦受 DPI 影響。若之後匯出為 PDF，請考慮設定 `ImageResolution` 以保持實體尺寸一致。  
* **X‑dimension 與條紋高度** – `XDimension.Pixels` 控制條紋 **寬度**，而非高度。若忘記設定，條碼可能顯得過細，特別是在低 DPI 下。  
* **執行緒安全** – `BarcodeGenerator` 實例 **不**具執行緒安全性。若平行產生大量條碼，請為每個執行緒建立新實例或同步存取。

## 完整原始碼（可執行）

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
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

將程式碼複製至 `Program.cs`，還原 NuGet 套件，然後執行 `dotnet run`。主控台會顯示成功產生的訊息，PNG 檔案會出現在 `C:/Barcodes/`。

## 結論

您現在已了解如何在 C# 中 **建立 rm4scc 條碼** 與 **產生 planet 條碼**，無論是自動尺寸或手動指定條紋高度。透過控制 `BarHeight.Pixels`，即可解決 **如何設定條碼高度** 的問題，確保您的郵政條碼能完美貼合任何標籤版面。

接下來，您可能想探索：

* **如何產生郵政條碼** 於其他格式，如 PDF 或 SVG（`BarCodeImageFormat.Pdf`、`BarCodeImageFormat.Svg`）。  
* 在條碼下方加入可讀的文字（`Parameters.Caption`）。  
* 將產生器整合至 ASP.NET Core API，以即時提供條碼服務。

歡迎嘗試不同的 `XDimension` 值、顏色或背景影像，以符合您的品牌形象，同時遵守條碼標準。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在此處示範的技巧之上。每個資源皆提供完整可運作的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中以自訂尺寸產生郵政條碼](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [如何在 C# 中建立 planet 條碼 PNG – 步驟指南](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [如何設定寬度並在 C# 中產生 Planet 條碼](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}