---
category: general
date: 2026-10-24
description: 學習如何在 ASP.NET 中使用 Aspose.BarCode 建立 GS1 條碼。一步一步的指南，從字串產生條碼並渲染為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: zh-hant
lastmod: 2026-10-24
og_description: 如何在 ASP.NET 中使用 Aspose.BarCode 建立 GS1 條碼。跟隨本教學從字串生成條碼、設定視覺設定，並儲存 PNG
  檔案。
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: 如何在 ASP.NET 中建立 GS1 條碼 – 完整 Aspose 指南
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: 如何在 ASP.NET 中使用 Aspose.BarCode 建立 GS1 條碼
url: /zh-hant/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 ASP.NET 中使用 Aspose.BarCode 建立 GS1 條碼

如果你需要在 ASP.NET 應用程式中 **建立 GS1 條碼**，本指南會向你展示完整步驟。你將會看到如何從字串產生條碼、設定視覺外觀，並將結果儲存為 PNG 圖片。

建立 GS1 條碼不需要自訂編碼邏輯。使用 Aspose.BarCode 可獲得可靠、符合標準的解決方案，支援 .NET 6+ 以及較早的框架。本教學涵蓋從專案設定到驗證輸出的一切，你可以直接將程式碼複製到自己的 Web 專案中。

## 前置條件

* Visual Studio 2022（或任何支援 .NET 的 IDE）
* .NET 6 SDK（或 .NET Framework 4.7.2 及以上版本）
* 具備 ASP.NET Core 或 ASP.NET Framework 的基本知識
* Aspose.BarCode 授權（免費評估版可用於測試）

不需要額外的第三方函式庫，因為 Aspose.BarCode 會在內部處理所有編碼與呈現。

## 步驟 1：建立新的 ASP.NET 專案

在 Visual Studio 開啟並建立一個 **ASP.NET Core Web App**（選擇 *Empty* 範本）。對於傳統的 Web Forms 專案，相同程式碼可放在 code‑behind 檔案中使用。

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

執行專案後，瀏覽器應顯示 *GS1 barcode generator is ready.*，此訊息證明 Web 主機已正常運作。

## 步驟 2：透過 NuGet 安裝 Aspose.BarCode

開啟 **Package Manager Console** 並執行以下指令：

```powershell
Install-Package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode.Generation` 命名空間，內含你將用來 **從字串產生條碼** 的 `BarcodeGenerator` 類別。NuGet 指令同時會在專案檔中加入必要的參考。

## 步驟 3：從字串產生簡易條碼

為說明基本用法，建立一個回傳 PNG 位元組陣列的輔助方法。此方法可在控制器、Razor 頁面或任何端點中呼叫。

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

現在你可以在任何端點呼叫 `GenerateBarcode("HelloWorld", EncodeTypes.Code128)`，並將產生的位元組寫入 HTTP 回應。這展示了 **barcode generator asp.net** 的範例，用於任意字串。

## 步驟 4：建立 GS1 條碼 – Micro PDF417 範例

GS1 條碼會嵌入應用程式識別碼 (AI) 以傳遞產品資訊。Aspose.BarCode 支援符合 GS1 標準的 Micro PDF417 變體，非常適合緊湊的資料表示。

### 4.1 準備 GS1 資料字串

GS1 資料必須以括號包住 AI 代碼。以產品識別碼 (01) 與批號 (10) 為例，字串如下：

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

括號是標準的一部份；Aspose.BarCode 會自動解析。

### 4.2 建立 GS1 Micro PDF417 產生器

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 透過 ASP.NET 端點公開產生器

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

存取 `https://localhost:5001/gs1barcode` 後，即會串流產生的 PNG。圖像符合 GS1 規範，且檔案亦會儲存至磁碟以供日後使用。

## 步驟 5：呈現其他條碼類型

相同的 **create barcode with aspose** 方法也適用於其他條碼類型。以下是一個快速範例，從 URL 產生 QR Code：

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

你可以將 `EncodeTypes.QR` 替換為 `EncodeTypes.Code128`、`EncodeTypes.DataMatrix` 或其他支援的類型。視覺參數（`XDimension`、`Resolution`、`Color`）可透過 `Parameters` 物件進行設定。

## 步驟 6：常見問題與最佳實踐建議

| 問題 | 發生原因 | 避免方式 |
|-------|----------------|-----------------|
| **AI 格式不正確** | 缺少括號或 AI 長度錯誤會導致編碼錯誤。 | 務必依照標準精確組合 GS1 字串。建議使用輔助方法來串接 AI。 |
| **欄位數過多** | Micro PDF417 只支援 1‑4 欄，設定為 5 會拋出例外。 | 在指派前先驗證欄位值：`if (columns < 1 || columns > 4) throw …` |
| **影像解析度過低** | `XDimension` 值過小會導致條碼在印表機上無法辨識。 | 列印用條碼請提升 `Resolution`（例如 `generator.Parameters.Image.Resolution = 300`）。 |
| **Linux 上的檔案路徑問題** | 硬編碼的反斜線在非 Windows 主機上會失效。 | 使用 `Path.Combine` 來組合檔案路徑，會自動處理作業系統的分隔符號。 |
| **未套用授權** | 免費評估版會在 30 天後加上浮水印。 | 請盡早套用授權：`new License().SetLicense("Aspose.BarCode.lic");` |

## 步驟 7：驗證產生的條碼

執行端點後，使用任意圖像檢視器開啟 PNG。為確認 GS1 資料正確編碼，你可以使用支援 GS1 Micro PDF417 的免費手機掃描器（許多條碼掃描應用都有此支援）。掃描圖像後，應會回傳：

```
(01)12345678901234
(10)ABCD
```

若掃描器回報錯誤，請再次檢查 AI 格式與欄位數。

## 結論

現在你已了解如何在 ASP.NET 環境中使用 Aspose.BarCode **建立 GS1 條碼**。本教學涵蓋了：

* 建立 ASP.NET 專案並安裝 Aspose.BarCode NuGet 套件。  
* 使用 **generate barcode from string** 產生一般條碼。  
* 實作 **create barcode with aspose** 以產生符合 GS1 的 Micro PDF417 圖像。  
* 將圖像儲存至磁碟，並透過 HTTP 端點串流。  

接下來你可以探索其他 GS1 符號（例如 GS1 DataMatrix），或將產生器整合至更大的訂單處理工作流程。可嘗試不同的 `XDimension`、顏色與錯誤更正等級，以符合品牌與掃描環境需求。

祝開發愉快，讓你的應用程式說出條碼的通用語言！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在已示範的技巧之上。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立帶 GS1 的 Code 128 條碼](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [如何使用 Aspose.BarCode for .NET 建立 ITF-14 條碼的靜默區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [如何建立 ITF-14 條碼（.NET）– 完整 Aspose.BarCode 教學](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}