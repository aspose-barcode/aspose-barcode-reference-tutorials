---
date: 2026-03-02
description: 學習如何使用 Aspose.BarCode for .NET 產生條碼，包括條碼產生的 Visual Studio 小技巧，這是一篇關於寬窄比例設定的逐步指南。
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: 如何產生條碼 – 寬窄比例設定
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一維寬窄比例設定

您是否想要在 .NET 應用程式中輕鬆 **how to generate barcode**？Aspose.BarCode for .NET 讓條碼產生在 Visual Studio 專案中變得簡單且功能強大。在本教學中，我們將示範如何使用自訂寬窄比例建立一維條碼，說明比例的重要性，並展示如何針對不同掃描環境進行調整。

## Quick Answers
- **What does the wide‑narrow ratio control?** 它定義了 1D 條碼中「寬」條與「窄」條的相對寬度。  
- **Which barcode type is used in the example?** Code 39 Extended，是一種常用於字母數字資料的符號。  
- **Can I change the ratio at runtime?** 可以 – 只需在儲存前將 `gen.Parameters.Barcode.WideNarrowRatio` 設為所需的值。  
- **Do I need a license for this feature?** 寬窄比例在免費試用版中即可使用；完整授權可解鎖所有渲染選項。  
- **Is this compatible with .NET Core?** 當然 – Aspose.BarCode 支援 .NET Framework、.NET Core，以及 .NET 5/6+。

## What is a Wide‑Narrow Ratio?
在一維條碼中，每條條碼要麼是「寬」要麼是「窄」。比例（例如 2 或 5）決定寬條相對於窄條的寬度倍數。調整此比例可提升低解析度印表機或掃描器的可讀性。

## Why Use Aspose.BarCode for .NET?
* **Full control** – 包括寬窄比例在內的所有視覺層面皆可透過程式碼設定。  
* **Cross‑platform** – 可在 Visual Studio、Visual Studio Code 以及任何 .NET 執行環境中運作。  
* **No external dependencies** – 無需原生 DLL 或第三方工具。  
* **Rich documentation and support** – 包含範例、論壇與快速入門指南。

## Prerequisites

在深入了解使用 Aspose.BarCode for .NET 的條碼世界之前，您需要先具備以下先決條件：

### 1. Visual Studio 環境
- 確保您的系統已安裝 Visual Studio，以便開發 .NET 應用程式。

### 2. Aspose.BarCode for .NET 函式庫
- 必須已安裝 Aspose.BarCode for .NET 函式庫。您可從 [website](https://releases.aspose.com/barcode/net/) 下載。

### 3. 授權金鑰（可選）
- 若您擁有授權金鑰，可用於解鎖函式庫的額外功能。您可從 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

現在您已具備先決條件，讓我們開始使用 Aspose.BarCode for .NET 建立具有寬窄比例設定的一維條碼。

## Import Namespaces

首先，您需要在專案中加入必要的命名空間，以存取 Aspose.BarCode for .NET 的功能。您可以在程式碼頂部加入以下 using 陳述式：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Step 1: Define Your Directory Path

首先定義您想儲存產生的條碼影像的路徑。您可以使用以下程式碼：

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您實際想儲存條碼影像的目錄路徑。

## Step 2: Create a One‑Dimensional Wide‑Narrow Ratio Barcode

現在，讓我們使用 Aspose.BarCode for .NET 建立具有寬窄比例設定的一維條碼。在此範例中，我們將使用 Code39Extended 編碼類型，並將資料設定為 `"ASPOSE"`：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

此程式碼行會以指定的編碼類型與資料初始化條碼產生器。

## Step 3: Set Wide/Narrow Ratio

寬窄比例決定條碼中寬與窄元素的比例。在此步驟中，我們將寬窄比例設定為 **2**：

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

接著，我們將產生的條碼影像儲存至指定路徑：

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Step 4: Adjust Wide‑Narrow Ratio

您可以嘗試不同的寬窄比例，以獲得理想的條碼外觀。例如，若想要較寬的條碼，將寬窄比例設定為 **5**：

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

然後儲存條碼影像：

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

現在，您已成功使用 Aspose.BarCode for .NET 建立具有不同寬窄比例的一維條碼。此函式庫提供彈性，讓您能依特定需求產生條碼。

## Common Issues and Solutions
- **Image not saved** – 請確認 `path` 變數指向已存在的資料夾，且應用程式具備寫入權限。  
- **Barcode appears distorted** – 在低解析度印表機上可嘗試較低的比例（例如 2）；較高比例可能導致列印瑕疵。  
- **Unsupported characters** – Code 39 Extended 支援完整 ASCII 集合；請確保資料字串未包含禁止的控制字元。

## Conclusion

Aspose.BarCode for .NET 是一個多功能的函式庫，可簡化您在 .NET 應用程式中的條碼產生與自訂。在本教學中，我們介紹了建立具有寬窄比例設定的一維條碼的基礎。透過微調各種參數，您可以產生完全符合需求的條碼，無論是於桌面應用程式中構建 **how to generate barcode** 功能，或是 **barcode generation visual studio** 服務。

## Frequently Asked Questions

### 1. 如何取得 Aspose.BarCode for .NET 的授權？
您可以從 [Aspose website](https://purchase.aspose.com/buy) 購買授權。

### 2. 我可以在沒有授權的情況下使用 Aspose.BarCode for .NET 嗎？
可以，您可以使用臨時授權，雖然功能有限。

### 3. Aspose.BarCode for .NET 相容於 .NET Core 嗎？
是的，Aspose.BarCode for .NET 相容於 .NET Core 與 .NET Framework。

### 4. 我可以產生的條碼類型有什麼限制嗎？
Aspose.BarCode for .NET 支援廣泛的條碼符號，包括 QR Code、Code 39 等多種。

### 5. 我該如何取得支援或詢問有關 Aspose.BarCode for .NET 的問題？
您可前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得支援與討論。

### Additional Q&A

**Q: 改變寬窄比例會影響掃描速度嗎？**  
**A:** 較高的比例會使條線變粗，可能提升低品質掃描器的可讀性，但會稍微增加掃描器處理的資料量。

**Q: 我可以為其他符號（如 Code128）設定比例嗎？**  
**A:** 可以，`WideNarrowRatio` 屬性適用於所有支援寬窄元素的 1D 符號。

---

**最後更新：** 2026-03-02  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}