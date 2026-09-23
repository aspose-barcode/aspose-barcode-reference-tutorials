---
date: 2026-06-14
description: 了解如何在 .NET 中使用 Aspose.BarCode（快速且可靠的條碼庫）讀取 DataMatrix 並產生結構化追加條碼。
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: DataMatrix 結構化追加設定
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 追加條碼
url: /zh-hant/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix 結構附加配置與 Aspose.BarCode for .NET

如果您是開發人員，想要在 .NET 應用程式中 **如何讀取 datamatrix** 並使用結構附加功能，Aspose.BarCode for .NET 是您的首選解決方案。在本步驟指南中，我們將示範如何產生與解碼跨多個符號的 DataMatrix 條碼。完成本教學後，您將能熟練建立、設定與讀取 DataMatrix 結構附加條碼。

## 快速解答
- **什麼函式庫處理 DataMatrix 結構附加？** Aspose.BarCode for .NET.
- **單一結構附加序列最多可包含多少個符號？** 最多 16 個 DataMatrix 符號。
- **開發是否需要授權？** 免費試用版可用於開發與測試。
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **可以不使用圖像檔案讀取條碼嗎？** 可以，您可以從位元組陣列或串流解碼。

## 什麼是 how to read datamatrix？
**how to read datamatrix** 指的是解碼 DataMatrix 符號的過程，並在適用時將結構附加序列的各片段拼接起來，以取得原始資料。Aspose.BarCode 內建支援此工作流程，會自動處理符號順序與資料串接。

## 為什麼使用 Aspose.BarCode 進行 DataMatrix 結構附加？
Aspose.BarCode 支援 **30+ 條碼符號**，且可在一般伺服器硬體上於 **200 ms** 內解碼最高達 **10,000 × 10,000 px** 的影像。此函式庫亦提供 **零相依部署**，不需額外的原生 DLL，且可在 Windows、Linux、macOS 的 .NET 執行環境中運作。

## 前置條件

在深入教學之前，您需要：

1. Aspose.BarCode for .NET Library – 從 [here](https://releases.aspose.com/barcode/net/) 下載。
2. 您也可以在 [here](https://releases.aspose.com/) 瀏覽其他 Aspose 產品。
3. 具備 .NET 開發環境，例如 Visual Studio 2022 或搭配 C# 擴充功能的 Visual Studio Code。

現在，讓我們開始建立與讀取 DataMatrix 結構附加條碼。

## 匯入命名空間

第一步是匯入提供條碼 API 的命名空間。

`BarCodeWriter` 類別是 Aspose.BarCode 用於建立條碼的入口，而 `BarCodeReader` 則負責解碼。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

現在您已匯入必要的命名空間，讓我們產生結構附加條碼。

## 如何讀取 DataMatrix 結構附加條碼？

將產生的影像（或串流）載入 `BarCodeReader`，啟用 `ReadStructuredAppend` 選項，然後呼叫 `ReadBarcode`。讀取器會自動回傳合併後的資料，並公開序列細節，如 `StructuredAppendFileId`、`StructuredAppendTotalCount` 與 `StructuredAppendSegmentId`。合併結果以單一字串返回，您亦可透過 `StructuredAppendSegmentId` 屬性取得各段識別碼以進行自訂處理。

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

在此步驟中，我們使用讀取器擷取條碼 ID、總計數與檔案 ID，以確認結構附加配置已正確解讀。

## 步驟 1：設定 DataMatrix 結構附加配置

要建立 DataMatrix 結構附加條碼，您需要設定其配置。這包括定義目錄路徑、條碼 ID、條碼數量與檔案 ID。

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

在此步驟中，我們已使用所需參數設定 DataMatrix 條碼。

## 常見問題與解決方案

- **段落順序不正確：** 確保 `StructuredAppendSegmentId` 的值從 0 起連續遞增，否則讀取器無法正確重組資料。
- **總計數不匹配：** `StructuredAppendTotalCount` 必須在所有符號中保持一致，若不一致會導致序列被視為不完整。
- **影像品質：** 低解析度影像可能導致解碼失敗。渲染條碼為點陣圖時，建議至少 **300 dpi**。

## 常見問答

### Q1：什麼是 DataMatrix 結構附加，為什麼會使用它？

A1：DataMatrix 結構附加是一項功能，允許您將大量資料分割成多個較小的條碼。當單一條碼空間受限或需要有效組織資料時，此功能特別有用。它常見於物流、醫療與製造領域。

### Q2：我可以在開源專案中使用 Aspose.BarCode for .NET 嗎？

A2：可以，Aspose.BarCode for .NET 提供可用於開源專案的免費試用版。您可在 [here](https://releases.aspose.com/) 取得試用版。

### Q3：是否有 Aspose.BarCode for .NET 的社群支援？

A3：有，您可以在 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 尋求社群支援並與其他使用者互動。

### Q4：如何取得 Aspose.BarCode for .NET 的臨時授權？

A4：若需用於評估或測試的臨時授權，可從 [here](https://purchase.aspose.com/temporary-license/) 取得。

### Q5：Aspose.BarCode for .NET 是否支援其他條碼類型？

A5：是，Aspose.BarCode for .NET 支援多種條碼類型，包括 QR Code、Code 128、EAN‑13 等等。您可在 [here](https://reference.aspose.com/barcode/net/) 查看完整文件，以取得支援條碼類型的完整清單。

---

**最後更新：** 2026-06-14  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [DataMatrix Reader Programming with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generate DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Master DataMatrix Macro Configuration with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}