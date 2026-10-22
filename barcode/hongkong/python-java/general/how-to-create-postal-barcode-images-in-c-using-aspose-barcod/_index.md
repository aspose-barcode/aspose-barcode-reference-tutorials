---
category: general
date: 2026-10-21
description: 學習如何在 C# 中使用 Aspose.BarCode 建立郵政條碼圖像——生成 Planet 與 RM4SCC 條碼、控制填充條，並將其儲存為
  PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: zh-hant
lastmod: 2026-10-21
og_description: 使用 Aspose.BarCode 在 C# 中建立郵政條碼圖像。本教學示範如何產生 Planet 與 RM4SCC 條碼、切換實心條，並儲存
  PNG 檔案。
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: 在 C# 中建立郵政條碼圖像 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Aspose.BarCode 建立郵政條碼圖像
url: /zh-hant/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中建立郵政條碼圖像

如果您需要在 .NET 專案中 **建立郵政條碼** 圖像，本指南提供一個完整、可直接執行的解決方案。您將會看到如何產生 Planet 與 RM4SCC 條碼、在實心與空心條之間切換，並將結果儲存為 PNG 檔案——只需幾行 C# 程式碼。

產生可靠的郵政條碼對於郵件自動化、大量標籤列印以及與物流平台的整合至關重要。完成本教學後，您將擁有一段可重複使用的程式碼片段，能直接複製到任何 C# 主控台或 Web 應用程式中。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* 已啟用的 **Aspose.BarCode** NuGet 套件 (`Install-Package Aspose.BarCode`)  

這些工具足以編譯並執行範例，無需其他相依性。

## **建立郵政條碼** 圖像的逐步指南

此流程包含四個邏輯步驟：

1. 準備輸出資料夾。  
2. 產生實心條的 Planet 條碼（預設外觀）。  
3. 產生空心條的 Planet 條碼。  
4. 產生實心條的 RM4SCC 條碼。

以下將分別說明每個步驟，完整原始碼則於說明之後呈現。

### 1. 準備輸出資料夾

條碼圖像需要一個可寫入的目錄。程式碼會在資料夾不存在時自動建立，以避免執行時拋出 `DirectoryNotFoundException`。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*為何重要*：若目錄缺失，程式會在產生任何條碼之前就停止。使用 `Directory.CreateDirectory` 是安全的，因為若資料夾已存在它不會執行任何操作。

### 2. 產生實心條的 Planet 條碼

Planet 條碼被多家郵政服務於國內郵件使用。預設的 `FilledBars` 設定會呈現實心條，這是最常見的視覺樣式。

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*說明*：

* `EncodeTypes.Planet` 告訴 Aspose.BarCode 使用 Planet 標準。  
* 資料字串 `"123456"` 為有效的 Planet 負載（6 個數字字符）。  
* `XDimension.Pixels = 4` 產生每條寬度為 4 px 的條碼，兼顧可讀性與檔案大小。  
* `Save` 將圖像儲存為 PNG，這是一種無失真格式，適合後續處理。

### 3. 產生空心條的 Planet 條碼

某些郵政規範要求 **空心**（中空）條。您可以透過 `FilledBars` 屬性切換此行為。

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*提示*：在實心與空心條之間切換時，請保持 `XDimension` 值不變，以確保圖像尺寸的一致性。

### 4. 產生實心條的 RM4SCC 條碼

RM4SCC（Royal Mail 四態客戶代碼）是英國的郵政條碼。與 Planet 類似，預設外觀使用實心條。

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*為何使用 RM4SCC*：RM4SCC 格式會編碼 6 位數字字串加上檢查碼，非常適合英國郵寄服務。

### 完整原始碼（單一程式區塊）

將以下程式碼片段複製到新的 C# 主控台專案中。它可在 .NET 6.0 下編譯，並在 `Barcodes` 子資料夾中產生三個 PNG 檔案。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### 預期輸出

執行程式會印出確認訊息，並建立三個檔案：

* `PostalPlanetFilledBars.png` – 實心條 Planet 條碼  
* `PostalPlanetEmptyBars.png` – 空心條 Planet 條碼  
* `PostalRM4SCCFilledBars.png` – 實心條 RM4SCC 條碼  

每張圖像的條寬為 4 px，適合螢幕預覽或列印就緒的 PDF 嵌入。

## 常見問題與邊緣情況處理

| Question | Answer |
|----------|--------|
| **如果資料字串無效會怎樣？** | Aspose.BarCode 會拋出 `ArgumentException`。在建立產生器之前，請先驗證輸入長度（Planet = 6 位數字，RM4SCC = 6 位數字）。 |
| **我可以更改圖像格式嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Gif`、`Bmp` 或 `Tiff` 即可。 |
| **如何調整條碼高度？** | 使用 `planetFilled.Parameters.Barcode.BarHeight`（預設為 50 px）。 |
| **在 Web API 中使用這段程式碼安全嗎？** | 絕對安全。產生器對於唯讀操作是執行緒安全的，但請在每個請求中建立新的 `BarcodeGenerator` 以避免共享狀態。 |
| **其他郵政標準呢？** | Aspose.BarCode 亦支援 `EncodeTypes.Postnet`、`EncodeTypes.USPSIntelligentMail` 等。使用方式相同，只需更改 `EncodeTypes` 的值即可。 |

## 結論

現在您已了解如何使用 Aspose.BarCode 在 C# 中 **建立郵政條碼** 圖像，涵蓋 Planet 與 RM4SCC 兩種格式，並示範如何在實心與空心條之間切換。完整且可執行的範例可直接放入任何 .NET 專案，即可取得即時的視覺結果。

### 後續步驟

* **產生其他郵政條碼** – 嘗試 `EncodeTypes.Postnet` 或 `EncodeTypes.USPSIntelligentMail`。  
* **自訂外觀** – 試驗 `BarHeight`、`ForeColor` 與 `BackColor` 以符合您的品牌形象。  
* **整合至 Web 服務** – 透過 ASP.NET Core 端點公開產生邏輯，以實現按需條碼產生。  

掌握這些技巧後，您即可自信地 **產生 planet 條碼** 圖像，並能回答「**如何在 C# 中產生條碼**」的相關問題，無論是開發桌面郵寄工具或雲端運輸 API。祝程式開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何產生實心與空心條的 Planet 條碼](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [如何在 C# 中產生 RM4SCC 條碼並產生 Planet 條碼](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [在 C# 中產生郵政條碼 – 完整指南與 Planet 條碼](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}