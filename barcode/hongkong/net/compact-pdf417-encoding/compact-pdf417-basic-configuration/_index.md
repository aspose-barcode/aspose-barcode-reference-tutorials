---
date: 2026-05-30
description: 了解如何使用 Aspose.BarCode for .NET 在 Visual Studio 中建立條碼及產生條碼。提供逐步說明與程式碼範例。
keywords:
- how to create barcode
- barcode generation visual studio
- install aspose barcode .net
linktitle: Compact PDF417 基本設定
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode and perform barcode generation visual studio
    using Aspose.BarCode for .NET. Step‑by‑step guide with code examples.
  headline: How to Create Barcode – Compact PDF417 with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode and perform barcode generation visual studio
    using Aspose.BarCode for .NET. Step‑by‑step guide with code examples.
  name: How to Create Barcode – Compact PDF417 with Aspose.BarCode
  steps:
  - name: Set the Output Path
    text: Define where the generated image will be saved. Replace `"Your Directory
      Path"` with an absolute or relative folder on your machine. Ensure the folder
      exists and the application has write permissions; otherwise you’ll encounter
      an *Invalid path* error.
  - name: Create the Barcode Generator
    text: '`EncodeTypes.Pdf417` specifies the PDF417 barcode symbology. The `BarcodeGenerator`
      class is Aspose.BarCode''s core engine for creating barcode images. Even though
      we’re using the standard PDF417 type, we’ll configure it to behave as a Compact
      PDF417 barcode by adjusting a few properties in the next '
  - name: Configure Barcode Parameters
    text: '`XDimension.Pixels` sets the width of a single module (X‑dimension) in
      pixels. `Columns` defines the number of data columns in the barcode. Feel free
      to experiment with these values to meet your specific size or data‑capacity
      requirements. For example, decreasing `XDimension.Pixels` reduces overall '
  - name: Save the Barcode Image
    text: Finally, save the barcode as a PNG file (or any supported format). Give
      the file a meaningful name and choose the format that best fits your application.
      PNG is loss‑less and works well for web and print, but you can also output JPEG,
      BMP, or TIFF if needed.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET, supporting over 50 barcode symbologies.
    question: What is the primary library?
  - answer: Visual Studio 2019, 2022, or any later version.
    question: Which IDE is recommended?
  - answer: Roughly 10 lines for a basic Compact PDF417 barcode.
    question: How many lines of code are needed?
  - answer: Yes—X‑dimension, column count, and truncation are fully configurable.
    question: Can I adjust barcode dimensions?
  - answer: A commercial license is mandatory for non‑trial deployments.
    question: Is a license required for production?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何建立條碼 – 使用 Aspose.BarCode 的 Compact PDF417
url: /zh-hant/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 建立條碼 – Compact PDF417

## 介紹

如果你是想在 .NET 專案中 **建立條碼** 圖片的開發人員，Aspose.BarCode for .NET 是一個強大的解決方案，能讓這項工作變得簡單。在本教學中，我們將示範產生 Compact PDF417 條碼——一種在物流、庫存追蹤與票證等領域常用的節省空間的 2‑D 符號。完成後，你將能直接在 Visual Studio 中產生並自訂 Compact PDF417 條碼，全面掌控尺寸、資料密度與外觀。你可以從主站點[here](https://releases.aspose.com/)下載最新的 Aspose 版本。

## 快速解答
- **主要的函式庫是什麼？** Aspose.BarCode for .NET，支援超過 50 種條碼符號。  
- **建議使用哪個 IDE？** Visual Studio 2019、2022 或任何更新的版本。  
- **需要多少行程式碼？** 基本的 Compact PDF417 條碼大約需要 10 行程式碼。  
- **我可以調整條碼尺寸嗎？** 可以——X‑dimension、欄數與截斷皆可完全設定。  
- **正式環境是否需要授權？** 商業授權在非試用部署時是必須的。

## 什麼是 Compact PDF417？
Compact PDF417 是一種高容量的 2‑D 條碼，與標準 PDF417 相比，可在更小的佔用空間內儲存多達 1,800 個字元。當空間受限但資料密度必須保持高時（例如小型產品標籤或登機證），它是理想的選擇。

## 為什麼選擇使用 Aspose.BarCode 的 Compact PDF417？
Aspose.BarCode 支援 **50+ 條碼類型**，且可在單一 Compact PDF417 符號中編碼 **高達 2,000 個字元**，同時將影像大小控制在 200 KB 以下。該函式庫在處理多百頁文件時不需將整個檔案載入記憶體，於一般伺服器硬體上可在次秒內完成產生。

## 前置條件

在開始之前，請確保你具備以下條件：

1. **Visual Studio** – 已安裝且可運作的 Visual Studio（2019、2022 或更新版本），用於 **條碼產生 Visual Studio** 開發。  
2. **Aspose.BarCode for .NET** – 從官方網站下載並安裝函式庫。下載連結請見[here](https://releases.aspose.com/barcode/net/)。  
3. **基本的 C# 知識** – 本指南假設你熟悉 C# 語法與專案設定。  
4. **文字編輯器** – 雖建議使用 Visual Studio，任何支援 C# 的編輯器皆可使用。

## 匯入命名空間

首先，將必要的命名空間加入你的 C# 檔案，以便存取條碼產生類別：

```csharp
using Aspose.BarCode.Generation;
```

```csharp
using Aspose.BarCode.Generation;
```

現在你已準備好開始建構 Compact PDF417 條碼。

## 如何在 .NET 中產生 Compact PDF417 條碼？

載入 `BarcodeGenerator` 並指定 `EncodeTypes.Pdf417` 類型，設定資料字串、啟用緊縮模式，最後呼叫 `Save`——全部程式碼不超過十行。此方式會產生可直接嵌入報表、列印於標籤或傳送至行動裝置的 PNG（或其他支援格式）檔案。

## 步驟說明

### 步驟 1：設定輸出路徑

定義產生的影像要儲存的位置。

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為機器上的絕對或相對資料夾路徑。請確保該資料夾已存在且應用程式具備寫入權限，否則會出現 *Invalid path* 錯誤。

### 步驟 2：建立條碼產生器

`EncodeTypes.Pdf417` 指定 PDF417 條碼符號。  
`BarcodeGenerator` 類別是 Aspose.BarCode 用來建立條碼影像的核心引擎。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

雖然我們使用的是標準 PDF417 類型，但接下來會透過調整幾個屬性，使其行為等同於 Compact PDF417 條碼。

### 步驟 3：設定條碼參數

`XDimension.Pixels` 設定單一模組（X‑dimension）的寬度（以像素為單位）。  
`Columns` 定義條碼中的資料欄數。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Pdf417.Columns = 3;
gen.Parameters.Barcode.Pdf417.Pdf417Truncate = true;
```

可依需求自行調整這些數值，以符合特定的尺寸或資料容量需求。例如，減少 `XDimension.Pixels` 會縮小整體寬度，而增加 `Columns` 則可在每列加入更多資料。

### 步驟 4：儲存條碼影像

最後，將條碼儲存為 PNG 檔案（或任何支援的格式）。

```csharp
gen.Save($"{path}CompactPdf417Basic.png", BarCodeImageFormat.Png);
```

為檔案命名具意義的名稱，並選擇最符合應用需求的格式。PNG 為無損格式，適合網頁與列印；若需要，也可輸出 JPEG、BMP 或 TIFF。

## 常見問題與技巧

- **Invalid path** – 確認目錄存在且應用程式具有寫入權限。  
- **Unsupported characters** – PDF417 支援 Unicode，但某些特殊符號可能需要轉義。  
- **Image size too large** – 降低 `XDimension.Pixels` 或減少欄數以縮小條碼。  
- **Performance on large batches** – 重複使用同一個 `BarcodeGenerator` 實例，僅在儲存之間變更 `CodeText` 屬性，以減少物件建立開銷。

## 常見問答

### Q1：我可以在 Web 與桌面應用程式中使用 Aspose.BarCode for .NET 嗎？
**A:** 可以，該函式庫支援 ASP.NET、WinForms、WPF 以及其他 .NET 應用程式類型。

### Q2：除了 Compact PDF417，我還能產生哪些條碼類型？
**A:** 它支援 QR Code、Code 128、Code 39、DataMatrix、Aztec 等超過 50 種符號。

### Q3：是否提供 Aspose.BarCode for .NET 的免費試用版？
**A:** 有，您可以在此取得 Aspose.BarCode for .NET 的免費試用版[here](https://releases.aspose.com/)。

### Q4：如何購買 Aspose.BarCode for .NET 的授權？
**A:** 授權可透過 Aspose 商店取得[here](https://purchase.aspose.com/buy)。

### Q5：是否有其他資源或文件可供參考？
**A:** 詳細的 API 文件與程式碼範例請參考[here](https://reference.aspose.com/barcode/net/)。

## 結論

你現在已學會使用 Aspose.BarCode for .NET 產生 **建立條碼** 圖片，特別是 Compact PDF417 變體。此方法可在 Visual Studio 中無縫運作，讓你完整掌控條碼外觀與資料編碼。歡迎探索其他條碼類型（如 QR Code、Code 128 等），並依需求微調參數以符合商業需求。如遇到任何問題，Aspose.BarCode 社群是絕佳的求助管道——請前往[forum](https://forum.aspose.com/c/barcode/13)取得協助。

---

**最後更新：** 2026-05-30  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aspose.BarCode for .NET 的完整教學與範例](/barcode/net/)
- [使用 Aspose.BarCode for .NET 進行 Aztec Code 文字編碼](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼靜止區](/barcode/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}