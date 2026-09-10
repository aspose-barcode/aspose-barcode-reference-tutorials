---
category: general
date: 2026-07-24
description: 使用 C# 條碼產生器產生郵政條碼。學習如何在僅幾行程式碼內建立 Planet 條碼並將條碼儲存為圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- c# barcode generator
- create planet barcode
- barcode save image
language: zh-hant
lastmod: 2026-07-24
og_description: 使用 C# 條碼產生器產生郵政條碼，然後將條碼儲存為 PNG 圖片以供郵政應用。快速、可靠，說明完整。
og_image_alt: Screenshot of a generated postal barcode image saved by a C# barcode
  generator
og_title: 在 C# 中產生郵政條碼 – Planet Barcode 指南
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate postal barcode using a C# barcode generator. Learn how to
    create Planet barcode and barcode save image in just a few lines of code.
  headline: Generate Postal Barcode in C# – Complete Guide with Planet Barcode
  type: TechArticle
- description: Generate postal barcode using a C# barcode generator. Learn how to
    create Planet barcode and barcode save image in just a few lines of code.
  name: Generate Postal Barcode in C# – Complete Guide with Planet Barcode
  steps:
  - name: What if my data contains letters?
    text: Planet barcodes accept only numeric characters. If you need alphanumeric
      data, consider switching to **Code128** or **QR** symbologies—both are supported
      by the same **c# barcode generator** library.
  - name: How do I change the image format?
    text: The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp`, etc.
      Just replace `BarCodeImageFormat.Png` with the desired enum value. PNG is recommended
      for lossless quality, but JPEG can reduce file size for web‑based applications.
  - name: Can I set a custom foreground/background color?
    text: 'Absolutely. Use the `Parameters.Barcode.BarcodeColor` and `Parameters.Barcode.BackgroundColor`
      properties:'
  - name: What about high‑resolution printing (300 dpi+)?
    text: 'Increase the `Resolution` property on the `BarcodeGenerator`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: 在 C# 中產生郵政條碼 – 完整指南（含 Planet 條碼）
url: /zh-hant/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生郵件條碼 – 使用 Planet 條碼的完整指南

是否曾在 .NET 專案中需要 **產生郵件條碼**，卻不確定該選擇哪個 API？你並不孤單——許多開發者在構建郵寄解決方案時會遇到這個問題，尤其是當郵政服務要求使用特定的 **Planet** 符號時。  

在本教學中，我們將使用 **C# 條碼產生器** 完整示範整個流程，說明如何 **建立 Planet 條碼** 物件，並示範最佳的 **條碼儲存影像** 方法，使其可直接列印或數位使用。完成後，你將擁有兩個可直接使用的 PNG：一個為實心條，另一個為空心條，完全符合郵件規範的要求。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.6 以上執行）  
- 參考 **Aspose.BarCode for .NET** 函式庫（或任何相容的 `BarcodeGenerator` 類別）  
- 基本的 C# 知識——只要會寫 `Console.WriteLine` 即可  

不需要額外服務、亦不需呼叫雲端，只要本機的 NuGet 套件與幾行程式碼即可。

---

## 步驟 1：安裝 C# 條碼產生器函式庫

首先，將函式庫加入你的專案。我們將使用 NuGet，因為它是最直接的方式。

```bash
dotnet add package Aspose.BarCode
```

> **小技巧：** 若你針對 .NET Framework，請在 Visual Studio 中開啟 NuGet 套件管理員，搜尋 **Aspose.BarCode** 即可。

安裝套件後，你即可使用 `BarcodeGenerator` 類別，這是我們 **c# 條碼產生器** 工作流程的核心。

## 步驟 2：建立簡易 Console 應用程式

建立一個新的 console 專案（或將程式碼加入現有專案）。程式骨架如下：

```csharp
using System;
using Aspose.BarCode.Generation;   // <-- core namespace
using Aspose.BarCode;               // for BarCodeImageFormat

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

執行此空白程式不會有任何輸出，但可確認編譯器已正確偵測到 `Aspose.BarCode` 參考。

## 步驟 3：產生郵件條碼 – 實心條

現在我們將使用 **產生郵件條碼** 的經典實心條樣式。Planet 符號需要數字字串；此處以 `"123456"` 作為範例。

```csharp
// Step 3.1: Create a Planet barcode generator with the data to encode
BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 3.2: Define the width of each bar (4 pixels works well for most printers)
filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3.3: Save the barcode image – bars are filled by default
filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**為何使用這些設定？**  
- `EncodeTypes.Planet` 告訴函式庫我們需要 **Planet** 格式，這是許多郵政服務的標準。  
- `XDimension.Pixels` 控制實體條寬；4 px 可在一般標籤印表機上產生清晰、可掃描的影像。  
- 呼叫 `Save` 會執行 **條碼儲存影像** 的操作。我們選擇 PNG，因為它保留無損細節，對高解析度列印至關重要。

執行程式後，你會在執行檔的工作目錄中看到 `PostalPlanetFilledBars.png`。開啟它，你應該會看到一排深色垂直條——正是郵政服務所要求的。

## 步驟 4：產生郵件條碼 – 空心條變體

某些郵件規範（或品牌指引）要求使用「空心」條樣式，即背景為深色而條為透明。為了達成此效果，我們將再次 **建立 planet 條碼**，僅切換一個屬性。

```csharp
// Step 4.1: Create a second Planet barcode generator for the same data
BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 4.2: Reuse the same bar width
emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Step 4.3: Configure the barcode to render empty bars (filled bars = false)
emptyGenerator.Parameters.Barcode.FilledBars = false;

// Step 4.4: Save the barcode image with empty bars
emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**有何變化？** 唯一的差異是 `FilledBars = false`。此設定會反轉繪製模式，產生條為「洞」的深色背景影像——非常適合已使用深色底的標籤紙張。

## 步驟 5：驗證輸出

在兩次 `Save` 呼叫之後，應該會得到兩個並排的 PNG 檔案：

| File | 視覺說明 |
|------|----------|
| `PostalPlanetFilledBars.png` | 白底黑條 – 經典郵件外觀 |
| `PostalPlanetEmptyBars.png` | 深色背景上切出的淺色「條」 – 空心條樣式 |

![產生郵件條碼範例](example-barcode.png){: .center alt="產生郵件條碼範例"}

如果影像看起來模糊，請再次確認 `XDimension.Pixels` 的數值；將其提升至 5 或 6 可能會提升低 DPI 印表機的可讀性。

## 常見問題與邊緣情況

### 如果我的資料包含字母怎麼辦？

Planet 條碼僅接受數字字元。如果需要字母與數字混合，請考慮改用 **Code128** 或 **QR** 符號——兩者皆受相同 **c# 條碼產生器** 函式庫支援。

### 如何變更影像格式？

`Save` 方法接受 `BarCodeImageFormat.Jpeg`、`Gif`、`Bmp` 等等。只要將 `BarCodeImageFormat.Png` 替換為想要的列舉值即可。建議使用 PNG 以獲得無損品質，但 JPEG 可在網路應用中減少檔案大小。

### 能否設定自訂前景/背景顏色？

當然可以。使用 `Parameters.Barcode.BarcodeColor` 與 `Parameters.Barcode.BackgroundColor` 屬性：

```csharp
filledGenerator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
filledGenerator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;
```

### 高解析度列印（300 dpi 以上）怎麼處理？

提升 `BarcodeGenerator` 上的 `Resolution` 屬性：

```csharp
filledGenerator.Parameters.ImageResolution.Dpi = 300;
```

## 完整範例程式

將所有步驟整合在一起，以下是一個可直接複製貼上至 `Program.cs` 並執行的完整獨立程式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------- Filled‑bars Planet barcode ----------
            BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;          // bar width
            filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Filled‑bars barcode saved.");

            // ---------- Empty‑bars Planet barcode ----------
            BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;          // same bar width
            emptyGenerator.Parameters.Barcode.FilledBars = false;            // render empty bars
            emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Empty‑bars barcode saved.");

            // Optional: inform the user where the files are located
            Console.WriteLine($"Files saved to: {Environment.CurrentDirectory}");
        }
    }
}
```

執行 `dotnet run`（或在 Visual Studio 按 **F5**）後，你會看到兩條確認訊息，接著產生兩個 PNG 檔案。

## 結論

現在你已了解如何在 C# 中使用可靠的 **c# 條碼產生器** **產生郵件條碼**，以及如何以實心與空心條樣式 **建立 planet 條碼** 物件，並掌握 **條碼儲存影像** 的完整步驟，以供後續處理。

從此你可以進一步探索：

- 在條碼下方加入可讀文字 (`Parameters.Barcode.CodeText`)、  
- 將 PNG 嵌入 PDF 發票（參考 **Aspose.PDF**），  
- 為成千上萬的地址自動化批次產生。

試著執行看看，調整條寬、變換顏色，你將快速掌握在任何 .NET 環境下的郵件條碼製作。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在專案中探索替代實作方式。

- [如何產生 Java 條碼 – 使用 Aspose 的澳洲郵政條碼](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [產生條碼影像 – Code 93 使用 Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [如何產生條碼 – Code 39 設定使用 Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}