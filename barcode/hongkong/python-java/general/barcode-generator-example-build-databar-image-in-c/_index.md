---
category: general
date: 2026-07-18
description: 條碼產生器範例，示範如何設定尺寸並在 C# 中產生 DataBar Stacked Omni‑Directional 條碼圖像。快速了解條碼編碼類型。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: zh-hant
lastmod: 2026-07-18
og_description: 條碼產生器範例會一步步指導您如何設定尺寸、選擇條碼編碼類型，並以最少的程式碼建立條碼影像 C# 專案。
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: 條碼產生器範例 – 快速於 C# 建立 DataBar 圖像
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: 條碼產生器範例 – 使用 C# 建立 DataBar 圖像
url: /zh-hant/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器範例 – 使用 C# 建立 DataBar 圖像

有沒有需要一個 **條碼產生器範例**，能真正產生實際條碼而不讓你抓狂的情況？你並不孤單。大多數開發者在嘗試弄清楚 **如何設定尺寸** 為 DataBar Stacked Omni‑Directional 條碼時會卡住，尤其是文件被大量術語埋沒。

在本教學中，我們將逐步說明一個完整、可直接執行的 C# 程式，展示 **how to generate databar** 圖像、挑選正確的 **barcode encode types**，最後 **create barcode image c#** 檔案，讓你可以放入任何專案。沒有多餘的說明——只提供可直接複製貼上的程式碼，並說明每一行的原理。

## 您需要的環境

- **.NET 6**（或任何較新的 .NET 版本）– 我們使用的 API 目標為 .NET Standard，因此也能在 .NET Framework 上執行。  
- **Aspose.BarCode for .NET** – 提供 `BarcodeGenerator` 的函式庫。你可以透過 NuGet 使用 `Install-Package Aspose.BarCode` 取得。  
- **C# IDE** – Visual Studio、Rider 或 VS Code 都可以。  
- 磁碟上的資料夾，用來儲存 PNG 檔案（程式碼會產生 `DatabarAspectRatio15.png` 與 `DatabarAspectRatio30.png`）。

全部準備好了嗎？太好了——讓我們開始吧。

## 條碼產生器範例 – 初始化產生器

首先，我們需要一個已設定為 **DataBar Stacked Omni‑Directional** 符號的 `BarcodeGenerator` 實例。這就是我們將使用的 **barcode encode type**。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **為什麼這很重要：** `EncodeTypes.DatabarStackedOmniDirectional` 告訴 Aspose 要渲染哪種符號。如果選錯類型，掃描器將無法辨識條碼，無論圖像看起來多好看。

## 如何設定條碼的尺寸

條碼的可讀性取決於其 **X‑dimension**（最窄條的寬度）。大多數情況下，2 像素的值就足夠，但你可以依據印表機或螢幕進行微調。

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **小技巧：** 如果你想知道 **how to set dimensions** 為其他條碼系列，只需使用相同的屬性鏈 (`Parameters.Barcode.XDimension`)，只要更改 `Pixels` 的值即可。

## 如何產生 DataBar Stacked Omni‑Directional 條碼

現在產生器已就緒，我們將調整 **aspect ratio** 屬性。此屬性控制 DataBar 的高寬比例，讓你可以產生短而方形的符號或高而窄的符號。

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **發生了什麼？** `AspectRatio = 15` 告訴引擎條的高度是寬度的 15 倍。產生的 PNG 會儲存在可執行檔旁邊。

## 建立條碼圖像 C# – 變更長寬比

讓我們透過將比例改為 30 並儲存第二個檔案，來證明其彈性。

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

執行程式後，你會得到兩個 PNG 檔案：

| 檔案 | 長寬比 | 大約尺寸 |
|------|--------|----------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

在任何圖像檢視器中開啟它們——你應該會看到乾淨且可掃描的 DataBar 符號。

## 條碼編碼類型概覽（可選但實用）

如果你想了解 Aspose 支援的其他 **barcode encode types**，以下是一張快速備忘表：

| EncodeTypes 列舉 | 說明 |
|------------------|------|
| `EncodeTypes.Code128` | 高密度字母數字 |
| `EncodeTypes.QR` | 二維矩陣碼 |
| `EncodeTypes.DatabarExpanded` | 零售用 GS1 DataBar |
| `EncodeTypes.DatabarStackedOmniDirectional` | **我們的重點** – 緊湊、全方向 |

了解正確的列舉可以讓你在切換專案時省去大量的反覆試驗。

## 常見陷阱與避免方法

- **Missing NuGet package** – 沒有 `Aspose.BarCode` 套件程式碼將無法編譯。請先執行 `dotnet add package Aspose.BarCode`。  
- **Wrong file path** – 若使用絕對路徑，請在 Windows 上再次確認反斜線 (`\\`)。如示範的相對路徑可保持可移植性。  
- **Aspect ratio too extreme** – 超過 50 的長寬比會使條碼對一般掃描器而言過高。大多數情況建議使用 15‑30。

## 完整原始碼（可直接複製貼上）

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

執行程式（`dotnet run` 或在 Visual Studio 按 **F5**）後，你會在主控台看到確認檔案已寫入磁碟的訊息。

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="條碼產生器範例輸出，顯示長寬比為 15 的 DataBar 條碼"}

## 總結

我們剛完成一個 **barcode generator example**，示範了 **how to set dimensions**、挑選正確的 **barcode encode types**，最後產生可在任何地方嵌入的 **create barcode image c#** 檔案。程式碼簡潔，概念清晰，現在你已具備堅實的基礎，可延伸此解決方案——例如加入文字說明、旋轉圖像，或切換至其他符號。

### 接下來做什麼？

- 嘗試 **different X‑dimensions** 以觀察掃描容差的變化。  
- 嘗試其他 **EncodeTypes**（如 `Code128` 或 `QR`）以擴充工具箱。  
- 自動化批次產生：遍歷產品 ID 的 CSV，為每筆產生 PNG。

如果遇到問題，請在下方留言或查閱 Aspose.BarCode 文件——其中有許多範例可補充本教學的內容。

祝開發順利，願你的條碼一次即能成功掃描！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在此處示範的技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [建立條碼圖像 C# – GS1 DataMatrix 範例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [如何產生 DataMatrix 條碼（ECC 200）使用 Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}