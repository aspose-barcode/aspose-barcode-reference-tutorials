---
date: 2026-02-12
description: 學習如何在 Java 中使用 Aspose.BarCode 建立自訂寬窄比例的 Code128 條碼，並高效產生條碼 PNG 圖片。請跟隨我們的逐步指南。
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: 如何在 Java 中建立具有寬窄比例的 CODE_128 條碼
url: /zh-hant/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中建立具有寬窄比例的 CODE_128 條碼

## 簡介

如果您需要 **建立 code128 條碼** 並且要精確控制視覺比例，調整寬窄比例是關鍵。在本教學中，我們將逐步說明如何使用 Aspose.BarCode for Java 進行 **條碼** 建立，示範如何設定比例、**產生條碼 PNG** 圖片，並 **將條碼影像儲存** 到磁碟。無論您是製作庫存標籤、運送標籤，或任何需要自訂樣式 CODE_128 條碼的應用，都能在此找到完整解決方案。

## 快速解答
- **什麼是寬窄比例？** 它控制條碼中寬條與窄條的相對寬度。  
- **哪種條碼類型支援比例調整？** 大多數 1‑D 條碼類型，包括 CODE_128，都允許設定自訂比例。  
- **需要授權嗎？** 提供免費試用版，但正式使用需購買商業授權。  
- **可以產生 PNG 格式的條碼影像嗎？** 可以——使用 `generator.save(...)` 產生條碼 PNG 影像。  
- **程式碼是否相容於 Java 8 以上？** 完全相容；Aspose.BarCode 支援所有現代 Java 版本。

## 先決條件

在開始撰寫程式碼之前，請確保您已具備以下條件：

- 已在機器上安裝 Java Development Kit (JDK)。  
- 已取得 Aspose.BarCode for Java 套件。可從 [下載連結](https://releases.aspose.com/barcode/java/) 取得。

## 匯入套件

首先，將必要的 Aspose.BarCode 類別匯入您的專案。

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 什麼是寬窄比例，為什麼要調整它？

寬窄比例決定「寬」條相對於「窄」條的粗細程度。調整此比例可以提升掃描器的可讀性、符合特定印刷標準，或僅僅是配合品牌的視覺風格。

## 如何在 Java 中建立具有寬窄比例的 code128 條碼

以下是一個 **逐步條碼** 指南，帶您完成整個流程的每個步驟。

### 步驟 1：設定文件目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

請確保目錄已存在且您具有寫入權限；此目錄將用於放置 **儲存條碼影像** 的檔案。

### 步驟 2：實例化條碼物件

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

此處我們透過將 `EncodeTypes.CODE_128` 傳入建構子，**建立 code128 條碼**。

### 步驟 3：設定寬窄比例

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

`setWideNarrowRatio` 方法讓您微調視覺間距。`3.0f` 代表寬條的寬度是窄條的三倍。

### 步驟 4：將影像儲存至磁碟

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

呼叫 `save` 後會 **產生條碼影像**，並以 PNG 檔案形式儲存，完成 **儲存條碼影像** 的步驟。

## 為什麼要調整寬窄比例？

- **掃描器相容性：** 某些掃描器在 2.0 至 3.0 的比例範圍內可獲得最佳讀取率。  
- **列印品質：** 調整比例可彌補印表機 DPI 限制，避免條碼變形。  
- **品牌一致性：** 部分公司希望條碼在視覺上與企業色彩或設計指南保持一致。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| 條碼看起來變形 | 比例對印表機而言過高或過低 | 調整傳入 `setWideNarrowRatio` 的數值（例如 2.0‑2.5）。 |
| 檔案未建立 | `dataDir` 路徑無效或權限不足 | 檢查目錄路徑並確保應用程式具有寫入權限。 |
| 掃描器無法讀取條碼 | 比例超出該條碼類型的建議範圍 | 使用標準比例（2.0‑3.0）或以目標掃描器進行測試。 |

## 常見問答

**Q: 可以在其他 Java 框架中使用 Aspose.BarCode 嗎？**  
A: 可以，Aspose.BarCode 設計上可與 Spring、Java EE、Android 以及其他 Java 環境無縫整合。

**Q: 如何產生不同條碼類型的條碼？**  
A: 只需在 `BarcodeGenerator` 建構子中更換條碼類型，例如使用 `EncodeTypes.QR` 產生 QR Code。

**Q: 有提供 Aspose.BarCode 的試用版嗎？**  
A: 有，您可以在 [此處](https://releases.aspose.com/) 取得免費試用版。

**Q: 哪裡可以找到 Aspose.BarCode 的詳細文件？**  
A: 請參考文件說明 [此處](https://reference.aspose.com/barcode/java/)。

**Q: 如何取得 Aspose.BarCode 的支援？**  
A: 前往 Aspose.BarCode 論壇 [此處](https://forum.aspose.com/c/barcode/13) 獲取支援與社群討論。

---

**最後更新：** 2026-02-12  
**測試環境：** Aspose.BarCode for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}