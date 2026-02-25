---
date: 2026-02-25
description: 在 **install Aspose.BarCode for .NET** 的同時，學習如何自訂 **databar stacked omnidirectional**
  的長寬比。精準的條碼設計變得輕鬆。
linktitle: One-Dimensional Databar Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 在 .NET 中自訂資料條堆疊式全向長寬比
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 自訂 .NET 中 databar stacked omnidirectional 長寬比

在條碼的世界裡，精準與客製化是達成理想結果的關鍵。在本教學中，你將學習如何使用 Aspose.BarCode for .NET **自訂 databar stacked omnidirectional 長寬比**。我們會把流程拆解成一步一步的說明，解釋每個設定的原因，並示範如何產生最終影像。現在就開始吧！

## 快速解答
- **我可以自訂什麼？** databar stacked omnidirectional 條碼的長寬比。  
- **需要哪個函式庫？** Aspose.BarCode for .NET（安裝 Aspose.BarCode for .NET）。  
- **X‑Dimension 可以設定多少像素？** 任意整數值；範例使用 2 像素。  
- **產生的影像儲存在哪裡？** 儲存於你透過 `path` 變數指定的資料夾。  
- **需要授權嗎？** 測試時可使用臨時授權；正式環境需購買正式授權。

## 什麼是 databar stacked omnidirectional？

`databar stacked omnidirectional` 是由 GS1 標準定義的一維條碼類型。它以緊湊且高密度的格式編碼數字資料，且可從任意方向讀取，非常適合小型商品與行動掃描。

## 為什麼要自訂長寬比？

調整 **長寬比** 可讓你控制寬度與高度之間的視覺平衡。當需要條碼符合特定標籤尺寸、符合品牌指引，或在受限的印刷條件下提升掃描可靠性時，這非常有用。

## 前置條件

在開始之前，請確保已具備以下項目：

### 1. 安裝 Aspose.BarCode for .NET  
你可以從官方網站 **[here](https://releases.aspose.com/barcode/net/)** 下載最新版本。依照安裝指南將 NuGet 套件加入你的專案。

### 2. 建立 .NET 專案  
簡單的 Console 或 Windows 應用程式即可。確保目標為 .NET 6+（或 .NET Framework 4.5+），以便函式庫無需額外設定即可運作。

### 3. 你的目錄路徑  
決定要將產生的 PNG 檔案儲存於何處，並記下絕對或相對路徑。

## 匯入命名空間

在開始自訂長寬比之前，先匯入所需的命名空間，以便存取 Aspose.BarCode 類別。

### Step 1: Import Aspose.BarCode Namespace

```csharp
using Aspose.BarCode;
```

現在你已準備好建立條碼產生器。

## databar stacked omnidirectional 長寬比設定

### Step 2: Initialize `BarcodeGenerator`

我們將建立一個 **databar stacked omnidirectional** 類型的產生器，並提供範例 GS1 資料字串。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarAspectRatio:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*提示：* 將 `"Your Directory Path"` 替換為實際的資料夾，例如 `@"C:\Barcodes\"`。

### Step 3: Set X‑Dimension Pixels

X‑Dimension 定義窄條的寬度。此範例使用 2 像素，你可以依印表機 DPI 調整此值。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Step 4: Customize DataBar Aspect Ratio

現在進入教學的核心——變更長寬比。

#### 4.1 Set Aspect Ratio to 15

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 15;
gen.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

條碼會以 **DatabarAspectRatio15.png** 儲存，呈現相對較高的外觀。

#### 4.2 Set Aspect Ratio to 30

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 30;
gen.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

將比例提升至 **30** 會使條碼變寬且變短，適用於寬標籤。

### Step 5: Verify the Output

使用任何影像檢視器開啟產生的 PNG 檔案。你會看到同一條碼的兩個版本，寬高比例不同。使用一般條碼掃描器掃描，確認仍可讀取。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| 條碼模糊 | X‑Dimension 對印表機 DPI 太低 | 增加 `XDimension.Pixels`（例如 3 或 4）。 |
| 掃描器無法讀取 | 長寬比過極端（例如 > 50） | 將比例維持在 10‑40 之間，以確保可靠掃描。 |
| 檔案未儲存 | `path` 字串無效 | 使用 `Path.Combine`，並確保資料夾已存在（`Directory.CreateDirectory`）。 |

## 常見問答

**Q: 條碼的長寬比是什麼，為什麼重要？**  
A: 長寬比是寬度與高度的比例。它會影響條碼在標籤上的適配程度，並可能影響掃描的可靠性。

**Q: 我可以使用 Aspose.BarCode for .NET 變更其他條碼類型的長寬比嗎？**  
A: 可以，許多一維與二維條碼皆提供 `AspectRatio` 屬性供微調。

**Q: 變更長寬比有什麼限制嗎？**  
A: 極端的數值可能違反編碼標準，使條碼無法讀取。請以目標掃描器進行測試。

**Q: 我在哪裡可以找到更多 Aspose.BarCode for .NET 的教學與範例？**  
A: 請參考官方 **[documentation](https://reference.aspose.com/barcode/net/)** 中的完整指南。

**Q: 如何取得 Aspose.BarCode for .NET 的臨時授權？**  
A: 你可以在 **[here](https://purchase.aspose.com/temporary-license/)** 申請試用授權。

## 結論

現在你已掌握如何使用 Aspose.BarCode for .NET **自訂 databar stacked omnidirectional 長寬比**。透過調整 `XDimension` 與 `DataBar.AspectRatio`，即可產生完全符合標籤尺寸、提升外觀一致性且保持掃描可靠性的條碼。可嘗試不同的比例，將程式碼整合至庫存或包裝流程中，盡情享受 Aspose 所提供的彈性。

如需更深入的資訊，請參閱完整的 **[documentation](https://reference.aspose.com/barcode/net/)**，或前往 **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** 加入社群。

---

**最後更新：** 2026-02-25  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}