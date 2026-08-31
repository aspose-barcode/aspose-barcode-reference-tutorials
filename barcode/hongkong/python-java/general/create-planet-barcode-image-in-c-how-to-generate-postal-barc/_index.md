---
category: general
date: 2026-07-15
description: 使用 C# 快速產生 Planet 條碼圖像。了解如何生成郵政條碼以及如何使用 Aspose.BarCode 將條碼圖像儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate postal barcode
- how to save barcode image
language: zh-hant
lastmod: 2026-07-15
og_description: 在 C# 中建立 Planet 條碼圖像。本指南說明如何產生郵政條碼以及如何儲存條碼圖像，並附有清晰的程式碼範例。
og_image_alt: Screenshot showing a generated Planet barcode image saved as PNG
og_title: 在 C# 中建立 Planet 條碼圖像 – 郵政條碼快速指南
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  headline: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  type: TechArticle
- description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  name: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  steps:
  - name: Why This Structure Works
    text: '- **Separate generators**: We instantiate two `BarcodeGenerator` objects
      because the `FilledBars` property is immutable once an image is rendered. Keeping
      them independent avoids side‑effects. - **X‑dimension choice**: A value of 4
      pixels balances readability and file size. If you need a higher‑reso'
  - name: Changing the Data Payload
    text: 'The `EncodeTypes.Planet` symbology expects numeric data up to 16 digits.
      To encode a different tracking number, just replace `"123456"` with your actual
      string:'
  - name: Adjusting Image Format
    text: If you need a JPEG for web delivery, swap `BarCodeImageFormat.Png` with
      `BarCodeImageFormat.Jpeg`. Remember JPEG introduces compression artifacts—avoid
      it for high‑precision scanning.
  - name: Handling Errors Gracefully
    text: 'When dealing with user‑supplied data, wrap the generation in a try‑catch
      block:'
  type: HowTo
- questions:
  - answer: Yes. Aspose.BarCode supports .NET Framework 4.5 and higher. Just change
      the target framework in your `.csproj` file.
    question: Does this work with .NET Framework 4.5?
  - answer: Replace `EncodeTypes.Planet` with any other enum value (e.g., `EncodeTypes.Code128`).
      The rest of the code stays the same.
    question: What if I need a different barcode symbology?
  - answer: 'Absolutely. Use `generator.Parameters.Barcode.BarColor = Color.Blue;`
      before saving. ## Conclusion You now know **how to create planet barcode image**
      in C#, **how to generate postal barcode** with the Aspose.BarCode library, and
      **how to save barcode image** as PNG files. The full example covered i'
    question: Can I change the bar color?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: 在 C# 中建立 Planet 條碼圖像 – 如何產生郵政條碼
url: /zh-hant/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 Planet 條碼圖像 – 如何產生郵件條碼

是否曾經需要在 .NET 專案中 **建立 planet 條碼圖像**，卻不知從何開始？你並不孤單。在本指南中，我們將示範如何使用 Aspose.BarCode **產生郵件條碼**，並說明 **如何將條碼圖像** 儲存為 PNG 檔案到磁碟。  

想像一下，你正在構建一個即時列印郵件標籤的寄件系統——擁有可靠的條碼產生器可以為你節省數小時的手動工作。完成本教學後，你將擁有一個可直接執行的主控台應用程式，會產生兩個 PNG 檔案：一個是實心條紋，另一個則僅顯示條紋輪廓。

## 前置條件

- .NET 6 SDK（或任何較新的 .NET 版本）已安裝。
- Visual Studio 2022 或 VS Code（搭配 C# 擴充功能）。
- **Aspose.BarCode for .NET** NuGet 套件。你可以透過 CLI 新增它：

```bash
dotnet add package Aspose.BarCode
```

不需要其他外部相依性。

## 步驟 1：建立專案骨架

首先，建立一個新的主控台專案，並引入條碼函式庫。

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

此時資料夾內會有一個 `Program.cs` 檔案，我們將在其中放入所有程式邏輯。

## 步驟 2：撰寫完整程式碼 – 建立 Planet 條碼圖像

以下是完整且獨立的程式。將它複製貼上至 `Program.cs`（覆寫 `dotnet new` 產生的範本程式）。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Namespace and class are optional in a top‑level program (C# 9+), but we keep them for clarity.
namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Create a Planet barcode generator with the desired data.
            // -----------------------------------------------------------------
            // The "Planet" symbology is used by many postal services for
            // tracking and sorting. Here we encode a simple numeric string.
            var generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // ---------------------------------------------------------------
            // 2️⃣  Set the X‑dimension (width of a single bar) to 4 pixels.
            // ---------------------------------------------------------------
            // XDimension controls the visual density of the barcode.
            // 4 px is a common default that works well on most printers.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 3️⃣  Save the barcode using the default *filled‑bars* appearance.
            // ---------------------------------------------------------------
            // BarCodeImageFormat.Png ensures a lossless image, perfect for
            // later processing or printing.
            string filledPath = "PlanetFilledBars.png";
            generator.Save(filledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Filled bars saved to {filledPath}");

            // -----------------------------------------------------------------
            // 4️⃣  Create another generator for the same data to show empty bars.
            // -----------------------------------------------------------------
            var emptyBarsGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyBarsGenerator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 5️⃣  Disable filled bars so only the outlines are drawn.
            // ---------------------------------------------------------------
            emptyBarsGenerator.Parameters.Barcode.FilledBars = false;

            // ---------------------------------------------------------------
            // 6️⃣  Save the barcode with empty bars.
            // ---------------------------------------------------------------
            string emptyPath = "PlanetEmptyBars.png";
            emptyBarsGenerator.Save(emptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Empty bars saved to {emptyPath}");

            // -----------------------------------------------------------------
            // 7️⃣  Quick verification – open the files if you’re on Windows.
            // -----------------------------------------------------------------
            // This is optional but handy when you run the demo locally.
            if (OperatingSystem.IsWindows())
            {
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = filledPath,
                    UseShellExecute = true
                });
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = emptyPath,
                    UseShellExecute = true
                });
            }
        }
    }
}
```

### 為何此結構可行

- **分離的產生器**：我們會建立兩個 `BarcodeGenerator` 物件，因為 `FilledBars` 屬性在圖像渲染後即為不可變。將它們分開可避免副作用。
- **X 方向尺寸選擇**：4 像素的值在可讀性與檔案大小之間取得平衡。若需要更高解析度的列印，可將其提升至 6 或 8。
- **以 PNG 儲存**：PNG 能保留條碼的銳利邊緣，這對郵政服務使用的光學掃描器至關重要。

## 步驟 3：執行示範並驗證輸出

編譯並執行程式：

```bash
dotnet run
```

你應該會在主控台看到訊息，確認兩個檔案已儲存。於專案資料夾中，你會看到：

- `PlanetFilledBars.png` – 實心條碼。
- `PlanetEmptyBars.png` – 僅有條紋輪廓。

以下為實心版本的視覺示例（僅供說明；實際輸出可能因 DPI 設定略有差異）。

![create planet barcode image example](https://example.com/planet-filled.png)

*Alt text: 示範建立 planet 條碼圖像的範例，顯示實心條紋的 Planet 條碼 PNG 圖片。*

## 步驟 4：微調條碼 – 常見變化

### 更改資料內容

`EncodeTypes.Planet` 符號要求最多 16 位數字資料。若要編碼其他追蹤號碼，只需將 `"123456"` 替換為實際的字串：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Planet, "9876543210123456");
```

### 調整圖像格式

若需要 JPEG 以供網路傳輸，請將 `BarCodeImageFormat.Png` 換成 `BarCodeImageFormat.Jpeg`。請記得 JPEG 會產生壓縮雜訊——對於高精度掃描應避免使用。

### 優雅地處理錯誤

處理使用者提供的資料時，請將產生過程包在 try‑catch 區塊中：

```csharp
try
{
    generator.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

這可確保應用程式在輸入無效時不會當機。

## 步驟 5：整合至更大型的應用程式

在實務的寄件系統中，你可能會即時產生條碼，並嵌入 PDF 或標籤範本中。以下是一段快速程式碼示例，說明如何取得條碼的 `byte[]` 以供後續處理：

```csharp
using System.IO;

// Generate the image in memory
using (MemoryStream ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    byte[] barcodeBytes = ms.ToArray();

    // Pass barcodeBytes to a PDF library, send over a network, etc.
}
```

現在你可以將此位元組陣列傳入 iTextSharp、QuestPDF 或其他文件產生器，而不必寫入檔案系統。

## 常見問題 (FAQ)

**Q: 這能在 .NET Framework 4.5 上運作嗎？**  
A: 可以。Aspose.BarCode 支援 .NET Framework 4.5 及以上版本。只需在 `.csproj` 檔案中更改目標框架即可。

**Q: 若需其他條碼符號集該怎麼辦？**  
A: 將 `EncodeTypes.Planet` 替換為其他列舉值（例如 `EncodeTypes.Code128`），其餘程式碼保持不變。

**Q: 可以更改條紋顏色嗎？**  
A: 當然可以。在儲存之前使用 `generator.Parameters.Barcode.BarColor = Color.Blue;`。

## 結論

現在你已了解如何在 C# 中 **建立 planet 條碼圖像**、如何使用 Aspose.BarCode 函式庫 **產生郵件條碼**，以及 **如何將條碼圖像** 儲存為 PNG 檔案。完整範例涵蓋了初始化、X 方向尺寸調整、實心條紋切換以及磁碟儲存，並提供了幾個實務整合的小技巧。

準備好進一步了嗎？試著將產生的 PNG 嵌入 PDF 標籤、嘗試不同顏色，或改用更高解析度的圖像格式。當你結合條碼產生與現代 .NET 工具時，無所不能。

如果你遇到任何問題或有擴充想法，歡迎在下方留言。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並以完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何使用 DataMatrix C40 以 PNG 儲存（Aspose.BarCode）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼安靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [產生條碼圖像 – Code 93（使用 Aspose.BarCode）](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}