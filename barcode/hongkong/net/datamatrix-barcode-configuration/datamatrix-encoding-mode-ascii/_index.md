---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode for .NET 在 ASCII 模式下建立 DataMatrix 條碼。本指南快速示範如何以
  C# 產生條碼。
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix 編碼模式 (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 在 ASCII 模式下建立 DataMatrix 條碼
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 於 ASCII 模式建立 DataMatrix 條碼

## 介紹

準備好 **建立 DataMatrix 條碼** 圖片，使用高效的 ASCII 編碼了嗎？在本教學中，您將學習如何使用 Aspose.BarCode for .NET 於 ASCII 模式產生 DataMatrix 條碼。我們會一步步說明——從專案設定到儲存最終圖像——讓您能在幾分鐘內將條碼產生功能加入 C# 應用程式。

## 快速解答

- **哪個函式庫最適合 .NET 的 DataMatrix？** Aspose.BarCode for .NET  
- **需要多少行程式碼？** 約 5‑7 行即可產生基本的 ASCII 條碼  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買授權  
- **支援哪些平台？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7  
- **可以調整尺寸或顏色嗎？** 可以，Aspose.BarCode 提供屬性設定尺寸與前景/背景顏色  

## 什麼是 DataMatrix 條碼？

DataMatrix 是一種二維條碼，能在緊湊的方形圖案中儲存文字與二進位資料。  
DataMatrix 條碼以黑白模組的格子編碼資訊，單一符號最多可容納 2,335 個英數字元。由於可在極小尺寸下列印且仍具高度可掃描性，廣泛應用於製造、物流與醫療保健領域。

## 如何於 ASCII 模式建立 DataMatrix 條碼？

載入 Aspose.BarCode 命名空間，建立 `BarcodeGenerator` 實例，將 `EncodeMode` 設為 **EncodeMode.ASCII**，指定資料字串，然後呼叫 `Save` 寫入圖像檔案。此方法僅需少量 C# 程式碼，即可產生符合規範、僅使用 ASCII 編碼的 DataMatrix 條碼。

## 為何在 DataMatrix 中使用 ASCII 編碼？

ASCII 模式是純文字資料的預設且最有效率的編碼，可為英數字串提供最小的符號尺寸。它支援全部 128 個 ASCII 字元，處理速度快於擴充模式，且確保與期待標準 ASCII 符號的舊版掃描器具最高相容性。

## 前置條件

1. **開發環境** – Visual Studio、Rider，或任何相容 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 從 [here](https://releases.aspose.com/barcode/net/) 下載最新套件。  
   - 文件說明: [Aspose.BarCode for .NET 文件說明](https://reference.aspose.com/barcode/net/)  
   - 社群支援: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **基本 C# 知識** – 熟悉 .NET 專案結構將有助於快速跟隨步驟。  
4. **其他 Aspose 產品** 可於 [此處](https://releases.aspose.com/) 找到。

## 匯入命名空間

要開始，請在 C# 檔案的頂部加入必要的 `using` 指令：

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

這些命名空間讓您可以存取 `BarcodeGenerator` 類別以及儲存輸出所需的影像相關型別。

## 步驟 1：建立目錄

選擇一個用於儲存產生之條碼圖像的資料夾。將 `"Your Directory Path"` 替換為您機器上實際存在的絕對或相對路徑。

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

此程式碼會在寫入檔案前確保目錄已存在，避免執行時錯誤。

## 步驟 2：以 ASCII 模式編碼資料

`BarcodeGenerator` 類別負責建立與設定條碼圖像。`DataMatrixEncodeMode` 列舉用於選擇 DataMatrix 符號的編碼演算法。

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

執行程式碼後，您會在指定的資料夾中看到 `datamatrix_ascii.png`。該圖像包含一個以緊湊 ASCII 模式編碼字串 `"1234567890"` 的 DataMatrix 條碼。

## 常見問題與解決方案

- **檔案存取錯誤** – 確保應用程式對目標資料夾具有寫入權限。以系統管理員身分執行 Visual Studio 可解決 Windows 上的權限問題。  
- **符號尺寸不正確** – 若條碼過大或過小，請調整 `generator.Parameters.Image.Width` 與 `Height`，或省略這些屬性讓 Aspose 自動計算最佳尺寸。  
- **不支援的字元** – ASCII 模式僅接受 0‑127 範圍內的字元。若需處理 Unicode 資料，請切換至 `DataMatrixEncodeMode.Base256` 或其他適當模式。

## 常見問答

**Q: 我可以在商業應用程式中使用這個嗎？**  
A: 可以，正式使用需購買有效的 Aspose 授權；亦提供免費試用版供評估。

**Q: 此函式庫支援 .NET Core 嗎？**  
A: 當然支援 – Aspose.BarCode 完全相容 .NET Core 3.1+、.NET 5、.NET 6 以及更高版本。

**Q: 在 ASCII 模式下最多能編碼多少字元？**  
A: 使用 ASCII 編碼時，單一 DataMatrix 符號最多可容納 2,335 個英數字元。

**Q: 我可以更改條碼的前景色或背景色嗎？**  
A: 可以，調整 `generator.Parameters.Image.ForeColor` 與 `BackColor` 為任意 `System.Drawing.Color` 值。

**Q: 哪裡可以找到更進階的範例？**  
A: 官方文件提供數十個範例，涵蓋自訂尺寸、顏色與錯誤更正等層級。

## 常見問答 (FAQ)

### Q1: 我可以在 C# 之外的其他程式語言中使用 Aspose.BarCode for .NET 嗎？

A1: Aspose.BarCode 支援多種程式語言，但本教學僅以 C# 為例說明。

### Q2: DataMatrix 條碼有哪些不同的編碼模式？

A2: DataMatrix 條碼支援多種編碼模式，包括 ASCII、C40、Text 與 Base256。每種模式適用於不同類型的資料。

### Q3: 我可以自訂產生的條碼外觀，例如尺寸與顏色嗎？

A3: 可以，Aspose.BarCode 提供多項參數讓您自訂條碼外觀，包括尺寸、顏色等。

### Q4: 是否提供 Aspose.BarCode for .NET 的免費試用版？

A4: 可以，您可從 [此處](https://releases.aspose.com/) 取得 Aspose.BarCode for .NET 的免費試用版。

### Q5: 哪裡可以購買 Aspose.BarCode for .NET 的授權？

A5: 您可於 Aspose 官方網站的 [此處](https://purchase.aspose.com/buy) 購買授權。

---

**最後更新：** 2026-06-09  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.BarCode for .NET 以位元組方式編碼 DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}