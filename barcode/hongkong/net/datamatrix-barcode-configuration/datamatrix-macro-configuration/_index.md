---
date: 2026-08-17
description: 了解如何使用 Aspose.BarCode for .NET 建立帶宏字元的 DataMatrix 條碼，並探索在應用程式中使用 DataMatrix
  的方法。
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix 宏設定
og_description: 了解如何使用 Aspose.BarCode for .NET 建立帶宏字元的 DataMatrix 條碼。本指南提供逐步程式碼、客製化選項以及驗證技巧，確保條碼產生的可靠性。
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: 使用 Aspose.BarCode 建立帶宏字元的 DataMatrix 條碼
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: 如何在 .NET 中使用宏字元建立 DataMatrix 條碼
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中使用宏字符建立 DataMatrix 條碼

## 介紹

產生包含宏字符的 **DataMatrix 條碼** 能讓您將額外的參考資訊封裝於微小的方形符號中。在本教學中，您將學習如何使用 Aspose.BarCode for .NET **建立 DataMatrix 條碼** 並加入宏字符、自訂尺寸與錯誤更正，並即時驗證結果。完成後，您即可在產品標籤、文件或醫療設備中嵌入支援宏的條碼。

## 快速回答
- **主要的函式庫是什麼？** Aspose.BarCode for .NET  
- **我可以建立帶有宏字符的 DataMatrix 條碼嗎？** 可以 – 設定 `MacroCharacters` 屬性。  
- **生產環境需要授權嗎？** 需要有效的 Aspose 授權才能在生產環境使用。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **有免費試用版嗎？** 當然有 – 可從官方 Aspose 網站下載。

## 前置條件

在深入宏設定之前，請確保您具備以下條件：

1. **Visual Studio** – 任何較新的版本皆可使用。  
2. **Aspose.BarCode for .NET** – 從 [下載連結](https://releases.aspose.com/barcode/net/) 下載。  
3. **基本的 .NET 知識** – 熟悉 C# 與 .NET 生態系統。

## 匯入命名空間

我們先匯入產生與辨識條碼所需的命名空間。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## 「產生 DataMatrix 條碼」搭配宏字符是什麼？

`MacroCharacters` 讓 DataMatrix 條碼能包含指向額外資料的宏符號。使用如 Macro05 或 Macro06 等宏字符，一個條碼即可指向更大的資料集或相關條碼序列，這在物流、製造與文件追蹤等需要緊湊編碼連結資訊的情境中相當有價值。

## 為什麼使用 Aspose.BarCode 產生 DataMatrix 條碼？

Aspose.BarCode 為您提供對 DataMatrix 大小、錯誤更正等級與宏設定的精確控制，支援超過 30 種條碼符號，且可在不將整張影像載入記憶體的情況下處理最高 10 MB 的檔案。其跨平台的 .NET 實作可在 .NET Framework、.NET Core 以及 .NET 5/6 上執行，並內建辨識功能，讓您即時驗證條碼。

## 步驟指南

### 步驟 1：設定專案

在 Visual Studio 中建立新的 Console Application（或任何 .NET 專案）。將您從下載取得的 Aspose.BarCode DLL 加入參考。

### 步驟 2：DataMatrix 宏設定

本教學的核心 – 在此我們實際 **建立帶有宏字符的 DataMatrix 條碼**。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **小技巧：** 將 `"ASPOSE"` 替換為您需要編碼的任意字串。宏字符 (`Macro05`) 會告訴掃描器此條碼屬於宏序列的一部份。

### 步驟 3：自訂條碼參數以進行錯誤更正

在儲存之前，您可以微調其他設定：

- **XDimension** – 控制每個模組（像素）的大小。  
- **Margin**、**ErrorCorrection** 與 **EncodingMode** – 均可透過 `gen.Parameters.Barcode.DataMatrix` 存取。

### 步驟 4：儲存條碼

上述程式碼會將影像儲存為您指定資料夾中的 `DataMatrixMacro.png`。PNG 為無損格式，適合後續處理。

### 步驟 5：辨識條碼

`BarCodeReader` 是 Aspose.BarCode 用於從影像解碼條碼的類別。使用 `BarCodeReader` 我們立即讀取剛產生的影像，以確認宏字符與資料正確。此往返驗證在自動化測試時特別方便。

## 如何在實務情境中使用 DataMatrix？

您可以將帶有宏字符的 DataMatrix 條碼應用於產品標籤、將序號連結至中央資料庫、透過嵌入對數位紀錄的參考來進行文件追蹤，亦可於醫療設備標籤上儲存患者或裝置資料於微小且可掃描的符號中。這些應用可減少人工輸入並提升可追溯性。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| 條碼無法辨識 | `XDimension` 設定不正確或影像解析度過低 | 將 `XDimension.Pixels` 提升至 4‑6，並以 PNG 或 TIFF 儲存 |
| 宏字符被忽略 | 讀取器不支援宏模式 | 使用明確支援 DataMatrix 宏的掃描器/讀取器（例如較新版的 ZXing） |
| 找不到路徑 | `path` 變數無效 | 確保目錄存在，或使用 `Path.Combine` 搭配 `Environment.CurrentDirectory` |

## 常見問答

**Q: 什麼是 Aspose.BarCode for .NET？**  
A: Aspose.BarCode for .NET 是一套功能強大的函式庫，讓 .NET 開發者能產生與辨識各種格式的條碼，包括 DataMatrix、QR 等。

**Q: 為什麼要使用 DataMatrix 條碼？**  
A: DataMatrix 條碼體積小、可靠性高且可儲存大量資料，適用於製造、物流與醫療等領域。

**Q: 在哪裡可以找到 Aspose.BarCode for .NET 的文件？**  
A: 您可於 [Aspose.BarCode for .NET 文件](https://reference.aspose.com/barcode/net/) 找到相關說明。

**Q: 有免費試用版可供 Aspose.BarCode for .NET 使用嗎？**  
A: 有，您可從 [免費試用連結](https://releases.aspose.com/) 下載。

**Q: 在哪裡可以取得 Aspose.BarCode for .NET 的支援？**  
A: 若您有任何問題或需要支援，可前往 Aspose.BarCode for .NET 論壇 [支援論壇](https://forum.aspose.com/c/barcode/13)。

---

**最後更新：** 2026-08-17  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [建立條碼 aspose .net - 設定 DataMatrix 代碼文字](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix 結構化附加設定與 Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}