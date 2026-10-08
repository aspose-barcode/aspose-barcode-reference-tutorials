---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 建立 2D 矩陣條碼——一步步教您產生帶有擴充碼文字的 DotCode 條碼。
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode 擴充碼文字設定
og_description: 學習使用 Aspose.BarCode for .NET 建立 2D 矩陣條碼。本指南一步步說明如何產生帶有擴充碼文字的 DotCode
  條碼。
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: 使用 Aspose.BarCode for .NET 建立 2D 矩陣條碼
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: 如何使用 Aspose.BarCode for .NET 建立 2D 矩陣條碼
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 建立 2D 矩陣條碼

## 介紹

在條碼產生與管理領域，Aspose.BarCode for .NET 脫穎而出，作為一套多功能解決方案，支援 **50+ 輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下處理上百頁的文件。無論您需要條碼用於產品追蹤、庫存管理或資料密集型應用，建立如 DotCode 的 **2d matrix barcode** 並使用擴充 codetext，即可在緊湊的方形符號中嵌入文字與二進位負載。本教學將逐步說明如何建構該擴充 codetext 並產生最終影像。

## 快速解答
- **什麼是「create dotcode extended codetext」的意思？** 這表示建立一個 DotCode 條碼，將 FNC1、ECICodetext、純文字以及符號分隔符全部納入單一的擴充負載中。  
- **需要哪個函式庫？** Aspose.BarCode for .NET。  
- **需要授權嗎？** 臨時授權可用於評估；正式環境需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7+。  
- **實作需要多長時間？** 基本範例約需 10‑15 分鐘。

## 如何建立 dotcode 擴充 codetext

載入您的專案、設定目錄、建構擴充 codetext，並產生影像——全部程式碼不超過十幾行。以下直接答案概述整個流程：

使用 `EncodeTypes.DotCode` 載入 `BarcodeGenerator`，透過 `DotCodeExtendedCodetextBuilder` 建構擴充 codetext（加入 FNC1、ECICodetext、純文字與 FNC3 分隔符），最後呼叫 `Save` 寫入 PNG 檔案。此序列即可一次呼叫產生完全符合規範的 2d matrix barcode。

## 什麼是 dotcode 擴充 codetext？

**dotcode 擴充 codetext** 是一個複合字串，將多個資料段落（例如 FNC1 識別碼、ECICodetext、純文字與 FNC3 分隔符）結合成 DotCode 可解碼的單一負載。它能在單一 2d matrix barcode 中編碼多語言文字、二進位資料與結構化資訊，十分適合供應鏈、醫療保健與物聯網等情境。

## 為何在此任務使用 Aspose.BarCode？

Aspose.BarCode 在一般伺服器硬體上可處理 **每秒高達 500 頁**，且支援 **超過 30 種條碼符號**，包括 DotCode。其 `GetExtendedCodetext` API 可保證控制字元正確放置，避免手動字串串接錯誤，並確保符合 ISO/IEC 24724。另提供內建錯誤更正與自動靜區處理，減少手動調整的需求。

## 前置需求

- **Aspose.BarCode for .NET** – 從 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 下載。  
- .NET 開發環境（建議使用 Visual Studio 2022 或更新版本）。  
- 可選：用於評估的臨時授權檔案。

## 匯入命名空間

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

這些命名空間提供 `BarcodeGenerator` 類別與範例所需的 `DotCodeExtendedCodetextBuilder` 輔助類別。

```csharp
using Aspose.BarCode.Generation;
```

現在已完成前置需求，讓我們將產生 DotCode 擴充 Code Text 的流程分解為逐步指南。

## 步驟 1：定義目錄路徑

指定產生的 PNG 要儲存的位置。使用應用程式可寫入的絕對或相對路徑。

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您系統上的實際路徑。

## 步驟 2：建立 dotcode 擴充 codetext

`DotCodeExtendedCodetextBuilder` 類別會將各段組合成單一的擴充 codetext 字串。

若要建立 DotCode 擴充 Code Text，請依照以下子步驟操作：

### 2.1 加入 fnc1 格式識別碼

FNC1 格式識別碼標示新資料欄位的開始。GS1 相容的 DotCode 符號必須使用此識別碼。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 加入 ecicodetext

ECICodetext 用於編碼特殊字元與國際文字。在此範例中，我們使用 UTF‑8 編碼 `"犬Right狗"`。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 加入純文字 codetext

您也可以將純文字加入 DotCode 擴充 Code Text。此處加入 `"Plain text"`。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 加入 fnc3 符號分隔符

FNC3 符號分隔符用於分隔程式碼的不同區段，提升掃描器的可讀性。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 加入 fnc3 讀取器初始化資訊

此步驟加入 FNC3 讀取器初始化資訊，告訴掃描器如何解讀後續資料。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 產生 codetext

現在呼叫 `textBuilder` 物件的 `GetExtendedCodetext` 方法，即可產生 DotCode 擴充 Codetext。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 步驟 3：產生 dotcode 影像

從擴充 codetext 產生條碼影像。

#### 3.1 初始化條碼產生器

`BarcodeGenerator` 類別是 Aspose.BarCode 用於建立任何條碼的核心物件。您以欲使用的符號 (`EncodeTypes.DotCode`) 以及剛剛建構的擴充 codetext 來實例化它。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

最後呼叫 `Save` 將 PNG 檔寫入磁碟。此影像即可嵌入報告、行動應用程式或列印標籤中。

## 常見問題與解決方案

- **編碼不正確** – 加入多語言文字時請使用 `ECIEncodings.UTF8`，否則字元可能會亂碼。  
- **檔案存取錯誤** – 確認應用程式對目標目錄具備寫入權限。  
- **缺少靜區** – 若掃描器需要額外白邊，請設定 `gen.Parameters.Barcode.Margin`。

## 常見問答

**Q: 我可以在行動應用程式中使用產生的條碼嗎？**  
A: 可以。產生的 PNG 影像可嵌入 iOS、Android 或任何跨平台行動應用程式中。

**Q: 若需編碼二進位資料而非文字該怎麼做？**  
A: 使用 `AddECICodetext` 方法搭配適當的 `ECIEncodings`（例如 `ECIEncodings.Base64`）即可嵌入二進位負載。

**Q: 如何調整條碼尺寸而不影響可讀性？**  
A: 調整 `XDimension.Pixels` 屬性；較高的數值會增大模組尺寸，較低則使條碼更緊湊。

**Q: 有辦法在條碼周圍加入靜區嗎？**  
A: 可以。設定 `gen.Parameters.Barcode.Margin` 以像素為單位定義所需的靜區。

**Q: 此函式庫支援 .NET 8 嗎？**  
A: 最新的 Aspose.BarCode 版本相容 .NET 8，只需引用相應的 NuGet 套件版本。

如需進一步指引或有任何問題，歡迎造訪 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 或在 [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) 與社群交流。

---

**最後更新：** 2026-09-28  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.BarCode 建立 DotCode 條碼 .NET（自動模式）](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}