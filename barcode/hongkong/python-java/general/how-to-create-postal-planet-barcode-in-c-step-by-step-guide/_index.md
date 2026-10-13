---
category: general
date: 2026-09-23
description: 學習如何在 C# 中建立帶有實心與空白條的郵政星球條碼圖像。請參考使用 BarcodeGenerator 與 X 軸尺寸設定的完整範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: zh-hant
lastmod: 2026-09-23
og_description: 使用此詳細教學在 C# 中建立郵政 Planet 條碼。透過 BarcodeGenerator 及 X‑dimension 設定，產生實心與空心兩種條形樣式。
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: 使用 C# 建立郵政星球條碼 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何在 C# 中建立郵政星球條碼 – 逐步指南
url: /zh-hant/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立郵政 Planet 條碼 – 步驟指南

如果您需要在 .NET 應用程式中**建立郵政 Planet 條碼**圖像，本教學提供即用的解決方案。無論您是構建郵寄標籤系統或地址驗證工具，都能清楚看到如何使用 Aspose.Barcode 的 `BarcodeGenerator` 類別產生實心條與空心條兩種變體。

您將學會如何設定 **Planet 條碼產生器**、以像素設定 **X‑dimension**（每根條的寬度），以及將結果儲存為 PNG 檔案。本指南亦說明為何會選擇實心條或空心條，並示範只需一行程式碼即可在兩者之間切換。

## 您需要的條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本（此程式碼同樣適用於 .NET Core 與 .NET Framework）
* Visual Studio 2022（或任何支援 C# 的 IDE）
* 已在專案中安裝 Aspose.Barcode for .NET NuGet 套件（`Aspose.Barcode`）
* 具有寫入權限的資料夾，以儲存產生的 PNG 檔案

這些前置條件可確保範例在編譯時不需額外設定。

## 步驟 1：設定輸出資料夾

第一步是定義條碼圖像要寫入的資料夾。使用絕對路徑或相對路徑皆可；只要確保資料夾已存在，或在程式中先行建立。

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*為什麼重要*：如果資料夾不存在，`BarcodeGenerator.Save` 會拋出例外。事先建立資料夾可讓程式在部署環境中更具韌性。

## 步驟 2：初始化 Planet 條碼產生器

**Planet 條碼產生器**（`EncodeTypes.Planet`）是許多郵政服務使用的特定符號集。您需要以欲編碼的資料初始化它——此例中為數字字串 `"123456"`。

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*為什麼重要*：`EncodeTypes.Planet` 告訴 Aspose.Barcode 使用 Planet 符號，其固定的條與空格模式適合郵件路由。

## 步驟 3：設定條碼 X‑dimension

**條碼 X‑dimension** 控制每根條的寬度。將其設為 4 像素，可產生清晰、易讀的條碼，且在一般標籤印表機上列印效果良好。

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*為什麼重要*：X‑dimension 設得太小會導致條碼無法辨識，設得太大則浪費標籤空間。四像素是 300 dpi 印表機的常見最佳值。

## 步驟 4：產生實心條 Planet 條碼

預設的繪製模式使用 **實心條**（黑條白底）。將圖像儲存為 PNG 可保留無損品質。

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**預期輸出**：`PostalPlanetFilledBars.png` 顯示經典的 Planet 條碼，所有條皆為實心。

![已建立的郵政 Planet 條碼（實心條）範例](https://example.com/filled-bars.png "已建立的郵政 Planet 條碼（實心條）範例")

*為什麼重要*：實心條是大多數郵政掃描器的行業標準外觀。使用 PNG 可確保列印時圖像保持銳利。

## 步驟 5：建立第二個產生器以產生空心條

為了說明 **實心條 vs 空心條** 的比較，我們再建立一個 `BarcodeGenerator` 實例，使用相同的資料。重複使用相同資料可確保兩張圖在視覺上可直接比較。

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## 步驟 6：套用相同的 X‑dimension 並切換為空心條

`FilledBars` 屬性可切換繪製模式。將其設為 `false` 後會產生 **空心條**（白條黑底）。X‑dimension 保持不變，以維持尺寸一致。

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*為什麼重要*：某些郵政服務或自訂工作流程需要反轉顏色，以在深色介質上取得更佳對比度。`FilledBars` 旗標讓您只需一行程式碼即可彈性切換。

## 步驟 7：產生空心條 Planet 條碼

最後，將空心條版本儲存至相同的輸出資料夾。

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**預期輸出**：`PostalPlanetEmptyBars.png` 呈現相同的 Planet 圖樣，但條為空心（白色），背景為黑色。

![已建立的郵政 Planet 條碼（空心條）範例](https://example.com/empty-bars.png "已建立的郵政 Planet 條碼（空心條）範例")

## 驗證結果

在任何圖像檢視器中開啟這兩個 PNG 檔案。您應該會看到兩個在顏色上相反但圖樣相同的條碼。若要確認條碼可被掃描，可使用支援 Planet 符號的智慧手機條碼閱讀應用程式。

若圖像出現變形，請再次檢查 **X‑dimension** 的數值，並確保輸出資料夾路徑不含非法字元。

## 常見問題與最佳實踐

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **找不到資料夾** | `Save` 在路徑不存在時拋出 `DirectoryNotFoundException`。 | 使用 `Directory.CreateDirectory` 於儲存前先建立資料夾。 |
| **條碼尺寸不正確** | 使用非整數 X‑dimension 或小於 2 像素的值會產生不可讀的條碼。 | 保持 X‑dimension ≥ 2 像素；4 像素適用於大多數印表機。 |
| **顏色反轉未套用** | 忘記將 `FilledBars = false`。 | 在設定 X‑dimension 後，明確設定 `FilledBars`。 |
| **圖像格式錯誤** | 使用 JPEG 會產生壓縮雜訊。 | 使用 `BarCodeImageFormat.Png` 取得無損輸出。 |

## 延伸範例

* **變更資料** – 將 `"123456"` 替換為任意最多 12 位的數字字串（Planet 最多支援 12 位）。  
* **調整圖像大小** – 修改 `XDimension.Pixels`，或透過 `barcodeGenerator.Parameters.Image` 設定 `Height`／`Width`。  
* **加入邊框** – 使用 `barcodeGenerator.Parameters.Barcode.BorderWidth` 為條碼繪製細線邊框。  
* **匯出其他格式** – 若工作流程需要，可將 `BarCodeImageFormat.Png` 改為 `Jpeg`、`Bmp` 或 `Tiff`。

## 結論

現在您已掌握如何在 C# 中使用 Aspose.Barcode 的 `BarcodeGenerator` **建立郵政 Planet 條碼**圖像。本教學說明了如何初始化 **Planet 條碼產生器**、設定 **條碼 X‑dimension**，以及產生 **實心條** 與 **空心條** 兩種 PNG 檔案。憑藉這些基礎，您可以將郵政條碼產生整合至任何 .NET 應用程式，客製化外觀，並確保在實務郵寄系統中可靠掃描。

想要探索更多嗎？試著產生其他郵政符號（例如 **Postnet** 或 **Intelligent Mail**），或結合 Aspose.PDF 將條碼加入 PDF 標籤。祝開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，能幫助您進一步掌握 API 功能並探索其他實作方式：

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}