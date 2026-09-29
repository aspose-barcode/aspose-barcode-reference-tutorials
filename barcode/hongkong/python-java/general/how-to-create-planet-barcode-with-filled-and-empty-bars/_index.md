---
category: general
date: 2026-09-29
description: 使用 Aspose.Barcode 的逐步指南：在 C# 中建立包含實心與空白條的行星條碼
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: zh-hant
lastmod: 2026-09-29
og_description: 快速在 C# 中建立 Planet 條碼。了解如何渲染實心條、切換為空心條，並使用 Aspose.Barcode 調整 X 尺寸。
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: 使用實心與空白條製作星球條碼 – C# 教學
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何創建帶有實心與空心條的行星條碼
url: /zh-hant/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立 planet barcode（填滿條與空白條）

如果你需要在 C# 中**建立 planet barcode**影像，本指南會明確說明如何產生填滿條與空白條兩種版本。你將會看到如何設定條寬（X‑dimension）、切換 `FilledBars` 屬性，並以 PNG 檔案儲存結果——全部使用 Aspose.Barcode 函式庫。

產生郵件條碼是物流系統、郵寄清單應用程式與物流儀表板的常見需求。完成本教學後，你將擁有兩個可直接使用的 PNG 檔案，可嵌入報告、電子郵件或列印文件中。

## 前置條件

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 或更新版本 | 為 C# 範例提供執行環境。 |
| Visual Studio 2022（或任何 C# IDE） | 讓你編譯並執行程式碼。 |
| **Aspose.Barcode for .NET** NuGet 套件 | 提供 `BarcodeGenerator` 類別與 `EncodeTypes.Planet`。使用 `dotnet add package Aspose.Barcode` 安裝。 |
| 具有寫入磁碟資料夾的權限 | `Save` 方法會將 PNG 檔寫入你指定的路徑。 |

## 步驟 1：設定專案並匯入命名空間

建立一個新的 console 專案（或將程式碼加入現有專案），並參照 Aspose.Barcode 命名空間。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

這些 `using` 指令讓你取得教學所需的 `BarcodeGenerator`、`EncodeTypes` 以及影像格式列舉值。

## 步驟 2：建立預設（填滿）條的 Planet 條碼

第一個條碼使用函式庫的預設呈現方式，會將條碼填滿。

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**為什麼會這樣運作：**  
`EncodeTypes.Planet` 告訴 Aspose.Barcode 使用 **Planet** 符號，這是美國郵政服務使用的郵件條碼。`XDimension` 屬性控制每條的寬度；設定為 4 像素即可產生在一般標籤印表機上列印良好的條碼。預設情況下，`FilledBars` 為 `true`，因此條碼呈現為實心。

## 步驟 3：建立空白條的 Planet 條碼

若要以*空白*條產生相同資料，只需切換 `FilledBars` 旗標，其他設定保持不變。

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**為什麼重要：**  
某些郵寄系統需要 **empty‑bars** 樣式，以提升條碼在深色背景或對比色方案下的可讀性。將 `FilledBars = false` 後，產生器只繪製條碼的輪廓，內部保持透明。

## 預期輸出

執行程式後，資料夾 `C:\Barcodes`（或你指定的路徑）會包含兩個 PNG 檔案：

| File | Visual description |
|------|---------------------|
| `PlanetFilledBars.png` | 條碼為白色背景上實心黑色矩形。 |
| `PlanetEmptyBars.png`  | 條碼為黑色輪廓，條內部透明（顯示背景）。 |

兩張影像皆編碼相同的數字字串 `"123456"`，且使用 4 像素的條寬，確保除了填充樣式外外觀一致。

## 常見變化與例外情況

### 變更條寬

若標籤印表機需要不同的條寬，可調整 `XDimension.Pixels` 的數值。對於高解析度印表機，**2** 或 **3** 像素較為適合；對於低解析度印表機，**5** 或 **6** 像素可提升掃描可靠度。

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### 使用不同的影像格式

Aspose.Barcode 支援 PNG、JPEG、BMP、GIF 與 TIFF。將 `BarCodeImageFormat.Png` 替換為其他列舉值，即可符合後續工作流程的需求。

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### 在迴圈中產生多筆條碼

當需要一次產生多筆 Planet 條碼（例如郵寄清單）時，可將產生器程式碼包在 `foreach` 迴圈中，並於每次迭代更改資料字串。

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### 處理無效輸入

Planet 符號僅接受 **5‑8** 位數字字串。提供無效值會拋出 `ArgumentException`。可使用簡易驗證方法來防止此情況。

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## 專業提示：使用掃描器模擬器驗證條碼

Aspose.Barcode 內建 `BarcodeReader` 類別，可用來確認產生的影像能正確解碼回原始資料。

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

若輸出於兩個檔案皆顯示 `"123456"`，即表示條碼正確產生。

## 結論

現在你已了解如何在 C# 中**建立 planet barcode**影像，並可使用填滿與空白條兩種樣式、控制 **Planet 條碼 XDimension**，以及使用 **Aspose.Barcode** 函式庫以 PNG 格式儲存結果。可依需求調整條寬、切換影像格式，或對一系列值進行迴圈，以符合任何郵遞碼工作流程。

接下來，你可以探索：

* **在條碼下方加入可讀文字** (`barcodeGenerator.Parameters.Caption.Show = true`)。
* **使用 Aspose.PDF 將條碼嵌入 PDF 文件**。
* **產生其他郵件符號**，例如 **USPS POSTNET** 或 **Intelligent Mail**。

歡迎自行嘗試各項參數，並將程式碼整合至你的運輸或郵寄系統。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基�礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索其他實作方式。

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}