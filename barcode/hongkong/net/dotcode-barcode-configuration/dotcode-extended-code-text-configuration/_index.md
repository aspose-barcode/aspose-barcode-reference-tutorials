---
date: 2026-01-27
description: 了解如何使用 Aspose.BarCode for .NET 建立 DotCode 延伸代碼文字——一步一步的指南，教您產生帶有延伸代碼文字的
  DotCode 條碼。
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 建立 DotCode 擴展代碼文字
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 建立 dotcode extended codetext

## Introduction

在條碼產生與管理領域，Aspose.BarCode for .NET 脫穎而出，提供多功能且高效的解決方案。無論您需要為產品、庫存或其他任何應用產生條碼，Aspose.BarCode for .NET 都能滿足需求。在本完整教學中，我們將 **create dotcode extended codetext**，並探討此功能在現代資料豐富環境中的重要性。DotCode 是一種二維矩陣條碼，可編碼文字與二進位資料，因而在各行各業皆具價值。

## Quick Answers
- **「create dotcode extended codetext」是什麼意思？** 它表示建立一個 DotCode 條碼，該條碼在單一延伸載荷中包含 FNC1、ECICodetext、純文字以及符號分隔符。  
- **需要哪個函式庫？** Aspose.BarCode for .NET.  
- **需要授權嗎？** 臨時授權可用於評估；正式使用則需完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 以上。  
- **實作需要多長時間？** 基本範例大約 10‑15 分鐘即可完成。

## 如何建立 dotcode extended codetext

以下是一個簡潔的逐步說明，完整展示如何建構延伸編碼文字並產生條碼影像。

## Prerequisites

在深入逐步指南之前，您需要先具備以下前置條件，以便順利跟隨操作：

1. Aspose.BarCode for .NET：確保已安裝並可使用 Aspose.BarCode for .NET 函式庫。若尚未安裝，可從 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 下載。  
2. 開發環境：應在系統上安裝可運作的 .NET 開發環境，建議使用 Visual Studio。

具備上述前置條件後，我們即可開始產生 DotCode Extended Code Text。

## Import Namespaces

首先，您需要在 .NET 專案中匯入必要的命名空間，以存取 Aspose.BarCode 函式庫的相關功能。以下示範如何操作：

```csharp
using Aspose.BarCode.Generation;
```

現在已完成前置作業，讓我們將產生 DotCode Extended Code Text 的流程分解為逐步說明。

## 步驟 1：定義目錄路徑

在此步驟中，您需要指定欲儲存產生之 DotCode Extended Code Text 影像的目錄路徑。

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您系統上的實際路徑。

## 步驟 2：建立 DotCode Extended Code Text

要建立 DotCode Extended Code Text，請依照以下子步驟操作：

### 2.1 新增 FNC1 格式識別碼

FNC1 格式識別碼用於指示新資料欄位的開始，屬於 DotCode Extended Code Text 的重要組成部分。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 新增 ECICodetext

ECICodetext 可用於編碼特殊字元與國際文字。在本範例中，我們使用 UTF‑8 編碼將 `"犬Right狗"` 進行編碼。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 新增純文字 Codetext

您亦可在 DotCode Extended Code Text 中加入純文字。本例中，我們加入了 `"Plain text"`。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 新增 FNC3 符號分隔符

FNC3 符號分隔符用於分隔程式碼的不同區段。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 新增 FNC3 讀取器初始化

此步驟會加入 FNC3 讀取器初始化資訊。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 產生 Codetext

現在，透過呼叫 `textBuilder` 物件的 `GetExtendedCodetext` 方法，產生 DotCode Extended Codetext。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 步驟 3：產生 DotCode 影像

若要將 DotCode Extended Code Text 產生為影像，請依照以下子步驟操作：

#### 4.1 初始化 Barcode Generator

使用適當的參數初始化 `BarcodeGenerator`。此例中，我們使用 `EncodeTypes.DotCode` 以及先前產生的 codetext。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

完成！您已成功使用 Aspose.BarCode for .NET 產生 DotCode Extended Code Text。

## 結論

Aspose.BarCode for .NET 是一套功能強大的工具，可簡化條碼產生程序。在本教學中，我們重點說明如何 **create dotcode extended codetext**，此功能在各行各業皆相當重要，特別是需要多語言與特殊字元編碼的情境。依循上述步驟，即可輕鬆為您的需求建立 DotCode Extended Code Text。

如需進一步指引或有任何疑問，請隨時造訪 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 或前往 [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) 與社群互動。

## 常見問答

### Q1：DotCode 的用途是什麼？

A1：DotCode 用於編碼文字與二進位資料，常見於醫療保健、物流等產業，用於追蹤與資料編碼。

### Q2：我可以自訂 DotCode 條碼的外觀嗎？

A2：可以，Aspose.BarCode for .NET 提供多種選項，可自訂 DotCode 條碼的外觀，包括尺寸與編碼模式。

### Q3：Aspose.BarCode for .NET 是否相容於各種 .NET 框架？

A3：是的，Aspose.BarCode for .NET 相容於多種 .NET 框架，確保彈性與易於整合。

### Q4：如何取得 Aspose.BarCode for .NET 的臨時授權？

A4：您可從 [Aspose 的網站](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供評估與測試使用。

### Q5：Aspose.BarCode for .NET 是否適合企業級條碼產生？

A5：絕對適合，Aspose.BarCode for .NET 為小規模與企業級條碼產生需求而設計，具備可擴充性與可靠性。

## 常見問題

**Q：我可以在行動應用程式中使用產生的條碼嗎？**  
A：可以。產生的 PNG 影像可嵌入 iOS、Android 或任何跨平台行動應用程式中。

**Q：如果需要編碼二進位資料而非文字該怎麼辦？**  
A：使用 `AddECICodetext` 方法，搭配適當的 `ECIEncodings`（例如 `ECIEncodings.Base64`）以嵌入二進位負載。

**Q：如何調整條碼尺寸而不影響可讀性？**  
A：調整 `XDimension.Pixels` 屬性；較高的數值會增大模組尺寸，較低的數值則使條碼更緊湊。

**Q：能否在條碼周圍加入安靜區域？**  
A：可以。設定 `gen.Parameters.Barcode.Margin` 以定義所需的像素安靜區。

**Q：此函式庫支援 .NET 8 嗎？**  
A：最新的 Aspose.BarCode 版本相容於 .NET 8，只需引用相應的 NuGet 套件版本。

---

**最後更新：** 2026-01-27  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}