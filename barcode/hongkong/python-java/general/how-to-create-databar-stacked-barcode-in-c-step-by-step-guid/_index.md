---
category: general
date: 2026-10-21
description: 使用 C# 快速建立 DataBar 堆疊條碼。於本完整教學中學習設定 X 尺寸、調整長寬比，並儲存 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: zh-hant
lastmod: 2026-10-21
og_description: 使用 C# 及 Aspose.BarCode 建立 DataBar 堆疊條碼。請參考本指南設定 X 尺寸、調整長寬比，並匯出 PNG
  檔案。
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: 在 C# 中建立 Databar 堆疊條碼 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: 如何在 C# 中建立 DataBar 堆疊條碼 – 逐步指南
url: /zh-hant/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 databar stacked barcode – 步驟指南

如果您需要在 .NET 應用程式中**建立 databar stacked barcode**，本指南將逐步說明。您將學會如何設定 X‑dimension、變更長寬比，並將條碼儲存為 PNG 檔案。

產生 DataBar 堆疊條碼並不需要複雜的建置流程。本教學涵蓋您所需的一切：必備套件、逐行程式碼說明，以及常見陷阱的提示。完成後，您即可在單一方法中產生多張不同長寬比的條碼圖像。

## 您需要的條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 C# 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 套件 – 提供 `BarcodeGenerator` 與 `EncodeTypes` 的函式庫  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：設定專案並匯入命名空間

建立一個新的主控台專案，或將程式碼加入現有專案。匯入必要的命名空間，讓編譯器能辨識條碼相關類別。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些 `using` 陳述式會公開 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat`，供範例稍後使用。

## 第二步：定義輸出資料夾

選擇一個資料夾來寫入產生的 PNG 檔案。使用絕對路徑或相對路徑皆可；範例使用名為 `Barcodes` 的相對資料夾。

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

以程式方式建立資料夾可避免目錄不存在時的執行時錯誤。

## 第三步：初始化 **create databar stacked barcode** 產生器

建立 `BarcodeGenerator` 實例，並使用 `EncodeTypes.DatabarStackedOmniDirectional`。範例資料 `(01)12345678901231` 符合 DataBar 所需的 GS1‑128 格式。

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

產生器物件會保存所有影響條碼外觀的參數。

## 第四步：設定 X‑dimension（最小條寬的像素數）

X‑dimension 控制條碼的整體大小，而不會改變編碼資料。設定為 `2` 像素可在大多數螢幕解析度下產生清晰且可掃描的圖像。

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

若需要更大或更小的條碼，可調整此數值；同時保持寬高比例一致。

## 第五步：配置長寬比並儲存第一張圖像

長寬比決定 DataBar 堆疊條碼的高寬關係。`15` 是常見的預設值，可產生緊湊的視覺效果。

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 方法會將 PNG 檔寫入先前定義的資料夾。檔名清楚標示所使用的長寬比。

### 長寬比 15 的預期輸出

產生的 `DatabarAspectRatio15.png` 與下圖相似。

![條碼圖像（長寬比 15）](https://example.com/images/databar-aspect15.png "條碼圖像（長寬比 15）")

*替代文字:* `create databar stacked barcode image saved with aspect ratio 15`

## 第六步：變更長寬比並儲存第二張圖像

您可以重複使用同一個 `BarcodeGenerator` 實例來產生變化。將 `AspectRatio` 改為 `30`，即可將每個條碼堆疊的高度加倍，適用於高解析度列印。

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### 長寬比 30 的預期輸出

`DatabarAspectRatio30.png` 圖像較高，寬度保持不變，提升遠距掃描的可讀性。

![條碼圖像（長寬比 30）](https://example.com/images/databar-aspect30.png "條碼圖像（長寬比 30）")

*替代文字:* `create databar stacked barcode image saved with aspect ratio 30`

## 完整原始碼

將所有步驟整合，即可得到一個可直接執行的完整程式。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

編譯並執行程式。執行完畢後，`Barcodes` 目錄會包含兩個 PNG 檔案，分別代表 **create databar stacked barcode** 的不同長寬比。

## 專業提示與常見陷阱

* **專業提示：** 大多數螢幕使用情境下，將 X‑dimension 設於 1 px 至 4 px 之間最為合適。較大的數值會增加檔案大小，卻不會提升掃描可靠度。  
* **陷阱：** 在產生器建立後變更 `EncodeTypes` 並不會更新內部編碼。請務必在建構子中指定正確的 `EncodeTypes`。  
* **專業提示：** 若需產生超過兩種長寬比，可將整數陣列於迴圈中遍歷，並在迴圈內呼叫 `Save`，以減少程式碼重複。  
* **陷阱：** 若儲存路徑缺乏寫入權限，會拋出 `UnauthorizedAccessException`。請確保應用程式具備相應的檔案系統權限。

## 結論

現在您已掌握如何在 C# 中使用 Aspose.BarCode **create databar stacked barcode**。本指南說明了環境設定、X‑dimension 調整、長寬比變更，以及 PNG 檔案的儲存方式。憑藉此基礎，您可以產生更多變化，將條碼建立整合至 Web API，或嵌入 PDF 報告中。

接下來，您可以探索以下相關主題，例如 **DataBar Stacked Omnidirectional** 掃描最佳實踐、在 **ASP.NET Core** 回應中嵌入條碼，或使用同一函式庫產生 **QR codes**。嘗試不同的 `EncodeTypes` 與影像格式，以符合您的應用需求。

祝開發順利！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，並以步驟說明與完整範例協助您掌握更多 API 功能，或在專案中探索替代實作方式。

- [如何使用 C# 與 Aspose.BarCode 建立 databar PNG 圖像](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [如何為 Databar Expanded Stacked 條碼設定欄位 – 完整 C# 教學](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [C# 中的 databar stacked omnidirectional 條碼 – 完整指南](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}