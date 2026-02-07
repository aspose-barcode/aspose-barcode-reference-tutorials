---
date: 2026-02-07
description: 學習如何使用 Aspose Barcode Java 建立 CODE_128 條碼、產生條碼圖像（Java），並設定精確的尺寸單位——非常適合用於庫存系統或運送標籤的條碼生成。
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: aspose barcode java：以尺寸單位建立 CODE_128 條碼
url: /zh-hant/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java：建立 CODE_128 條碼與尺寸單位

## 簡介

在本分步教學中，您將 **使用 aspose barcode java** 來建立 CODE_128 條碼、產生 barcode image java，並精確控制輸出之尺寸單位。無論您是為庫存系統、運送標籤產生器，或任何需要可靠條碼的 Java 應用程式打造條碼，Aspose.BarCode for Java 只需幾行程式碼即可提供完整彈性。

## 快速解答
- **我需要哪個函式庫？** Aspose.BarCode for Java (aspose barcode java)。  
- **支援哪種條碼類型？** CODE_128 (create code128 barcode java)。  
- **如何設定尺寸單位？** 使用 `BarHeight` 屬性搭配 `.setPoint()`。  
- **我可以以其他格式產生 barcode image java 嗎？** 可以 – PNG、JPEG、BMP 等。  
- **前置條件是什麼？** 已安裝 JDK、Aspose.BarCode 函式庫，以及 Java IDE。

## 什麼是 **create code128 barcode java**？

在 Java 中建立 CODE_128 條碼即是實例化 `BarcodeGenerator` 類別，使用 `EncodeTypes.CODE_128` 列舉，並提供欲編碼的資料字串。此符號因支援完整 ASCII 字元集且具高資料密度，廣泛應用於物流領域——非常適合庫存系統的條碼情境。

## 為何使用 Aspose.BarCode 來 **generate barcode image java**？

- **完整的尺寸控制** – 您可以設定條碼高度、模組大小與影像解析度。  
- **無外部相依性** – 純 Java，於任何支援 JDK 的平台皆可運作。  
- **豐富的自訂功能** – 支援顏色、字型、邊距，甚至 QR Code。  
- **高效能** – 於毫秒內產生影像，適用於批次處理與產生運送標籤條碼的工作流程。  

## 前置條件

在開始之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 已在您的機器上安裝 8 版或更新版本。  
2. **Aspose.BarCode for Java 函式庫** – 從 Aspose 官方網站下載最新的 JAR（試用版或授權版）。  
3. **Java IDE** – 如 IntelliJ IDEA、Eclipse，或具 Java 擴充功能的 VS Code。  

## 匯入命名空間

在 Java 類別的頂部加入必要的匯入，以便存取 Aspose.BarCode 的 API：

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何使用 Aspose.BarCode **generate barcode image java**？

以下為完整工作流程。每一步皆以簡明文字說明，且原始程式碼區塊保持不變。

### 步驟 1：定義資源目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您希望儲存條碼影像的絕對路徑。此資料夾將保存產生的 PNG/JPEG 檔案，您日後可將其嵌入發票、裝箱單或庫存報告中。

### 步驟 2：實例化條碼物件

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

此處我們透過傳入 `EncodeTypes.CODE_128` 以及資料字串 `"1234567"` 來 **create code128 barcode java**。

### 步驟 3：設定條碼高度（尺寸單位）

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` 方法以點 (point) 為單位定義高度 (1 point = 1/72 吋)。調整此數值以符合版面需求——較大的值會產生較高的條碼，常用於高解析度的運送標籤。

### 步驟 4：儲存影像

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()` 呼叫會將產生的條碼寫入您指定的資料夾。影像格式會根據檔案副檔名自動判斷（此例為 JPEG）。只要更改副檔名，即可切換為 PNG、BMP 或 TIFF。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **未建立影像** | `dataDir` 路徑不正確或缺少寫入權限。 | 確認資料夾存在且應用程式具有寫入權限。 |
| **條碼顯示過小** | 條碼高度以點為單位設定過低，無法符合所選 DPI。 | 提升傳入 `setPoint()` 的數值，或透過 `bb.getParameters().getImage().setResolution()` 調整影像 DPI。 |
| **不支援的字元** | CODE_128 僅支援 ASCII，您傳入了 Unicode。 | 對於非 ASCII 資料，請使用其他符號（例如 QR_CODE）。 |

## 常見問與答

**Q: Aspose.BarCode for Java 是否同時適用於條碼產生與辨識？**  
A: 是的，該函式庫支援廣泛符號的產生與辨識。

**Q: 我可以自訂產生的條碼影像外觀嗎？**  
A: 當然可以。您可以變更顏色、加入說明文字、調整邊距，甚至使用豐富的 `Parameters` API 嵌入商標。

**Q: 我要如何取得 Aspose.BarCode for Java 的暫時授權？**  
A: 前往 [here](https://purchase.aspose.com/temporary-license/) 申請評估用的暫時授權。

**Q: 我可以在哪裡取得 Aspose.BarCode for Java 的支援？**  
A: Aspose.BarCode 社群論壇是最佳的求助管道。請查看 [forum](https://forum.aspose.com/c/barcode/13) 獲得答案或提出新問題。

**Q: Aspose.BarCode for Java 支援哪些條碼符號？**  
A: 該函式庫支援數十種符號，包括 CODE_128、QR_CODE、UPC_A、DataMatrix、PDF417 等等。

### 額外提示（專業提示）

- **批次處理：** 將上述步驟包在迴圈中，以產生數百條條碼，供大量庫存上傳使用。  
- **解析度控制：** 使用 `bb.getParameters().getImage().setResolution(300)` 產生 300 dpi 影像，適合高品質列印標籤。  

---

**最後更新：** 2026-02-07  
**測試環境：** Aspose.BarCode for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}