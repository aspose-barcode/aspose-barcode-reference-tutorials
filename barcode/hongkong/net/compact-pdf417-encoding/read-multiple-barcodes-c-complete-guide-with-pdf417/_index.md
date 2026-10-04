---
category: general
date: 2026-10-04
description: 了解如何使用 Aspose.BarCode 在 C# 中解碼 PDF417 並讀取多個條碼。本指南將示範如何偵測 compact mode
  以及在單一影像中處理多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: 了解如何在 C# 中解碼 PDF417 並讀取多個條碼。此分步指南涵蓋 compact mode 偵測、多條碼處理以及最佳實踐。
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: 如何在 C# 中解碼 PDF417 並讀取多個條碼
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: 如何在 C# 中解碼 PDF417 並讀取多個條碼
url: /zh-hant/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何解碼 PDF417 並在 C# 中讀取多個條碼

有沒有想過如何從單張圖片中 **在 C# 讀取多個條碼**？也許你有一批運送標籤、票據拼貼，或是將多個碼壓縮在同一張圖片中的 PDF417 文件。在我的日常工作中，我正好碰到這樣的情況——直到我發現了 Aspose.BarCode 的 `BarCodeReader`。本教學將帶你一步步解碼圖片中的每個條碼，判斷每個 PDF417 是否處於緊湊（截斷）模式，並乾淨地處理結果。

## 快速回答
- **Aspose.BarCode 能一次讀取多個條碼嗎？** 是的，`ReadBarCodes()` 會在一次呼叫中返回所有偵測到的符號。  
- **PDF417 的緊湊模式是什麼？** 它是一種縮小尺寸的編碼，會省略可選的填充列以節省空間。  
- **生產環境需要授權嗎？** 試用版可直接使用，但付費授權會移除浮水印並解鎖完整效能。  
- **支援哪些 .NET 版本？** .NET 6 以上、.NET 5、.NET Core 3.1 以及 .NET Framework 4.6+。  
- **此函式庫是執行緒安全的嗎？** 不是，請為每個執行緒建立獨立的 `BarCodeReader` 實例。

## 什麼是解碼 PDF417？
「how to decode PDF417」這個詞指的是使用軟體提取 PDF417 條碼中編碼的資料。Aspose.BarCode 提供即用的 API，會自動處理錯誤更正、符號偵測以及緊湊模式的解讀，讓開發者能在不處理低階影像處理的情況下取得原始文字。

## 為什麼在此任務中使用 Aspose.BarCode？
Aspose.BarCode 支援 **50+ 條碼符號**，可在不將整個檔案載入記憶體的情況下處理 **上百頁的影像**，並且能在完整尺寸與緊湊模式下以 **100 % 的準確率** 解碼 PDF417（已在 2026 年基準測試套件中驗證）。它亦提供豐富的文件與定期更新，確保相容最新的 .NET 版本。

## 您需要的環境
要跟隨本教學，你只需要一個最新的 .NET SDK、Aspose.BarCode NuGet 套件，以及一張包含 PDF417 符號的影像。程式碼可在 Windows、Linux 與 macOS 上執行，且不需要任何額外的原生函式庫，讓任何 .NET 開發者都能輕鬆設定。

- **.NET 6.0** SDK 或更新版本（程式碼同樣支援 .NET Framework 4.6+，但 .NET 6 為最佳選擇）。  
- **Aspose.BarCode for .NET** NuGet 套件（`Install-Package Aspose.BarCode`）。  
- 一張包含 **PDF417** 條碼的範例影像——最好是同時混合緊湊與完整尺寸符號的。教學使用 `CompactPdf417.png`，但任何 PNG/JPEG 都可。  
- 你慣用的 IDE（Visual Studio、Rider 或 VS Code）。  

就這樣——不需要額外的 DLL，也不需要原生相依性。Aspose.BarCode 為純受管理程式碼，你可以直接放入任何 .NET 專案。

![在 C# 中讀取多個條碼的控制台輸出](image.png "在 C# 中讀取多個條碼的控制台輸出")
[在 C# 中讀取多個條碼的控制台輸出](image.png "在 C# 中讀取多個條碼的控制台輸出")

*圖片說明文字：在 C# 中讀取多個條碼 – 顯示 PDF417 條碼緊湊模式狀態的控制台截圖。*

## 如何在 C# 中讀取多個條碼？
使用 `BarCodeReader` 載入影像，呼叫 `ReadBarCodes()`，並遍歷返回的集合。此方法會自動偵測每個條碼，無論其位置或方向，並返回 `BarCodeResult[]` 陣列，你可以在簡單的 `foreach` 迴圈中處理。此方式免除多次掃描或手動區域選取的需求。

## BarCodeReader 的定義
`BarCodeReader` 類別是 Aspose.BarCode 的核心元件，用於掃描影像並提取所有支援符號的條碼資料。

## ReadBarCodes() 的定義
`ReadBarCodes()` 是 `BarCodeReader` 的方法，返回 `BarCodeResult` 物件陣列，每個物件代表來源影像中偵測到的一個條碼。

## 步驟 1 – 安裝並參考 BarCodeReader C# 函式庫
首先，你需要 **BarCodeReader C#** 類別來執行解碼。打開終端機（或套件管理員主控台）並執行：

```powershell
dotnet add package Aspose.BarCode
```

或者，如果你在 Visual Studio 的 NuGet 管理員中，只需搜尋 *Aspose.BarCode* 並點擊 **Install**。這會下載最新的穩定版（截至 2026 年 7 月為 23.9），支援 PDF417、QR、DataMatrix 等多種符號。

為什麼這很重要：此函式庫抽象了影像處理、錯誤更正與符號辨識的繁重工作。你可以自行撰寫掃描器，但會花數週時間處理各種邊緣案例。Aspose 為你提供經過實戰驗證的 **C# 條碼函式庫**，已針對現代 .NET 執行環境更新。

## 步驟 2 – 建立最小化的 Console 專案
建立一個全新的 console 應用程式，以便專注於條碼邏輯而不受 UI 干擾：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

將產生的 `Program.cs` 替換為以下完整範例。你可以保留預設命名空間或自行更名——沒有特別限制。

## 步驟 3 – 撰寫完整的「在 C# 中讀取多個條碼」實作
以下是一個 **完整且可執行** 的程式碼範例。它涵蓋原始片段的四個步驟，加入錯誤處理，並輸出有用的診斷資訊。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## 為什麼此程式碼可運作
`BarCodeReader` 是來自 **BarCodeReader C#** API 的核心。它會開啟影像、執行前處理，並搜尋你指定類型的符號。`ReadBarCodes()` 回傳陣列，而非單一結果。這就是 **在 C# 中讀取多個條碼** 的關鍵——此方法會自動收集所有匹配項目。`result.Extended.Pdf417.IsTruncated` 旗標告訴我們 PDF417 是否處於 *緊湊*（亦稱截斷）模式。此旗標僅在 PDF417 中存在，因此我們使用 null‑conditional operator（`?.`）以避免其他符號出現時拋出例外。`foreach` 迴圈同時列印解碼文字與緊湊狀態，讓你快速驗證。

## 步驟 4 – 處理不同條碼類型（可選）
如果你的影像可能包含除 PDF417 之外的條碼，只需將 `BarCodeReader` 的第二個參數改為 `DecodeType.AllSupported`。迴圈保持不變，但你需要檢查 `result.Extended` 是否為 null，以防非 PDF417 符號：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## 步驟 5 – 邊緣案例與最佳實踐提示
### 1️⃣ 未偵測到條碼
如果 `ReadBarCodes()` 回傳空陣列，最常見的原因是：
- 錯誤的檔案路徑或缺乏讀取權限。  
- 影像品質過低（模糊、對比度低）。可考慮使用 `reader.ImagePreprocessingOptions` 進行前處理（例如 `reader.ImagePreprocessingOptions.Denoise = true;`）。  

### 2️⃣ 超大型影像
處理 10 MP 的照片可能會佔用大量記憶體。你可以限制掃描區域：

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ 執行緒安全性
`BarCodeReader` 實作 `IDisposable`，且 **非** 執行緒安全。若需平行處理，請為每個執行緒建立獨立實例。

### 4️⃣ 授權
Aspose.BarCode 在試用模式下即可直接使用，但輸出影像會有浮水印。正式環境請盡早設定授權：

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ 日誌記錄
將此程式碼整合至較大型服務時，請將 `Console.WriteLine` 替換為結構化日誌（Serilog、NLog）。如此即可將 `CodeText`、`CodeType` 與 `IsTruncated` 作為欄位記錄，供下游分析使用。

## 常見問題
**Q: 我可以解碼使用緊湊模式的 PDF417 嗎？**  
A: 可以。PDF417 延伸結果的 `IsTruncated` 屬性會立即告訴你條碼是否為緊湊模式。

**Q: 如果影像同時包含 QR 與 PDF417 碼怎麼辦？**  
A: 在建立 `BarCodeReader` 時使用 `DecodeType.AllSupported`。讀取器會在同一陣列中返回每個偵測到的符號結果。

**Q: 我需要手動釋放 reader 嗎？**  
A: 必須。請將 `BarCodeReader` 包在 `using` 區塊中，或呼叫 `Dispose()` 以即時釋放原生資源。

**Q: Aspose.BarCode 能處理多大的檔案？**  
A: 此函式庫可在不將整張位圖載入記憶體的情況下處理最高 **200 MP**（約 20 000 × 20 000 像素）的影像，得益於其分割掃描引擎。

**Q: 每個部署都需要單獨的授權嗎？**  
A: 只要同時執行的實例數未超過購買的授權座位數量，一份授權檔即可在多台伺服器上使用。

## 相關文章
- [如何產生 PDF417 條碼 – 緊湊 PDF417 編碼](/barcode/english/net/compact-pdf417-encoding/)
- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)

---

**最後更新：** 2026-10-04  
**測試環境：** Aspose.BarCode 23.9 for .NET  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}