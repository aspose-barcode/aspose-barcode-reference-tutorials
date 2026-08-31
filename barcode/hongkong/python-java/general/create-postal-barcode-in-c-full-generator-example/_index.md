---
category: general
date: 2026-07-15
description: 快速使用 C# 建立郵政條碼。此條碼產生器範例示範如何將 Planet 與 RM4SCC 條碼匯出為 PNG 格式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: zh-hant
lastmod: 2026-07-15
og_description: 使用此一步一步的指引在 C# 中建立郵政條碼。了解可將條碼圖像匯出為 PNG 格式的條碼產生器範例。
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: 使用 C# 建立郵政條碼 – 完整生成器指南
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: 在 C# 中建立郵政條碼 – 完整產生器範例
url: /zh-hant/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立郵政條碼 – 完整產生器範例

有沒有想過要在 .NET 專案中 **建立郵政條碼**，卻找不到完整文件？你並不孤單。無論是建置郵件標籤系統，或是自動化大量郵資，產生乾淨的條碼 PNG 都是必備技能。在本教學中，我們將一步步示範完整的 **條碼產生器範例**，說明如何 **匯出條碼影像** 為 **條碼 PNG 格式**。

我們會涵蓋從設定輸出資料夾，到調整模組寬度與條高度（適用 Planet 與 RM4SCC 標準）的所有細節。完成後，你將擁有一個可直接執行的 Console 應用程式，會產生四個 PNG 檔案——兩個自動高度、兩個固定 100 px 高度。沒有冗長說明，只有可直接 copy‑paste 的實用解決方案。

## 前置條件

在開始之前，請確保你已具備：

- .NET 6 SDK 或更新版本（程式碼同樣適用於 .NET Core 與 .NET Framework）
- 你熟悉的 IDE 或編輯器（Visual Studio、VS Code、Rider…）
- Aspose.BarCode for .NET NuGet 套件（使用 `dotnet add package Aspose.BarCode` 安裝）

就這些——不需要額外服務，也不需要 Web API。只要一個本機 C# 專案即可。

## 建立郵政條碼 – 步驟說明

以下我們將整個流程分成五個清晰步驟。每個步驟都有描述性的 **H2** 標題，包含主要或次要關鍵字，讓你快速找到所需資訊。

### 步驟 1：準備輸出目錄

首先，我們需要一個資料夾來存放產生的 PNG 檔案。硬編碼路徑在示範中可以接受，但正式環境建議從設定檔讀取。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **小技巧：** 使用 `Path.Combine` 可讓程式碼跨作業系統，`Directory.CreateDirectory` 即使資料夾已存在也安全可呼叫。

### 步驟 2：產生自動高度的 Planet 條碼

現在進入 **如何產生 planet 條碼** 的核心。我們建立 `BarcodeGenerator` 實例，設定模組寬度（X‑dimension），讓函式庫自行決定條高度。

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

`EncodeTypes.Planet` 列舉告訴 Aspose 我們要使用 Planet 符號，這是多國郵政服務常見的格式。因為沒有手動設定 `BarHeight`，產生器會選擇一個合理的預設值，確保條碼可讀。

### 步驟 3：產生自動高度的 RM4SCC 條碼

RM4SCC 是加拿大的郵政條碼格式。程式碼與 Planet 範例相同，展示了 **條碼產生器範例** 的通用模式，任何支援的符號皆可套用。

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

同樣依賴自動高度，適合快速原型或交由印表機自行縮放的情境。

### 步驟 4：產生固定高度 (100 px) 的 Planet 條碼

有時郵件系統要求嚴格的條高度——例如印表機必須是 100 px。以下示範如何 **匯出條碼影像** 並強制設定高度。

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

設定 `BarHeight.Pixels` 會覆寫自動計算。其他設定保持不變，確保自動與固定高度的影像在視覺上保持一致。

### 步驟 5：產生固定高度 (100 px) 的 RM4SCC 條碼

我們對 RM4SCC 也使用相同的固定高度方式。這再次證明 **條碼產生器範例** 的彈性：可依符號自行混合自動與手動設定。

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### 完整程式碼清單

將以下程式碼貼到新的 Console 專案，即可直接 **執行**。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

執行此程式後會產生以下檔案（全部為 **條碼 PNG 格式**）：

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

每張影像都是清晰的黑白條碼，隨時可供列印或後續處理。

## 為何此方法可行

- **一致性：** 於所有條碼將 `XDimension.Pixels` 固定為 4，確保模組寬度相同，對於需要特定點大小的掃描器尤為重要。
- **彈性：** 同一套程式碼即可在自動與固定高度之間切換，無需重寫產生器邏輯——非常適合多載具解決方案。
- **效能：** 產生 PNG 為輕量操作，Aspose 直接將影像串流寫入磁碟，避免不必要的記憶體開銷。
- **可移植性：** `Path.Combine` 與 `Directory.CreateDirectory` 使程式碼跨平台，於 Windows、Linux、macOS 均可執行。

## 常見問題與避免方式

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| 條碼看起來模糊 | 使用過低的 X‑dimension（例如 1 px） | 將 `XDimension.Pixels` 提升至至少 3‑4，適用於郵政條碼 |
| 掃描器拒絕影像 | 條高度對印表機而言過小或過大 | 使用 `BarHeight.Pixels` 依印表機規格調整 |
| PNG 檔案損毀 | 忘記關閉串流（使用 Aspose 時較少發生） | 讓 `Save` 方法自行處理釋放，除非必要不要自行管理串流 |
| 找不到輸出資料夾 | 硬編碼路徑指向不存在的目錄 | 在儲存前一定呼叫 `Directory.CreateDirectory` |

## 延伸範例

掌握 **建立郵政條碼** 基礎後，你可以進一步探索：

- **在條碼下方加入可讀文字**（`DisplayText` 屬性）
- **變更顏色**（`ForeColor`、`BackColor`）以符合品牌形象
- **批次處理** CSV 清單中的郵遞區號（在迴圈中使用產生器）
- **匯出其他格式** 如 SVG 或 PDF（`BarCodeImageFormat.Svg`、`BarCodeImageFormat.Pdf`）

上述每項延伸皆遵循本 **條碼產生器範例** 的相同模式，讓你無需從頭開始即可實驗。

## 結論

你

## 接下來該學什麼？

以下教學與本指南緊密相關，能在此基礎上延伸技術，並提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能與不同實作方式。

- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}