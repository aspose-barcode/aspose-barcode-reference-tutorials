---
category: general
date: 2026-07-18
description: 使用 C# PDF417 條碼產生器在 C# 中建立 PDF417 條碼。遵循逐步教學以建立擴充代碼文字、設定外觀，並儲存圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: zh-hant
lastmod: 2026-07-18
og_description: 即時在 C# 中建立 PDF417 條碼。本指南說明如何使用 C# PDF417 條碼產生器、設定擴充模式，並匯出 PNG。
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: 在 C# 中建立 PDF417 條碼 – 完整生成器教學
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 在 C# 中建立 PDF417 條碼 – 條碼產生器指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 PDF417 條碼 – 條碼產生器指南

有沒有遇過需要在 C# 應用程式中 **建立 PDF417 條碼**，卻不知道從哪裡開始？你並不孤單——許多開發者在首次處理二維條碼時都會卡關。好消息是？只要使用內建的 **C# PDF417 條碼產生器**，只需幾行程式碼就能產生功能完整的條碼。

在本教學中，我們將完整說明整個流程：建立混合不同字元集的擴充編碼文字、設定產生器的視覺樣式，最後將條碼儲存為 PNG 檔案。完成後，你將擁有一段可直接放入任何 .NET 專案的即用程式碼，並提供處理 Unicode 字元或自訂模組寬度等邊緣案例的技巧。

---

## 所需環境

在開始之前，請確保你的機器上已具備以下項目：

- **.NET 6.0** 或更新版本（此範例亦支援 .NET Framework 4.6 以上）
- **Aspose.BarCode for .NET**（或任何提供 `BarcodeGenerator`、`EncodeTypes.Pdf417` 等功能的相容函式庫）
- 程式碼編輯器——Visual Studio、Rider，或是 VS Code 都可以
- 一個可寫入的資料夾，因為產生器會將 PNG 儲存至該處

就這些——不需要額外的 NuGet 套件，條碼函式庫本身已足夠。

---

## 逐步指南：**建立 PDF417 條碼**

### 1. 安裝條碼函式庫

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，裡面包含我們整個教學都會使用的 `BarcodeGenerator` 類別。

### 2. 建立擴充編碼文字

PDF417 支援 **擴充編碼**，允許在同一條碼中混合不同字元集。以下我們建立三個段落：

- 一個 Windows‑1251（西里爾文）段落
- 一個包含 Unicode 字元（日文「狗」與「右」的漢字）的 UTF‑8 段落
- 一個純文字段落

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**為什麼這很重要：**  
如果只使用純文字，你只能使用預設的 ASCII 子集。透過明確宣告 ECI（Extended Channel Interpretation）段落，可確保掃描器正確解讀每個部分，無論使用何種語言或符號。

### 3. 初始化 **C# PDF417 條碼產生器**

現在我們已取得有效的編碼文字字串，將它交給產生器。`using` 陳述式會自動釋放底層資源。

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. 設定外觀與編碼模式

預設設定會產生一個非常小的條碼，可能不易辨識。讓我們微調幾個參數：

- **X‑Dimension** – 控制每個模組的寬度（像素大小）
- **EncodeMode** – 告訴引擎將輸入視為擴充模式
- **TwoDDisplayText** – 可選的人類可讀文字，顯示在條碼下方

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**專業提示：** 若在標籤印表機上列印條碼，將 `XDimension` 提升至 20 px 或更高；大多數掃描器都喜歡多留一點空間。

### 5. 儲存條碼影像

最後，將影像寫入磁碟。函式庫支援 PNG、JPEG、BMP 以及多種向量格式——PNG 是安全的預設選擇，因為它能保留清晰的邊緣。

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

請確認 `YOUR_DIRECTORY` 已存在且可寫入。執行程式後，你應該會看到類似下圖的檔案。

![使用 C# PDF417 條碼產生器產生的 PDF417 條碼](https://example.com/images/pdf417-extended.png "使用 C# PDF417 條碼產生器產生的 PDF417 條碼")

---

## 使用 **C# PDF417 條碼產生器** – 深入探討

### 處理 Unicode 與特殊字元

若直接將 Unicode 符號寫入純文字條碼，產生器可能會退回預設編碼，導致輸出亂碼。使用 `AddECICodetext` 可明確告訴編碼器使用哪種字元集，避免猜測。若需支援 **阿拉伯文**、**希伯來文** 或 **表情符號**，只要選擇相對應的 `ECIEncodings` 值即可。

### 調整錯誤更正等級

PDF417 提供四個錯誤更正等級（0‑8）。等級越高，條碼的抗損毀能力越強，但同時會使條碼變大。可透過以下方式調整：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### 列印與螢幕的縮放

在螢幕上顯示時，你可以保留預設的 96 dpi。若要高解析度列印（300 dpi 或更高），請設定：

```csharp
generator.Parameters.ImageResolution = 300;
```

如此可確保儲存的 PNG 具備足夠細節，適合雷射印表機使用。

### 常見陷阱

- **缺少 `using` 指示** – 忘記 `using Aspose.BarCode.Encoding;` 會導致 `ECIEncodings` 未定義。
- **找不到資料夾** – `Save` 方法不會自動建立中間資料夾；請事先建立或使用 `Path.Combine` 搭配 `Environment.CurrentDirectory`。
- **編碼模式錯誤** – 若將 `EncodeMode` 保持在 `Pdf417EncodeMode.Auto`，函式庫可能會把擴充編碼文字當作純文字處理，進而移除 ECI 標記。

---

## 完整、可直接執行的範例

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## 接下來該學什麼？

以下教學與本指南的技巧密切相關，提供完整的程式碼範例與逐步說明，協助你掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 建立 dotcode 擴充編碼文字](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [建立條碼影像 C# – 設定 Codablock F 的列與欄](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}