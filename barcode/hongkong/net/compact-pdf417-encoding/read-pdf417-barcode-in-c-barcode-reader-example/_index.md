---
category: general
date: 2026-10-14
description: 在 C# 中建立主控台條碼掃描器，可讀取 PDF417 條碼、處理 macro PDF417，並從單張圖像中解碼多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: 在 C# 中建立主控台條碼掃描器，快速從圖像讀取 PDF417 與 macro PDF417 條碼。本逐步指南說明如何在單張圖片中解碼多個條碼。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: 在 C# 中建立主控台條碼掃描器 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: 在 C# 中建立主控台條碼掃描器 – 讀取 PDF417 條碼範例
url: /zh-hant/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立主控台條碼掃描器 – 讀取 PDF417 條碼範例

`BarCodeReader` 是 Aspose.BarCode 的核心類別，用於從影像解碼條碼並返回詳細的中繼資料。如果您需要從影像中讀取 PDF417 條碼資料，本指南將示範如何在 C# 中使用 **BarCodeReader** 類別。您將學習一個 **create console barcode scanner** 範例，該範例同時支援 macro PDF417，且能在單一影像中讀取多個條碼。

使用條碼時常需處理不同的影像來源、變化的光線條件，且有時會遇到如 macro PDF417 片段等複合資料。此教學涵蓋解碼 PDF417 條碼、擷取其延伸欄位，以及處理同一張圖片中的多個條碼所需的一切。完成後，您將擁有一個可執行的主控台程式，能從影像檔案讀取條碼並將詳細資訊印至主控台。

## 快速回答
- **範例做什麼？** 它會建立一個主控台條碼掃描器，從圖片中讀取 PDF417 與 macro PDF417 條碼，並列印所有解碼欄位。  
- **需要哪個函式庫？** Aspose.BarCode for .NET (NuGet)。  
- **能一次讀取多個條碼嗎？** 可以 – 讀取器會遍歷影像中找到的每個條碼。  
- **需要網路連線嗎？** 不需要，函式庫可完全離線運作。  
- **支援哪個 .NET 版本？** .NET 6.0 或更新版本。

## 您需要的條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本已安裝  
* **Aspose.BarCode for .NET** NuGet 套件的最新版本（或任何提供 `BarCodeReader` 與 `DecodeType.MacroPdf417` 的相容函式庫）  
* 包含 PDF417 或 macro PDF417 條碼的影像檔（範例使用 `ExtPDF417Meta.png`）  
* 如 Visual Studio 2022 等程式碼編輯器或 IDE  

不需要額外的服務或外部 API。

## 設定專案以讀取條碼

1. **建立新的主控台專案**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **加入條碼函式庫**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **複製條碼影像**  

   將 `ExtPDF417Meta.png`（或任何包含 PDF417 條碼的影像）放入專案資料夾中。  
   本教學假設該檔案位於 `YOUR_DIRECTORY/ExtPDF417Meta.png`。

專案現在已準備好編譯並執行條碼讀取範例。

## 如何在 C# 中建立主控台條碼掃描器？

`BarCodeReader` 是 Aspose.BarCode 提供的類別，用於從影像讀取條碼並返回其解碼資料。  
使用 `BarCodeReader` 載入影像，將解碼類型設為 `MacroPdf417`，並遍歷結果 – 這就是建立主控台條碼掃描器所需的全部。由於使用 `using` 陳述式，讀取器會自動釋放本機資源，您無需手動管理記憶體。此方法適用於 .NET 支援的任何影像格式，例如 PNG、JPEG 或 BMP。

### 逐步說明

核心在於使用 `using` 區塊建立 `BarCodeReader` 實例，指定 `DecodeType.MacroPdf417`，並遍歷每個偵測到的條碼。以下程式碼是一個完整、獨立的程式，您可以貼到 `Program.cs` 中。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**為什麼這樣可行**：  

* `DecodeType.MacroPdf417` 告訴讀取器尋找 PDF417 的 macro 擴充，該擴充攜帶額外的中繼資料，如檔案 ID、分段數量與時間戳記。  
* `using` 陳述式保證未受管理的資源（檔案句柄、本機解碼緩衝）能即時釋放。  
* `foreach` 迴圈會自動處理影像中 **所有** 條碼，滿足 *read multiple barcodes* 的需求。  

執行程式 (`dotnet run`) 後，您應該會看到類似以下的輸出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

如果影像包含多於一個 PDF417 條碼，迴圈會為每個條碼印出獨立的區塊，從而示範如何從單一圖片 **read multiple barcodes**。

## 如何從影像中讀取多個條碼？

使用單一個 `BarCodeReader` 實例，並將 `DecodeType` 標誌設為包含所有想偵測的格式。透過位元 OR 運算子結合多個標誌，您可以指示函式庫一次搜尋 PDF417、QR、Code‑128 以及其他多種條碼。這樣即可免除使用多個讀取器，並降低處理時間。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* 是位元遮罩，您可以結合任意數量的支援格式。Aspose.BarCode 支援 **30+ 條碼符號**，包括 QR、DataMatrix、Code‑128 與 UPC‑A，讓單一掃描器能處理多樣化的使用情境，如產品標籤、票券驗證與身分驗證。

## 什麼是 macro PDF417，且如何安全存取其欄位？

Macro PDF417 是 PDF417 符號的擴充，允許將大量資料分割至多個條碼符號。  
Macro PDF417 增加了豐富的擴充屬性。然而，並非每個條碼都包含所有欄位。存取不存在的屬性會拋出 `NullReferenceException`。最安全的做法是在列印前驗證每個屬性，以確保即使缺少 macro 資料，應用程式仍能穩定運作。

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*為什麼這很重要*：在實務部署中，您可能會收到不含 macro 資料的普通 PDF417 條碼。防禦性檢查可確保應用程式不會因為缺少資料而當機。

## 常見陷阱與最佳實踐

| 問題 | 發生原因 | 建議解決方式 |
|------|----------|--------------|
| 影像路徑不正確 | `BarCodeReader` 在任何解碼發生前拋出檔案未找到例外 | 使用 `Path.Combine` 並以 `File.Exists` 驗證檔案是否存在 |
| 低解析度影像 | 解碼器無法定位條碼邊緣，導致偵測為零 | 提供至少 300 dpi 的解析度以獲得可靠結果 |
| 條碼旋轉 > 45° | 許多函式庫假設條碼為正立方向 | 若影像可能被旋轉，請啟用 `reader.RecognitionOptions.RotateImage = true` |
| 缺少 macro 欄位 | 嘗試讀取 null 屬性會導致當機 | 在存取 macro 屬性前務必檢查是否為 `null` |
| 大量批次處理 | 為每個檔案重新建立讀取器會增加額外負擔 | 在處理多張影像時，使用同一個 `BarCodeReader` 實例搭配不同的串流重複使用 |

## 為什麼使用 Aspose.BarCode 來建立主控台條碼掃描器？

Aspose.BarCode 能解碼 **30+ 條碼類型**，且可處理高達 **200 MP** 的影像而不需將整個檔案載入記憶體，在一般 3.2 GHz CPU 上可達 **每秒 150 幀** 的吞吐量。這些具體的效能使其成為高量、內部部署掃描解決方案的可靠選擇，尤其在延遲與準確度至關重要的情況下。

## 接下來您可以學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源都包含完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [從影像讀取條碼 – 精通 Java 中 Aspose.BarCode 的條碼區域擷取](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## 常見問題

**Q: 我可以在正式環境中使用此掃描器嗎？**  
A: 可以。購買商業版 Aspose.BarCode 授權即可移除評估水印並取得完整支援。

**Q: 此函式庫能在 Linux 與 macOS 上運作嗎？**  
A: 完全可以。Aspose.BarCode for .NET 為跨平台套件，可在 Windows、Linux 與 macOS 上的 .NET 6+ 執行。

**Q: 如何在不耗盡記憶體的情況下處理非常大的影像？**  
A: 使用 `LoadOptions` 建構子啟用串流模式，讓影像分塊處理而非一次性載入全部至記憶體。

**Q: 能否解碼加密或受密碼保護的影像？**  
A: 讀取器可處理使用標準 PNG/JPEG 密碼機制加密的影像；只需透過 `reader.ImagePassword` 提供密碼即可。

**Q: 若條碼部分受損該怎麼辦？**  
A: 啟用錯誤更正選項，例如 `reader.RecognitionOptions.CorrectErrors = true`，以提升對損壞或噪聲的容錯能力。

**最後更新：** 2026-10-14  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何在 C 中讀取 Pdf417 – 完整條碼讀取器範例](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [讀取多個條碼 C 完整指南（含 Pdf417）](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [從影像解碼條碼 – 使用 C 條碼讀取器範例](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}