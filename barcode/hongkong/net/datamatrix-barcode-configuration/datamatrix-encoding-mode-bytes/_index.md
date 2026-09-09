---
date: 2026-05-30
description: 了解如何使用 Aspose.BarCode for .NET 於 Bytes 模式產生 DataMatrix 條碼，並讀取 DataMatrix
  條碼——一步一步的條碼指南。
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: DataMatrix 編碼模式（Bytes）
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 於 Bytes 模式產生 DataMatrix 條碼
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 以 Bytes 模式產生 DataMatrix 條碼（使用 Aspose.BarCode for .NET）

在本教學中，您將學習如何使用 Bytes 編碼模式**產生 DataMatrix 條碼**，然後使用 Aspose.BarCode for .NET**讀取 DataMatrix 條碼**。無論您是構建倉儲管理系統或行動票務應用程式，以下逐步條碼指南將向您展示如何設定條碼產生器、產生高品質影像，並再次解碼——只需幾行 C# 程式碼。

## 快速解答
- **我可以在 .NET 中產生 DataMatrix 條碼嗎？** 是的，使用 `BarcodeGenerator` 搭配 `EncodeTypes.DataMatrix`，並設定 `DataMatrixEncodeMode.Bytes`。
- **哪個方法用來讀取條碼？** `BarCodeReader` 讀取影像並回傳編碼文字。
- **生產環境是否需要授權？** 需要商業授權；亦提供免費試用版。
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。
- **我能編碼多少位元組？** 單一 DataMatrix 符號最多可容納 1,555 位元組。

## 什麼是產生 DataMatrix 條碼？
**產生 DataMatrix 條碼**指的是建立一種二維方形條碼，可儲存二進位資料。Aspose.BarCode 會將符號渲染為 PNG、JPG 或 SVG 影像，任何掃描器皆能解碼。此條碼廣泛用於庫存追蹤、文件管理與驗證，因其具備高資料密度與錯誤更正能力，即使在低品質列印下亦相當可靠。

## 為什麼使用 Bytes 編碼模式？
Bytes 模式允許您直接嵌入原始二進位資料（最高 1,555 位元組），無需先轉換為文字，這對於序號、GUID 或加密負載特別適合。Aspose.BarCode 支援 **30 多種條碼符號**，且能在不將整個檔案載入記憶體的情況下處理 **數百頁文件**，確保在高吞吐量情境下仍具快速效能。

## 前置條件

1. Aspose.BarCode for .NET：要開始使用，您必須安裝 Aspose.BarCode for .NET 程式庫。您可以從 [此處](https://releases.aspose.com/barcode/net/) 下載。亦可在 [此處](https://releases.aspose.com/) 找到其他 Aspose 產品。
2. 開發環境：請確保已設定開發環境，包含 Visual Studio 或您偏好的其他 IDE。
3. C# 基礎知識：本教學假設您具備 C# 程式設計的基本概念。

如需協助，請造訪 [Aspose.BarCode 支援](https://forum.aspose.com/c/barcode/13)。

具備上述前置條件後，即可開始使用 Bytes 模式在 DataMatrix 格式中編碼資料。

## 匯入命名空間

要使用 Aspose.BarCode for .NET，請在 C# 檔案頂部匯入所需的命名空間：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

環境設定完成後，讓我們一步步說明如何**產生 DataMatrix 條碼**，並再度讀取它。

## 如何在 Bytes 模式下產生 DataMatrix 條碼？

載入 `BarcodeGenerator`、將編碼模式設為 Bytes、設定可選的顯示文字、儲存影像，最後使用 `BarCodeReader` 驗證結果——整個流程僅需六個簡潔步驟。此方法可確保產生符合 ISO/IEC 16022 標準的可靠條碼。

### 步驟 1：初始化 BarcodeGenerator

`BarcodeGenerator` 是用於產生特定符號與資料條碼影像的主要類別。

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### 步驟 2：將 DataMatrix 編碼模式設為 Bytes

`DataMatrixEncodeMode.Bytes` 告訴產生器將輸入視為原始二進位位元組，而非文字。

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### 步驟 3：設定顯示文字

`CodeText` 屬性設定條碼符號下方顯示的人類可讀文字。

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### 步驟 4：儲存條碼影像

`Save` 方法將產生的條碼寫入指定格式的影像檔案。

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### 步驟 5：嘗試辨識

`BarCodeReader` 讀取條碼影像並提取編碼資料。

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### 步驟 6：迭代並顯示結果

遍歷 `reader.ReadBarCodes()` 以取得每個偵測到的條碼及其 `CodeText`。

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

透過上述步驟，您已成功在 Bytes 模式下**產生 DataMatrix 條碼**，並使用 Aspose.BarCode for .NET 進行驗證。此函式庫抽象化低階編碼細節，讓您專注於業務邏輯，而非條碼數學。

## 常見問題與解決方案

- **編碼資料被截斷** – 請確認位元組陣列未超過 1,555 位元組；否則函式庫會自動切換至較大符號尺寸或拋出例外。
- **影像模糊** – 在呼叫 `Save` 前，透過設定 `generator.Parameters.ImageResolution` 將影像解析度提升（例如 300 dpi），即可產生更清晰的圖檔。
- **讀取器回傳 null** – 請確認影像路徑正確且檔案未損壞；同時確保 `BarCodeReader` 使用 `DecodeType.DataMatrix` 進行實例化。

## 常見問答

**Q: 什麼是 DataMatrix 編碼模式？**  
A: DataMatrix 編碼模式定義輸入資料如何轉換為二維圖樣；Bytes 模式直接儲存原始二進位位元組。

**Q: 我如何取得 Aspose.BarCode for .NET 的免費試用？**  
A: 您可從 [此處](https://releases.aspose.com/) 取得 Aspose.BarCode for .NET 的免費試用版。

**Q: 我在哪裡可以找到 Aspose.BarCode for .NET 的文件？**  
A: Aspose.BarCode for .NET 的文件可於 [此處](https://reference.aspose.com/barcode/net/) 取得。

**Q: Aspose.BarCode for .NET 是否適用於商業用途？**  
A: 是的，Aspose.BarCode for .NET 可用於商業用途。您可從 [此處](https://purchase.aspose.com/buy) 購買授權。

**Q: 我可以使用臨時授權來使用 Aspose.BarCode for .NET 嗎？**  
A: 可以，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得 Aspose.BarCode for .NET 的臨時授權。

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## 相關教學

- [使用 Aspose.BarCode for .NET 的 ASCII 模式掌握 DataMatrix 編碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [使用 C# 讀取 DataMatrix 條碼 – 產生 DataMatrix 模式（自動）](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼（ECC 200）](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}