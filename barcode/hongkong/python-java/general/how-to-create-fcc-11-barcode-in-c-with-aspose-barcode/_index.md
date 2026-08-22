---
category: general
date: 2026-08-22
description: 使用 Aspose.BarCode 在 C# 中建立 FCC 11 條碼。學習逐步程式碼、設定尺寸，並為澳洲郵政產生 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: zh-hant
lastmod: 2026-08-22
og_description: 使用 C# 及 Aspose.BarCode 建立 FCC 11 條碼。請參考本簡明教學，產生澳洲郵政的 PNG 條碼，包括 FCC
  59 與 FCC 62 變體。
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: 在 C# 中建立 FCC 11 條碼 – 完整 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: 如何在 C# 中使用 Aspose.BarCode 建立 FCC 11 條碼
url: /zh-hant/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立 FCC 11 條碼

如果您需要在 .NET 應用程式中 **建立 FCC 11 條碼**，本教學將示範完整程式碼。您將了解如何設定條碼尺寸、選擇正確的編碼表，並將結果儲存為 PNG 檔案。

產生 Australia Post 條碼是物流、郵寄系統與庫存追蹤的常見需求。本教學涵蓋 FCC 11 格式，並示範如何使用不同的編碼表產生 FCC 59 與 FCC 62 條碼，讓您可以將相同模式套用於其他郵政服務。

## 您需要的環境

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 C# 的 IDE）  
* 有效的 **Aspose.BarCode for .NET** 授權 – 社群版可用於評估  
* 具寫入權限的資料夾，用於儲存 PNG 檔案  

上述前置條件可確保程式碼能順利編譯與執行，無需額外設定。

## 第一步：安裝 Aspose.BarCode NuGet 套件

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新穩定版的函式庫加入您的專案檔案。套件內含本教學中會使用的 `BarcodeGenerator` 類別。

## 第二步：定義輸出資料夾

建立一個用來存放產生圖像的資料夾。路徑可以是絕對路徑或相對於執行檔的路徑。

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` 會確保資料夾已存在，避免在 `Save` 方法寫入檔案時發生執行時錯誤。

## 第三步：產生 FCC 11 條碼

FCC 11 格式是 Australia Post 郵件條碼的預設編碼。以下程式碼會產生編碼為數字字串 `1101234567` 的條碼。

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**為什麼這樣寫會成功：**  
* `EncodeTypes.AustraliaPost` 告訴函式庫套用 Australia Post 的編碼規則。  
* 資料字串 `1101234567` 符合 FCC 11 規範：前兩位數字 (`11`) 表示格式，其後 7 位為客戶參考號碼。  
* `XDimension` 與 `BarHeight` 控制條碼的印刷尺寸，對掃描器的可讀性相當重要。  

執行程式後，您會在 `Barcodes` 資料夾中看到 `PostalAustraliaPostFCC11.png`。圖像如下：

![建立 FCC 11 條碼範例](https://example.com/fcc11.png "由 Aspose.BarCode 產生的 FCC 11 條碼")

## 第四步：建立其他 Australia Post 條碼（可選）

雖然主要目標是 **建立 FCC 11 條碼**，但在不同郵件類別下，您可能還需要 FCC 59 或 FCC 62 條碼。以下程式碼重複使用同一個 `BarcodeGenerator` 實例，只變更資料字串與可選的編碼表。

### 4.1 使用 N‑Table 編碼的 FCC 59

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 使用 N‑Table 編碼的 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 使用 C‑Table 編碼的 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 使用其他編碼的 FCC 62

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

四張圖像會全部儲存在同一資料夾中，方便您比較視覺差異。

## 第五步：了解編碼表

Australia Post 定義了三種編碼表：

* **N‑Table** – 解析純數字的客戶資訊。當資料僅包含數字時使用。  
* **C‑Table** – 支援英數字元，適用於包含字母的參考編號。  
* **Other** – 為自訂或擴充資料格式的備援方案。

選擇正確的編碼表可確保條碼掃描器正確解碼資訊。若未設定 `AustralianPostEncodingTable` 屬性，函式庫預設使用 N‑Table，可能會截斷非數字字元。

## 小技巧、邊緣案例與常見陷阱

| 情境 | 建議做法 |
|-----------|----------------------|
| 資料字串長度不足 | 在數字部分前方補零，以符合 FCC 規範。 |
| 印刷出的條碼模糊 | 將 `XDimension` 提升至 5 或 6 像素，並檢查印表機的 DPI 設定。 |
| 掃描器回傳「格式無效」 | 確認使用的編碼表（N‑Table、C‑Table、Other）與資料內容相符。 |
| 在沒有 GUI 的 Linux 上執行 | 確認已引用 `System.Drawing.Common` 套件，或使用 `Save` 方法搭配 `BarCodeImageFormat.Png`，此方式不需要顯示環境。 |
| 需要其他影像格式 | 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Tiff` 即可。 |

以上實務技巧皆來自真實的郵件條碼部署經驗。

## 完整可執行範例

以下是一個獨立的程式，您可以直接複製到新建的 Console 專案（`dotnet new console`）中執行，無需額外修改。



## 接下來您可以學習什麼？

以下教學與本篇內容緊密相關，能進一步深化您對本指南所示技術的掌握。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您在專案中探索更多 API 功能與替代實作方式。

- [如何在 Java 中產生 Australia Post 條碼 – 使用 Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [使用 Aspose.BarCode 建立一維 Databar GS1 編碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [如何在 .NET 中為 Code 16K 條碼設定靜默區 (quiet zone) – 使用 Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}