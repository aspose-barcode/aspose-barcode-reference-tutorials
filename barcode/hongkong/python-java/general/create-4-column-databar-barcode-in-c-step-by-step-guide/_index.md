---
category: general
date: 2026-08-09
description: 使用 Aspose.BarCode 在 C# 中快速建立 4 列 DataBar 條碼。於本簡明指南學習如何設定列、行，並將圖像儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: zh-hant
lastmod: 2026-08-09
og_description: 使用 Aspose.BarCode 在 C# 中建立 4 欄 DataBar 條碼，然後自訂列並匯出 PNG 圖像供您的應用程式使用。
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: 在 C# 中建立 4 欄 DataBar 條碼 – 快速教學
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: 在 C# 中建立 4 欄 DataBar 條碼 – 步驟指南
url: /zh-hant/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 4 列 DataBar 條碼 – 步驟指南

如果您需要在 C# 中 **建立 4 列 DataBar 條碼**，本教學將會完整說明。 我們將逐步示範產生 DataBar Expanded Stacked 條碼、設定四個欄位，並將結果儲存為 PNG 圖片。

在本指南中您將學會：

* 為 **DataBar Expanded Stacked** 符號初始化 `BarcodeGenerator`。  
* 將欄位數設定為 4（主要需求）。  
* 在需要三行堆疊佈局時調整列數。  
* 使用適當的 **barcode image format** 將條碼匯出為 PNG。

您只需要 Aspose.BarCode for .NET 函式庫（版本 23.10 或更新）以及 .NET 6+ 開發環境（例如 Visual Studio 2022）。不需要其他相依性。

---

## 如何建立 4 列 DataBar 條碼

第一步是建立一個針對 **DataBar Expanded Stacked** 符號的 `BarcodeGenerator` 實例。此類別封裝所有渲染選項，讓在欄位‑基礎與列‑基礎佈局之間切換變得簡單。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼這樣可行：**  
`EncodeTypes.DatabarExpandedStacked` 告訴 Aspose.BarCode 產生 DataBar 系列的堆疊版本。`DataBar.Columns` 屬性控制條碼佔用多少個垂直模組。將其設定為 4 即符合 **建立 4 列 DataBar 條碼** 的需求。最後，`Save` 會使用 **barcode image format** `Png` 將視覺圖像寫入磁碟。

### 設定 DataBar Expanded Stacked 欄位

如果需要不同的欄位數，只要變更指派給 `Columns` 的整數即可。此屬性接受 1 到 4 的值，適用於 expanded stacked 變體。

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*小技巧：* 請務必使用支援 DataBar 系列的掃描器測試產生的條碼，因為僅憑外觀無法保證可讀性。

### 儲存條碼圖像

`BarCodeImageFormat` 列舉提供多種選項（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。PNG 為無損格式，適用於大多數網頁與桌面情境。

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

如果需要其他格式，只要將 `Png` 替換為相應的列舉值即可。儲存的檔案可直接嵌入 HTML、PDF，或列印於標籤上。

## 建立具自訂列數的條碼

有時需要以特定列數而非欄位數的堆疊佈局。相同的 `BarcodeGenerator` 類別提供 `Rows` 屬性以滿足此需求。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼列數重要：**  
當堆疊條碼的高度大於寬度時，`Rows` 屬性決定符號被分割成多少個水平切片。設定 `Rows = 3` 會產生三列堆疊條碼，適合較窄的標籤寬度。

### 動態設定條碼列數

您可以根據輸入資料在執行時計算列數：

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

此彈性讓您 **設定條碼列數** 而無需重新編譯應用程式。

## 完整端對端範例

以下是一個單一程式，同時產生 4 欄條碼與 3 列條碼，示範兩種設定如何共存。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**預期輸出：**  
兩個 PNG 檔案會出現在應用程式的工作目錄中：

* `DatabarCols4.png` – 具四個垂直欄位的 DataBar Expanded Stacked 條碼。  
* `DatabarRows3.png` – 同一符號以三個水平列排列。

兩張影像皆可在任何圖像檢視器中開啟，或嵌入 UI 控制項。

---

## 常見問題與邊緣情況

| 問題 | 答案 |
|----------|--------|
| *我可以使用其他條碼符號嗎？* | 可以。將 `EncodeTypes.DatabarExpandedStacked` 替換為其他 `EncodeTypes` 值（例如 `EncodeTypes.QR`），但 `Columns` 與 `Rows` 屬性僅適用於 DataBar 系列。 |
| *如果資料字串超過最大長度會怎樣？* | DataBar Expanded Stacked 符號最多支援 61 個數字字元。超過此限制會拋出 `ArgumentException`。請在指派給產生器前先驗證輸入。 |
| *需要手動釋放 `BarcodeGenerator` 嗎？* | `BarcodeGenerator` 實作 `IDisposable`。在長時間執行的服務中，建議使用 `using` 區塊或手動呼叫 `Dispose()` 以釋放本機資源。 |
| *可以產生 SVG 而非 PNG 嗎？* | 當然可以。在 `Save` 方法中使用 `BarCodeImageFormat.Svg`。 |
| *此函式庫相容 .NET Core 嗎？* | Aspose.BarCode for .NET 支援 .NET Core 3.1、.NET 5、.NET 6 以及更高版本。無需修改程式碼。 |

## 結論

現在您已了解如何在 C# 中使用 Aspose.BarCode **建立 4 列 DataBar 條碼**、如何透過列數調整佈局，以及如何以方便的 **barcode image format** 匯出結果。完整範例同時展示欄位‑基礎與列‑基礎設定，為任何標籤列印或行動掃描情境奠定堅實基礎。

**後續步驟**

* 嘗試不同的資料內容並驗證掃描器相容性。  
* 探索其他樣式選項，例如前景/背景顏色 (`generator.Parameters.Barcode.Color`)。  
* 使用 `Graphics` API 將條碼與其他圖形結合，打造自訂標籤設計。  

隨意將程式碼套用於 ASP.NET Core、Windows Forms 或 Xamarin 專案——Aspose.BarCode 可在所有 .NET 平台上運作。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，並提供完整可執行的程式碼範例與步驟說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [建立 DotCode 條碼影像 – 行與欄 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [建立條碼影像 C# – 設定 Codablock F 行與欄](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [如何使用 Aspose.BarCode for .NET 建立 DotCode 延伸代碼文字](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}