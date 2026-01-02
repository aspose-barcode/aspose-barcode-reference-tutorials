---
date: 2026-01-02
description: 了解如何使用 Aspose.BarCode for .NET 建立 Aztec 碼並進行辨識。本指南涵蓋在 .NET 應用程式中編碼、儲存及讀取
  Aztec 碼的方式。
linktitle: Aztec Code Text Encoding
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼
url: /zh-hant/net/aztec-barcode-encoding/aztec-code-text-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 進行 Aztec Code 文字編碼

## 介紹

準備好深入探索 **使用 Aspose.BarCode for .NET 建立 Aztec Code** 的精彩世界了嗎？在本完整指南中，我們將一步步說明如何 **建立 Aztec Code**、編碼自訂文字、儲存影像，並再次讀取。完成本教學後，您不僅能掌握技術步驟，還能了解為何此格式是現代應用中緊湊資料儲存的絕佳選擇。讓我們開始吧！

## 快速回答
- **本教學教什麼？** 如何在 .NET 中建立、儲存與辨識帶有文字編碼的 Aztec Code。  
- **需要哪個函式庫？** Aspose.BarCode for .NET。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **實作需要多久？** 基本範例約 10‑15 分鐘即可完成。

## 什麼是 Aztec Code？
Aztec Code 是一種二維條碼，能在緊湊的方形圖案中儲存大量資料。與 QR Code 不同的是，它不需要周圍的「靜止區」，因此特別適合空間受限的設計。

## 為什麼使用 Aspose.BarCode for .NET 來建立 Aztec Code？
- **完整控制** 編碼選項（字元集、錯誤更正、尺寸）。  
- **強韌辨識** 引擎，可從影像、串流或攝影機即時讀取 Aztec Code。  
- **跨平台** 支援 .NET Framework、.NET Core 以及 .NET 5/6。  
- **無外部相依** – 完全以受管理程式碼執行。

## 前置條件

在展開這段精彩旅程之前，您需要先具備以下條件：

1. Aspose.BarCode for .NET：請先安裝此功能強大的函式庫。文件可於 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 取得。  
2. Visual Studio：請在您的系統上安裝 Visual Studio，以建立與執行 .NET 應用程式。  
3. 基本的 C# 知識：熟悉 C# 程式語言會更有幫助，雖然我們會提供詳細說明，確保每位讀者都能跟上。

現在已說明完前置條件，接下來進入 Aztec Code 文字編碼的操作步驟。

## 匯入命名空間

首先，您需要匯入使用 Aspose.BarCode for .NET 所必須的命名空間。將以下程式碼加入 `.cs` 檔案的最上方：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## 如何使用 Aspose.BarCode for .NET 建立 Aztec Code

### 步驟 1：定義目錄路徑

設定要儲存產生之 Aztec Code 影像的路徑。將 `"Your Directory Path"` 替換為您想要的目錄路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：初始化 Aztec Code 產生器

建立 `BarcodeGenerator` 實例，將 `EncodeTypes` 設為 Aztec，並指定要編碼的文字。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Aspose常に先を行く");
```

### 步驟 3：設定條碼參數

配置條碼參數。本例中，我們將 XDimension 設為像素，並將 CodeTextEncoding 設為 UTF‑8。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.Aztec.CodeTextEncoding = Encoding.UTF8;
```

### 步驟 4：儲存 Aztec Code 影像

將產生的 Aztec Code 影像儲存至先前指定的目錄。

```csharp
gen.Save($"{path}AztecCodeTextEncoding.png", BarCodeImageFormat.Png);
```

### 步驟 5：辨識 Aztec Code

嘗試辨識剛剛建立的 Aztec Code。我們使用 `BarCodeReader` 完成此動作。

```csharp
BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.Aztec);
foreach (BarCodeResult result in read.ReadBarCodes())
    Console.WriteLine("AztecCodeTextEncoding:" + result.GetCodeText(Encoding.UTF8));
```

## 常見問題與技巧

- **檔案路徑問題** – 確認 `path` 變數以正確的目錄分隔符（`\` 或 `/`）結尾，符合您的作業系統。  
- **編碼不符** – 必須將 `CodeTextEncoding` 設為與來源文字相同的字元集，否則可能出現亂碼。  
- **授權例外** – 若未使用有效授權，產生的影像可能會帶有浮水印。

## 常見問答

### Q1：什麼是 Aztec Code？

A1：Aztec Code 是一種二維條碼格式，可編碼文字、URL 等多種資料類型。

### Q2：為什麼要使用 Aspose.BarCode for .NET？

A2：Aspose.BarCode for .NET 是功能強大的函式庫，能簡化 .NET 應用程式中條碼的建立與辨識，為您節省時間與精力。

### Q3：我可以使用 Aspose.BarCode for .NET 自訂 Aztec Code 的外觀嗎？

A3：可以，您能自訂 Aztec Code 的尺寸、顏色與編碼選項，以符合需求。

### Q4：Aspose.BarCode for .NET 有提供免費試用嗎？

A4：有，您可前往 [here](https://releases.aspose.com/) 取得免費試用版。

### Q5：我可以在哪裡取得支援或提問有關 Aspose.BarCode for .NET 的問題？

A5：可加入 Aspose.BarCode for .NET 社群，於支援論壇 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) 取得協助並分享經驗。

### Q6：我能從串流而非檔案讀取 Aztec Code 嗎？

A6：當然可以。`BarCodeReader` 也接受 `Stream` 物件，讓您從記憶體、網路或資料庫 Blob 讀取。

### Q7：如何變更 Aztec Code 的錯誤更正等級？

A7：使用 `gen.Parameters.Barcode.Aztec.ErrorCorrection` 設定所需等級（例如 `ErrorCorrectionLevel.L`、`M`、`Q`、`H`）。

## 結論

在本教學中，我們探討了使用 Aspose.BarCode for .NET 進行 **Aztec Code 文字編碼** 的精彩領域。從前置條件、匯入命名空間，到逐步 **建立 Aztec Code**、自訂外觀、儲存影像，再到再次辨識，我們已為您奠定將 Aztec Code 整合至 .NET 應用的堅實基礎，無論是庫存追蹤或安全資料傳輸，都能得心應手。

歡迎前往 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 深入了解更多進階功能與最佳實踐。祝開發順利！

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}