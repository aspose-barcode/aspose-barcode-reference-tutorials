---
category: general
date: 2026-08-22
description: 條碼產生器教學，示範如何產生條碼影像、驗證輸入，並在 C# 中使用 Aspose.BarCode 捕捉無效條碼例外。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- generate barcode image
- how to generate barcode
- invalid barcode example
- how to catch barcode
language: zh-hant
lastmod: 2026-08-22
og_description: 條碼產生器教學說明如何使用 Aspose.BarCode 在 C# 中產生條碼圖像、驗證資料，並捕捉條碼錯誤。
og_image_alt: barcode generator tutorial showing exception handling for invalid codes
og_title: 條碼產生器教學 – 在 C# 中捕捉無效代碼
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Barcode generator tutorial showing how to generate barcode image, validate
    input, and catch invalid barcode exceptions in C# with Aspose.BarCode.
  headline: 'Barcode generator tutorial: catch invalid codes in C#'
  type: TechArticle
tags:
- barcode
- C#
- exception‑handling
title: 條碼產生器教學：在 C# 中捕捉無效代碼
url: /zh-hant/python-java/general/barcode-generator-tutorial-catch-invalid-codes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器教學 – 捕捉 C# 中的無效代碼

如果您在尋找一篇 **條碼產生器教學**，不僅能產生條碼影像，還能保護應用程式免於不良輸入，那麼您來對地方了。本指南將帶您完整走過工作流程：安裝函式庫、設定驗證、產生影像，以及在代碼文字無效時處理例外。

產生條碼是物流、庫存與銷售點系統的常見需求。然而，將錯誤的字串傳入產生器可能會導致執行時錯誤或產生無法辨識的條碼。完成本教學後，您將了解 **如何安全產生條碼** 影像，並看到一個實作 **無效條碼範例** 以及正確的錯誤處理方式。

## 您需要的環境

- .NET 6.0（或任何較新的 .NET 版本）
- Visual Studio 2022 或其他 C# IDE
- **Aspose.BarCode for .NET** NuGet 套件  
  (`Install-Package Aspose.BarCode`)  
- 具備 C# 例外處理的基本知識

## 步驟 1：安裝並引用 Aspose.BarCode

在 Visual Studio 開啟您的專案，然後執行 NuGet 指令：

```powershell
Install-Package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，內含本教學中會使用的 `BarcodeGenerator` 類別。

## 步驟 2：建立一個帶有故意錯誤值的條碼產生器

**無效條碼範例** 的第一部分示範如何為 *Planet* 符號建立產生器，並使用違反規範的代碼。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Planet symbology – the string is too long and contains illegal characters
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
```

> **為什麼重要** – `EncodeTypes.Planet` 只接受特定長度的數字字串。傳入 `"1234567WRONG"` 會觸發函式庫內部的驗證邏輯。

## 步驟 3：啟用嚴格驗證，使函式庫拋出例外

預設情況下 Aspose.BarCode 會嘗試修正輕微錯誤。若要實作一個健全的 **如何捕捉條碼** 情境，應開啟明確的驗證：

```csharp
            // Step 3.1: Tell the generator to throw when the code text is incorrect
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;
```

> **說明** – 將 `ThrowExceptionWhenCodeTextIncorrect` 設為 `true` 會強制 API 在提供的文字不符合符號規則時拋出 `ArgumentException`。當您需要保證資料完整性時，這是建議的做法。

## 步驟 4：在 try‑catch 區塊中產生條碼影像

現在嘗試產生影像，並捕捉預期的錯誤：

```csharp
            try
            {
                // Step 4.1: Attempt to create the barcode image
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 4.2: Handle the validation error
                Console.WriteLine($"Planet error: {ex.Message}");
            }
```

**預期輸出**

```
Planet error: The code text is invalid for the selected symbology.
```

例外訊息證實函式庫正確偵測到問題。

## 步驟 5：對另一種符號（Postnet）重複相同流程

為了說明相同模式適用於任何條碼類型，我們以常見的郵政條碼 **Postnet** 重新執行步驟：

```csharp
            // Step 5.1: Create a Postnet generator with an invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                // Step 5.2: Attempt to generate the Postnet image
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 5.3: Capture the validation error
                Console.WriteLine($"Postnet error: {ex.Message}");
            }
        }
    }
}
```

**預期輸出**

```
Postnet error: The code text is invalid for the selected symbology.
```

兩個範例皆示範了 **如何產生條碼** 影像，同時安全處理格式錯誤的輸入。

## 步驟 6：儲存有效的條碼影像（可選）

若稍後提供正確的字串，您可以將產生的影像存檔：

```csharp
            // Valid example – generate and save a QR code
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
```

> **小技巧**：在將字串傳給 `BarcodeGenerator` 前務必先驗證。即使關閉 `ThrowExceptionWhenCodeTextIncorrect`，無效字串仍可能產生無法辨識的條碼。

## 常見陷阱與避免方式

| 陷阱 | 為什麼會發生 | 解決方法 |
|---------|----------------|-----|
| 將字母字元傳給僅接受數字的符號（例如 Planet、Postnet） | 除非啟用嚴格驗證，函式庫會靜默截斷或替換字元 | 設定 `ThrowExceptionWhenCodeTextIncorrect = true` |
| 忘記引用 `Aspose.BarCode` 命名空間 | 編譯時出現 “BarcodeGenerator does not exist” 錯誤 | 在檔案頂部加入 `using Aspose.BarCode.Generation;` |
| 使用過時的 NuGet 套件 | 可能缺少新符號或錯誤修正 | 定期更新套件 (`dotnet add package Aspose.BarCode --version x.x.x`) |

## 完整可執行範例

以下是完整程式碼，您可以直接複製、貼上並執行：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet – invalid code
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Planet error: {ex.Message}");
            }

            // Postnet – invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Postnet error: {ex.Message}");
            }

            // Valid QR code – optional saving
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
        }
    }
}
```

執行此程式會列印兩條無效條碼的錯誤訊息，並為有效的 QR 代碼產生 `qr.png` 檔案。

## 結論

本 **條碼產生器教學** 向您展示了如何 **產生條碼影像** 物件、強制嚴格驗證，並在 C# 中 **捕捉條碼** 相關例外。透過啟用 `ThrowExceptionWhenCodeTextIncorrect`，您可以將格式錯誤的輸入轉為可管理的錯誤，而非靜默失敗。

接下來您可以：

- 探索其他符號，如 Code128、EAN13 或 DataMatrix。
- 透過 `GeneratorParameters` 自訂顏色、尺寸與邊距。
- 將條碼產生整合至 ASP.NET Core API 或 Windows Forms 應用程式。

記得在呼叫 `GenerateBarCodeImage` 之前 **先驗證輸入**，這是確保系統可靠、掃描無誤的最佳方式。祝您開發順利！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，提供完整的程式碼範例與逐步說明，協助您掌握更多 API 功能並在專案中探索其他實作方式。

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}