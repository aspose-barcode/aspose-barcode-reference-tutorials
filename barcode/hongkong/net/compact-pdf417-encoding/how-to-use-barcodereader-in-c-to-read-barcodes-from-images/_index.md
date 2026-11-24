---
category: general
date: 2026-11-23
description: 學習如何在 C# 中使用 BarCodeReader 從圖像讀取條碼，包括 Macro PDF417 解碼，並提供完整程式碼範例與清晰說明。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: zh-hant
lastmod: 2026-11-23
og_description: 如何在 C# 中使用 BarCodeReader 從圖像讀取條碼。跟隨此一步一步的指引，使用即用程式碼解碼 Macro PDF417
  及其他格式。
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: 如何在 C# 中使用 BarCodeReader – 快速從圖像讀取條碼
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: 如何在 C# 中使用 BarCodeReader 從圖像讀取條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarCodeReader 從圖像讀取條碼

如果你需要 **如何使用 BarCodeReader** 來快速掃描條碼，本指南會精確說明。無論你是在建置 point‑of‑sale 系統或自動化文件接收，你都能學會只用幾行程式碼在 C# 專案中從圖像讀取條碼。

在本教學中，你將看到一個完整、可執行的範例，解碼 Macro PDF417 條碼、擷取其擴充屬性，並將有用資訊輸出至主控台。無需外部文件說明——所有需要的內容都在此處。

## 前置條件

開始之前，請確保你已具備：

* .NET 6.0（或更新版本）已安裝——程式碼以最新 LTS 版為目標。
* 已參考 **Aspose.BarCode**（或任何相容）NuGet 套件，提供 `BarCodeReader`。
* 一張包含 Macro PDF417 條碼的影像檔（範例使用 `ExtPDF417Meta.png`）。

> **專業提示：** 若使用 Visual Studio，可透過 `dotnet add package Aspose.BarCode` 或 NuGet 套件管理員 UI 加入套件。

## 步驟 1：建立 BarCodeReader 實例

在使用條碼函式庫時，第一件事就是實例化一個讀取器，指向來源影像並告訴 API 要偵測哪種條碼類型。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*此步驟的重要性：*  
`BarCodeReader` 會開啟影像、配置原生記憶體，並為指定的 `DecodeType` 準備解碼演算法。將類型限制為 `MacroPdf417` 可減少 CPU 負載並提升偵測精確度。

## 步驟 2：讀取影像中所有偵測到的條碼

單一影像可能包含多個條碼，尤其是處理 macro‑encoded 資料時。`ReadBarCodes` 方法會回傳 `BarCodeResult` 物件的可列舉集合，每個物件代表一個偵測到的條碼。

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*此步驟的重要性：*  
遍歷集合可確保捕捉每一個實例，這對批次處理或文件內嵌多個條碼的情境相當重要。

## 步驟 3：存取擴充的 Macro PDF417 屬性

Macro PDF417 會儲存額外的中繼資料，如檔案識別碼、段號與總段數。這些值可透過 `BarCodeResult` 的 `Extended.Pdf417` 屬性取得。

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*此步驟的重要性：*  
擴充欄位讓你重新組合多段文件或驗證所有段落屬於同一來源。若略過此步驟，僅會得到原始文字，失去寶貴的上下文資訊。

## 步驟 4：輸出最有用的資訊

最後，將資料寫入主控台（或任何日誌）以驗證讀取結果。範例會列印條碼類型、解碼文字以及多個 macro 欄位。

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**預期的主控台輸出**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **注意：** 若影像未包含 Macro PDF417 條碼，`ReadBarCodes()` 會回傳空集合，迴圈本體不會執行。於正式程式碼中務必檢查結果是否為空。

## 讀取 C# 影像條碼 – 處理常見情境

### 1. 解碼多種條碼格式

若需偵測多於一種格式，可傳入組合的 `DecodeType` 旗標：

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. 處理大型影像

大型影像可能導致記憶體使用量過高。將影像縮小後再傳給讀取器：

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. 錯誤處理

將讀取邏輯包在 try‑catch 區塊，以捕捉解碼失敗的例外：

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## 完整可執行範例

以下是可直接複製、貼上並執行的完整程式碼，包含所有步驟、必要的 `using` 指示詞，以及簡易的錯誤處理骨架。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**執行程式** 後會列印每個偵測到的 Macro PDF417 條碼及其擴充欄位，或提示未偵測到條碼。

## 結論

你現在已了解 **如何使用 BarCodeReader** 從 C# 應用程式的影像中讀取條碼，並取得 Macro PDF417 的中繼資料。此解決方案涵蓋初始化、迭代、擴充屬性存取，以及處理多種格式、大型影像與錯誤的實務技巧。

接下來，你可以探索：

* **讀取 QR Code** – 將 `DecodeType.MacroPdf417` 改為 `DecodeType.QR`。
* **將解碼資料** 儲存至資料庫或 JSON 檔案，以供後續處理。
* **整合至 ASP.NET Core**，透過 Web API 接收上傳的影像。

歡迎自行嘗試不同條碼類型與影像來源，祝開發順利！

## 接下來該學什麼？

以下教學與本指南所示技術密切相關，提供完整的程式碼範例與逐步說明，協助你掌握更多 API 功能，並在專案中探索其他實作方式。

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}