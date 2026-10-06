---
date: 2026-08-17
description: 探索使用 Aspose.BarCode for .NET 的 DataMatrix 讀取程式設計。透過本完整指南了解如何在 .NET 應用程式中產生與讀取
  DataMatrix 條碼。
keywords:
- create barcode image .net
- barcode reader guide
- generate datamatrix c#
- c# barcode recognition library
- barcode image handling c#
lastmod: 2026-08-17
linktitle: DataMatrix 讀取程式設計
og_description: 使用 Aspose.BarCode 在 .NET 中建立條碼圖像，以產生與讀取 DataMatrix 代碼。本指南提供逐步設定、程式碼片段及
  C# 中條碼圖像處理的最佳實踐。
og_image_alt: Tutorial image showing DataMatrix barcode generated with Aspose.BarCode
  in a .NET application
og_title: 使用 Aspose.BarCode DataMatrix 在 .NET 中建立條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  headline: Create barcode image .NET with Aspose.BarCode for DataMatrix
  type: TechArticle
- description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  name: Create barcode image .NET with Aspose.BarCode for DataMatrix
  steps:
  - name: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
    text: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
  - name: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
    text: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
  type: HowTo
- questions:
  - answer: It embeds configuration data in a DataMatrix symbol so a scanner can automatically
      set parameters like illumination or decoding mode.
    question: What is DataMatrix reader programming?
  - answer: The library offers a unified API for over 50 barcode types, high‑performance
      encoding/decoding, and full .NET Core support.
    question: Why choose Aspose.BarCode for .NET?
  - answer: A trial version is available for evaluation; a commercial license is required
      for production deployments.
    question: Can I use Aspose.BarCode for free?
  - answer: You can request a short‑term license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: You can buy a full license from the [Aspose purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase a full license?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- DataMatrix
- Aspose.BarCode
- barcode generation
- C# barcode
- create barcode image
title: 在 .NET 中使用 Aspose.BarCode for DataMatrix 建立條碼圖像
url: /zh-hant/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for DataMatrix 建立 .NET 條碼影像

在本教學中，您將學習如何 **建立 .NET 條碼影像** 應用程式，使用 Aspose.BarCode 產生與讀取 DataMatrix 代碼。無論您需要在製造標籤中嵌入條碼或自動化庫存追蹤，本指南都會一步步帶領您，從專案設定到讀取條碼，讓您快速實作可靠的解決方案。

## 快速解答
- **「reader programming」是什麼意思？** 它會對 DataMatrix 符號進行編碼，使掃描器能自動自行設定。  
- **支援哪個 .NET 版本？** Aspose.BarCode 可在 .NET Framework 4.0+、.NET Core 2.0+ 以及 .NET 5/6+ 上運作。  
- **開發時需要授權嗎？** 免費試用版足以進行測試；正式上線則需商業授權。  
- **Aspose.BarCode 支援多少條碼格式？** 超過 50 種 1D 與 2D 符號，包括 DataMatrix、QR 及 PDF417。  
- **可以在不儲存影像檔的情況下讀取條碼嗎？** 可以——使用 `MemoryStream` 完全在記憶體中處理影像。

## 什麼是 DataMatrix 條碼讀取程式設計？
DataMatrix 條碼讀取程式設計是一種將特殊設定資料嵌入 DataMatrix 符號內的技術，讓掃描器在偵測到該符號時能自動調整照明、解碼模式及其他操作參數。此方法減少手動設定掃描器的需求，並提升製造線或倉儲分揀系統等高產能環境的處理速度。

## 為什麼在 .NET 使用 Aspose.BarCode？
Aspose.BarCode for .NET 提供統一的 API，支援超過 50 種條碼符號，能在不將整個檔案載入記憶體的情況下處理多兆位元組的影像，且在一般伺服器硬體上可於毫秒以下完成編碼與解碼，成為桌面與雲端應用程式在需要可靠條碼處理時的高效選擇。

## 前置條件

在開始之前，請確保您已具備：

1. **Visual Studio**（任何近期版本）已安裝支援的 .NET 執行環境。  
2. **Aspose.BarCode for .NET** – 從 [download page](https://releases.aspose.com/barcode/net/) 下載。  
3. **Basic C# knowledge** – 您應該能熟悉建立主控台或桌面專案。

## 匯入命名空間

`Aspose.BarCode` 提供條碼產生與讀取的核心類別，而 `System.Drawing` 處理影像操作。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## `BarcodeGenerator` 類別是什麼？
`BarcodeGenerator` 類別是 Aspose.BarCode 用於在記憶體中建立條碼影像的主要物件；它封裝了定義符號、視覺外觀、編碼選項與輸出格式所需的所有設定，讓開發者只需呼叫一次方法即可產生高品質的條碼。

## 如何定義目錄路徑

定義一個資料夾，用於儲存產生的條碼影像。  

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您機器上實際的資料夾路徑。

## 如何初始化 DataMatrix 產生器

建立 `BarcodeGenerator` 實例，將符號設定為 DataMatrix，並啟用 reader programming。

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

主要設定：
- `XDimension = 4` 像素控制模組大小。  
- `IsReaderProgramming = true` 告訴掃描器此符號攜帶設定資料。

## 如何產生條碼影像

呼叫 `Save` 方法將影像寫入指定路徑。

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

影像預設以 PNG 格式儲存，但您也可以選擇 JPEG、BMP 或 TIFF。

## 如何讀回條碼

使用 `BarCodeReader` 解碼已儲存的影像並驗證 reader‑programming 標誌。`BarCodeReader` 類別是解碼條碼的核心元件；它讀取影像、偵測支援的符號，並提供如 `IsReaderProgrammable` 等屬性，以指示 DataMatrix 符號是否包含 reader‑programming 資訊。

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

當標誌正確編碼時，讀取器會回傳 `IsReaderProgrammable` = `true`。

## 常見問題與除錯
- **找不到影像** – 請確認目錄路徑以反斜線 (`\`) 結尾，或使用 `Path.Combine`。  
- **讀取器回傳 false** – 確保在呼叫 `Save` **之前** 已設定 `IsReaderProgramming`。  
- **不支援的影像格式** – 請使用 PNG 或 JPEG；BMP 與 TIFF 可能在較舊的 Windows 版本上需要額外的編解碼器。

## 常見問答

**Q: DataMatrix 讀取程式設計是什麼？**  
A: 它將設定資料嵌入 DataMatrix 符號，使掃描器能自動設定如照明或解碼模式等參數。

**Q: 為什麼選擇 Aspose.BarCode for .NET？**  
A: 它提供超過 50 種條碼類型的統一 API，高效能的編碼/解碼，並完整支援 .NET Core。

**Q: 可以免費使用 Aspose.BarCode 嗎？**  
A: 可使用試用版進行評估；正式上線則需商業授權。

**Q: 如何取得臨時授權？**  
A: 您可從 [temporary license page](https://purchase.aspose.com/temporary-license/) 申請短期授權。

**Q: 如何購買完整授權？**  
A: 您可從 [Aspose purchase page](https://purchase.aspose.com/buy) 購買完整授權。

**Q: 此函式庫相容於最新的 .NET 版本嗎？**  
A: 是的，支援 .NET Framework 4.0+、.NET Core 2.0+，以及 .NET 5/6+。

## 結論

透過本指南，您現在已了解如何 **建立 .NET 條碼影像** 解決方案，產生 DataMatrix 符號並使用 Aspose.BarCode 讀回。將這些程式碼片段整合至任何 C# 專案——桌面、服務或 Web——即可在製造、物流或醫療等領域自動化條碼工作流程。

如需更深入的參考資料，請瀏覽官方 [documentation](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) 社群。

---

**最後更新：** 2026-08-17  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}