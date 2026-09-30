---
date: 2026-08-17
description: 了解如何使用 Aspose.BarCode for .NET 建立 datamatrix 條碼 – 非常適合條碼產生、庫存管理及 C# 條碼產生專案。
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 設定
og_description: 使用 Aspose.BarCode for .NET 建立 datamatrix 條碼 – 為庫存管理與 C# 條碼專案提供快速、高效能的解決方案。
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: 使用 Aspose.BarCode for .NET 建立 datamatrix 條碼
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: 如何使用 Aspose.BarCode 建立 datamatrix 條碼
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 建立 DataMatrix 條碼

在現代供應鏈軟件中，您常常需要快速且可靠地 **建立 datamatrix 條碼 aspose**。本教學將帶您使用 Aspose.BarCode for .NET 產生 DataMatrix ECC 000‑140 符號，該函式庫負責編碼、錯誤更正與影像渲染等繁重工作。完成本指南後，您將擁有一段可直接嵌入任何 .NET 庫存管理專案的即用型 C# 程式碼片段。

## 快速答覆
- **主要的函式庫是什麼？** Aspose.BarCode for .NET  
- **涵蓋哪種條碼類型？** DataMatrix ECC 000‑140  
- **使用哪種程式語言？** C# (C Sharp)  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權  
- **一般實作時間？** 基本產生器約需 10‑15 分鐘  

## DataMatrix ECC 000‑140 是什麼？
DataMatrix 是一種二維條碼，能在緊湊的方形內儲存大量資料。**ECC 000‑140** 錯誤更正等級可復原高達 140 % 的受損碼字，適用於標籤可能被刮傷或污損的惡劣倉儲環境。

## 為何選擇 Aspose.BarCode for .NET？
Aspose.BarCode for .NET 提供完整且高效能的 API，簡化多種條碼符號的建立，內建錯誤更正、自動尺寸調整與廣泛平台支援，讓企業級庫存與標籤解決方案更加理想。

- **強韌 API：** 支援 30 種以上條碼符號，並自動套用編碼規則。  
- **跨平台：** 可在 Windows、macOS 與 Linux 上執行，無需原生相依性。  
- **高效能：** 在一般 2.5 GHz CPU 上，能於 50 毫秒內產生 200 × 200 像素的 DataMatrix，支援高產能標籤線。  

## 前置條件
開始之前，請確保您已具備以下項目：

1. **Visual Studio** – 任一近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.BarCode for .NET** – 從 [download link](https://releases.aspose.com/barcode/net/) 下載。您亦可前往 [this link](https://releases.aspose.com/) 取得其他資源。  
3. **.NET 專案** – 已準備好參考 Aspose.BarCode 程式集。  

## 匯入命名空間
在您的 C# 檔案中，加入必要的 using 指示，以便存取條碼類別。

```csharp
using Aspose.BarCode.Generation;
```

**`BarcodeGenerator` 類別是 Aspose.BarCode 用於建立條碼影像的核心引擎。**  
**`BarcodeGenerator` 類別是 Aspose.BarCode 用於建立與設定條碼影像的核心引擎。**  
```csharp
using Aspose.BarCode.Generation;
```

## 條碼產生於庫存管理的使用案例
想像您需要在配送中心為數千個托盤貼標籤。透過產生 DataMatrix ECC 000‑140 條碼，您可以在單一具錯誤容忍度的符號中嵌入產品編號、批號與有效日期，手持掃描器可即時讀取，將人工輸入錯誤降低至最高 95 %。

## 如何在 C# 中使用 Aspose 建立 DataMatrix 條碼
載入資料、設定產生器，並儲存影像——只需三個簡潔步驟。`BarcodeGenerator` 會自動選擇最佳模組大小並套用 ECC 140 更正等級，您無需自行計算檢查碼，快速且有效率。

### 步驟 1：定義輸出目錄
選擇一個用於寫入 PNG 檔案的資料夾。呼叫 `Save` 前必須先確保路徑已存在。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：建立條碼產生器
實例化 `BarcodeGenerator`、將符號設定為 DataMatrix、提供資料內容，並選擇最高的錯誤更正等級。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

在此程式碼片段中，我們會：

* 選擇 **DataMatrix** 作為條碼類型。  
* 提供範例值 (`"Åspóse.Barcóde©"`)。  
* 設定 **XDimension** 以控制模組大小（此處為 4 像素）。  
* 選擇最高錯誤更正等級（**ECC 140**）。  
* 將輸出儲存為 PNG 檔案。  

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **路徑無效** | 確保 `path` 以目錄分隔符 (`\` 或 `/`) 結尾，且資料夾已存在。 |
| **不支援的字元** | DataMatrix 支援 UTF‑8；避免使用控制字元並使用正確的編碼。 |
| **授權未套用** | `Aspose.BarCode.License` 類別可套用商業授權以解鎖全部功能。請在產生任何條碼前先呼叫它。 |

## 常見問答

**Q: 我可以在 Linux 伺服器上使用 Aspose.BarCode for .NET 嗎？**  
A: 可以。此函式庫完全跨平台，能在 .NET 5+、.NET 6+ 以及 .NET Core 的 Linux 環境中執行，無需額外相依性。

**Q: 函式庫如何處理大量條碼批次？**  
A: 您可以在迴圈中重複使用同一個 `BarcodeGenerator` 實例；每次呼叫 `Save` 重新渲染影像大約需要 40‑60 毫秒，適合每分鐘產生數千張標籤。

**Q: 我需要手動編碼資料以符合 ECC 140 嗎？**  
A: 不需要。設定 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` 會自動套用正確的錯誤更正演算法。

**Q: 試用版足以用於開發嗎？**  
A: 免費試用版提供完整功能，包括 ECC 140，但會在產生的影像上加上浮水印。正式環境請套用授權以移除浮水印。

**Q: 我可以自訂條碼的顏色嗎？**  
A: 當然可以。使用 `generator.Parameters.Barcode.Color` 與 `generator.Parameters.Barcode.BackColor` 來符合您的品牌色彩。

---

**最後更新：** 2026-08-17  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [精通 Aspose.BarCode for .NET 的 ASCII DataMatrix 編碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}