---
date: 2026-09-23
description: 了解如何在 .NET 中使用 Aspose.BarCode 產生帶有擴充代碼文字的 DataMatrix 條碼，適用於庫存與物流應用。
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix 擴充代碼文字設定
og_description: 如何在 .NET 中使用 Aspose.BarCode 產生帶有擴充代碼文字的 DataMatrix 條碼。遵循快速分步指南，適用於庫存與物流解決方案。
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: 如何在 .NET 中使用 Aspose.BarCode 建立 DataMatrix 代碼文字
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: 如何在 .NET 中使用 Aspose.BarCode 建立 DataMatrix 代碼文字
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中使用 Aspose.BarCode 建立 DataMatrix 條碼文字

將條碼整合到現代 .NET 應用程式已不再是小眾任務——它是庫存、物流與行動掃描解決方案的核心需求。在本指南中，您將 **學習如何使用 Aspose.BarCode** 來設定帶有擴展條碼文字的 DataMatrix 條碼、產生圖像，並以程式方式驗證。您將了解此方法為庫存條碼建立的理想選擇，以及它如何適用於 .NET Core 或 .NET 6 專案。

## 快速答覆
- **需要哪個函式庫？** Aspose.BarCode for .NET  
- **使用哪種條碼類型？** DataMatrix with extended code text  
- **可以使用 .NET Core / .NET 6 嗎？** 是的，API 是跨平台的  
- **測試需要授權嗎？** 免費試用版可用於開發；正式環境需購買授權  
- **實作需要多久？** 基本範例約需 10‑15 分鐘  

## Aspose.BarCode for .NET 是什麼？
Aspose.BarCode for .NET 是一套商業函式庫，可讓開發人員產生與辨識超過 30 種條碼符號，包括 DataMatrix、QR 以及 Code 128，且能產出最高 10,000 × 10,000 像素的圖像，無需外部相依性。它支援 .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6/7。

## 為何使用 DataMatrix 擴展條碼文字？
DataMatrix 擴展條碼文字允許在單一符號中嵌入多種編碼方案——UTF‑8、C40、Text、X12——可容納高達 **3116 個碼字**（約 155 KB 資料）於一個緊湊的方形中。此功能非常適合多語言產品標籤、醫療設備追蹤以及智慧包裝，能同時結合字母數字 ID 與二進位負載。

## 前置條件
在開始之前，請確認您已具備以下項目：

1. **Aspose.BarCode for .NET** – 從官方網站 **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)** 下載。  
2. **.NET 開發環境** – Visual Studio、Rider 或搭配 .NET SDK 的 VS Code。  
3. **基本的 C# 知識** – 您應該熟悉類別、命名空間以及 `using` 指令。

## 匯入命名空間
在 C# 檔案的頂部加入所需的命名空間，讓編譯器知道條碼類別的所在位置。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

這些命名空間讓您同時存取條碼產生與辨識功能。

## 如何設定 DataMatrix 擴展條碼文字？

載入建構器，加入所需的段落，讓 Aspose.BarCode 自動處理 ECI 標記。以下直接說明步驟：建立 `DataMatrixExtCodetextBuilder`，加入 Unicode、C40、純文字與 Text 模式段落，最後取得供產生器使用的合併字串。

### 步驟 1：定義輸出資料夾
指定產生的條碼圖像要儲存的位置。將佔位符替換為您機器上有效的路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：建立擴展條碼文字
`DataMatrixExtCodetextBuilder` 是協助類別，依據 DataMatrix 規範組合擴展條碼文字，會自動插入所需的 ECI（Extended Channel Interpretation）標記。

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

此範例示範如何在單一 DataMatrix 符號中結合 Unicode 字元、C40 編碼、純文字與 Text 模式。

### 步驟 3：產生最終的條碼文字字串
完成所有部分的設定後，取得 Aspose.BarCode 將嵌入條碼的合併字串。

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### 步驟 4：建立 DataMatrix 條碼
`BarcodeGenerator` 為產生條碼圖像的核心類別。使用 `EncodeTypes.DataMatrix` 與擴展條碼文字建立實例，接著設定視覺參數，如 X‑dimension、圖像格式，以及可選的人類可讀文字。

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

上述程式碼 **建立了帶有指定擴展條碼文字的 Aspose .NET 條碼**，並以 PNG 檔案儲存。

### 步驟 5：透過讀取驗證條碼
`BarCodeReader` 會驗證產生的符號是否能正確解碼，這對自動化測試流程與品質保證至關重要。

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

若設定正確，主控台將輸出先前建立的完整擴展條碼文字。

## 常見問題與除錯

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| 條碼無法辨識 | X‑dimension 太低 | 將 `XDimension.Pixels` 提高（例如，4 → 6） |
| 字元亂碼 | ECI 編碼錯誤 | 確保 `ECIEncodings.UTF8` 與字元集相符 |
| 檔案未儲存 | 路徑無效 | 使用絕對路徑或確認資料夾已存在 |
| 授權例外 | 試用版已過期 | 套用臨時或正式授權（請參閱 FAQ） |

## 常見問答

### Q1: Aspose.BarCode for .NET 是什麼？
A1: Aspose.BarCode for .NET 是一套功能強大的函式庫，讓開發人員能產生與辨識各種條碼符號，包括 DataMatrix、QR、Code128 等。

### Q2: 在哪裡可以找到 Aspose.BarCode for .NET 的文件？
A2: 您可前往完整 API 參考 **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**。

### Q3: 是否提供 Aspose.BarCode for .NET 的免費試用版？
A3: 有，您可從 **[Aspose.BarCode free trial download](https://releases.aspose.com/)** 下載免費試用版。

### Q4: 如何取得測試用的臨時授權？
A4: 可申請評估用的臨時授權，請前往 **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)** 索取。

### Q5: 在哪裡可以取得 Aspose.BarCode for .NET 的支援或提問？
A5: 官方的 Aspose.BarCode 論壇是最佳的求助管道：**[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**。

**最後更新：** 2026-09-23  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟教學](/barcode/net/datamatrix-barcode-configuration/)
- [使用 Aspose.BarCode for .NET (C#) 於 ASCII 模式產生 DataMatrix 條碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [使用 Aspose.BarCode for .NET 產生帶文字編碼的 Aztec 條碼](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}