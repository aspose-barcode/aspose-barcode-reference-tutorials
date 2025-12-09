---
date: 2025-12-04
description: 學習如何在 Java 中使用 Aspose.BarCode 產生條碼圖像，透過條碼產生 Java 範例示範儲存為 JPEG、PNG、GIF
  及其他格式。
linktitle: Saving Barcode Images to Different Formats
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 生成不同格式的條碼圖像
url: /zh-hant/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.BarCode 產生不同格式的條碼圖像

## 簡介

如果您正在尋找 **how to generate barcode** 圖像的快速且可靠的解決方案，Aspose.BarCode for Java 讓這變得輕而易舉。在本教學中，我們將逐步說明一個 **barcode generation Java example**，它會產生 Code‑128 條碼並將其儲存為多種常見的圖像格式——JPEG、PNG、GIF 以及 TIFF。完成後，您不僅會了解產生條碼的原理，還能僅透過一行程式碼就 **convert barcode to GIF** 或其他任何支援的格式。

## 快速答案

- **需要什麼函式庫？** Aspose.BarCode for Java  
- **支援的輸出格式？** JPEG、PNG、GIF、TIFF、BMP 等  
- **典型的實作時間？** 基本範例 5‑10 分鐘  
- **前置條件？** JDK 8+ 以及 classpath 中的 Aspose.BarCode JAR  
- **可以更換條碼類型嗎？** 可以——任何 Aspose.BarCode 支援的條碼類型  

## 什麼是 Java 中的條碼產生？

條碼產生是將字母與數字資料轉換為機器可讀的視覺圖案的過程。Java 開發人員常在庫存系統、票務或支付處理等情境中需要此功能。Aspose.BarCode 抽象化了低階編碼細節，讓您可以專注於業務邏輯。

## 為什麼要使用 Aspose.BarCode for Java？

- **Zero‑dependency API** – 無需本機函式庫或外部服務。  
- **High‑fidelity rendering** – 即使在高 DPI 下亦能產生清晰圖像。  
- **Broad format support** – 從點陣圖 (PNG、JPEG) 到向量圖 (SVG、PDF) 均受支援。  
- **Enterprise‑ready** – 為大量產生與多執行緒環境進行最佳化。  

## 前置條件

在開始之前，請確保您已具備：

- **Java Development Kit (JDK) 8 或更新版本** 已安裝且已設定 `JAVA_HOME`。  
- **Aspose.BarCode for Java** 函式庫已從 [official release page](https://releases.aspose.com/barcode/java/) 下載。  
- **Java IDE** 如 IntelliJ IDEA、Eclipse 或 VS Code（非必須但建議使用）。  

## 逐步指南

### 步驟 1：匯入必要的命名空間

首先，將必要的 import 加入您的 Java 類別中。這些 import 會載入 Aspose.BarCode 的核心類別以及標準 I/O 工具。

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

> **專業提示：** 保持 import 的組織性；這樣程式碼更易閱讀，也能避免意外的名稱衝突。

### 步驟 2：設定資源目錄路徑

定義一個用來儲存產生圖像的資料夾。將佔位符替換為您機器上實際存在的絕對或相對路徑。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

> **為什麼重要：** 集中管理輸出位置可簡化清理工作，且讓您在多個範例中重複使用相同路徑。

### 步驟 3：實例化條碼產生器

建立一個 `BarcodeGenerator` 物件，指定條碼類型（此處為 `CODE_128`）並提供要編碼的資料。

```java
// Instantiate barcode object, set the symbology type to Code128 and set the code text.
BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "1234567");
```

您可以根據需求將 `EncodeTypes.CODE_128` 替換為任何其他支援的類型（例如 `QR`、`EAN_13`、`PDF_417`）。

### 步驟 4：以所需格式儲存條碼圖像

Aspose.BarCode 允許您透過 `BarCodeImageFormat` 列舉選擇輸出格式。以下範例將圖像儲存為 JPEG；將列舉值改為 `PNG`、`GIF`、`TIFF` 等，即可 **convert barcode to GIF** 或其他格式。

```java
// Save the image to your system and set its image format to JPEG.
bb.save(dataDir + "barcode-image-format.jpg", BarCodeImageFormat.JPEG);
```

**範例變化**

| 目標格式 | Enum value |
|----------|------------|
| PNG | `BarCodeImageFormat.PNG` |
| GIF | `BarCodeImageFormat.GIF` |
| TIFF | `BarCodeImageFormat.TIFF` |
| BMP | `BarCodeImageFormat.BMP` |

只需將 `BarCodeImageFormat.JPEG` 替換為相應的列舉，並在檔名中調整副檔名即可。

## 常見使用情境

- **庫存管理** – 即時產生產品條碼以供標籤使用。  
- **票務系統** – 建立包含活動資訊的 QR 或 Code‑128 票券。  
- **支付處理** – 將付款代碼（例如 GS1 DataBar）嵌入收據。  
- **文件自動化** – 在 PDF、發票或裝運清單中加入條碼。  

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| `save` 時出現 *FileNotFoundException* | 確認 `dataDir` 指向已存在的資料夾，且應用程式具有寫入權限。 |
| 條碼顯示模糊 | 在儲存前呼叫 `bb.getParameters().setResolution(300);` 提高 DPI。 |
| 輸出錯誤的條碼類型 | 確認您為資料格式使用了正確的 `EncodeTypes` 列舉值。 |
| 需要透明背景 | 使用 `BarCodeImageFormat.PNG`，並設定 `bb.getParameters().setBackgroundColor(Color.getTransparent());` |

## 常見問答

**Q1: 我可以自訂產生的條碼外觀嗎？**  
A: 可以。Aspose.BarCode 提供字型、顏色、邊距等屬性，甚至可在條碼下方加入說明文字。

**Q2: Aspose.BarCode 適用於大規模應用嗎？**  
A: 絕對適用。它針對高吞吐量情境設計，在多執行緒環境下每秒可產生數千個條碼。

**Q3: Aspose.BarCode 的更新頻率如何？**  
A: 此函式庫會定期推出新條碼類型、效能提升與錯誤修正等更新。請參閱 [official documentation](https://reference.aspose.com/barcode/java/) 取得最新發行說明。

**Q4: 我可以在購買前試用 Aspose.BarCode 嗎？**  
A: 可以——在 [Aspose download page](https://releases.aspose.com/) 提供完整功能的免費試用版，讓您在未取得授權前評估所有功能。

**Q5: 我可以在哪裡取得社群支援？**  
A: 前往 [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13) 獲得同儕協助、範例程式碼，以及 Aspose 團隊的官方回覆。

## 結論

現在您已掌握完整的 **how to generate barcode** 教學，涵蓋使用 Aspose.BarCode for Java 建立 Code‑128 條碼並儲存為多種圖像格式。只需幾行程式碼，即可 **convert barcode to GIF**、PNG、TIFF 或其他任何支援的類型，讓條碼產生成為 Java 應用程式的無縫功能。探索其他條碼類型、嘗試不同的渲染選項，並將此程式碼片段整合至更大的工作流程，如庫存系統或自動化文件管線。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}