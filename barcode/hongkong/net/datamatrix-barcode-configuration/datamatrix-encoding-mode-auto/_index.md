---
date: 2026-01-15
description: 一步一步的條碼教學指南，使用 Aspose.BarCode for .NET 在 C# 中讀取 DataMatrix 條碼並產生條碼圖像。
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: 讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（Auto）

在當今快速變化的數位世界中，能夠快速且可靠地 **read DataMatrix barcode C#** 對於從庫存追蹤到安全文件處理等各種需求都至關重要。本教學將帶領您使用 Aspose.BarCode for .NET 於 *Auto* 模式產生 DataMatrix 條碼，並示範如何在 C# 中讀取該條碼。無論您是遵循 **barcode tutorial guide** 還是僅需一個完整的程式碼範例，您都將完成本指南，獲得可直接套用於專案的可運作解決方案。

## 快速解答
- **Auto 模式的作用是什麼？** 它讓 Aspose.BarCode 自動為您的資料選擇最佳的編碼方案。  
- **需要哪個函式庫？** Aspose.BarCode for .NET（提供免費試用）。  
- **我可以在同一個應用程式中讀取條碼嗎？** 可以 – 使用 `BarCodeReader` 搭配 `DecodeType.DataMatrix`。  
- **生產環境需要授權嗎？** 需要商業授權才能在生產環境使用。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什麼是讀取 DataMatrix 條碼 C#？
在 C# 中讀取 DataMatrix 條碼表示將黑白模組的二維矩陣解碼回原始文字或資料。Aspose.BarCode 提供簡易的 API，將低階影像處理抽象化，讓您專注於業務邏輯。

## 為什麼使用 Aspose.BarCode 產生條碼影像 C#？
- **Reliability:** 處理所有 DataMatrix 標準，並自動選擇最佳編碼。  
- **Flexibility:** 完全掌控尺寸、ECI 編碼與影像格式。  
- **Cross‑platform:** 支援 .NET Framework、.NET Core 與 .NET 5+ 應用程式。

## 前置條件

1. **.NET Environment** – 從 [.NET 官方網站](https://dotnet.microsoft.com/download/dotnet) 安裝最新的 .NET 執行環境。  
2. **Aspose.BarCode for .NET** – 從 [網站](https://releases.aspose.com/barcode/net/) 下載函式庫。  

## 匯入命名空間

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

現在已匯入命名空間，讓我們一步一步走過程式碼。

## 步驟 1：設定目錄路徑

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您希望儲存產生的 PNG（或其他格式）之資料夾路徑。

## 步驟 2：在 Auto 模式下建立 DataMatrix 條碼

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

`DataMatrixEncodeMode.Auto` 設定讓函式庫自行決定提供文字的最佳編碼。您可以自由將範例文字替換為任何需要 **generate barcode image C#** 的字串。

## 步驟 3：讀取條碼（read DataMatrix barcode C#）

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

此程式碼片段會解碼剛剛產生的影像，並將原始文字輸出至主控台，示範從產生到讀取的完整往返流程。

## 常見問題與解決方案

| Issue | Cause | Fix |
|-------|-------|-----|
| **未偵測到條碼** | 影像解析度太低 | 增加 `XDimension.Pixels`（例如設定為 6） |
| **出現雜訊字元** | ECI 編碼錯誤 | 將 `ECIEncoding` 設為符合資料的編碼（UTF‑8、ASCII 等） |
| **`ReadBarCodes` 發生例外** | 在讀取前 Bitmap 已被釋放 | 在讀取完成前保持 `Bitmap` 實例存活 |

## 常見問答

**Q: DataMatrix 編碼模式「Auto」是什麼？**  
A: 它讓 Aspose.BarCode 自動為提供的資料選擇最佳的編碼方式，簡化 **how to generate datamatrix barcode** 的流程。

**Q: 我可以自訂產生的條碼尺寸嗎？**  
A: 可以 – 調整 `generator.Parameters.Barcode.XDimension.Pixels` 以變更模組大小。

**Q: Aspose.BarCode for .NET 可用於商業用途嗎？**  
A: 當然可以。請從 [網站](https://purchase.aspose.com/buy) 購買授權。

**Q: 有提供免費試用嗎？**  
A: 有，您可以透過 [此連結](https://releases.aspose.com/) 取得 Aspose.BarCode 的免費試用。

**Q: DataMatrix 條碼提供哪些編碼選項？**  
A: Aspose.BarCode 支援 UTF‑8、ASCII 以及其他 ECI 編碼；可透過 `ECIEncoding` 設定所需的編碼。

## 結論

您現在擁有一個完整、可投入生產的範例，能 **reads DataMatrix barcode C#**，在 Auto 模式下產生條碼，並驗證結果——全部使用 Aspose.BarCode for .NET。可嘗試不同的文字、尺寸與 ECI 設定，以符合您的特定情境，並參考官方 [文件](https://reference.aspose.com/barcode/net/) 以進行更深入的客製化。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

---