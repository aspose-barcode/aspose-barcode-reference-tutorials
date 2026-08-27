---
date: 2026-05-24
description: 了解如何使用 Aspose.BarCode for .NET 建立含 Start/Stop Characters 的 codabar 條碼。為開發人員提供的逐步條碼生成教學。
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar Start/Stop Characters
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 在 Aspose.BarCode for .NET 中建立 Codabar 條碼（Start/Stop Characters）
url: /zh-hant/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.BarCode for .NET 中建立帶有起止字元的 Codabar 條碼

## 介紹

在本教學中，您將 **建立 codabar 條碼** 影像，包含明確的起止字元，使用 Aspose.BarCode for .NET。無論您是建構零售庫存系統、實驗室樣本追蹤器，或醫療紀錄解決方案，Codabar 的數字符號依賴這些邊界符號以確保可靠掃描。接下來的幾分鐘，我們將從環境設定到儲存 PNG 檔案全部說明，讓您立即開始產生 Codabar 條碼。

## 快速回答
- **需要什麼函式庫？** Aspose.BarCode for .NET  
- **可以將條碼儲存為哪種格式？** PNG (`BarCodeImageFormat.Png`)  
- **開發時需要授權嗎？** 免費試用可用於測試；商業授權則需於正式環境使用。  
- **可以更改起止符號嗎？** 可以 – 使用 `CodabarSymbol.A`, `B`, `C` 或 `D`。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7。

## 什麼是 Codabar 以及為何起止字元很重要？

Codabar 是一種廣泛應用於圖書館、醫療保健與庫存管理的數字條碼符號。起止字元（A‑D 或破折號）定義條碼的邊界，使掃描器能以 99.9 % 的讀取準確率偵測資料的起始與結束位置。

## 為什麼使用 Aspose.BarCode for .NET？

Aspose.BarCode 支援 **30+ 條碼符號**，且可產生最高 **10,000 × 10,000 px** 的影像，無需將整個文件載入記憶體。它可在 Windows、Linux 與 macOS 上執行，並相容於 .NET Framework、.NET Core 與 .NET 5+，為您在所有現代平台上提供彈性。

## 前置條件

1. **Environment Setup** – 確保 .NET 開發環境可正常運作。如需指引，請參考[文件](https://reference.aspose.com/barcode/net/)。  
2. **Aspose.BarCode for .NET Library** – 從官方[來源](https://releases.aspose.com/barcode/net/)下載並安裝函式庫。  
3. **Basic .NET Knowledge** – 熟悉 C# 以及 Visual Studio、Rider 或 VS Code 等 IDE。  
4. **IDE** – Visual Studio、Rider 或 Visual Studio Code 都可以。

現在我們已說明完前置條件，讓我們深入實作程式碼。

## 如何產生帶有起止字元的 Codabar 條碼？

載入 `BarcodeGenerator`，將編碼類型設定為 **Codabar**，並傳入已包含所需起止符號的資料字串（例如 “-12345-”）。接著設定 X‑Dimension，必要時選擇不同的起止符號，最後將影像儲存為 PNG。此端到端流程只需幾行 C# 程式碼即可產生可直接使用的條碼。

### 匯入命名空間

`BarcodeGenerator` 及相關型別位於 `Aspose.BarCode.Generation` 命名空間。

```csharp
using Aspose.BarCode.Generation;
```

### 步驟 1：初始化條碼產生器

`BarcodeGenerator` 是建立條碼影像的核心類別。建構子接受符號類型與資料字串兩個參數。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **專業提示：** 破折號（`-`）是 Codabar 的有效起止符號之一。您也可以根據應用需求使用 `A`、`B`、`C` 或 `D`。

### 步驟 2：設定 X‑Dimension（條碼元素寬度）

`XDimension` 控制最窄條的寬度。較大的數值可提升低解析度印表機的可讀性，較小的數值則可在高密度標籤上節省空間。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **為什麼重要：** 調整 `XDimension` 有助於符合掃描器規格，該規格通常要求最小條寬為 0.25 mm。

### 步驟 3：定義起止字元

Codabar 支援四種起止符號（A、B、C、D）。以下分別示範每種選項。請選擇符合您整合系統規範的符號。

#### 設定起始 A 與結束 A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### 設定起始 B 與結束 B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### 設定起始 C 與結束 C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### 設定起始 D 與結束 D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

您可以為每個需要的符號重複上述設定；以下範例會儲存四張獨立影像——每對起止符號各一張。

### 步驟 4：儲存產生的條碼影像（PNG）

`Save` 將條碼寫入檔案。使用 `BarCodeImageFormat.Png` 會產生無損的 PNG 影像，適合網頁與列印使用情境。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

每個檔案現在皆包含一個 **codabar 條碼範例**，並帶有相對應的起止符號。

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| 條碼顯示失真 | 對所選印表機解析度而言 X‑Dimension 設定過低 | 增加 `XDimension.Pixels`（例如調整為 3 或 4） |
| 掃描器無法讀取起止字元 | 目標系統的起止符號設定錯誤 | 確認所需的符號 (A‑D) 並相應設定 |
| PNG 檔案為空或損毀 | 輸出路徑無效或寫入權限不足 | 確保 `path` 指向已存在的資料夾且應用程式具有寫入權限 |

## 常見問答

**Q1: 什麼是 Codabar，為何起止字元重要？**  
A: Codabar 是一種用於庫存、圖書館與醫療保健的數字條碼符號。起止字元定義條碼的邊界，確保掃描器知道資料的起始與結束位置。

**Q2: 我可以使用 Aspose.BarCode for .NET 自訂 Codabar 條碼的外觀嗎？**  
A: 可以。除了 X‑Dimension，您還可以變更顏色、加入邊距，並使用相同 API 匯出為 PDF 或 SVG。

**Q3: Codabar 條碼在資料編碼方面有什麼限制？**  
A: Codabar 主要支援數字資料 (0‑9) 以及有限的特殊字元，不適合完整的字母數字字串。

**Q4: Aspose.BarCode for .NET 是否適合商業使用，如何取得授權？**  
A: 適合，且已具備生產環境可用性。可於[Aspose 的購買頁面](https://purchase.aspose.com/buy)取得授權。

**Q5: 我可以在哪裡尋求協助或討論 Aspose.BarCode for .NET 相關問題？**  
A: 加入[Aspose.BarCode for .NET 支援論壇](https://forum.aspose.com/c/barcode/13)，與 Aspose 工程師及其他開發者交流。

---

**最後更新：** 2026-05-24  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [Codabar 起止字元與校驗碼](/barcode/net/codabar-encoding-and-checksum/)
- [如何在 Aspose.BarCode for .NET 中為 Codabar 條碼加入校驗碼](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Aspose.BarCode for .NET 的完整教學與範例](/barcode/net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}