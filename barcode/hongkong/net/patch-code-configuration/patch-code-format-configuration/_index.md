---
date: 2026-03-02
description: 使用 Aspose Barcode .NET 產生 Patch Code 條碼。了解如何快速產生 Patch Code 條碼並提升文件管理。立即下載程式庫！
linktitle: Patch Code Format Configuration
second_title: Aspose.BarCode .NET API
title: Aspose 條碼 .NET – 在 .NET 中建立 Patch Code 條碼
url: /zh-hant/net/patch-code-configuration/patch-code-format-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 建立 Patch Code 條碼

在本教學中，您將學習 **如何使用 Aspose.BarCode for .NET 產生 Patch Code 條碼**。Patch Code 是一種二維符號，可協助在大型檔案庫中組織與檢索文件。完成本指南後，您只需幾行程式碼，即可在任何 .NET 應用程式中加入 Patch Code 條碼。

## 快速答覆
- **需要哪個函式庫？** Aspose.BarCode for .NET  
- **可以不使用 QR 產生 Patch Code 嗎？** 可以 – 設定 PatchFormat 並略過 QR 設定。  
- **建議使用哪種影像格式？** PNG 最適合無損渲染。  
- **開發階段需要授權嗎？** 免費試用版可供測試；正式上線需購買商業授權。  
- **支援 .NET Core 嗎？** 當然支援 – 函式庫可用於 .NET 5/6 以及 .NET Core 3.1+。  

## 介紹

Patch Code 條碼是文件管理系統的重要組成部分，可協助文件的辨識與組織。Aspose.BarCode for .NET 是一套功能強大的函式庫，讓開發者能輕鬆產生各種條碼，包括 Patch Code。

在本教學中，我們將學習如何使用 Aspose.BarCode for .NET 建立 Patch Code 條碼。內容涵蓋必要的前置作業、匯入所需命名空間，以及將範例程式碼逐步拆解說明。完成後，您將能在 .NET 應用程式中輕鬆產生 Patch Code 條碼。

## 什麼是 Aspose.BarCode for .NET？
Aspose.BarCode for .NET 是一套相容於 .NET 的 API，讓您 **產生與讀取** 多種條碼符號，從傳統的一維條碼到進階的二維符號，如 Patch Code 與 QR。它將底層編碼細節抽象化，讓您專注於業務邏輯。

## 為什麼要產生 Patch Code 條碼？
- **快速文件檢索** – 掃描 Patch Code 即可立即定位實體檔案。  
- **緊湊的資料儲存** – 可直接在符號內儲存中繼資料（例如文件類型、建立日期）。  
- **內建 QR 補充** – 可選擇加入 QR 條碼，以攜帶 URL 或較長的文字資訊。  

## 前置作業

在開始產生 Patch Code 條碼之前，請確保已具備以下條件：

- 已在系統上安裝 Visual Studio 或任何 .NET 開發環境。  
- Aspose.BarCode for .NET 函式庫。可從 [此處](https://releases.aspose.com/barcode/net/) 下載。  
- 具備基本的 C# 與 .NET 程式設計知識。  

## 匯入命名空間

首先，請匯入使用 Aspose.BarCode for .NET 所需的命名空間。範例如下：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

現在我們已完成前置作業與命名空間的設定，接下來將範例程式碼分成多個步驟說明。

## 如何使用 Aspose.BarCode for .NET 產生 Patch Code 條碼

### 步驟 1：設定路徑

先定義要儲存產生之 Patch Code 條碼影像的路徑。您可以這樣設定目錄路徑：

```csharp
string path = "Your Directory Path";
```

請將 `"Your Directory Path"` 替換為實際欲輸出的資料夾路徑。

### 步驟 2：初始化條碼產生器

建立 `BarcodeGenerator` 類別的實例，以開始產生 Patch Code 條碼。此處指定條碼類型為 `EncodeTypes.PatchCode`，並提供唯一的條碼文字，例如 `"Patch I"`。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.PatchCode, "Patch I");
```

### 步驟 3：產生不含 QR 的 Patch Code

您可以在不加入 QR 條碼的情況下產生 Patch Code。將 Patch Format 設為 `PatchFormat.A4`，然後儲存產生的條碼影像。

```csharp
gen.Parameters.Barcode.PatchCode.PatchFormat = PatchFormat.A4;
gen.Save($"{path}PatchCodeA4WithoutQR.png", BarCodeImageFormat.Png);
```

### 步驟 4：產生含 QR 的 Patch Code

若要同時產生含 QR 條碼的 Patch Code，仍將 Patch Format 設為 `PatchFormat.A4`。此外，您可以透過 `ExtraBarcodeText` 屬性加入額外資訊，並將條碼文字位置設定為 `CodeLocation.None` 以停用文字顯示。

```csharp
gen.Parameters.Barcode.PatchCode.PatchFormat = PatchFormat.A4;
gen.Parameters.Barcode.PatchCode.ExtraBarcodeText = "Aspose page extra info";
gen.Parameters.Barcode.CodeTextParameters.Location = CodeLocation.None;
gen.Save($"{path}PatchCodeA4WithQR.png", BarCodeImageFormat.Png);
```

透過上述四個簡單步驟，即可使用 Aspose.BarCode for .NET 建立 Patch Code 條碼。此函式庫簡化了整個流程，讓 .NET 開發者能高效且友善地完成條碼產生。

## 常見問題與解決方案
- **路徑無效錯誤** – 確認資料夾已存在且應用程式具備寫入權限。  
- **授權例外** – 試用版可供評估；正式環境請套用有效授權以移除浮水印。  
- **不支援的影像格式** – API 支援 PNG、JPEG、BMP、GIF 以及 TIFF。呼叫 `Save` 時請使用上述格式之一。  

## 常見問答

### 什麼是 Aspose.BarCode for .NET？
Aspose.BarCode for .NET 是一套功能強大的函式庫，讓 .NET 開發者能產生與讀取各種條碼，包括 Patch Code、QR Code 等。

### 從哪裡可以下載 Aspose.BarCode for .NET？
您可從 [Aspose 官方網站](https://releases.aspose.com/barcode/net/) 下載 Aspose.BarCode for .NET。

### Aspose.BarCode for .NET 適用於文件管理系統嗎？
適用，因為它能產生用於文件辨識與組織的 Patch Code 條碼。

### 可以先試用 Aspose.BarCode for .NET 再決定是否購買嗎？
可以，您可從 [此處](https://releases.aspose.com/) 取得免費試用版。

### 在哪裡可以取得 Aspose.BarCode for .NET 的支援？
若有任何問題或需要協助，可前往 Aspose.BarCode for .NET 支援論壇 [此處](https://forum.aspose.com/c/barcode/13)。

**其他問答**

**Q:** *我可以自訂產生的 Patch Code 大小嗎？*  
**A:** 可以。在呼叫 `Save` 前，調整 `gen.Parameters.Image.Width` 與 `Height` 即可。

**Q:** *能否直接將條碼嵌入 PDF 中？*  
**A:** 完全可以。使用 Aspose.PDF 將產生的 PNG（或串流）加入 PDF 頁面即可。

## 結論

本教學說明了如何使用 **Aspose.BarCode for .NET** 產生 Patch Code 條碼。我們介紹了前置作業、匯入必要的命名空間，並以清晰的步驟示範了如何建立無 QR 以及含 QR 的 Patch Code。掌握這些技巧後，您即可在任何文件管理或歸檔解決方案中整合可靠的可掃描識別碼。

---

**最後更新：** 2026-03-02  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}