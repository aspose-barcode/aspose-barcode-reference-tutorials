---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼，客製化長寬比、ECC 模式，以及 DataMatrix
  C40 編碼，以高效建立條碼。
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix 條碼設定
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 產生 DataMatrix 條碼 – 使用 Aspose.BarCode 的專業指南
url: /zh-hant/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生 DataMatrix 條碼 – Aspose.BarCode 專業指南

歡迎閱讀我們使用 Aspose.BarCode for .NET 的 **generate datamatrix barcode** 完整教學系列。無論您是精通條碼輸出調校的資深開發者，或是渴望了解基礎的新人，本指南將逐步說明每個步驟——從基本設定到進階編碼技術——讓您在任何 .NET 應用程式中產生可靠、可掃描的條碼。

## 快速解答
- **主要目的為何？** 以程式方式建立與自訂 DataMatrix 條碼。  
- **使用哪個函式庫？** Aspose.BarCode for .NET。  
- **需要授權嗎？** 提供免費試用；正式環境需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以自訂長寬比嗎？** 可以——請參閱「如何自訂 DataMatrix 長寬比」章節。

## 什麼是 generate datamatrix barcode？
DataMatrix 條碼是一種由黑白方格組成的二維矩陣，可儲存最多 2 300 個字母數字字元。使用 Aspose.BarCode，您可以直接從 .NET 程式碼 **generate datamatrix barcode** 圖像、PDF 或 SVG，並控制尺寸、錯誤更正等級與編碼模式，以符合任何行業標準。

## 為何使用 Aspose.BarCode 產生 DataMatrix？
Aspose.BarCode 能以最高 **600 dpi** 渲染 DataMatrix 符號，無像素化問題，確保在高解析度印表機上掃描清晰。它支援 **超過 50 種 ECC 與 macro 模式**——包括 ECC 000‑140、ECC 200 以及 Macro 05/06——讓您依資料大小選擇最佳錯誤更正等級。API 提供 **ASCII、C40、Text、X12 與 Bytes** 編碼選項，讓資料高效打包。整合僅需一個 NuGet 套件，且不需外部原生函式庫。

## 如何自訂 DataMatrix 長寬比
`BarCodeGenerator` 的 `AspectRatio` 屬性控制產生之 DataMatrix 符號的寬高比例。`BarCodeGenerator` 是 Aspose.BarCode 中用於建立條碼影像的主要類別。

**直接答案：** 在呼叫 `GenerateBarCodeImage()` 之前，設定 `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2`（或介於 0.5 至 2.0 之間的任意值）。函式庫會自動重新計算模組大小，以在符合要求比例的同時維持掃描可靠性。

### 步驟說明
1. **實例化** `BarCodeGenerator` with `EncodeTypes.DataMatrix`。  
2. **調整** `AspectRatio` to your desired value。  
3. **產生** the image and verify with a scanner or Aspose’s built‑in reader。

## 如何產生 DataMatrix ECC 000‑140 條碼
ECC 000‑140 適用於需要緊湊符號的短資料字串，提供最高 140 個錯誤更正碼字。`DataMatrixEccMode.Ecc000140` 為 DataMatrix 選擇 ECC 000‑140 錯誤更正方案。

**直接答案：** 在渲染之前使用 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140`。此設定會將編碼器切換至 ECC 000‑140 演算法，為給定資料產生最小的矩陣，同時提供強健的錯誤更正。

### 實用技巧
在編碼少於 20 個字元的數字資料時，ECC 000‑140 常會產生 10 × 10 的矩陣，節省寶貴的標籤空間。

## 如何產生 DataMatrix ECC 200 條碼
ECC 200 是最廣泛採用的 DataMatrix 模式，支援最多 2 335 個字母數字字元，且提供卓越的錯誤更正。`DataMatrixEccMode.Ecc200` 為 DataMatrix 選擇 ECC 200 錯誤更正方案。

**直接答案：** 設定 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200`，並透過 `CodeText` 提供您的資料。函式庫會自動選擇最佳的矩陣大小。

### 何時偏好使用 ECC 200
在較長字串、混合類型資料，或需要最高抗損壞能力時使用 ECC 200——最多可恢復符號的 **30 %**。

## 如何精通 DataMatrix ASCII 編碼
ASCII 模式以每字元單一位元組編碼，對純文字而言是最節省空間的方式。`DataMatrixEncodeMode.Ascii` 告訴產生器使用 ASCII 編碼產生 DataMatrix 符號。

**直接答案：** 指定 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii`，並將 `CodeText` 設為您的 ASCII 字串。引擎在不增加額外開銷的情況下打包資料，為純 ASCII 內容產生最小的矩陣。

### 範例情境
倉庫 SKU 由大寫字母與數字組成（例如 “AB1234”），非常適合 ASCII 模式，通常會產生 12 × 12 的矩陣。

## 如何產生 DataMatrix Mode (Auto)
Auto 模式讓 Aspose.BarCode 分析輸入並自動挑選最有效率的編碼（ASCII、C40、Text、X12 或 Bytes）。`DataMatrixEncodeMode.Auto` 啟用此自動選擇功能。

**直接答案：** 設定 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`。函式庫會評估資料，選擇最佳模式，並在單一步驟中繪製條碼。

### 好處
Auto 模式減少開發工作量，並確保混合類型資料產生最小的符號，提高掃描速度。

## 如何使用 DataMatrix 編碼模式 (Bytes)
Bytes 模式設計用於二進位資料，例如加密負載或壓縮檔案。`DataMatrixEncodeMode.Bytes` 指示產生器將每個位元組視為原始資料。

**直接答案：** 使用 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes`，並將 Base64 編碼的字串作為 `CodeText`。編碼器將每個位元組視為原始資料，保留精確的二進位表示。

### 使用案例
將 128 位元 GUID 或小型加密令牌直接嵌入 DataMatrix 符號中。

## 如何精通 DataMatrix 編碼模式 (C40)
C40 模式壓縮大寫字母與數字資料，與 ASCII 相比可減少高達 **40 %** 的大小。`DataMatrixEncodeMode.C40` 啟用此壓縮演算法。

**直接答案：** 設定 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40`，並提供大寫字串（例如 “HELLO WORLD”）。引擎將三個字元打包成兩個碼字，縮小最終矩陣。

### 專業提示
當負載主要由大寫字母、數字與空格組成時，C40 效果最佳。若有混合大小寫，建議使用 Auto 模式。

## 如何設定 DataMatrix 代碼文字
`CodeText` 屬性定義條碼中儲存的精確資料。它可以是純文字、數字字串，甚至 XML 負載。`CodeText` 是 `BarCodeGenerator` 的主要字串屬性，用於保存條碼負載。

**直接答案：** 在渲染之前指派 `generator.Parameters.Barcode.CodeText = "YourDataHere"`。此屬性接受任意 UTF‑8 字串，長度上限受所選 ECC 模式限制。

### 進階提示
將 `CodeText` 與 `ExtendedDataMatrix` 結合，可嵌入額外的中繼資料而不增加可見矩陣大小。

## 如何精通 DataMatrix 宏配置
Macro 模式（Macro 05 與 Macro 06）允許在主 DataMatrix 符號內嵌入次要 DataMatrix 符號，適用於連結外部資料來源。`DataMatrixMacroMode.Macro05` 與 `DataMatrixMacroMode.Macro06` 啟用這些宏功能。

**直接答案：** 使用 `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05`（或 `Macro06`）啟用宏模式，並為次要負載設定 `MacroPdf417` 屬性。產生器會建立複合符號，掃描器可將其解讀為兩個連結的碼。

### 真實案例
在宏部分嵌入 URL，同時在主矩陣保留產品識別碼，實現無縫的網頁至條碼整合。

*使用 Aspose.BarCode for .NET 教學清單*

## DataMatrix 條碼設定教學
### [自訂 DataMatrix 長寬比](./datamatrix-aspect-ratio-customization/)
了解如何使用 Aspose.BarCode for .NET 自訂 DataMatrix 條碼長寬比。條碼產生步驟指南。
### [產生 DataMatrix ECC 000-140 條碼](./datamatrix-ecc-000-140-configuration/)
使用 Aspose.BarCode for .NET 輕鬆建立 DataMatrix ECC 000-140 條碼。提升庫存管理效率等。
### [產生 DataMatrix ECC 200 條碼](./datamatrix-ecc-200-configuration/)
學習如何在 .NET 中使用 Aspose.BarCode 產生 DataMatrix ECC 200 條碼。以高效條碼建立簡化作業流程。
### [精通 DataMatrix ASCII 編碼](./datamatrix-encoding-mode-ascii/)
學習使用 Aspose.BarCode for .NET 於 ASCII 模式建立 DataMatrix 條碼。開發者步驟指南。
### [產生 DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
了解如何使用 Aspose.BarCode for .NET 產生 DataMatrix Mode (Auto)。本步驟指南涵蓋前置作業至條碼讀取。
### [DataMatrix 編碼模式 (Bytes)](./datamatrix-encoding-mode-bytes/)
學習使用 Aspose.BarCode for .NET 於 Bytes 模式編碼 DataMatrix 資料。遵循我們的步驟指南完成條碼產生與辨識。
### [精通 DataMatrix 編碼模式 (C40)](./datamatrix-encoding-mode-c40/)
學習 DataMatrix 編碼模式 (C40) 與 Aspose.BarCode for .NET。有效建立自訂條碼。探索步驟指南。
### [設定 DataMatrix 代碼文字](./datamatrix-extended-code-text-configuration/)
學習使用 Aspose.BarCode for .NET 設定 DataMatrix 延伸代碼文字。於 .NET 應用程式中產生、辨識與整合條碼。
### [精通 DataMatrix 宏配置](./datamatrix-macro-configuration/)
了解如何使用 Aspose.BarCode for .NET 設定 DataMatrix 宏條碼。於 .NET 應用程式中產生、自訂與辨識 DataMatrix 條碼。

## 常見問題

**Q: 如何決定使用哪種 ECC 模式？**  
A: 對於小資料集且需要有限錯誤更正時選擇 ECC 000‑140，較大資料或需更高可靠性時則使用 ECC 200。Macro 模式則提供額外的資料層以進行連結。

**Q: 我可以在 DataMatrix 條碼中嵌入自訂文字嗎？**  
A: 可以，將 `CodeText` 屬性設定為您的自訂字串，然後選擇適當的編碼模式（ASCII、C40 等）以控制大小。

**Q: 有沒有辦法自動選擇最佳編碼模式？**  
A: 將 `EncodeMode` 設為 `Auto`；Aspose.BarCode 會評估負載，自動挑選最節省空間的模式。

**Q: 大量條碼批次的效能考量是什麼？**  
A: 重複使用單一 `BarCodeGenerator` 實例，啟用多執行緒，並產生 PNG 影像以獲得無損品質，或使用 JPEG 以減少檔案大小。處理 10 000 個符號通常在標準 8 核心伺服器上於 30 秒內完成。

**Q: Aspose.BarCode 支援 .NET Core 與 .NET 5/6 嗎？**  
A: 當然支援——此函式庫完全相容於 .NET Framework、.NET Core 以及最新的 .NET 版本，於所有平台提供相同功能集。

**最後更新：** 2026-06-09  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [精通 DataMatrix ASCII 編碼與 Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}