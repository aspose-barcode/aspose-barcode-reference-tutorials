---
category: general
date: 2026-08-15
description: 如何在 C# 中設定條碼參數並產生條碼圖像。一步一步學習建立 Databar 條碼並儲存為 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: zh-hant
lastmod: 2026-08-15
og_description: 如何在 C# 中使用 Aspose.Barcode 設定條碼，然後產生條碼圖像。請跟隨本指南建立 Databar 條碼並儲存 PNG
  檔案。
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: 如何在 C# 中設定條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何設定條碼 – 完整 C# 指南
url: /zh-hant/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定條碼 – 完整 C# 指南

如果你正在尋找在 .NET 專案中 **如何設定條碼** 參數，本教學將展示你所需的完整步驟。你將學會 **如何產生條碼** 圖片、建立 Databar 條碼，並以像素為單位精確控制條碼高度——全部使用乾淨、可投入生產的 C# 程式碼。

在本指南中，你將會：

* 安裝所需的 NuGet 套件。  
* 建立 Databar Omnidirectional 條碼（「建立 Databar 條碼」部分）。  
* 調整 X‑dimension 與條碼高度，以示範 **如何設定條碼** 的尺寸。  
* 將結果儲存為 PNG 檔案，涵蓋 **generate barcode image C#** 的情境。

此程式碼相容於最新的 Aspose.Barcode for .NET（撰寫時為 v 24.12），可在 .NET 6 或更新版本上執行。

---

## 前置條件

在開始之前，請確保你已具備：

* .NET 6 SDK（或更新版本）。  
* 如 Visual Studio 2022 或 VS Code 等開發環境。  
* 可連網下載 Aspose.Barcode NuGet 套件的網路連線。

不需要額外的第三方函式庫。

---

## 第一步：安裝 Aspose.Barcode for .NET

在 C# 中 **產生條碼** 圖片最可靠的方式是使用 Aspose.Barcode。於專案資料夾的終端機執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新的穩定版套件加入你的專案檔，確保你擁有 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉。

*小技巧：* 定期使用 `dotnet list package --outdated` 檢查套件更新，以獲得錯誤修正與新條碼符號的支援。

---

## 第二步：建立 Databar 條碼（create Databar barcode）

Databar Omnidirectional 適用於零售與物流，因為它能編碼 GTIN‑14 值加上其他資料。以下程式碼會建立條碼物件：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*為什麼重要：* `EncodeTypes.DatabarOmniDirectional` 列舉告訴函式庫使用 Databar 符號，而字串 `"(01)12345678901231"` 符合 GS1 應用識別碼格式，用於 14 位元的 GTIN。

---

## 第三步：定義常用參數 – X‑dimension 與基礎高度

大多數條碼掃描器要求最小 X‑dimension（最窄條的寬度）。將其設為 2 像素即可得到緊湊且可讀的圖像。

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

之後你可以在不重新建立產生器的情況下調整條碼高度——這正是 **如何設定條碼** 屬性於實例化之後的核心。

---

## 第四步：設定第一個條碼高度並儲存圖像（generate barcode image C#）

現在示範 **如何設定條碼** 高度的第一步。條碼高度決定每條的視覺長度；30 像素會產生較短的條碼，60 像素則會產生較高的版本。

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

執行後，`DatabarBarHeight30Pixels.png` 會包含一個條高為 30 像素的 Databar 條碼。使用任何圖像檢視器開啟即可驗證結果。

---

## 第五步：變更條碼高度並儲存第二張圖像

為說明 **如何設定條碼** 的值可以即時變更，我們將條碼高度調整為 60 像素，並寫入第二個檔案。

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

現在你擁有兩個 PNG 檔案，內容相同的 Databar 資料但視覺高度不同。這在需要較大條碼供列印標籤或較小條碼供螢幕顯示時相當實用。

---

## 第六步：完整、可執行的範例

將所有步驟整合，以下是一個自包含的主控台程式，執行上述所有操作。將程式碼複製到新的 `Program.cs` 檔案，將 `YOUR_DIRECTORY` 替換為實際資料夾路徑，然後執行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**預期輸出**

執行程式後，主控台會印出：

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

而 `C:\Barcodes`（或你自行指定的路徑）資料夾中會出現兩個 PNG 檔案。兩張圖片皆顯示可被標準 GS1 讀取器掃描的有效 Databar Omnidirectional 條碼。

---

## 常見問題

**這能支援其他影像格式嗎？**  
可以。將 `BarCodeImageFormat.Png` 改為 `Jpeg`、`Bmp`、`Gif` 或 `Tiff` 即可產生對應的檔案類型。

**我可以變更前景顏色嗎？**  
將 `generator.Parameters.Barcode.ForeColor` 設為任意 `System.Drawing.Color` 值，例如 `Color.Blue`。

**如果我要使用其他符號集該怎麼辦？**  
在建構子中傳入不同的 `EncodeTypes` 值，例如 `EncodeTypes.Code128` 產生線性條碼，或 `EncodeTypes.QR` 產生矩陣碼。

**有沒有辦法把條碼嵌入 PDF？**  
Aspose.Barcode 提供 `PdfGenerator` 類別。產生圖像後，你可以使用 Aspose.PDF 將其加入 PDF 頁面。

---

## C# 條碼產生的最佳實踐

* **重複使用 `BarcodeGenerator` 實例**，當你僅需微調尺寸時，可避免不必要的記憶體配置。  
* **釋放產生器**（`generator.Dispose()`）於使用完畢後，以即時釋放原生資源。  
* **驗證輸入資料**（例如 GTIN 長度）於建立條碼前，防止執行時例外。  
* **使用實體掃描器測試** X‑dimension 或條碼高度的變更；極端值可能影響可讀性。  
* **確保輸出資料夾對執行帳號具有寫入權限**，否則 `Save` 會拋出 `UnauthorizedAccessException`。

---

## 結論

現在你已掌握 **如何設定條碼** 的屬性，如 X‑dimension 與條碼高度，亦了解 **如何產生條碼** 圖片的完整 C# 程式碼，並能使用 Aspose.Barcode 建立 **create Databar barcode** 檔案。透過本完整範例，你可以產生多個 PNG 檔案，具備不同視覺特性，滿足任何 .NET 應用程式對 **generate barcode image C#** 的需求。

接下來，可探索如 **如何大量產生條碼**、將條碼嵌入 PDF，或切換至 QR、Code 128 等其他符號集。試著調整本文示範的參數，以微調條碼外觀，符合你的掃描環境。祝開發順利！

## 接下來你可以學什麼？

以下教學與本指南緊密相關，能進一步擴充你的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能或探索替代實作方式。

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}