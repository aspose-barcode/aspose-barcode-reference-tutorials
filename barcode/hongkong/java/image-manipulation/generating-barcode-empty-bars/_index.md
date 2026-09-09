---
date: 2026-04-12
description: 學習如何使用 Aspose.BarCode 在 Java 中建立帶有空白條的 Code128 條碼。本指南將教您快速產生 Java 條碼圖像。
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: 生成帶空條的條碼
second_title: Aspose.BarCode Java API
title: 如何在 Java 中創建帶空白條的 Code128 條碼
url: /zh-hant/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中建立帶空白條的 Code128 條碼

## 簡介

將條碼產生整合到 Java 應用程式中是常見需求，無論您是構建庫存系統、票務平台，或是 POS 解決方案。使用 **Aspose.BarCode for Java**，您只需幾行程式碼即可 **create Code128 barcode** 圖片。在本教學中，我們將逐步說明如何 **generate barcode Java** 圖片，讓條碼呈現空白（未填充）條，讓您完整掌控條碼的視覺樣式。

## 快速答覆
- **Which library?** Aspose.BarCode for Java  
- **Primary use case?** 建立帶空白條的 Code128 條碼，用於自訂 UI 設計  
- **Prerequisites?** Java JDK 8+、Aspose.BarCode JAR、寫入權限至儲存輸出圖像的資料夾  
- **Typical implementation time?** 基本範例約需 5‑10 分鐘  
- **Can I customize colors?** 是 – API 提供廣泛的樣式選項  

## 什麼是 Code128 條碼？

Code128 是一種高密度線性條碼符號，可編碼完整的 ASCII 字元集。它廣泛應用於物流、運輸與零售，因為能緊湊地表示字母數字資料。預設情況下，Aspose.BarCode 會將 Code128 條碼繪製為實心矩形；將 **FilledBars** 屬性設為 `false` 後，條碼會變為空心（輪廓）條，這對於品牌樣式非常有用。

## 為何使用 Aspose.BarCode for Java？

- **Rich feature set** – 支援超過 50 種條碼類型，包括 QR、DataMatrix 與 PDF417。  
- **No external dependencies** – 單一 JAR 可在任何 Java 執行環境上運行。  
- **Fine‑grained control** – 您可以調整條寬、顏色、字型，以及 `FilledBars` 屬性。  
- **Cross‑platform** – 可在 Windows、Linux 與 macOS 上執行，且不需原生函式庫。  

## 先決條件

在開始之前，請確保您已具備以下條件：

1. **Java Development Environment** – 已安裝 JDK 8 或更新版本，且已設定 `JAVA_HOME`。  
2. **Aspose.BarCode for Java** – 從[download page](https://releases.aspose.com/barcode/java/) 下載最新的 JAR。  
3. **Document Directory** – 電腦上用於儲存產生的條碼圖像的資料夾。  

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的類別：

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

這些匯入讓您能使用條碼產生器、影像格式列舉以及例外處理。

## 步驟 1：設定資源目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您在先決條件中建立的資料夾的絕對路徑。此路徑即為 PNG 檔案寫入的位置。

## 步驟 2：建立 Code128 條碼產生器實例

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

此處我們以 **CODE_128** 符號和範例文字 `"TEXT"` 來實例化 `BarcodeGenerator`。這是一個 **barcode generator Java example**，您可以依需求調整為任意要編碼的字串。

## 步驟 3：將 FilledBars 屬性設為 False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

將 `FilledBars` 設為 `false` 後，產生的條碼將顯示空心條而非實心條，達成我們想要的視覺效果。

## 步驟 4：儲存條碼圖像

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

`save` 方法會將條碼以 PNG 格式寫入指定目錄。若需其他影像類型，可將 `BarCodeImageFormat.PNG` 改為 `JPG`、`BMP` 或 `TIFF`。

## 常見使用情境

- **Custom branding** – 空心條可與背景圖案或顏色疊加，用於自訂品牌。  
- **Print‑ready assets** – 產生高解析度 PNG，供發票或運送標籤使用。  
- **Dynamic generation** – 於 Web 服務或桌面應用程式即時產生條碼。  

## 故障排除提示

- **Invalid path** – 確保 `dataDir` 以檔案分隔符 (`/` 或 `\\`) 結尾，或使用 `File.separator` 進行串接。  
- **License required** – 試用版可用於評估，但正式環境需購買完整授權。  
- **Unsupported characters** – Code128 支援完整 ASCII 集合；除非改用其他符號，否則請避免使用 Unicode 字元。  

## 結論

您現在已學會如何使用 Aspose.BarCode for Java **create Code128 barcode** 圖像，並呈現空心條。此簡易方法可快速產生可自訂的條碼圖形，無論是桌面庫存工具或雲端 API 都適用。

## 常見問答

### Aspose.BarCode 是否相容於所有 Java 開發環境？

是，Aspose.BarCode 設計為可無縫整合至任何 Java IDE 或建置系統，包括 Maven、Gradle 以及純 JAR 專案。

### 我可以自訂產生的條碼外觀嗎？

當然可以！除了 `FilledBars`，您還能使用豐富的 API 調整顏色、條寬、邊距，甚至加入可讀文字。

### Aspose.BarCode 是否提供試用版？

是，您可透過[此處](https://releases.aspose.com/) 取得免費試用版，探索 Aspose.BarCode 的功能。

### 我該如何取得 Aspose.BarCode 的支援？

如有任何問題或需要協助，請前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)。

### 我在哪裡可以找到 Aspose.BarCode 的詳細文件？

完整文件可在[此處](https://reference.aspose.com/barcode/java/) 取得。

**其他問題**

**Q: 如何以不同格式（例如 JPEG）產生條碼圖像？**  
A: 將 `save` 的第二個參數改為 `BarCodeImageFormat.JPEG`。

**Q: 我可以在迴圈中產生多個條碼嗎？**  
A: 是 – 在迴圈內實例化新的 `BarcodeGenerator`，或使用相同實例並設定新的 `CodeText`。

---

**最後更新：** 2026-04-12  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}