---
date: 2026-08-02
description: 逐步指南，說明如何在 C# 中讀取 DataMatrix 條碼並使用 Aspose.BarCode for .NET 以自動編碼產生條碼影像。
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: DataMatrix 編碼模式（自動）
og_description: 了解如何使用 Aspose.BarCode for .NET 在 C# 中讀取 DataMatrix 條碼並以自動模式產生。此教學涵蓋環境設定、程式碼與故障排除。
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: 如何在 C# 中讀取 DataMatrix 條碼 – 自動模式
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: 如何在 C# 中讀取 DataMatrix 條碼 – 自動模式
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 DataMatrix 條碼 – 自動模式

在當今快速變遷的數位世界中，**如何讀取 DataMatrix** 快速且可靠對於庫存追蹤、文件安全處理以及其他眾多企業情境至關重要。本教學將帶您使用 Aspose.BarCode for .NET 於 *Auto* 模式產生 DataMatrix 條碼，並示範如何在 C# 中讀取該條碼。無論您是跟隨條碼教學指南，或是需要即用的程式碼範例，您都將獲得可直接嵌入任何 .NET 專案的生產就緒解決方案。

## 快速解答
- **「Auto」模式會做什麼？** 它讓 Aspose.BarCode 自動為您的資料選擇最佳的編碼方案。  
- **需要哪個函式庫？** Aspose.BarCode for .NET（提供免費試用）。  
- **可以在同一個應用程式中讀取條碼嗎？** 可以 – 使用 `BarCodeReader` 搭配 `DecodeType.DataMatrix`。  
- **生產環境需要授權嗎？** 商業授權是生產使用的必要條件。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  

`BarCodeReader` 是 Aspose.BarCode 用於掃描影像並取得條碼資訊的類別。

## 什麼是讀取 DataMatrix 條碼 C#？
在 C# 中讀取 DataMatrix 條碼即是將黑白模組組成的二維矩陣解碼回原始文字或資料。Aspose.BarCode 抽象化了低階影像處理，讓您專注於業務邏輯，同時函式庫會自動處理錯誤更正、符號大小選擇與 Unicode 支援。

## 為什麼使用 Aspose.BarCode 產生條碼影像（C#）？
Aspose.BarCode 會自動挑選最佳編碼，支援 **30+ 條碼符號**，且可產生最高達 **1558 × 1558 模組** 的 DataMatrix 符號——遠大於大多數競爭對手。它可在 Windows、Linux 與 macOS 上執行，無需原生相依性，為您提供單一跨平台 API，同時支援產生與讀取。

## 前置條件

1. **.NET 環境** – 從 [.NET website](https://dotnet.microsoft.com/download/dotnet) 安裝最新的 .NET 執行時。  
2. **Aspose.BarCode for .NET** – 從 [website](https://releases.aspose.com/barcode/net/) 下載函式庫。  

## 匯入命名空間
`Aspose.BarCode` 命名空間包含了建立與讀取條碼所需的所有類別。請在檔案最上方匯入它，於其他程式碼之前。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

現在命名空間已就緒，讓我們一步一步走過程式碼。

## 步驟 1：設定目錄路徑
選擇一個資料夾，用來儲存產生的 PNG（或任何支援的格式）。此路徑可以是絕對路徑或相對於專案的路徑。

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您偏好的資料夾。將輸出資料夾設為可配置，使教學能在不同環境中重複使用。

## 步驟 2：以自動模式建立 DataMatrix 條碼
`DataMatrixEncodeMode.Auto` 告訴產生器自動為提供的資料選擇最佳的編碼方案。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

隨意將範例文字替換為您需要 **如何產生 DataMatrix** 的任意字串。自動模式會在 Base‑256、ASCII 或其他方案之間自動切換，以產生最小的符號。

## 步驟 3：讀取條碼（讀取 DataMatrix 條碼 C#）
`BarCodeReader` 是 Aspose.BarCode 用於掃描影像並取得條碼資訊的類別。它支援從串流、檔案與 Bitmap 物件讀取，非常適合 **從檔案讀取條碼** 的情境。

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

此程式碼片段會解碼剛剛產生的影像，並將原始文字印到主控台，示範從產生到讀取的完整往返流程。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **未偵測到條碼** | 影像解析度太低 | 增加 `XDimension.Pixels`（例如設定為 6） |
| **出現雜訊字元** | ECI 編碼錯誤 | 設定 `ECIEncoding` 為符合您資料的編碼（UTF‑8、ASCII 等） |
| **`ReadBarCodes` 發生例外** | Bitmap 在讀取前已被釋放 | 保持 `Bitmap` 實例存活至讀取完成後再釋放 |

## 常見問答

**Q: DataMatrix 編碼模式「Auto」是什麼？**  
A: 它讓 Aspose.BarCode 自動為提供的資料選擇最佳的編碼方式，簡化 **如何產生 DataMatrix** 的流程。

**Q: 我可以自訂產生條碼的尺寸嗎？**  
A: 可以 – 調整 `generator.Parameters.Barcode.XDimension.Pixels` 即可改變模組大小。

**Q: Aspose.BarCode for .NET 可用於商業用途嗎？**  
A: 當然可以。請從 [website](https://purchase.aspose.com/buy) 購買授權。

**Q: 有提供免費試用嗎？**  
A: 有，您可以透過 [this link](https://releases.aspose.com/) 取得 Aspose.BarCode 的免費試用版。

**Q: DataMatrix 條碼支援哪些編碼選項？**  
A: Aspose.BarCode 支援 UTF‑8、ASCII 以及其他 ECI 編碼；可透過 `ECIEncoding` 設定所需的編碼。

## 結論

您現在擁有一個完整、可投入生產的範例，**讀取 DataMatrix 條碼 C#**、以 Auto 模式產生條碼，並驗證結果——全部使用 Aspose.BarCode for .NET。可自行嘗試不同文字、尺寸與 ECI 設定，以符合您的特定情境，並參考官方 [documentation](https://reference.aspose.com/barcode/net/) 進一步自訂。

---

**最後更新：** 2026-08-02  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相關教學

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/)
- [DataMatrix Structured Append Configuration with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [DataMatrix Reader Programming with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}