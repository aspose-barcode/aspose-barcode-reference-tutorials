---
category: general
date: 2026-07-18
description: 使用 C# 快速產生 PDF417 條碼。學習如何生成條碼、設定參數及儲存影像檔案——包含 AI 10 處理。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: zh-hant
lastmod: 2026-07-18
og_description: 在 C# 中建立 PDF417 條碼，完整教學。了解如何產生條碼、調整設定、儲存影像，同時處理 AI 10。
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: 在 C# 中建立 PDF417 條碼 – 快速、彈性、完整程式碼範例
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: 在 C# 中建立 PDF417 條碼 – 完整逐步指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 PDF417 條碼 – 完整步驟指南

是否曾需要**建立 pdf417 條碼**，卻不確定該選擇哪個函式庫或設定？您並不孤單——許多開發者在首次嘗試 GS1‑Micro‑PDF417 時都會碰到這個問題。好消息是，只要幾行 C# 程式碼，就能產生格式正確的條碼，調整外觀，並直接將影像寫入磁碟。

在本教學中，我們將示範如何使用 Aspose.BarCode 函式庫**產生條碼**，說明如何**設定參數**（如 X‑dimension 與欄位數），以及展示如何**儲存影像**檔案，支援 AI 10 與 AI 21 兩種變體。完成後，您將擁有可重複使用的程式碼片段，能直接嵌入任何 .NET 專案。

## 前置條件

在深入之前，請確保您已具備以下條件：

- .NET 6+ 或 .NET Framework 4.7.2（任何近期的執行環境皆可）
- Visual Studio 2022 或您喜愛的 C# 編輯器
- **Aspose.BarCode for .NET** NuGet 套件（`Install-Package Aspose.BarCode`）
- 一個可寫入的磁碟資料夾，用於存放 PNG 檔案

就這樣——不需要額外工具，也不需複雜設定。準備好了嗎？讓我們開始吧。

## 步驟 1：使用 GS1‑Micro 格式建立 PDF417 條碼

首先，我們會**建立 pdf417 條碼**物件，並提供初始的 AI 資料。於 GS1‑Micro‑PDF417 中，AI 10（批號/批次號）通常是起始點，因此我們會立即對其進行編碼。

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **為何重要：** `EncodeTypes.GS1MicroPdf417` 讓函式庫遵循 GS1‑Micro 規範，會自動在 AI 前加上方括號。若省略此設定，產生的將是一般 PDF417，可能在零售環境中無法掃描。

## 步驟 2：設定條碼參數

現在我們已有條碼實例，需要微調其視覺特性。這正是**設定參數**的環節。我們將調整三個常見設定：

1. **X‑dimension** – 控制最小條寬（以像素為單位）
2. **Column count** – 影響整體形狀；欄位較少會使條碼較高
3. **IsLinked** – 啟用可選的連結模組，將條碼與資料字串關聯

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **專業提示：** 若目標是手機掃描，建議將 X‑dimension 提升至 3‑4 像素；較大的模組在低解析度相機下更易辨識。

## 步驟 3：儲存影像 – 第一版（AI 10）

設定好產生器後，我們終於可以**儲存影像**。`Save` 方法會依指定的格式將條碼寫入檔案。此處使用 PNG，因為它能保留清晰的邊緣且不產生壓縮雜訊。

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

此時，您應該會在 `outputDir` 中看到名為 `GS1MicroPdf417_AI10.png` 的檔案。使用任何影像檢視器開啟，即可看到乾淨且高對比度的 PDF417，已可直接列印。

## 步驟 4：切換至不同的 AI（AI 21）並再次儲存

通常您需要編碼不同的應用識別碼，例如 AI 21（序號）。只需變更 `CodeText` 屬性即可。此範例同時示範了 **barcode ai 10** 與 **barcode ai 21** 的處理方式。

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **如果需要更多 AI 呢？** 只要在同一字串中串接即可，例如 `"(10)ABCD(21)12345(240)XYZ"`。函式庫會自動解析括號。

## 完整範例程式

將上述步驟整合起來，以下是一個可直接貼入 Console 應用程式的完整範例：

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**預期輸出：** 兩個 PNG 檔案會出現在 `C:\Barcodes\`——`GS1MicroPdf417_AI10.png` 與 `GS1MicroPdf417_AI21.png`。兩者皆為可掃描的 PDF417；前者編碼 AI 10，後者編碼 AI 21。

## 常見陷阱與避免方法

- **缺少資料夾權限：** 若 `Save` 拋出 `UnauthorizedAccessException`，請再次確認路徑是否存在且應用程式具備寫入權限。
- **AI 格式不正確：** 忘記加上括號（`(10)`）會導致條碼被視為純資料，進而破壞 GS1 驗證。
- **X‑dimension 設定過小：** 條寬小於 1 像素的條碼在影像縮放時可能會消失。螢幕顯示時至少使用 2 像素。

## 往後步驟與相關主題

既然您已了解**產生條碼**、**設定參數**以及**儲存影像**的方式，接下來可以探索以下主題：

- 在條碼下方加入**可讀文字** (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- 匯出為**PDF** 而非 PNG (`BarCodeImageFormat.Pdf`)
- 將條碼產生整合至 **ASP.NET Core API**，即時產生影像

上述每個主題皆直接建立在本指南的基礎上。

---

### 快速回顧

- **建立 pdf417 條碼**：使用 `BarcodeGenerator` 並搭配 `EncodeTypes.GS1MicroPdf417`
- **設定參數**：如 X‑dimension、欄位數與連結屬性
- **儲存影像**：以 PNG 格式產生 AI 10 與 AI 21 兩種變體
- 已處理 **barcode ai 10**，並透過單一屬性變更切換至 **barcode ai 21**

試著執行、微調設定，您就會擁有可投入生產的強大條碼引擎。如有任何問題或需要更深入的說明，歡迎在下方留言——祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以示範的技術為基礎。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼靜區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [如何在 .NET 中建立具錯誤更正的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}