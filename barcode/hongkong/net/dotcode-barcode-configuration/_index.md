---
date: 2026-06-14
description: 了解如何使用 Aspose.BarCode for .NET 產生 DotCode 條碼，涵蓋長寬比、編碼模式、擴充文字與讀取器初始化。
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: 如何產生 DotCode 條碼 – 設定指南
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何產生 DotCode 條碼 – 設定指南
url: /zh-hant/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何產生 DotCode 條碼 – 設定指南

## 簡介
**如何產生 DotCode** 條碼快速且可靠是開發庫存、追蹤或行動掃描解決方案的開發者常見需求。於本教學中，我們將逐一說明 Aspose.BarCode for .NET 為 DotCode 符號提供的所有設定選項——比例調整、自動與位元組編碼模式、延伸文字處理、讀取器初始化、列/欄佈局，以及結構化附加模式。完成後，您將能產生符合業界標準、尺寸完美且高密度的 DotCode 圖像，並能無縫整合至任何 .NET 應用程式。

## 快速問答
- **建立 DotCode 條碼的主要類別是什麼？** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **哪個屬性控制比例？** `BarCodeImageAspectRatio`.
- **我可以在 Auto 與 Bytes 編碼之間切換嗎？** Yes, via `EncodeMode` property.
- **DotCode 需要單獨的讀取器嗎？** No, the same `BarcodeGenerator` can decode when `ReadBarcode` is called.
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 如何使用 Aspose.BarCode for .NET 產生 DotCode 條碼？
`BarcodeGenerator` 是 Aspose.BarCode 中用於建立條碼圖像的主要類別。使用 `EncodeTypes.DotCode` 載入 `BarcodeGenerator`，設定所需屬性（比例、編碼模式、列/欄等），然後呼叫 `GenerateBarCodeImage()`——函式庫會回傳可直接使用的 `System.Drawing.Image` 或位元組陣列。此單一步驟工作流程處理所有低階編碼細節，支援 PNG、JPEG、SVG 等輸出格式，且可渲染最高達 10 000 × 10 000 px 的圖像而不會佔用過多記憶體。

## 什麼是 DotCode 條碼？
DotCode 條碼是一種高密度、方形的 2D 符號，可在緊湊的點矩陣中儲存最多 1 200 個數字或 800 個英數字元。它針對小型包裝標籤與行動掃描進行最佳化，即使在低解析度相機上亦能提供快速讀取率。

## 為何在 Aspose.BarCode 中使用 DotCode？
Aspose.BarCode 支援 **20+** 種 2D 條碼類型，包括 DotCode，且可在不將整張圖像載入記憶體的情況下處理超過 **200 MB** 的檔案。函式庫保證在標準智慧型手機相機上達到 **99.9 %** 的掃描準確率，並提供內建的錯誤更正等級，以降低讀取失敗的機率。

## 先決條件
- .NET Framework 4.5 或更高版本，或 .NET Core 3.1 / .NET 5+。
- Aspose.BarCode for .NET（建議使用最新版本）。
- 臨時或完整授權金鑰（試用版可用於開發）。

## DotCode 比例自訂
**aspect‑ratio** 決定 DotCode 矩陣的伸展或壓縮程度。使用 `BarCodeImageAspectRatio` 屬性設定介於 **0.5**（較高）至 **2.0**（較寬）之間的值。**1.0** 的比例會產生完美的正方形符號，這是預設值，且最適合大多數掃描器。

> **提示：** 在窄標籤上列印時，**0.75** 的比例通常能提升可讀性，同時不會犧牲資料容量。

## DotCode 編碼模式（自動）
在 **Auto** 模式下，函式庫會分析輸入字串，並自動選擇最有效的編碼方式（數字、英數或位元組）。此方式可最大化資料密度並減少整體符號大小。

> **直接答案：** 在 `BarcodeGenerator` 上設定 `EncodeMode = EncodeModes.Auto`，讓 Aspose.BarCode 為您的資料決定最佳編碼，確保在保留所有字元的同時產生盡可能小的 DotCode。

## DotCode 編碼模式（位元組）
當您需要儲存二進位資料或預先編碼的位元組陣列時，請選擇 **Bytes** 模式。此模式會強制產生器將輸入視為原始位元組，繞過自動字元集偵測。

> **直接答案：** 使用 `EncodeMode = EncodeModes.Bytes` 並提供 `byte[]` 負載，即可將加密識別碼或壓縮檔等二進位資訊直接嵌入 DotCode 符號。

## DotCode 延伸文字配置
延伸文字允許您附加非主要資料負載的補充資訊，這些資訊可在報告或 GUI 中與條碼一起顯示。將 `ExtendedCodeText` 屬性設定為任意字串（最多 **256** 個字元），並透過 `ExtendedCodeTextFont` 選擇字型。

> **專業提示：** 將延伸文字搭配較小的字型大小（例如 8 pt），以降低視覺佔用，同時仍提供可供人閱讀的上下文。

## DotCode 讀取器初始化
`BarCodeReader` 是用於從圖像或串流解碼條碼的類別。讀取 DotCode 圖像與產生過程同樣簡單。使用圖像串流建立 `BarCodeReader` 並指定 `EncodeTypes.DotCode`。呼叫 `ReadBarCode()` 以取得解碼後的字串。

> **直接答案：** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – 這段單一程式碼區塊即可在不依賴外部套件的情況下解碼符號。

## DotCode 列與欄配置
DotCode 允許明確控制列與欄的數量，這會影響符號大小與錯誤更正容量。使用 `Rows` 與 `Columns` 屬性設定介於 **10** 至 **144** 之間的值。較大的矩陣會提升資料容量與韌性。

> **最佳實踐：** 對於必須經受粗糙處理的庫存標籤，將 **Rows = 64** 與 **Columns = 64** 設定，以增加額外的冗餘。

## DotCode 結構化附加模式配置
結構化附加允許將大型負載分割至多個 DotCode 符號，並可依序讀取。將 `StructuredAppend = true`，並為每個部分定義 `StructuredAppendCount` 與 `StructuredAppendIndex`。

> **直接答案：** 在每個 `BarcodeGenerator` 上啟用 `StructuredAppend`，指派唯一索引（從 1 開始），並設定總計數；函式庫會自動嵌入必要的連結資訊。

## 常見問題與解決方案
- **在低解析度螢幕上條碼無法辨識：** 在產生前將 `Resolution` 屬性提升至至少 **300 dpi**。
- **資料截斷警告：** 確認輸入長度未超過所選列/欄的最大限制；如有需要，調整尺寸或切換至 Bytes 模式。
- **開發期間授權過期：** 使用從 Aspose 入口網站取得的臨時授權；在正式部署前以永久金鑰取代。

## 常見問答

**Q: 我可以以 SVG 格式產生 DotCode 條碼嗎？**  
A: 是的，於產生器上設定 `BarCodeImageFormat = BarCodeImageFormat.Svg` 即可取得可伸縮向量輸出。

**Q: 可以在 DotCode 符號內嵌入標誌嗎？**  
A: Aspose.BarCode 不支援在 DotCode 中直接嵌入標誌，但您可以在產生後使用標準圖形庫將圖像疊加。

**Q: DotCode 的錯誤更正機制如何運作？**  
A: 此符號內建 Reed‑Solomon 錯誤更正；增加列/欄會自動提升更正等級。

**Q: 需要額外的程式庫來從 PDF 讀取 DotCode 嗎？**  
A: 不需要，同一個 `BarCodeReader` 可從 PDF 頁面、圖像或串流中提取 DotCode，無需額外工具。

**Q: 單一 DotCode 符號的最大資料容量是多少？**  
A: 最高可容納 **1 200** 個數字或 **800** 個英數字元，視所選列/欄配置而定。

---

**最後更新：** 2026-06-14  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

## DotCode 條碼設定教學
### [自訂 DotCode 比例](./dotcode-aspect-ratio-customization/)
學習使用 Aspose.BarCode for .NET 自訂 DotCode 條碼的比例。輕鬆為您的應用程式建立量身訂做的條碼。

### [DotCode 編碼模式（自動）](./dotcode-encoding-mode-auto/)
探索 Aspose.BarCode for .NET 中的 DotCode 編碼模式（Auto），這是一個強大的條碼產生工具。學習如何一步步產生 DotCode 條碼。查閱文件、下載函式庫，並取得臨時授權。

### [DotCode 編碼模式（位元組）](./dotcode-encoding-mode-bytes/)
學習使用 Aspose.BarCode for .NET 進行 DotCode 編碼：一步步的條碼產生指南。

### [DotCode 延伸文字配置](./dotcode-extended-code-text-configuration/)
使用 Aspose.BarCode for .NET 輕鬆產生 DotCode 延伸文字配置。遵循我們的步驟指南，快速建立高效條碼。

### [DotCode 讀取器初始化](./dotcode-reader-initialization/)
學習如何使用 Aspose.BarCode for .NET 初始化 DotCode 讀取器。輕鬆為各種應用程式建立 DotCode 條碼。

### [DotCode 列與欄配置](./dotcode-rows-columns-configuration/)
學習使用 Aspose.BarCode for .NET 配置 DotCode 的列與欄。輕鬆產生精確且可自訂的 2D 條碼。

### [DotCode 結構化附加模式配置](./dotcode-structured-append-mode-configuration/)
學習使用 Aspose.BarCode for .NET 配置 DotCode 結構化附加模式，並建立高效條碼。

## 相關教學

- [使用 Aspose.BarCode for .NET 自訂 DotCode 比例](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [使用 Aspose.BarCode for .NET 的 DotCode 延伸文字配置](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose.BarCode for .NET 中的 DotCode 編碼模式（自動）](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}