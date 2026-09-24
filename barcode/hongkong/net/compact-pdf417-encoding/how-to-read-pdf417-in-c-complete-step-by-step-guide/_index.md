---
category: general
date: 2026-07-15
description: 如何在 C# 中讀取 PDF417 條碼，並從圖像中讀取多個條碼。學習使用 C# 讀取條碼圖像，提供詳細程式碼與技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: zh-hant
lastmod: 2026-07-15
og_description: 如何在 C# 中快速讀取 PDF417 條碼。本指南將示範如何從單一圖像中讀取多個條碼並解碼每個屬性。
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: 如何在 C# 中讀取 PDF417 – 完整程式碼範例與說明
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: 如何在 C# 中讀取 PDF417 – 完整逐步指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 – 完整逐步指南

有沒有想過如何使用 C# 從圖像中**讀取 PDF417**？你並不是唯一有此疑問的人。大多數開發人員在需要從掃描文件中提取擴展的 Macro‑PDF417 欄位時會卡住。好消息是，只需幾行程式碼就能解碼 PDF417、在同一張圖片中讀取多個條碼，並取得規格所提供的所有隱藏屬性。

在本教學中，我們將逐步說明一個真實案例，展示 **how to read PDF417**、如何從單一檔案**read multiple barcodes**，以及為何 **read barcode image C#** 程式碼會呈現此樣子。完成後，你將擁有一個可直接執行的主控台應用程式，能印出所有可能需要的資訊——檔案 ID、段落 ID、檢查碼、時間戳記，等等。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼同樣適用於 .NET Core 與 .NET Framework）。  
* Visual Studio 2022（或任何你偏好的編輯器）。  
* **Aspose.BarCode for .NET** NuGet 套件 – 這是實際解析 PDF417 的函式庫。  
* 一張包含 Macro‑PDF417 條碼的範例圖像（例如 `ExtPDF417Meta.png`）。  

不需要額外設定；此函式庫已內建所有所需的解碼器。

## 步驟 1：安裝 Aspose.BarCode

在終端機中開啟你的專案資料夾，並執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會取得最新的穩定版（截至 2026 年 7 月為 23.12）。如果你偏好在 Visual Studio 內使用套件管理員主控台，請使用：

```powershell
Install-Package Aspose.BarCode
```

> **專業提示：** 在 `.csproj` 中鎖定版本 (`23.12.0`) 以避免日後不慎產生相容性問題。

## 步驟 2：建立主控台應用程式骨架

如果尚未有專案，請建立新的主控台專案：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

將自動產生的 `Program.cs` 替換為以下程式碼。我們會在接下來的章節說明每個區塊的作用。

## 步驟 3：撰寫完整的「How to Read PDF417」程式碼

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### 為何此程式碼可運作

* **`BarCodeReader`** 是核心類別，用於串流圖像、偵測條碼，並回傳 `BarCodeResult` 物件的集合。  
* 傳入 **`DecodeType.MacroPdf417`** 會告訴函式庫特別處理 Macro‑PDF417；它仍會回傳普通的 PDF417 符號，滿足 **read multiple barcodes** 的需求。  
* **`Extended.Pdf417.MacroPdf417`** 物件包含 ISO/IEC 15438 標準所定義的所有可選欄位——在此可取得 `FileID`、`SegmentID`、`Checksum` 等資訊。  
* `using` 區塊確保原生資源被釋放，避免長時間執行的服務發生記憶體泄漏。

## 步驟 4：執行應用程式並驗證輸出

在終端機中執行：

```bash
dotnet run
```

你應該會看到類似以下的結果：

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

如果圖像中包含多於一個條碼，迴圈會印出分隔線 (`----------------------------------------`) 並繼續處理下一個結果——這正是實務上 **read multiple barcodes** 的呈現方式。

## 常見問題與邊緣案例

### 如果圖像同時包含 Macro‑PDF417 與一般 PDF417 符號，該怎麼辦？

相同的 `BarCodeReader` 呼叫會回傳兩者。你可以透過檢查 `result.CodeType`（`MacroPdf417` 與 `Pdf417`）來區分。對於普通 PDF417，擴充屬性會是 `null`，因此 `if (macro != null)` 的防護可避免 `NullReferenceException`。

### 條碼被旋轉或傾斜——讀取器仍能正常工作嗎？

Aspose.BarCode 內建旋轉與變形補償功能。只要條碼寬度至少佔圖像寬度的 30%，解碼器通常能成功。若遇極端情況，可在呼叫 `ReadBarCodes()` 前啟用 `reader.Options.AllowInvertedBarcodes = true;`。

### 如何處理大量圖像批次？

將讀取邏輯包在 `foreach (var file in Directory.GetFiles(folder, "*.png"))` 迴圈中。`using` 模式確保每張圖像的原生資源在下一次迭代前釋放，從而降低記憶體使用量。

## 完整原始碼清單（可直接複製貼上）

以下是一個完整的程式區塊，方便快速複製貼上。沒有隱藏的相依性——只需要 Aspose.BarCode NuGet 套件。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## 重點回顧 – 本文涵蓋內容

* **How to read PDF417** 使用 Aspose.BarCode 於 C#。  
* 從單一圖像**read multiple barcodes** 的完整步驟。  
* 如何**read barcode image C#** 並擷取所有 Macro‑PDF417 欄位。  
* 旋轉、批次處理以及處理缺少擴充資料的技巧。

## 往後步驟與相關主題

* **Encode PDF417** – 使用 `BarCodeBuilder` 產生自己的 Macro‑PDF417 條碼。  
* **Read other 2‑D symbologies** – QR、DataMatrix、Aztec – 使用相同的 `BarCodeReader` 類別。  
* **Integrate with ASP.NET Core** – 建立接受上傳圖像並回傳解碼欄位 JSON 的 Web 端點。  

隨意嘗試：更改圖像路徑、將普通 PDF417 放入同一資料夾，或調整 `DecodeType` 旗標觀察函式庫的行為。玩得越多，你就會越熟悉 **read barcode image C#** 的情境。

遇到難以解碼的圖像嗎？在下方留言或在範例專案的 GitHub 倉庫開啟 issue。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode 建立條碼 – Compact PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}