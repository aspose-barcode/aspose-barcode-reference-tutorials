---
date: 2026-08-02
description: 了解如何建立 DataMatrix 條碼、產生 datamatrix，並探索使用 Aspose.BarCode for .NET 專案的高密度條碼產生。
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: DataMatrix ECC 200 設定
og_description: 使用 Aspose.BarCode for .NET 建立 DataMatrix 條碼。本教學展示高密度條碼產生、臨時 Aspose
  授權設定，以及一步一步的 C# 程式碼。
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: 建立 DataMatrix 條碼 – Aspose.BarCode .NET 指南
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: 如何使用 Aspose.BarCode for .NET 建立 DataMatrix 條碼（ECC 200）
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 建立 DataMatrix 條碼 (ECC 200)

## 介紹

在本指南中，您將 **建立 DataMatrix 條碼** (ECC 200) 使用 Aspose.BarCode for .NET。無論您是構建庫存追蹤器、銷售點系統，或是自動化文件工作流程，高密度條碼都能在極小的空間內儲存大量資料。我們將逐步說明每個設定步驟，解釋為何每個設定重要，並提供可直接執行的 C# 程式碼片段。

## 快速解答
- **哪個函式庫最適合在 .NET 中使用 DataMatrix？** Aspose.BarCode for .NET  
- **ECC 200 提供哪種 ECC 等級？** 高密度錯誤更正，確保掃描穩定。  
- **執行範例是否需要授權？** 評估期間可使用臨時授權；正式上線需購買正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **可以輸出 PNG、JPEG 或 TIFF 嗎？** 可以 – `Save` 方法支援多種影像格式。

## 什麼是 DataMatrix ECC 200？

DataMatrix ECC 200 是一種高密度的二維條碼，可在緊湊的方形或矩形圖樣中儲存最多 2,335 個字母數字字元或 1,556 位元組的二進位資料。它使用 Reed‑Solomon 錯誤更正來復原遺失或受損的模組，非常適合航空零件標記、藥品標籤與物流等對可靠性要求極高的應用。

## 為什麼使用 Aspose 條碼產生？

Aspose.BarCode 支援 **30+ 種條碼類型**，可在不將整個檔案載入記憶體的情況下渲染最高 10,000 × 10,000 px 的影像，且在 Windows、Linux 與 macOS 上皆能產生一致的輸出。其 API 讓您能掌控每一個渲染參數，是 **ASP.NET 條碼產生** 場景中最具彈性的選擇。

## 前置條件

1. **開發環境** – 已安裝相應 .NET 框架的 Visual Studio。  
2. **Aspose.BarCode for .NET** – 從官方網站下載並安裝，[此處](https://releases.aspose.com/barcode/net/)。  
3. **授權** – 從 [此處](https://purchase.aspose.com/temporary-license/) 取得測試用臨時授權。  
4. **C# 基礎** – 熟悉 C# 語法與專案結構。

現在已完成基礎說明，讓我們進入 DataMatrix ECC 200 的設定。

## 匯入命名空間

`Aspose.BarCode.Generation` 命名空間包含建立條碼所需的所有類別。請在檔案頂部匯入：

```csharp
using Aspose.BarCode.Generation;
```

## 如何逐步建立 DataMatrix 條碼 (ECC 200)

要產生 DataMatrix ECC 200 條碼，只需載入欲編碼的資料、在 `BarcodeGenerator` 上設定少數關鍵參數，然後呼叫 `Save` 寫入影像檔案。此三步流程處理編碼、錯誤更正與輸出格式選擇，讓您能以最少程式碼將條碼產生整合至任何 .NET 應用程式。

### 步驟 1：初始化 Barcode Generator

`BarcodeGenerator` 是 Aspose.BarCode 的核心類別，用於建立與渲染條碼。它接受條碼類型與要編碼的文字。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

將 `"Your Directory Path"` 替換為您希望儲存影像的資料夾路徑。

### 步驟 2：設定 XDimension 與 ECC 類型

`XDimension` 定義每個 DataMatrix 模組的像素大小，而 `DataMatrixEcc` 則選擇錯誤更正等級。ECC 200 為此條碼類型提供最高的更正能力。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

若需要較大或較小的模組，請調整像素值；螢幕顯示常用 4‑6 px，列印標籤則建議 8‑10 px。

### 步驟 3：產生並儲存條碼影像

`Save` 方法將條碼寫入檔案。您可透過傳入對應的 `BarCodeImageFormat` 列舉值選擇 PNG、JPEG 或 TIFF。

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

若工作流程需要其他格式，將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Tiff` 即可。

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 條碼顯示模糊 | XDimension 設定過低 | 將 `XDimension.Pixels` 提升至 6‑8 |
| 手機掃描失敗 | ECC 等級錯誤 | 確認 `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| 檔案未建立 | 路徑字串無效 | 使用絕對路徑或確保資料夾已存在 |

## 常見問答

**Q: 可以在 .NET Core 主控台應用程式中使用此程式碼嗎？**  
A: 可以，相同的 API 在 .NET Core、.NET 5 與 .NET 6 專案中皆可使用。

**Q: 如何將輸出格式改為 JPEG？**  
A: 在 `Save` 呼叫中將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。

**Q: 能否直接將條碼嵌入 PDF 中？**  
A: 能 – 先產生影像，然後使用 Aspose.PDF 或其他 PDF 函式庫將其加入 PDF。

**Q: 若需編碼 Unicode 字元該怎麼做？**  
A: DataMatrix 支援 UTF‑8，只需如範例般將 Unicode 字串傳入產生器。

**Q: 函式庫是否支援批次產生多個條碼？**  
A: 當然可以 – 將產生程式碼放入迴圈，並為每次迭代更換資料/值。

## 結論

我們已完整說明如何使用 Aspose.BarCode for .NET **建立 DataMatrix 條碼** (ECC 200)：從前置條件、命名空間匯入、X‑dimension 設定、ECC 等級選擇，到以您偏好的格式儲存影像。您亦可探索其他屬性，如邊距、背景色與旋轉，以微調輸出以符合特定需求。

如遇任何問題，社群隨時在 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 提供協助。祝您開發順利！

---

**最後更新：** 2026-08-02  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix ECC 000-140 條碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/net/datamatrix-barcode-reading/)
- [建立條碼 PNG – DataMatrix 長寬比調整 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}