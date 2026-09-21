---
date: 2026-05-24
description: 了解如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼 .NET，涵蓋 Auto、FullRange、Compact
  及 Rune 符號模式，並提供逐步指引。
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Aztec Symbol Mode 範例
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 建立 Aztec 條碼 .NET
url: /zh-hant/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 精通 Aztec 符號模式與 Aspose.BarCode for .NET

如果您希望快速且可靠地 **create aztec barcode .net**，Aspose.BarCode for .NET 為您提供完整功能的 API，支援 .NET Framework、.NET Core 以及 .NET 5/6+。在本教學中，我們將探討四種 Aztec 符號模式——Auto、FullRange、Compact 與 Rune——並示範如何在它們之間切換並將結果儲存為影像。完成後，您只需幾行程式碼即可在任何 .NET 應用程式中嵌入 Aztec 條碼。

## 快速解答
- **什麼函式庫在 .NET 中產生 Aztec 條碼？** Aspose.BarCode for .NET.  
- **Aztec 支援多少種符號模式？** 四種：Auto、FullRange、Compact 與 Rune.  
- **開發時需要授權嗎？** 免費試用可用於評估；商業授權則需於正式環境使用.  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 與 .NET 6+.  
- **我可以輸出 PNG、JPEG 或 SVG 嗎？** 可以——支援任何標準影像格式.

## create aztec barcode .net 是什麼？
`create aztec barcode .net` 指的是在 .NET 環境中使用 Aspose.BarCode API 產生 Aztec 二維條碼的過程。API 會自動處理編碼、符號模式選擇與影像渲染，使開發者能夠產生高品質的條碼，而不必處理錯誤更正計算或像素操作等底層細節。

## 為什麼要使用 Aspose.BarCode 產生 Aztec 條碼？
Aspose.BarCode 支援 **30+ 條碼符號**，且可在不將整個檔案載入記憶體的情況下渲染最高 **10,000 × 10,000 px** 的影像。它在一般伺服器上能於 **2 秒** 內處理 500 頁文件，適合高吞吐量的企業情境。

## 前置條件

在開始之前，請確保您已具備以下前置條件：

- 具備 .NET 開發的工作知識。  
- 機器上已安裝 Visual Studio。  
- 擁有 Aspose.BarCode for .NET 的副本。您可在[此處](https://releases.aspose.com/barcode/net/)下載。您亦可在[此處](https://releases.aspose.com/)探索其他 Aspose 產品。

現在您已準備就緒，讓我們深入 Aztec 符號模式範例。

## 匯入命名空間

首先，您需要匯入使用 Aspose.BarCode for .NET 所必需的命名空間。打開 Visual Studio 專案，並在程式碼檔案的頂部加入以下 using 陳述式：

```csharp
using Aspose.BarCode.Generation;
```

有了這些命名空間，您現在即可開始使用 Aspose.BarCode for .NET。

## 如何設定 Aztec 條碼的 Barcode Generator？
`BarcodeGenerator` 類別是根據所選符號與設定選項產生條碼影像的核心元件。它提供簡易的 API，讓您指定條碼類型、要編碼的資料，以及各種渲染參數，然後將結果儲存為影像檔案。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

在此步驟中，我們已設定產生器並提供了要編碼的代碼文字。

## 如何將 Aztec Symbol Mode 設為 Auto？

`AztecSymbolMode` 列舉定義了 Aztec 條碼的四種可能符號模式，而 **Auto** 選項讓函式庫自動選擇在保留所有資料與錯誤更正需求的前提下，最緊湊的尺寸。此模式適用於大多數情況，當您希望取得最小的條碼而不需手動調整時。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

此步驟確保 Aztec Symbol Mode 會自動決定，並將產生的條碼影像儲存。

## 如何強制使用 FullRange 符號模式？

當您需要最大的資料容量時，可選擇 `AztecSymbolMode` 列舉的 **FullRange** 值。此模式會停用自動尺寸縮減，允許條碼儲存完整的字元範圍，達到最高的資訊密度，適用於大型資料集。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

這將產生使用 FullRange Aztec Symbol Mode 的條碼。

## 如何產生 Compact Aztec 條碼？

`AztecSymbolMode` 列舉的 **Compact** 值透過減少矩陣使用的層數來產生較小的條碼。這會產生更節省空間的影像，適用於顯示區域受限的應用，例如手機螢幕或小型標籤。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

此步驟將條碼設定為使用 Compact Aztec Symbol Mode 產生。

## 如何建立 Rune Aztec 條碼？

**Rune** 模式是 Aztec 符號的特殊變體，使用自訂字元集編碼數字資料，提供獨特的視覺風格，同時保有與其他模式相同的錯誤更正強度。當您需要強調數字資訊的條碼時，此模式相當有用。

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

此步驟將代碼文字改為「123」，並產生使用 Rune Aztec Symbol Mode 的條碼。

## 常見問題與解決方案

- **Image not saving** – 確認輸出資料夾已存在且應用程式具有寫入權限。  
- **Unexpected symbol size** – 確認程式碼中未在其他位置覆寫 `EncodeMode`。  
- **License exception** – 試用版會加上浮水印；請套用有效授權以移除。

## 常見問與答

**Q: Aztec Symbol Mode 在條碼產生中的目的為何？**  
A: Aztec Symbol Mode 決定函式庫如何將資料打包至層中，影響條碼的尺寸、容量與可讀性。

**Q: 我可以在 Aspose.BarCode for .NET 中變更 Aztec 條碼的代碼文字嗎？**  
A: 可以，只需在呼叫 `Save` 之前將新字串指派給 `CodeText` 屬性。

**Q: 是否提供 Aspose.BarCode for .NET 的免費試用版？**  
A: 有，您可在[此處](https://releases.aspose.com/)下載 Aspose.BarCode for .NET 的免費試用版。

**Q: 我可以在哪裡找到 Aspose.BarCode for .NET 的完整文件？**  
A: 您可在[此處](https://reference.aspose.com/barcode/net/)參考 Aspose.BarCode for .NET 的完整文件。

**Q: 如何取得 Aspose.BarCode for .NET 的臨時授權？**  
A: 您可透過前往[此連結](https://purchase.aspose.com/temporary-license/)取得臨時授權。

## 結論

在本教學中，我們探討了如何使用 Aspose.BarCode **create aztec barcode .net**，涵蓋 Auto、FullRange、Compact 與 Rune 符號模式。現在您已具備堅實的基礎，可將多功能的 Aztec 條碼嵌入任何 .NET 應用程式，無論是桌面、Web 伺服器或雲端服務。

如果您有任何問題或需要進一步協助，請隨時前往 Aspose.BarCode 社群的[支援論壇](https://forum.aspose.com/c/barcode/13)尋求協助。

---

**最後更新：** 2026-05-24  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.BarCode for .NET 進行 Aztec 代碼文字編碼](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [使用 barcode generator .net 進行 Aztec 位元組編碼](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [如何在 .NET 中使用錯誤更正建立 Aztec 條碼](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}