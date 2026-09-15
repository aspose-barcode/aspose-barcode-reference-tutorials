---
category: general
date: 2026-07-27
description: 快速建立星球條碼圖像。學習如何使用 C# 產生星球條碼，並自訂實心或空白條。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: zh-hant
lastmod: 2026-07-27
og_description: 在幾秒內創建行星條碼圖像。跟隨本指南了解如何生成行星條碼、調整 X 軸尺寸，並在實心條與空心條之間切換。
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: 建立行星條碼圖像 – 完整 C# 教學
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: 製作行星條碼圖像 – 步驟指南
url: /zh-hant/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 planet 條碼圖像 – 完整 C# 教程

有沒有想過 **如何產生 planet 條碼** 用於郵件系統或物流應用程式？你不是第一個為此抓頭的人。在本教程中，我們將逐步說明建立 **create planet barcode image** 檔案所需的一切，從 `BarcodeGenerator` 類別的基礎到調整 X‑dimension 以及將實心條換成空心條。

我們還會簡要看看相關的符號系統——RM4SCC——讓你了解相同的圖樣如何應用於其他郵政條碼。完成後，你將擁有三段可直接執行的程式碼，產生 PNG 檔案，直接放入你的專案中使用。

## 你需要的環境

- .NET 6.0 或更新版本（程式碼同樣支援 .NET Framework 4.7+）  
- 參考 **Aspose.BarCode**（或任何提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的函式庫）  
- 你熟悉的 IDE——Visual Studio、Rider 或 VS Code 都可以  
- 一個可寫入影像的資料夾（在範例中將 `YOUR_DIRECTORY` 替換成實際路徑）

就這些。除了條碼函式庫本身，無需額外的 NuGet 套件。

---

## 步驟 1：設定專案與引用

首先，建立一個小型的 console 應用程式，讓程式碼可以立即執行。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **小技巧：** 保持 `Main` 方法簡潔；將每個情境委派給獨立的方法。這樣程式碼更易閱讀，也與原始範例中的三個示例相呼應。

---

## 步驟 2：**create planet barcode image**（預設實心條）

Planet 符號被多家郵政服務用於追蹤編號。要 **create planet barcode image** 並使用一般的實心條，只需以下三行程式碼：

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### 為什麼 X‑dimension 很重要
X‑dimension 決定每個微小條（或稱「模組」）的寬度。**4 像素** 的設定可產生在螢幕上清晰、在標準標籤印表機上列印良好的條碼。如果需要更高解析度的列印，可將數值調整至 6 或 8。

### 預期輸出
開啟產生的 `PostalPlanetFilledBars.png`，你會看到經典的 Planet 條碼——實心的垂直條，兩側各有安靜區。外觀與郵件信封上常見的範例相同。

---

## 步驟 3：**create planet barcode image**（空心條）

有時郵政規範要求使用 *空心條* 風格，即條碼以輪廓而非實心呈現。只要改變一個屬性即可切換。

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### 「FilledBars = false」的作用
將 `FilledBars` 設為 `false` 會讓渲染引擎只繪製條的輪廓。這在需要較輕量的螢幕顯示圖像，或列印規範明確要求空心樣式時特別有用。

### 預期輸出
`PostalPlanetEmptyBars.png` 檔案顯示與前述相同的圖樣，但每條僅為細線而非實心方塊。非常適合在彩色紙張上低對比度列印。

---

## 步驟 4：產生 RM4SCC 條碼（加分項）

雖然本教學的重點是 Planet 符號，但同一套 API 也能 **create planet barcode image**‑類似的結果，用於其他郵政條碼。以下示範如何產生 RM4SCC（荷蘭郵編條碼）：

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### 何時使用 RM4SCC
RM4SCC 是荷蘭的「Postcode」條碼。如果你在開發跨國物流平台，同時具備 Planet 與 RM4SCC 產生器可省下大量樣板程式碼。

---

## 常見問題與特殊情況

### 若需要不同的影像格式該怎麼做？
只要將 `BarCodeImageFormat.Png` 換成 `Jpeg`、`Bmp` 或 `Gif` 即可。函式庫會自動處理轉換。

### 如何變更條碼高度？
使用 `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`（或像素，視函式庫版本而定）。較高的數值會產生較長的條碼，有助於在低解析度掃描器上提升辨識率。

### 能否直接將條碼嵌入 PDF？
絕對可以。`Save` 方法在寫入串流的重載會回傳 `byte[]`，將該串流交給 PDF 產生函式庫（例如 iTextSharp），即可自動產生郵寄標籤。

### 若資料字串包含非數字字符會怎樣？
Planet 與 RM4SCC 只接受 **純數字** 資料。傳入字母會拋出 `ArgumentException`。請先驗證輸入：

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### X‑dimension 會影響掃描速度嗎？
較大的 X‑dimension 會產生更健壯的條碼，通常能提升掃描速度，尤其在低品質掃描器上。然而，同時也會使標籤尺寸變大，需要在可讀性與空間限制之間取得平衡。

---

## 完整範例（三種方法全部示範）

以下是可直接貼到新 console 專案的完整程式碼。將 `YOUR_DIRECTORY` 替換為你的應用程式可寫入的絕對或相對路徑。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

執行程式後，開啟三個 PNG 檔案，即可看到前述說明的圖像。無需額外設定。

---

## 重點回顧與後續步驟

我們已從零開始說明 **如何產生 planet 條碼** 圖像，切換實心與空心樣式，並延伸至 RM4SCC。關鍵要點如下：

1. 使用正確的 `EncodeTypes` 與資料建立 `BarcodeGenerator`。  
2. 調整 `XDimension.Pixels` 以控制條寬。  
3. 設定 `FilledBars = false` 取得空心條變體。  
4. 以你偏好的影像格式儲存結果。

現在你已能 **create planet barcode image** 檔案，以下是幾個後續建議：

- **批次產生**：遍歷 CSV 中的追蹤號，為每筆產生 PNG。  
- **動態尺寸**：在 Web API 中將 X‑dimension 與條碼高度作為可設定參數。  
- **與標籤印表機整合**：將 PNG 位元組直接傳給支援 ZPL 的印表機，即時列印標籤。

盡情實驗吧——更換資料字串、嘗試不同尺寸，或在同一標籤上結合 QR Code。條碼函式庫足夠彈性，能應付各種需求。

有任何棘手情境不確定該如何處理？歡迎在下方留言，我們一起排除問題。祝開發順利！

## 接下來可以學什麼？

以下教學與本篇內容密切相關，能進一步深化你對 API 功能的掌握，並探索在專案中實作的其他方式。

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}