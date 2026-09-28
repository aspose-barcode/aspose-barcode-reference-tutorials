---
category: general
date: 2026-07-18
description: 使用 Aspose.BarCode 於 C# 建立 GS1 條碼圖像，提供逐步指南教您如何產生條碼 C# —— 無廢話，僅提供可執行程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: zh-hant
lastmod: 2026-07-18
og_description: 使用此簡明教學在 C# 中建立 GS1 條碼圖像。學習如何使用 Aspose.BarCode 於 C# 產生條碼，並在數秒內儲存為
  PNG 檔案。
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: 在 C# 中建立 GS1 條碼圖像 – 完整操作指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: 在 C# 中建立 GS1 條碼圖像 – 如何快速生成條碼
url: /zh-hant/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 GS1 條碼圖像 – 如何產生條碼 C#

是否曾需要為包裝標籤 **建立 gs1 條碼圖像**，卻不知從何開始？您並不孤單。在本教學中，您將看到 **如何產生 barcode c#** 程式碼，能在幾分鐘內產生 GS1‑MicroPDF417 圖像。

我們將逐步說明整個流程——安裝函式庫、設定產生器、交換 AI（應用程式識別碼）資料，最後儲存一組 PNG 檔案。完成後，您將擁有一個可直接執行的主控台應用程式，能產出多張 GS1 條碼圖像，每張皆反映不同的 AI 組合。

---

## 您需要的條件

- **.NET 6+**（或 .NET Framework 4.6+）。最新的執行環境與 Aspose.BarCode 相容性最佳。
- **Aspose.BarCode for .NET** – 透過 NuGet 安裝（`Install-Package Aspose.BarCode`）。
- 磁碟上的資料夾，用於寫入 PNG 檔案（我們稱之為 `YOUR_DIRECTORY`）。
- 基本的 C# 語法概念——不需要任何進階知識。

如果您已具備上述條件，太好了。若尚未安裝，請先取得 NuGet 套件；只需在套件管理員主控台輸入一行指令，即可自動處理所有相依性。

## 步驟 1：建立最小化的主控台專案

在您喜愛的 IDE（Visual Studio、Rider 或 VS Code）中開啟，並建立一個新的主控台專案：

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

將自動產生的 `Program.cs` 替換為下一步所示的程式碼。此骨架提供乾淨的起點，讓我們能 **建立 gs1 條碼圖像** 而不受多餘雜訊干擾。

## 步驟 2：如何建立 gs1 條碼圖像 – 初始化產生器

此操作的核心是 `BarcodeGenerator`。我們將以初始的 GS1‑MicroPDF417 值啟動它，例如 `(17)991231(10)ABCD`。此字串編碼了兩個 AI：有效日期 (17) 與批次/批號 (10)。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**為什麼這很重要：** `EncodeTypes.GS1MicroPdf417` 告訴 Aspose 我們使用的是緊湊且高密度的 GS1 格式。以有效的 AI 字串作為起點，可確保第一個儲存的 PNG 已符合 GS1 標準。

## 步驟 3：調整視覺參數 – 微調尺寸與版面配置

過小或形狀不規則的條碼無法被掃描。此處我們將 X‑dimension（模組寬度）設定為 2 像素，限制欄位數以保持圖像窄幅，並啟用連結功能，以便日後需要時可將多個條碼串接。

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**小技巧：** 若需要較高的條碼，請增加 `Rows` 而非欄位。調整 `XDimension` 以符合大多數掃描器要求的最小 0.33 mm 模組尺寸。

## 步驟 4：儲存第一個條碼 – AI 17 + AI 10

現在我們實際將圖像寫入磁碟。檔名會反映所使用的 AI，方便日後查找。

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

執行程式後，您應該會在 `YOUR_DIRECTORY` 中看到一個清晰的 PNG。打開它，您會看到細小的條紋以及下方的可讀文字。這就是我們將產生的第一張 **gs1 條碼圖像**。

## 步驟 5：變更編碼資料 – 重複使用相同的產生器

與其為每組 AI 建立新的 `BarcodeGenerator`，我們只需交換 `CodeText` 屬性並再次呼叫 `Save`。此方法是大量 **建立 gs1 條碼圖像** 最有效的方式。

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**為什麼要重複使用？** 更改 `CodeText` 可避免重新實例化產生器的開銷，並確保所有圖像的視覺設定保持一致。

## 步驟 6：執行、驗證與微調

編譯並執行：

```bash
dotnet run
```

現在您應該會有五個 PNG 檔案，每個檔名皆以其所含的 AI 組合命名。使用圖像檢視器開啟任一檔案，即可看到條碼及其下方的編碼文字。為了再次確認資料正確性，可在手機上使用免費的 GS1 掃描應用程式——對準螢幕上的 PNG，即可顯示 AI 值。

### 常見問題與避免方法

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 條碼無法讀取 | `XDimension` 太低（例如 1 像素） | 提升至 2 或 3 像素 |
| 缺少 AI 括號 | `CodeText` 格式不正確 | 務必將每個 AI 包在括號內 |
| 圖像過大 | 欄位或列過多 | 減少 `Columns` 或讓 Aspose 自動調整大小 |
| 執行時錯誤 `EncodeTypes` 未找到 | 缺少 `using Aspose.BarCode.Generation` | 加入缺少的 `using` 指令 |

## 步驟 7：擴充範例 – 產生更多 AI 組合

如果您需要為數十種產品變體 **建立 gs1 條碼圖像**，可考慮從 CSV 檔案載入 AI 組合：

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

## 結論

您現在擁有一個完整、可直接執行的 C# 程式，能 **建立 gs1 條碼圖像** 以應對多種 AI 情境，示範了使用 Aspose.BarCode **如何產生 barcode c#** 的最簡單方法。透過重複使用單一 `BarcodeGenerator` 實例、微調視覺參數，並交換 `CodeText`，即可產出任意數量符合 GS1‑MicroPDF417 標準的 PNG，滿足專案需求。

接下來可以嘗試加入顏色（`barcodeGen.Parameters.Barcode.ForeColor`）、將條碼嵌入 PDF，或改用其他 GS1 符號如 DataMatrix。相同的流程仍適用——初始化、設定、指定 `CodeText`，然後儲存。

如果遇到任何問題，歡迎留下評論，或分享您的變化版本。祝編程愉快，願您的掃描永遠順利！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，建立在所示技術之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼靜止區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼靜止區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [如何產生條碼 – 使用 Aspose.BarCode 的 Code 39 設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}