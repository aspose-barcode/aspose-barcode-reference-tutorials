---
date: 2026-01-04
description: 學習如何使用 Aspose.BarCode for .NET 產生帶有起始與終止字元的 Codabar 條碼。為開發者提供的逐步條碼生成教學。
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: 在 Aspose.BarCode for .NET 中產生帶有起始/終止字元的 Codabar 條碼
url: /zh-hant/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 產生帶有起始/終止字元的 Codabar 條碼

## 介紹

歡迎閱讀本完整指南，了解如何使用 Aspose.BarCode for .NET **產生 Codabar 條碼** 影像，並加入起始/終止字元。無論您是在建置零售庫存系統、實驗室樣本追蹤器，或是醫療紀錄解決方案，Codabar 都是一種可靠的數字條碼規格，必須明確的起始與終止符號才能正確掃描。接下來的幾分鐘，我們將從前置條件說明到最終 PNG 檔案的儲存，帶您一步步完成 Codabar 條碼的產生。

## 快速解答
- **需要哪個函式庫？** Aspose.BarCode for .NET  
- **條碼可以儲存為哪種格式？** PNG (BarCodeImageFormat.Png)  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **可以更改起始/終止符號嗎？** 可以 – 使用 CodabarSymbol.A、B、C 或 D。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 前置條件

在開始之前，請確保您已具備以下條件，以便順利跟隨本教學：

1. **環境設定** – 確保機器上已安裝可使用的 .NET 開發環境。如需指引，請參考[文件說明](https://reference.aspose.com/barcode/net/)。  
2. **Aspose.BarCode for .NET 函式庫** – 從官方[來源](https://releases.aspose.com/barcode/net/)下載並安裝。  
3. **基本 .NET 知識** – 熟悉 C# 與 Visual Studio（或其他喜好的 IDE）會讓步驟更順暢。  
4. **IDE** – Visual Studio、Rider 或 Visual Studio Code 都可。

現在已完成前置條件的說明，讓我們深入實作程式碼。

## 匯入命名空間

要開始使用 Aspose.BarCode for .NET，請先匯入必要的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

## 如何產生 Codabar 條碼 – 步驟指南

### 步驟 1：初始化 BarcodeGenerator

建立 `BarcodeGenerator` 實例，將 **Codabar** 設為編碼類型，並提供已包含起始/終止字元的資料字串（例如 “-12345-”）。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **專業提示：** 連字號（`-`）是 Codabar 的有效起始/終止符號之一。您也可以依需求使用 A、B、C 或 D。

### 步驟 2：設定 X‑Dimension（條碼元素寬度）

X‑Dimension 控制最窄條的寬度，請依掃描環境調整。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **為什麼重要：** 較大的 X‑Dimension 能提升低解析度印表機的可讀性；較小的數值則可在高密度標籤上節省空間。

### 步驟 3：定義起始與終止字元

Codabar 支援四種起始/終止符號（A、B、C、D）。以下分別示範每種設定方式，請選擇符合您系統規格的符號。

#### 設定 Start A 與 Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### 設定 Start B 與 Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### 設定 Start C 與 Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### 設定 Start D 與 Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

您可以針對需要的每種符號重複上述設定；以下範例會分別儲存四張圖片——每對起始/終止符號各一張。

### 步驟 4：儲存產生的條碼影像（PNG）

最後，將條碼寫入 PNG 檔案。此步驟示範 **save barcode png** 的使用情境，並為測試提供即時可用的資產。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

每個檔案現在皆包含對應起始/終止符號的 **Codabar 條碼範例**。

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 條碼顯示失真 | X‑Dimension 對於所選印表機解析度過低 | 增加 `XDimension.Pixels`（例如 3 或 4） |
| 掃描器無法讀取起始/終止字元 | 目標系統使用了錯誤的起始/終止符號 | 確認所需符號（A‑D）並正確設定 |
| PNG 檔案為空或損毀 | 輸出路徑無效或寫入權限不足 | 確保 `path` 指向已存在的資料夾且應用程式具備寫入權限 |

## 常見問答

### Q1：什麼是 Codabar，為什麼起始與終止字元很重要？

**A1：** Codabar 是一種廣泛應用於庫存、圖書館與醫療領域的數字條碼規格。起始與終止字元定義條碼的邊界，讓掃描器能正確辨識資料的起始與結束位置。

### Q2：我可以使用 Aspose.BarCode for .NET 自訂 Codabar 條碼的外觀嗎？

**A2：** 可以。除了 X‑Dimension，您還能調整顏色、加入邊距，甚至使用相同 API 將條碼嵌入 PDF 或 SVG 格式。

### Q3：Codabar 條碼在資料編碼方面有什麼限制嗎？

**A3：** Codabar 主要支援數字（0‑9）與少數特殊字元，不適合完整的英數字串。

### Q4：Aspose.BarCode for .NET 適合商業使用嗎？如何取得授權？

**A4：** 適合。此套件已具備生產環境可用的穩定性。您可於 [Aspose 的購買頁面](https://purchase.aspose.com/buy) 取得授權。

### Q5：我可以在哪裡尋求協助或討論 Aspose.BarCode for .NET 相關問題？

**A5：** 歡迎加入 [Aspose.BarCode for .NET 支援論壇](https://forum.aspose.com/c/barcode/13)，與 Aspose 工程師及其他開發者交流。

**最後更新：** 2026-01-04  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}