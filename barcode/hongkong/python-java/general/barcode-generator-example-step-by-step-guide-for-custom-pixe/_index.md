---
category: general
date: 2026-08-12
description: 條碼產生器範例，示範如何以精確的像素尺寸產生條碼。學習設定模組寬度、條碼高度，並建立 Planet 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: zh-hant
lastmod: 2026-08-12
og_description: 條碼產生器範例示範如何以精確的像素尺寸產生條碼。請遵循本指南，控制 Planet 與 RM4SCC 代碼的模組寬度與條碼高度。
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: 條碼產生器範例 – 在 C# 中自訂像素大小
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 條碼產生器範例 – 自訂像素尺寸的逐步指南
url: /zh-hant/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器範例 – 自訂像素尺寸的逐步指南

如果你需要一個 **條碼產生器範例**，讓你能夠控制每一個像素，這份指南會一步步說明如何做到。你將學會設定模組寬度、定義固定條高，並產生 Planet 與 RM4SCC 條碼，確保尺寸可預測。

大多數開發者在「如何產生條碼」圖像時，會遇到在不同螢幕或印表機上顯示不一致的問題。以下程式碼片段透過公開 Aspose.BarCode for .NET 函式庫的像素層級參數，解決了這個問題，讓你不必猜測即可產生一致的輸出。

## 你將學到

* 如何安裝所需的 NuGet 套件。  
* 如何產生自動計算高度的 Planet 條碼。  
* 如何產生高度明確為 100 像素的 Planet 條碼。  
* 如何使用相同的明確高度產生 RM4SCC 條碼。  
* 為什麼 **條碼像素尺寸** 會影響掃描可靠性。  
* 產生 Planet 條碼圖像時常見問題的除錯技巧。

你只需要 .NET 6 或更新版本、基本的 C# 開發環境，以及下載 NuGet 套件的網路連線。

---

## 條碼產生器範例 – 建置開發環境

在撰寫任何程式碼之前，請先確保 Aspose.BarCode 函式庫已加入你的專案。

### 安裝 Aspose.BarCode 套件

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新的穩定版 **Aspose.BarCode** 加入你的 `csproj`。還原完成後，即可開始使用 `BarcodeGenerator` 類別。

> **專業提示：** 目標設定為 .NET 6 或 .NET 7，可享受最新的效能提升與預設 UTF‑8 處理。

### 加入必要的 `using` 指令

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

這些命名空間會公開稍後教學中使用的 `BarcodeGenerator` 類別與 `BarCodeImageFormat` 列舉。

---

## 如何產生自訂像素尺寸的條碼

以下三個步驟示範完整的 **條碼產生器範例**。每一步都以先前的結果為基礎，你可以直接將整段程式碼貼到 Console 應用程式中執行，無需修改。

### 步驟 1 – 產生自動計算高度的 Planet 條碼

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**為什麼這樣可行：**  
`XDimension` 屬性定義單一條碼模組（最小的黑白單元）的寬度。當你省略 `BarHeight` 時，函式庫會自動計算一個保持 Planet 代碼標準長寬比的高度。

**預期輸出：** 產生名為 `PlanetAuto.png` 的 PNG 檔案，內含乾淨的 Planet 條碼。其高度會根據 4 像素的模組寬度自動調整，通常約為 60 像素（六字元資料）。

### 步驟 2 – 產生高度明確為 100 像素的 Planet 條碼

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**為什麼可能需要這樣做：**  
某些掃描設備要求最小條高才能可靠偵測。透過設定 `BarHeight.Pixels`，你可以保證每張產生的圖像皆符合此需求，無論編碼資料長度為何。

**預期輸出：** `PlanetHeight100.png` 與前一步的資料相同，但條碼高度正好為 100 像素，讓你完全掌控視覺大小。

### 步驟 3 – 產生相同高度的 RM4SCC 條碼

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**為什麼重要：**  
`EncodeTypes.RM4SCC` 是物流領域常用的堆疊線性條碼。將其條高與 Planet 條碼對齊，可在同一標籤上同時出現兩種符號時，簡化批次處理流程。

**預期輸出：** `RM4SCCHeight100.png` 顯示尺寸恰當的 RM4SCC 條碼，條高與 Planet 條碼設定的 100 像素相同。

> **結果驗證：** 用圖像檢視器開啟每個 PNG，確認黑條寬度正好為 4 像素，且在你指定的情況下高度為 100 像素。亦可將檔案匯入條碼掃描應用程式，確認解碼結果為「123456」。

---

## 了解條碼像素尺寸與條高

### 什麼是 **條碼像素尺寸**？

*Pixel size*（像素尺寸）指的是螢幕或印表機上，用來表示單一模組 (`XDimension`) 的實際像素數量。較大的像素尺寸會產生較大的條碼，對低解析度掃描器較友善，但會佔用更多標籤空間。

### `BarHeight` 如何影響可讀性？

`BarHeight` 屬性控制條碼的垂直長度。大多數 1‑D 條碼（包括 Planet 與 RM4SCC）的標準建議在 300 dpi 印刷時，最小高度為 10 mm，約等於 118 像素。低於此高度可能導致讀取錯誤，尤其在手機相機掃描時更為明顯。

### 何時讓函式庫自動計算高度？

如果條碼僅用於螢幕顯示，自動計算可保持長寬比一致，且減少手動調整的工作。若是必須符合嚴格 ISO 規範的印刷標籤，則應 **明確設定條高**。

---

## 產生 Planet 條碼時的常見陷阱與最佳實踐

| 陷阱 | 為什麼會發生 | 解決方式 |
|------|--------------|----------|
| 條太細或太粗 | 高解析度螢幕上 `XDimension` 預設為 1 像素 | 將 `XDimension.Pixels` 設為至少 3‑4，以提升可視性 |
| 掃描器讀不到碼 | `BarHeight` 對掃描器焦距太小 | 大多數行動掃描器使用 `BarHeight.Pixels` ≥ 100 |
| 圖片縮放後模糊 | 以 JPEG 儲存產生壓縮雜訊 | 使用 PNG (`BarCodeImageFormat.Png`) 以獲得無損輸出 |
| 條碼類型不符預期 | 使用錯誤的 `EncodeTypes` 列舉值 | 再次確認使用 `EncodeTypes.Planet` 產生 Planet 符號 |

### 專業提示：效能最佳化

在批次產生上千條條碼時，請重複使用同一個 `BarcodeGenerator` 實例，僅在每次儲存前變更 `CodeText` 與尺寸參數。這樣可避免重複分配內部渲染物件，執行時間最高可縮短約 30 %。

---

## 完整範例 – 整合所有步驟

建立新的 Console 專案（`dotnet new console -n BarcodeDemo`），然後將 `Program.cs` 內容取代為下列程式碼：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

使用 `dotnet run` 執行程式。執行完畢後，你會在專案資料夾中看到三個 PNG 檔案，分別示範不同的 **條碼產生器範例** 情境。

---

## 往後的學習方向與相關主題

* **如何產生其他格式的條碼** – 探索 `EncodeTypes.Code128`、`EncodeTypes.QR` 與 `EncodeTypes.DataMatrix` 以滿足 2‑D 需求。  
* **在 PDF 中嵌入條碼** – 結合 Aspose.BarCode 與 Aspose.PDF，直接在發票範本上放置條碼。  
* **根據使用者輸入動態調整條碼尺寸** – 計算  

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化你所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能，並在自己的專案中探索其他實作方式。

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}