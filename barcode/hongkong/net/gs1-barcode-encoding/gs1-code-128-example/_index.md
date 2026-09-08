---
date: 2026-09-08
description: 了解如何在 C# 中使用 Aspose.BarCode for .NET 建立 Code 128 條碼並產生 GS1 條碼。提供逐步指南、先決條件以及免編碼客製化。
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 範例
og_description: 了解如何在 C# 中使用 Aspose.BarCode for .NET 建立 Code 128 條碼並產生 GS1 條碼。遵循逐步指南快速產生並儲存條碼圖像。
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: 如何使用 Aspose.BarCode 以 GS1 建立 Code 128 條碼
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: 如何使用 Aspose.BarCode 以 GS1 建立 Code 128 條碼
url: /zh-hant/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 建立符合 GS1 標準的 Code 128 條碼

在本教學中，您將學習如何使用 .NET 的 Aspose.BarCode 函式庫**建立 Code 128 條碼**，以符合 GS1 標準。無論您需要條碼用於庫存、運輸或銷售點，本指南將一步步帶領您完成設定開發環境到儲存最終影像的全過程，讓您在幾分鐘內即可開始產生可靠的條碼。

## 快速回答
- **產生條碼的主要類別是什麼？** `BarcodeGenerator` 會建立並設定條碼影像。  
- **GS1 Code 128 使用哪種條碼符號？** 它使用 `EncodeTypes.Code128` 類型，搭配 GS1 專屬的資料格式。  
- **開發時需要授權嗎？** 免費試用可用於評估；正式上線需購買商業授權。  
- **可以更改影像格式嗎？** 可以——只要更改檔案副檔名，即可儲存為 PNG、JPEG、BMP 或 TIFF。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 以及 .NET 6+。

## 什麼是建立 Code 128 條碼？
`create code 128 barcode` 指的是產生一種使用 Code 128 符號的線性條碼，可編碼字母與數字資料。此符號因支援完整 ASCII 集且能嵌入 GS1 應用識別碼 (Application Identifiers) 而在物流領域被廣泛採用。條碼可儲存產品識別碼、序號以及其他自訂資料，適用於各種商業情境。

## 為何使用 Aspose.BarCode 產生 GS1 Code 128？
Aspose.BarCode 支援 **30+ 條碼符號**，且可渲染最高達 **10,000 × 10,000 px** 的影像而不失真，適合高解析度標籤列印。此函式庫亦會自動驗證 GS1 資料結構，降低生產線上條碼格式錯誤的風險。此外，它提供豐富的尺寸、顏色與版面自訂選項，協助符合嚴格的產業標準。

## 前置條件
在開始之前，請確保您具備以下條件：

1. **.NET 開發環境** – Visual Studio 2022、Rider，或任何支援 .NET 6+ 的 IDE。  
2. **Aspose.BarCode for .NET** – 從 **Aspose.BarCode for .NET 下載頁面** 下載，網址為 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/)，並將 NuGet 套件 `Aspose.BarCode` 加入您的專案。  
3. **基本的 C# 知識** – 您應該能熟練建立主控台或 Windows 應用程式。  
4. **了解 GS1 Code 128** – 雖非必須，但有助於使用；GS1 會使用如 `(01)` 代表 GTIN、`(21)` 代表序號的應用識別碼 (AI)。

## 如何一步步建立 Code 128 條碼

載入函式庫、設定條碼類型、指定 GS1 資料、客製化尺寸，最後儲存影像。對於「如何建立 Code 128 條碼？」這個問題的直接答案是：**實例化 `BarcodeGenerator` 並使用 `EncodeTypes.Code128` 以及 GS1 格式的資料，視需要調整 `XDimension`，最後呼叫 `Save` 並指定檔名與格式**。以下各節將逐步說明每個步驟。

### 步驟 1：設定目錄路徑
定義儲存產生影像的資料夾。將路徑設為可配置，可讓程式碼在不同環境中重複使用。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

將 `"Your Directory Path"` 替換為應用程式可寫入的絕對或相對路徑，例如 `@"C:\\Barcodes"` 或 `Path.Combine(Environment.CurrentDirectory, "Output")`。

### 步驟 2：建立 GS1 Code 128 條碼
建立條碼產生器、指定符號類型，並提供 GS1 格式的資料。資料字串必須包含以括號包住的應用識別碼 (Application Identifiers)。

```csharp
string path = "Your Directory Path";
```

範例使用 GTIN `(01)12345678901231`、序號 `(21)ASPOSE`，以及額外的自訂 AI `(30)9876`。Aspose.BarCode 會自動插入符合 GS1 標準所需的 FNC1 字元。

### 步驟 3：自訂條碼參數
調整視覺參數，例如 `XDimension`（窄條的寬度），以控制條碼密度。亦可修改高度、顏色與邊距。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

將 `XDimension = 2` 設定可產生大多數手持式讀取器易於掃描的條碼，同時保持影像尺寸適中。

### 步驟 4：儲存條碼影像
將產生的條碼寫入磁碟。您可以選擇 PNG 以獲得無損品質、JPEG 以減少檔案大小，或 TIFF 以配合列印流程。`Save` 方法會依檔案副檔名寫入相應格式的影像檔。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

將 `GS1Code128Example.png` 替換為任意符合您期望輸出格式的有效檔名與副檔名。

### 步驟 5：驗證條碼（可選）
儲存後，您可以將影像重新載入應用程式，或使用條碼掃描器確認編碼資料與原始字串相符。此步驟在開發與自動化測試時相當有用。

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## 常見問題與除錯技巧
- **未偵測到 FNC1** – 確認資料字串以左括號開頭且包含有效的 GS1 AI；函式庫僅對已識別的模式自動插入 FNC1。  
- **影像未儲存** – 確認目標目錄存在且應用程式具備寫入權限。可使用 `Directory.CreateDirectory(path)` 即時建立目錄。  
- **條碼過於密集** – 降低 `XDimension` 或增加影像高度，讓掃描器有更多空間讀取窄條。  
- **不支援的字元** – Code 128 只能編碼完整的 ASCII 集，請避免使用超出此範圍的 Unicode 字元。

## 常見問答

**Q: 我可以在不安裝完整 .NET Framework 的情況下於 Web API 產生條碼嗎？**  
A: 可以，Aspose.BarCode 支援 .NET Core 以及 .NET 5/6，您可以建立輕量級的 REST 端點，按需回傳條碼影像。

**Q: 此函式庫支援批次產生多個條碼嗎？**  
A: 完全支援。遍歷資料字串集合，為每個字串實例化 `BarcodeGenerator`，並在迴圈內呼叫 `Save`。此函式庫具備執行緒安全性，可進行平行處理。

**Q: 有沒有方法直接將條碼嵌入 PDF？**  
A: 可使用 Aspose.PDF 建立 PDF 文件，然後以條碼影像串流呼叫 `PdfPage.AddImage`。此作法可避免寫入中間檔案至磁碟。

**Q: 如何確保條碼符合 ISO/GS1 品質標準？**  
A: 將 `BarcodeGenerator.Options.Barcode.XDimension` 設為至少 0.33 mm，並依標籤尺寸設定 `BarHeight`。Aspose.BarCode 會驗證 AI 格式，對無效資料拋出例外。

**Q: 生產環境使用有哪些授權選項？**  
A: Aspose 提供永久授權、訂閱制以及雲端授權模式。試用授權可用於評估，但付費授權會移除評估浮水印並解鎖全部功能。

## 其他資源

- **文件** – 前往 [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/) 取得完整 API 參考。  
- **下載** – 從 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) 取得最新函式庫版本。  
- **免費試用** – 前往 [https://releases.aspose.com/](https://releases.aspose.com/) 開始 30 天試用。  
- **購買** – 於 [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy) 購買商業授權。  
- **支援** – 加入社群論壇 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) 取得除錯協助。

---

**最後更新：** 2026-09-08  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何在 .NET 建立 ITF-14 條碼 – 完整 Aspose.BarCode 教學](/barcode/net/)
- [使用 Aspose.BarCode .NET API 產生一維 Databar 2D 條碼](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}