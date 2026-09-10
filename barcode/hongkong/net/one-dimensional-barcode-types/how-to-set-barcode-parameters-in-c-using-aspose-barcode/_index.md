---
category: general
date: 2026-09-10
description: 如何在 C# 中使用 Aspose.BarCode 設定條碼屬性 – 另請參閱如何建立條碼及 C# 條碼產生技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to create barcode
- c# barcode generation
language: zh-hant
lastmod: 2026-09-10
og_description: 如何在 C# 中使用 Aspose.BarCode 設定條碼屬性。了解如何建立條碼、調整尺寸，並為您的應用程式產生 PNG 圖像。
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: 如何在 C# 中設定條碼參數 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode properties in C# with Aspose.BarCode – also see
    how to create barcode and master c# barcode generation techniques.
  headline: How to set barcode parameters in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- csharp
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 設定條碼參數
url: /zh-hant/net/one-dimensional-barcode-types/how-to-set-barcode-parameters-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 設定條碼參數

如果您需要在 C# 專案中 **如何設定條碼**，本指南將示範完整流程。您將學會如何建立條碼、設定 X‑dimension、選擇欄位數，並將結果儲存為 PNG 檔案——全部以單一可執行範例呈現。

以程式方式產生條碼可省去手動步驟，並確保在不同環境下產出一致的結果。完成本教學後，您即可將條碼產生整合至發票系統、庫存追蹤或任何需要機器可讀資料的 .NET 應用程式。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* 有效的 **Aspose.BarCode for .NET** 授權（開發階段可使用免費試用版）  

同時需要在專案中加入 `Aspose.BarCode` NuGet 套件的參考：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立條碼產生器 – 如何建立條碼

第一步是以欲使用的條碼類型與資料實例化 `BarcodeGenerator`。本範例使用 **MicroPdf417**，這是一種適合小標籤的緊湊型 2‑D 格式。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a MicroPdf417 barcode generator with the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,      // symbology
    "Micro data");                // data to encode
```

*為何重要*：選擇正確的 `EncodeTypes` 會告訴函式庫套用哪套編碼規則。`MicroPdf417` 在保持錯誤更正能力的同時，限制了條碼尺寸。

## 步驟 2：設定 X‑dimension – 如何設定條碼

X‑dimension 定義單一模組（最小的黑白方格）的寬度。調整此數值會直接影響整體影像大小與可掃描性。

```csharp
// Step 2: Set the X‑dimension (module width) of the barcode in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*為何重要*：較大的 X‑dimension 會產生較為穩健的條碼，掃描器可在較遠距離讀取，但同時會增加影像佔用空間。`2` 像素是螢幕顯示的平衡預設值。

## 步驟 3：選擇欄位數 – 如何設定條碼

MicroPdf417 支援 1‑4 欄。欄位數越多，條碼在垂直方向上越壓縮，適用於較窄的標籤。

```csharp
// Step 3: Specify the number of columns (1‑4 are allowed for MicroPdf417)
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

*為何重要*：欄位數會改變條碼的長寬比。選擇最大 `4` 欄可在保持可讀性的同時降低高度。

## 步驟 4：儲存影像 – C# 條碼產生

最後，將條碼寫入檔案。`BarCodeImageFormat.Png` 格式保留無損品質，適合後續處理。

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**預期輸出** – 桌面上會出現名為 `MicroPdf417.png` 的檔案。開啟後可看到一個緊湊的 MicroPdf417 條碼，編碼內容為 “Micro data”。

## 完整可執行範例 – C# 條碼產生

將所有步驟整合，即可得到一個可直接複製、貼上並執行的自包含程式：

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with MicroPdf417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Micro data");

        // 2. Set module width (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3. Choose 4 columns for a compact layout
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4. Define output path and save as PNG
        string filePath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode generated and saved to: {filePath}");
    }
}
```

使用 `dotnet run` 執行程式。若主控台顯示檔案路徑且無錯誤，即表示條碼產生成功。

## 常見陷阱 – **如何設定條碼** 屬性時

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 影像模糊 | X‑dimension 設定過低，無法符合目標尺寸 | 將 `XDimension.Pixels` 提升至 3 或 4 |
| 掃描器讀取失敗 | 欄位數與資料長度不匹配 | 減少 `Pdf417.Columns` 或縮短編碼文字 |
| 執行時拋出 `License not found` | 生產環境缺少 Aspose 授權 | 使用 `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` 載入有效授權檔 |
| 未產生 PNG 檔案 | 輸出資料夾不存在或缺乏寫入權限 | 確認目錄已建立且程式具備足夠權限 |

提前處理這些問題，可省下大量除錯時間，特別是將條碼產生納入自動化流程時。

## 延伸範例 – 如何建立其他類型的條碼

相同的程式模式適用於所有支援的條碼類型。若要產生 QR Code 而非 MicroPdf417，只需將 `EncodeTypes` 改為相應值：

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR,               // change symbology
    "https://example.com");       // data to encode
qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
```

您亦可透過 `Parameters` 物件調整錯誤更正等級、顏色與邊距。Aspose.BarCode API 文件列出了所有可設定的屬性。

## 效能考量 – C# 條碼產生

* **批次處理** – 在大量產生條碼時，重複使用同一個 `BarcodeGenerator` 實例，只在儲存前變更 `CodeText` 屬性。  
* **平行化** – 函式庫對獨立的產生器物件是執行緒安全的，您可以在多執行緒下同時產生條碼，以加速大批工作。  
* **記憶體使用** – PNG 直接寫入磁碟，降低堆積分配。若需在記憶體中處理，請改用 `MemoryStream` 取代檔案路徑。

## 結論

您現在已掌握在 C# 中 **如何設定條碼** 的尺寸、欄位數與輸出格式。完整範例示範了 **如何建立條碼**，從實例化到儲存 PNG 圖檔的每一步。憑藉此基礎，您可以產生任何支援的條碼類型、客製化外觀，並將流程整合至更大型的 .NET 應用程式。

**後續步驟**  

* 探索其他條碼類型，例如 `EncodeTypes.Code128` 或 `EncodeTypes.DataMatrix`（次要關鍵字：*c# barcode generation*）。  
* 透過設定 `generator.Parameters.Barcode.Color` 與 `BackgroundColor` 來加入自訂顏色。  
* 使用 Aspose.PDF 或 iTextSharp 將產生的 PNG 嵌入 PDF 報表。

歡迎自行嘗試不同的 X‑dimension、欄位數與資料內容。條碼產生是一項強大的工具——只要熟悉基本的 **如何設定條碼** 工作流程，就能輕鬆擴充以滿足任何商業需求。祝開發順利！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並提供其他實作方式的範例程式碼。

- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}