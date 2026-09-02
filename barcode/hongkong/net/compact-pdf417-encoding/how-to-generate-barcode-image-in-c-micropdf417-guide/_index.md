---
category: general
date: 2026-07-18
description: 學習如何在 C# 中使用 MicroPdf417 格式產生條碼圖像。一步一步設定尺寸並儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- micro pdf417 barcode
- BarcodeGenerator class
- set barcode dimensions
- save barcode as png
language: zh-hant
lastmod: 2026-07-18
og_description: 如何在 C# 中產生條碼圖像？請跟隨本指南建立 MicroPdf417 條碼、調整其大小，並匯出為 PNG 檔案。
og_image_alt: Screenshot of a MicroPdf417 barcode image generated in C#
og_title: 如何在 C# 中生成條碼圖像 – 完整的 MicroPdf417 教學
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  headline: How to Generate Barcode Image in C# – MicroPdf417 Guide
  type: TechArticle
- description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  name: How to Generate Barcode Image in C# – MicroPdf417 Guide
  steps:
  - name: Change Image Format
    text: 'You aren’t limited to PNG. Switch to JPEG or BMP by adjusting the second
      argument of `Save`:'
  - name: Increase DPI for Print
    text: 'For high‑resolution prints, bump the `Resolution` property:'
  - name: Add Quiet Zone (Margin)
    text: 'A quiet zone helps scanners differentiate the barcode from surrounding
      graphics:'
  - name: Encode Different Data Types
    text: 'MicroPdf417 works with numeric, alphanumeric, and binary data. If you need
      to embed a URL, just replace the text:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中產生條碼圖像 – MicroPdf417 指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼圖像 – MicroPdf417 指南

有沒有想過在 C# 中 **如何產生條碼圖像** 而不必翻閱無盡的文件？你並不是唯一的疑問者。無論你是要建立票務系統、產品目錄，或只是需要一個快速的 QR‑style 代碼，掌握條碼產生技術都能為你節省時間與麻煩。

在本教學中，我們將逐步說明如何使用 `BarcodeGenerator` 類別產生 **MicroPdf417 條碼圖像**、調整其尺寸，並將結果儲存為 PNG。內容精簡——只提供一個完整、可直接執行的範例，讓你今天就能複製貼上到專案中。

## 你將學會

- 設定 `BarcodeGenerator` 以使用 MicroPdf417 格式  
- **設定條碼尺寸**，如模組寬度與欄位數  
- **將條碼儲存為 PNG** 至你選擇的資料夾  
- 可選的高解析度輸出與錯誤處理調整  

完成後，你將能自信地回答 *「如何產生條碼圖像」*，同時也奠定了建立其他條碼類型的堅實基礎。

---

## 前置條件

在開始之前，請確保你已具備以下條件：

1. **.NET 6.0 或更新版本**（此程式碼亦可於 .NET Framework 4.5+ 執行）  
2. 參考 **Aspose.BarCode** 函式庫（或任何提供 `BarcodeGenerator` 的函式庫）。你可以透過 NuGet 取得：  

   ```bash
   dotnet add package Aspose.BarCode
   ```

3. 一個不錯的 IDE——Visual Studio、Rider 或 VS Code 都可以。  
4. 對將要儲存 PNG 檔案的目錄具有寫入權限。  

> **專業提示：** 若你使用其他條碼函式庫，類別名稱可能會不同，但整體流程仍然相同。

## 步驟 1：建立 MicroPdf417 條碼產生器

首先，你需要一個已設定為 **MicroPdf417 條碼** 格式的 `BarcodeGenerator` 實例。此物件是將文字轉換為視覺條碼的引擎。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // Choose the MicroPdf417 format
    "Åspóse.Barcóde©");               // The data you want to encode
```

**為什麼重要：**  
`EncodeTypes.MicroPdf417` 告訴函式庫使用緊湊的 PDF417 變體，適合短字串與有限空間。文字可以包含 Unicode 字元，如上所示，因而不受限於純 ASCII。

## 步驟 2：設定條碼尺寸

現在產生器已建立，你可能想要控制每個模組（小方格）的大小以及條碼的欄位數。這就是 **設定條碼尺寸** 的用意所在。

```csharp
// Step 2: Adjust appearance – module width and column count
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels
generator.Parameters.Barcode.Pdf417.Columns = 4;    // Number of columns (affects height)
```

- **`XDimension.Pixels`** – 較大的數值會讓條碼較易掃描，但會增加檔案大小。  
- **`Pdf417.Columns`** – 欄位較少會使條碼在垂直方向壓縮；欄位較多則在水平方向拉長。  

> **注意：** 若將模組寬度設定過低（例如 1 像素），在高 DPI 螢幕上會產生模糊影像。2‑4 像素之間的值對大多數印表機而言表現良好。

## 步驟 3：將條碼圖像儲存為 PNG

在產生器設定完成後，最後一步是將圖形寫入磁碟。這即符合 **將條碼儲存為 png** 的需求。

```csharp
// Step 3: Export the barcode to a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**背後發生了什麼？**  
`Save` 會將條碼渲染成位圖，編碼為 PNG（無損壓縮），並將位元組寫入指定位置。若目錄不存在，`Save` 會拋出例外——因此在正式程式碼中建議將其包在 `try/catch` 區塊內。

## 完整可執行範例

將上述步驟整合起來，以下是一個可即時執行的獨立 Console 應用程式：

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set dimensions
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 3️⃣ Define output path
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        // 4️⃣ Save as PNG
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

**預期輸出：** 於桌面上產生一個清晰的 `MicroPdf417.png` 檔案，顯示編碼字串 `Åspóse.Barcóde©`。使用任何影像檢視器開啟以確認條碼清晰且可被掃描。

## 進階選項（可選）

如果你想擴充基本流程，可考慮以下調整——每項皆對應我們清單中的次要關鍵字。

### 變更影像格式

並非只能使用 PNG。只要調整 `Save` 的第二個參數，即可改為 JPEG 或 BMP：

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

### 提升列印 DPI

若需高解析度列印，可提升 `Resolution` 屬性：

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

### 新增靜區（邊距）

靜區可協助掃描器將條碼與周圍圖形區分開來：

```csharp
generator.Parameters.Barcode.QR.QrQuietZone = 4; // 4 modules of margin
```

### 編碼不同資料類型

MicroPdf417 支援數字、字母數字與二進位資料。若需嵌入 URL，只需更換文字內容：

```csharp
generator.CodeText = "https://example.com";
```

## 常見問題與避免方法

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 條碼顯得模糊 | `XDimension.Pixels` 設為 1 或儲存後再調整影像大小 | 請使用至少 2 像素，並避免後處理縮放 |
| 掃描器無法讀取條碼 | 欄位數過多，超過資料長度 | 減少 `Pdf417.Columns`，或讓函式庫自動調整大小（`Columns = 0`） |
| Unicode 字元顯示為 � | 函式庫版本過舊或缺少字型支援 | 更新 Aspose.BarCode 至最新版本，並確保正確編碼 |
| `Save` 拋出 `DirectoryNotFoundException` | 輸出資料夾不存在 | 事先建立資料夾，或使用已知資料夾的 `Path.Combine` |

## 測試你的條碼

產生圖像後，你可以使用任何條碼掃描應用程式（大多數智慧手機相機已內建條碼讀取功能）來驗證。將相機對準螢幕上的 PNG 檔或列印出來——若應用程式讀取到 `Åspóse.Barcóde©`，即表示你成功回答了 **如何產生條碼圖像**。

## 結論

我們已說明所有使用 C# 與 MicroPdf417 格式 **產生條碼圖像** 所需的知識：

1. **建立** 含有資料的 `BarcodeGenerator`。  
2. **設定條碼尺寸** 以控制大小與可讀性。  
3. **將條碼儲存為 PNG**（或任何其他支援的格式）。  

從此你可以嘗試不同的條碼類型、調整列印 DPI，或直接將圖像嵌入 PDF 或報表。建構基礎相同，隨時可以將 `EncodeTypes.MicroPdf417` 換成 `EncodeTypes.QR` 或 `EncodeTypes.Code128`，再重複上述步驟。

對其他條碼標準有疑問或需要協助調整外觀嗎？在下方留言，我們祝你編程愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以示範的技巧為基礎。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生具有自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼（ECC 200）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}