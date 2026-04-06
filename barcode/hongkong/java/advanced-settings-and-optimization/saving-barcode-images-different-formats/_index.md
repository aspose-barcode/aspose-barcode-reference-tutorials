---
date: 2026-02-04
description: 學習如何在 Java 中使用 Aspose.BarCode 建立 Code128 條碼圖像，這是一個產生條碼的 Java 範例，示範如何儲存為
  JPEG、PNG、GIF 及其他格式。
linktitle: Saving Barcode Images to Different Formats
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 生成 Code128 條碼圖像
url: /zh-hant/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.BarCode 建立 code128 條碼影像

## 介紹

如果您正在尋找 **how to generate barcode** 影像，想在 Java 應用程式中快速且可靠地產生，Aspose.BarCode for Java 讓這變得輕鬆。在本教學中，我們將示範一個 **barcode generation Java example**，它 **creates a Code‑128 barcode**，並將其儲存為多種常見影像格式——JPEG、PNG、GIF 與 TIFF。完成本指南後，您將清楚知道如何 **create code128 barcode** 檔案、將其轉換為 GIF、PNG 或任何其他支援的格式，並將此流程整合至更大的 Java 專案中。

## 快速回答
- **需要什麼函式庫？** Aspose.BarCode for Java  
- **支援的輸出格式？** JPEG、PNG、GIF、TIFF、BMP 等等  
- **典型實作時間？** 基本範例約 5‑10 分鐘  
- **先決條件？** JDK 8+ 以及 classpath 中的 Aspose.BarCode JAR  
- **可以更改條碼類型嗎？** 可以——任何 Aspose.BarCode 支援的條碼類型  

## 如何在 Java 中建立 code128 條碼

一旦引用函式庫，建立 **code128 barcode** 只需要三行程式碼。以下我們將逐步說明每個步驟、解釋其重要性，並示範如何插入您自己的資料。

## 什麼是 Java 中的條碼產生？

條碼產生是將字母數字資料轉換為機器可讀的視覺圖案的過程。Java 開發人員常在庫存系統、票務或付款處理等情境需要此功能。Aspose.BarCode 抽象化了底層編碼細節，讓您專注於業務邏輯。

## 為什麼使用 Aspose.BarCode for Java？

- **Zero‑dependency API** – 無需原生函式庫或外部服務。  
- **High‑fidelity rendering** – 即使在高 DPI 下亦能產生清晰影像。  
- **Broad format support** – 支援從點陣圖 (PNG、JPEG) 到向量圖 (SVG、PDF)。  
- **Enterprise‑ready** – 為大量產生與多執行緒環境最佳化。  

## 先決條件

在開始之前，請確保您已具備以下條件：

- **Java Development Kit (JDK) 8 或更新版本** 已安裝，且已設定 `JAVA_HOME`。  
- **Aspose.BarCode for Java** 函式庫已從[官方發佈頁面](https://releases.aspose.com/barcode/java/)下載。  
- **Java IDE**（如 IntelliJ IDEA、Eclipse 或 VS Code），非必須但建議使用。  

## 逐步指南

### 步驟 1：匯入必要的命名空間

首先，將必要的匯入加入您的 Java 類別中。這些匯入提供了 Aspose.BarCode 的核心類別以及標準 I/O 工具。

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

> **小技巧：** 保持匯入的組織性；這樣程式碼更易閱讀，且可避免意外的名稱衝突。

### 步驟 2：設定資源目錄路徑

定義一個用於儲存產生影像的資料夾。將佔位符替換為您機器上實際存在的絕對或相對路徑。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

> **為什麼重要：** 集中管理輸出位置可簡化清理，且讓您在多個範例中重複使用相同路徑。

### 步驟 3：實例化條碼產生器

建立一個 `BarcodeGenerator` 物件，指定條碼類型（此處為 `CODE_128`），並提供要編碼的資料。

```java
// Instantiate barcode object, set the symbology type to Code128 and set the code text.
BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "1234567");
```

您可以根據使用情境，將 `EncodeTypes.CODE_128` 替換為任何其他支援的類型（例如 `QR`、`EAN_13`、`PDF_417`）。

### 步驟 4：以所需格式儲存條碼影像

Aspose.BarCode 允許您透過 `BarCodeImageFormat` 列舉選擇輸出格式。以下範例將影像儲存為 JPEG；若要 **convert barcode to GIF** 或其他格式，只需將列舉值改為 `PNG`、`GIF`、`TIFF` 等。

```java
// Save the image to your system and set its image format to JPEG.
bb.save(dataDir + "barcode-image-format.jpg", BarCodeImageFormat.JPEG);
```

**範例變體**

| 所需格式 | 列舉值                         |
|----------|--------------------------------|
| PNG      | `BarCodeImageFormat.PNG`       |
| GIF      | `BarCodeImageFormat.GIF`       |
| TIFF     | `BarCodeImageFormat.TIFF`      |
| BMP      | `BarCodeImageFormat.BMP`       |

只需將 `BarCodeImageFormat.JPEG` 替換為相應的列舉，並在檔名中調整檔案副檔名。

## 大量條碼產生

當需要產生數百或數千張標籤時，您可以將上述步驟放入迴圈，並重複使用同一個 `BarcodeGenerator` 實例。Aspose.BarCode 為執行緒安全，您亦可使用 Java 的 `ExecutorService` 進行平行化，以實現 **bulk barcode generation** 而不犧牲效能。

## 常見使用情境

- **Inventory management** – 即時產生商品條碼以供標籤使用。  
- **Ticketing systems** – 建立包含活動資訊的 QR 或 Code‑128 票券。  
- **Payment processing** – 將付款代碼（例如 GS1 DataBar）嵌入收據。  
- **Document automation** – 在 PDF、發票或裝運清單中加入條碼。  

## 常見問題與解決方案

| 問題                              | 解決方案                                                                 |
|-----------------------------------|--------------------------------------------------------------------------|
| *FileNotFoundException* 在 `save` 時 | 確保 `dataDir` 指向已存在的資料夾，且應用程式具有寫入權限。 |
| 條碼顯示模糊                       | 在儲存前呼叫 `bb.getParameters().setResolution(300);` 提高 DPI。 |
| 條碼類型輸出錯誤                   | 確認您使用了正確的 `EncodeTypes` 列舉值對應資料格式。 |
| 需要透明背景                       | 使用 `BarCodeImageFormat.PNG`，並設定 `bb.getParameters().setBackgroundColor(Color.getTransparent());` |

## 常見問與答

**Q1: 可以自訂產生的條碼外觀嗎？**  
A: 可以。Aspose.BarCode 提供字型、顏色、邊距等屬性，甚至可在條碼下方加入說明文字。

**Q2: Aspose.BarCode 適用於大規模應用嗎？**  
A: 絕對適用。它針對高吞吐量情境設計，在多執行緒環境下每秒可產生數千個條碼。

**Q3: Aspose.BarCode 的更新頻率為何？**  
A: 此函式庫會定期推出新條碼類型、效能提升與錯誤修正的更新。請參閱[官方文件](https://reference.aspose.com/barcode/java/)以取得最新發行說明。

**Q4: 可以在購買前試用 Aspose.BarCode 嗎？**  
A: 可以——在[Aspose 下載頁面](https://releases.aspose.com/)提供完整功能的免費試用，讓您在未取得授權前評估所有功能。

**Q5: 哪裡可以取得社群支援？**  
A: 前往[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)取得同儕協助、範例程式碼，以及 Aspose 團隊的官方回覆。

## 結論

您現在已掌握完整的 **how to generate barcode** 教學，涵蓋使用 Aspose.BarCode for Java 建立 **Code‑128 barcode** 並儲存為多種影像格式。只需幾行程式碼，即可 **convert barcode to GIF**、PNG、TIFF 或其他支援類型，讓條碼產生成為 Java 應用程式的無縫部份。可嘗試其他條碼類型、調整渲染選項，並將此程式碼片段嵌入至更大的工作流程，例如庫存系統或自動化文件管線。

---

**最後更新：** 2026-02-04  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}