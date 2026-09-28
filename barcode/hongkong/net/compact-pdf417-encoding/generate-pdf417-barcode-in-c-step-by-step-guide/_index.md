---
category: general
date: 2026-08-09
description: 快速於 C# 產生 PDF417 條碼。學習如何使用 BarcodeGenerator API 以緊湊模式、欄位控制及 PNG 輸出產生
  PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: zh-hant
lastmod: 2026-08-09
og_description: 使用 C# 產生 PDF417 條碼，提供簡潔範例。本指南說明如何設定緊湊模式、設定欄位，並將結果儲存為 PNG 圖像。
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: 在 C# 中產生 PDF417 條碼 – 完整教學
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: 在 C# 中產生 PDF417 條碼 – 步驟說明指南
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 PDF417 條碼 – 步驟指南

如果你需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學會完整示範如何操作。你將看到一個完整、可執行的程式，能建立緊湊的 PDF417 條碼、調整其尺寸，並將影像儲存為 PNG 檔案。

產生 PDF417 條碼是行動票證、庫存追蹤與文件安全等情境的常見需求。本指南涵蓋必要的設定選項、說明每個設定的意義，並提供實務使用的小技巧。

## 前置條件

在開始之前，請確保你已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* 具備 Visual Studio 2022 或 Visual Studio Code 等 C# IDE  
* **Aspose.BarCode for .NET** NuGet 套件（版本 23.10 或更新）  

你可以使用以下 CLI 指令安裝套件：

```bash
dotnet add package Aspose.BarCode
```

以下程式碼假設已正確引用套件，且你對輸出目錄具有寫入權限。

## Step 1: 設定專案並匯入命名空間

建立新的 Console 專案，並加入必要的 `using` 指令。這些命名空間會公開 `BarcodeGenerator` 類別與影像格式列舉。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**為什麼這很重要：** 匯入正確的命名空間可讓編譯器找到 `BarcodeGenerator` 類型與 `BarCodeImageFormat` 列舉。若缺少命名空間，會導致編譯錯誤，進而中斷條碼產生流程。

## Step 2: 使用 PDF417 編碼初始化 `BarcodeGenerator`

`BarcodeGenerator` 建構子接受兩個參數：條碼符號系統 (`EncodeTypes.Pdf417`) 與要編碼的文字。PDF417 支援廣泛的字元，包括 Unicode 符號。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**說明：**  
* `EncodeTypes.Pdf417` 告訴函式庫使用 PDF417 標準。  
* 範例文字包含重音字元與版權符號，以示範 Unicode 處理。  

如果只需要編碼數字資料，可傳入純字串，例如 `"1234567890"`。

## Step 3: 調整 X‑dimension 以獲得更細緻的解析度

X‑dimension 控制單一條碼模組（最小的黑或白元素）的寬度。設定較小的像素值即可得到更高解析度的影像。

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼要調整？** 預設的 3–4 像素 X‑dimension 在高 DPI 螢幕上可能顯得粗糙。將其降低至 **2 像素** 可在可讀性與檔案大小之間取得平衡，特別是之後啟用緊湊模式時。

## Step 4: 設定欄位數量

PDF417 允許你指定條碼應包含多少欄位。欄位較少會使條碼變窄但變高，欄位較多則產生較寬、較短的條碼。

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**實用小技巧：** 若行動票證需放在窄標籤內，**3–5** 欄的設定相當合適。若資料量大且希望條碼較短，可增加欄位數。

## Step 5: 啟用緊湊模式以截除空白列

緊湊模式會移除條碼矩陣中不必要的列，減少整體影像大小，同時不會遺失編碼資料。

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**何時使用：** 若條碼用於儲存或網路傳輸，緊湊模式可將 PNG 檔案縮小最多 30 %。但某些舊版掃描器可能不支援截除的 PDF417，請以目標硬體測試。

## Step 6: 將條碼儲存為 PNG 影像

選擇輸出路徑並呼叫 `Save`。`BarCodeImageFormat.Png` 列舉會產生適合大多數應用的無損影像。

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**結果驗證：** 用任何影像檢視器開啟 PNG 檔案，你應該會看到密集且高對比度的條碼，且文字與範例相符。使用 PDF417 讀取器（如 ZXing 或手機應用）掃描影像，會回傳原始字串 `"Åspóse.Barcóde©"`。

![已產生的 PDF417 條碼影像（已儲存為 PNG）](compact-pdf417.png "在 C# 中產生的 PDF417 條碼")

*上圖示範了本教學程式的最終輸出。*

## 完整、可執行的範例

將所有步驟整合起來，以下是一個完整的 Console 程式，你可以直接複製、貼上並執行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 預期輸出

執行程式會印出：

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

`CompactPdf417.png` 檔案包含一個緊湊的 PDF417 條碼，編碼了提供的 Unicode 字串。使用標準 PDF417 讀取器掃描影像，即可取得完全相同的文字。

## 常見變化與邊緣案例

| 情況 | 調整方式 | 原因 |
|-----------|------------|--------|
| **較長的資料負載**（例如 > 150 字元） | 將 `generator.Parameters.Barcode.Pdf417.Columns` 增加至 6‑8 | 更多欄位可防止條碼變得過高。 |
| **需要透明背景** | 使用 `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | 透明 PNG 在 UI 疊加時更易整合。 |
| **產生 JPEG 供網頁使用** | 將格式改為 `BarCodeImageFormat.Jpeg`，並可選擇設定 `ImageQuality` | JPEG 可減少檔案大小，但會犧牲無損品質。 |
| **處理 null 或空字串輸入** | 在建立產生器前先檢查輸入：`if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | 防止執行時例外，確保產生有意義的條碼。 |

## 生產環境使用小技巧

* **例外處理：** 將產生邏輯包在 `try/catch` 區塊中，以記錄磁碟空間不足或參數無效等錯誤。  
* **效能：** 若大量產生條碼且設定相同，請重複使用同一個 `BarcodeGenerator` 實例；只在每次儲存前更新 `CodeText` 屬性。  
* **安全性：** 若編碼文字包含敏感資訊，建議在傳入產生器前先加密，掃描後再解密。

## 結論

你現在已掌握如何在 C# 中使用 Aspose.BarCode 套件 **產生 PDF417 條碼**，並能設定緊湊模式、調整欄位數量，最後將結果匯出為 PNG 影像。本教學從專案設定到邊緣案例處理，提供一套可直接投入使用的條碼解決方案。

接下來，可探索 **在 C# 中建立 QR Code**、**批次產生條碼**、以及 **將條碼掃描整合至行動應用** 等相關主題。這些皆建立在你剛剛熟悉的 `BarcodeGenerator` 基礎上。

祝編程愉快！

## 接下來該學什麼？

以下教學與本指南示範的技巧密切相關，並提供完整的程式範例與逐步說明，協助你掌握更多 API 功能，或在自己的專案中探索替代實作方式。

- [如何產生 PDF417 條碼 – 緊湊 PDF417 編碼](/barcode/english/net/compact-pdf417-encoding/)
- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}