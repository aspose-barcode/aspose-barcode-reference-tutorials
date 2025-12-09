---
date: 2025-12-08
description: 學習如何使用 Aspose.BarCode 在 Java 中建立 Code128 條碼並產生條碼圖像。使用簡單且可重用的程式碼設定條碼圖像的精確尺寸單位。
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 在 Java 中建立 Code128 條碼
url: /zh-hant/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 code128 條碼 Java 並使用 Aspose.BarCode 設定尺寸單位

## 介紹

在本分步指南中，您將 **建立 code128 條碼 Java** 程式碼，產生條碼影像並讓您控制輸出尺寸單位。無論您是建置庫存系統、運送標籤產生器，或任何需要可靠條碼的 Java 應用程式，Aspose.BarCode for Java 都能讓此過程簡單且高度客製化。

## 快速回答
- **需要哪個函式庫？** Aspose.BarCode for Java。  
- **涵蓋哪種條碼類型？** CODE_128（create code128 barcode java）。  
- **如何設定尺寸單位？** 使用 `BarHeight` 屬性搭配 `.setPoint()`。  
- **可以產生其他格式的條碼影像 Java 嗎？** 可以 – PNG、JPEG、BMP 等。  
- **前置需求是什麼？** 已安裝 JDK、Aspose.BarCode 函式庫，以及 Java IDE。

## 什麼是 **create code128 barcode java**？

在 Java 中建立 CODE_128 條碼即是以 `EncodeTypes.CODE_128` 列舉實例化 `BarcodeGenerator` 類別，並提供欲編碼的資料字串。此符號因支援完整 ASCII 字元集且具高資料密度，廣泛應用於物流領域。

## 為什麼使用 Aspose.BarCode 來 **generate barcode image java**？

- **完整的尺寸控制** – 可設定條高、模組大小與影像解析度。  
- **無外部相依性** – 純 Java，適用於任何支援 JDK 的平台。  
- **豐富的客製化** – 支援顏色、字型、邊距，甚至 QR Code。  
- **高效能** – 以毫秒級產生影像，適合批次處理。

## 前置條件

在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已在機器上安裝 8 版或更新版本。  
2. **Aspose.BarCode for Java 函式庫** – 從 Aspose 官方網站下載最新 JAR（試用版或正式授權）。  
3. **Java IDE** – 如 IntelliJ IDEA、Eclipse，或具 Java 擴充功能的 VS Code。  

## 匯入命名空間

在 Java 類別的最上方加入必要的匯入，以便存取 Aspose.BarCode 的 API：

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何使用 Aspose.BarCode **generate barcode image java**？

以下為完整工作流程。每一步皆以簡明文字說明，原始程式碼區塊保持不變。

### 步驟 1：定義資源目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您想要儲存條碼影像的絕對路徑。

### 步驟 2：實例化條碼物件

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

此處我們 **create code128 barcode java**，傳入 `EncodeTypes.CODE_128` 與資料字串 `"1234567"`。

### 步驟 3：設定條高（尺寸單位）

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` 方法以點為單位定義高度（1 點 = 1/72 英吋）。依您的版面需求調整此數值。

### 步驟 4：儲存影像

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()` 呼叫會將產生的條碼寫入先前指定的資料夾。影像格式會依檔案副檔名自動推斷（此例為 JPEG）。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **影像未建立** | `dataDir` 路徑不正確或缺乏寫入權限。 | 確認資料夾存在且應用程式具備寫入權限。 |
| **條碼顯示過小** | 以點為單位的條高對所選 DPI 而言太低。 | 增加傳入 `setPoint()` 的數值，或透過 `bb.getParameters().getImage().setResolution()` 調整影像 DPI。 |
| **不支援的字元** | CODE_128 只支援 ASCII；您傳入了 Unicode。 | 對非 ASCII 資料使用其他符號（例如 QR_CODE）。 |

## 常見問答

**Q: Aspose.BarCode for Java 是否同時支援條碼產生與辨識？**  
A: 是的，該函式庫支援廣泛符號的產生與辨識。

**Q: 我可以自訂產生的條碼影像外觀嗎？**  
A: 當然可以。您可以變更顏色、加入說明文字、調整邊距，甚至使用豐富的 `Parameters` API 嵌入商標。

**Q: 如何取得 Aspose.BarCode for Java 的臨時授權？**  
A: 前往[此處](httpshttps://purchase.aspose.com/temporary-license/) 申請臨時授權以進行評估。

**Q: 我可以在哪裡取得 Aspose.BarCode for Java 的支援？**  
A: Aspose.BarCode 社群論壇是最佳求助管道。請查看[論壇](https://forum.aspose.com/c/barcode/13) 取得答案或提出新問題。

**Q: Aspose.BarCode for Java 支援哪些條碼符號？**  
A: 函式庫支援數十種符號，包括 CODE_128、QR_CODE、UPC_A、DataMatrix、PDF417 等等。

---

**最後更新：** 2025-12-08  
**測試環境：** Aspose.BarCode for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}