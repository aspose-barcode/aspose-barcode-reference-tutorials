---
category: general
date: 2026-07-18
description: 快速生成 PDF417 條碼。了解如何設定連結模式以及如何使用 Aspose.BarCode 生成 PDF417 條碼，提供清晰的逐步教學。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: zh-hant
lastmod: 2026-07-18
og_description: 即時產生 PDF417 條碼。本教學示範如何設定連結模式以及使用 Aspose.BarCode 產生 PDF417 條碼，並附上可執行的程式碼。
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: 在 C# 中生成 PDF417 條碼 – 完整逐步指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: 在 C# 中生成 PDF417 條碼 – 完整程式設計指南
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 PDF417 條碼 – 完整程式指南

是否曾經需要在 .NET 應用程式中 **產生 PDF417 條碼**，卻不知從何開始？你並不孤單。無論你是要建造登機證印表機、倉儲掃描器，或只是試驗 2‑D 條碼，讓 PDF417 正式運作其實比想像中更簡單。

在本指南中，我們將逐步說明如何使用 Aspose.BarCode **產生 PDF417 條碼**、展示 **如何設定 linked mode**，以及說明 **如何以自訂參數產生 PDF417 條碼**——全部以一個可直接複製貼上的範例呈現。

## 你將學會

- 必備的 NuGet 套件。
- 如何以自訂文字初始化 PDF417 產生器。
- **如何設定 linked mode** 讓條碼可跨列顯示。
- 模組大小與欄位數的額外調整方式。
- 如何將結果儲存為 PNG、JPEG 或任何支援的格式。
- 常見問題與快速除錯技巧。

### 前置條件

- .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.7+）。
- 基本的 C# 知識。
- Visual Studio 2022（或任何你慣用的 IDE）。
- 免費的 Aspose.BarCode 試用版或正式授權。

> **專業提示：** 若是全新機器，請在專案資料夾的終端機中執行 `dotnet add package Aspose.BarCode`。此指令會自動下載所有必需的套件。

---

## Step 1: Install Aspose.BarCode and Add Namespaces

First things first—let’s bring the library into the project.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

然後，在 C# 檔案的最上方加入必要的命名空間：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **為什麼這很重要：** 若未引用 `Aspose.BarCode.Generation` 命名空間，就無法使用 `BarcodeGenerator`；而 `System.Drawing.Imaging` 命名空間則提供 `ImageFormat` 列舉，用於儲存檔案。

---

## Step 2: Initialize the PDF417 Barcode Generator

Now we create a generator instance and feed it the text we want to encode. This is the core of **how to generate PDF417 barcode**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **說明：** `EncodeTypes.Pdf417` 告訴 Aspose 我們使用的是 PDF417 符號。第二個參數 `"Aspose"` 則是條碼被掃描時會顯示的資料。

---

## Step 3: Define the Module Size (X‑Dimension)

The module size controls how big each tiny square (or “pixel”) of the barcode appears. Smaller values yield a tighter barcode; larger values make it more readable on low‑resolution printers.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **常見範圍：** 1–4 像素適用於大多數螢幕。若在高 DPI 標籤印表機上列印，可將數值調高至 3 或 4。

---

## Step 4: Configure Columns and Enable Linked Mode

Here’s where we answer **how to set linked mode**. Linked mode lets a PDF417 barcode split across multiple rows, which is handy when you have limited horizontal space.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **為什麼要使用 linked mode？** 想像一下條碼必須放入狹窄的 UI 元件中。將 `IsLinked = true` 後，函式庫會自動將符號分割成多列，同時保持可掃描性。

> **邊緣情況：** 若同時將 `Columns` 設得過低且啟用 linked mode，Aspose 可能會大幅增加列數，導致圖像畫布過小而溢位。請留意最終圖像的尺寸。

---

## Step 5: Save the Barcode Image

Finally, write the barcode out to a file. You can choose PNG, JPEG, BMP, or even PDF. PNG is loss‑less, making it ideal for further processing.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **結果：** 你會看到一個清晰的 PDF417 條碼，具備三欄、2 像素的模組大小，且若資料超過單列寬度，會自動以 linked rows 方式呈現。

---

## Full Working Example

Below is the complete, ready‑to‑run program. Copy‑paste it into a new console project (`dotnet new console`) and hit **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### 預期輸出

執行程式後會在主控台印出確認訊息，且資料夾中會出現 `Pdf417Linked.png`。開啟 PNG 檔案即可看到一個三欄的 PDF417 條碼，若資料過長會跨兩列（感謝 linked mode）。使用手機條碼掃描 App 掃描後會顯示文字 **“Aspose”**。

---

## 常見問題與除錯

### 1. *條碼模糊是什麼原因？*  
通常是 DPI 設定問題。可提升 `XDimension.Pixels`，或使用 `generator.Save(..., BarCodeImageFormat.Png, 300)` 以 300 DPI 儲存圖像。

### 2. *可以編碼更長的字串嗎？*  
可以——PDF417 最多可容納約 1,850 個字元。若超過所選欄位數的容量，函式庫會自動增加列數。調整 `Columns` 或啟用 `IsLinked` 以保持條碼尺寸緊湊。

### 3. *正式環境需要授權嗎？*  
Aspose.BarCode 在評估模式下仍可使用，但產生的條碼會帶有小水印。購買授權即可移除水印，並解鎖如錯誤更正等進階功能。

### 4. *如何以其他格式產生 PDF417 條碼？*  
只要變更 `Save` 的第二個參數即可。JPEG 使用 `BarCodeImageFormat.Jpeg`；PDF 使用 `BarCodeImageFormat.Pdf`。

---

## 延伸範例

既然已掌握 **如何產生 PDF417 條碼** 以及 **如何設定 linked mode**，你可以進一步探索：

- **錯誤更正等級** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **加入邊框** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **自訂顏色** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **將條碼嵌入 PDF 報表** – 結合 Aspose.PDF 與 Aspose.BarCode。

上述所有調整皆遵循相同模式：在 `generator.Parameters.Barcode.Pdf417`（或通用的 `Barcode` 物件）下找到相應屬性並賦值即可。

---

## 結論

我們已完整說明如何在 C# 中 **產生 PDF417 條碼**，從安裝 Aspose.BarCode、設定 linked mode 到儲存圖像。依照上述步驟，你即可在任何 .NET 解決方案中嵌入可投入生產的條碼產生器。

重點回顧：

1. 使用 `EncodeTypes.Pdf417` 初始化。
2. 調整 `XDimension` 以取得最佳視覺效果。
3. 設定 `Columns` 並啟用 `IsLinked` 以控制版面（**how to set linked mode**）。
4. 以所需格式儲存。

歡迎自行嘗試其他參數，並在留言區分享你的成果或提出問題。祝程式開發順利，條碼一次即能成功掃描！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步深化你的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能或探索其他實作方式。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}