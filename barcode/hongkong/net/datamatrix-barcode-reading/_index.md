---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 輕鬆讀取與產生 DataMatrix 條碼。探索讀取程式設計、結構化附加與產生指南。
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: DataMatrix 條碼讀取
og_description: 使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼的快速跨平台指南，涵蓋讀取、結構化附加與產生。（150‑160
  字）
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: 如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: 如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼
url: /zh-hant/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何讀取 DataMatrix 條碼

如果您需要在 .NET 環境中高效地 **如何讀取 DataMatrix**，本指南將為您提供逐步說明，涵蓋讀取、設定結構化追加（Structured Append）以及使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼。您將了解為何此函式庫是首選、事前需要準備什麼，以及在哪裡可以找到最實用的程式碼片段。

## 快速解答
- **What is DataMatrix?** 一種二維矩陣條碼，可在極小的空間內儲存大量資料。  
- **Which library helps you read DataMatrix in .NET?** Aspose.BarCode for .NET。  
- **Do I need a license?** 提供免費試用版；正式上線需購買商業授權。  
- **Can I generate DataMatrix barcodes as well?** 可以——使用相同的 API 來 **如何產生 DataMatrix** 條碼，並自訂設定。  
- **Supported platforms?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7，支援 Windows、Linux 與 macOS。

## 什麼是 DataMatrix 條碼讀取？
讀取 DataMatrix 條碼即從影像、PDF 頁面或即時視訊畫面中提取編碼的文字或二進位資料。Aspose.BarCode 的解碼器可直接處理 `System.Drawing.Image`、`Stream` 或 `PdfPage` 物件，讓您可以直接從檔案、記憶體串流或相機擷取的影像傳入，無需額外的轉換步驟。

## 為什麼使用 Aspose.BarCode 讀取 DataMatrix？
Aspose.BarCode 在標準 2.5 GHz CPU 上可每秒處理高達 **5,000 條條碼**，支援 **50+ 輸入格式**，且 **不需任何外部原生相依性**。此函式庫可在 Windows、Linux 與 macOS 上執行，支援 ECC 000 至 ECC 200 的錯誤更正等級，並內建結構化追加（Structured Append）處理功能——在處理 1,000 頁批次時，記憶體使用量仍低於 20 MB。

## 前置條件
- .NET Framework 4.5+ 或 .NET Core 3.1+（任何近期的 .NET 版本）。  
- 已安裝 Aspose.BarCode for .NET NuGet 套件。  
- 具備 C# 基礎知識，並使用 Visual Studio 或 Rider 等 IDE。

## DataMatrix 讀取程式設計：無縫整合

### 如何在 .NET 中讀取 DataMatrix 條碼？
`BarcodeReader` 是 Aspose.BarCode 用於從影像、串流或 PDF 頁面解碼條碼的類別。  
載入影像或 PDF 頁面，建立 `BarcodeReader`，若預期有多個條碼則啟用 `ReadMultipleBarcodes` 旗標，然後呼叫 `Read`。此方法會回傳 `BarCodeResult` 集合，內含解碼後的值、符號類型與置信度分數。  
`BarCodeResult` 代表單一解碼條碼，包含其值、符號類型與置信度分數。

### 如何啟用結構化追加（Structured Append）處理？
在呼叫 `Read` 之前，將 `ReadStructuredAppend` 屬性設為 `true`。讀取器會自動將屬於同一邏輯訊息的片段串接起來，回傳單一合併結果。

## DataMatrix 結構化追加設定：精準組織資料
結構化追加允許單一邏輯訊息分散於多個 DataMatrix 符號上。啟用此功能後，Aspose.BarCode 會根據每個符號內嵌的序號組合片段。此方式非常適合編碼長網址、大型二進位資料或多頁文件。

## 產生 DataMatrix 條碼：以 Aspose.BarCode for .NET 釋放創意
`BarcodeGenerator` 是 Aspose.BarCode 用於產生可自訂參數條碼影像的類別。您在讀取時使用的同一個 `BarcodeGenerator` 類別亦可建立 DataMatrix 符號。您可以控制模組大小、邊距、ECC 等級，甚至嵌入標誌圖像。產生器可輸出 PNG、JPEG、SVG 或 PDF 檔案，為網站、列印或行動應用提供完整彈性。

## DataMatrix 條碼讀取教學
### [DataMatrix 讀取程式設計](./datamatrix-reader-programming/)
探索使用 Aspose.BarCode for .NET 的 DataMatrix 讀取程式設計。透過本完整指南學習在 .NET 應用程式中產生與讀取 DataMatrix 條碼。

### [DataMatrix 結構化追加設定](./datamatrix-structured-append-configuration/)
了解如何在 .NET 中使用 Aspose.BarCode 建立與讀取 DataMatrix 結構化追加設定，以實現高效能的資料組織。

### [產生 DataMatrix 條碼](./datamatrix-versions/)
學習如何在 .NET 中使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼。支援自訂尺寸、ECC 等級等功能。

## 常見問題

**Q: 我可以在商業專案中使用 Aspose.BarCode 嗎？**  
A: 可以。正式上線需購買有效的商業授權，但可使用免費試用版進行評估。

**Q: 此函式庫支援從 PDF 檔案讀取 DataMatrix 嗎？**  
A: 當然支援。您可以將 PDF 頁面載入為影像串流，直接傳給條碼讀取器。

**Q: 當條碼分散於多張影像時，如何處理 Structured Append？**  
A: 若在解碼前啟用 `ReadStructuredAppend` 屬性，API 會自動組合這些片段。

**Q: 產生 DataMatrix 條碼時有哪些錯誤更正等級可供選擇？**  
A: 您可依需求的資料密度與容錯度，選擇 ECC 000、050、080、100、140 或 200。

**Q: 有什麼方法可以提升大量影像批次的讀取效能嗎？**  
A: 有——將 `BarcodeReader` 的 `ReadMultipleBarcodes` 設為 `true`，並以平行執行緒處理影像。

---

**最後更新:** 2026-09-28  
**測試環境:** Aspose.BarCode for .NET 24.12  
**作者:** Aspose

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix Append](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [以 ASCII 模式使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}