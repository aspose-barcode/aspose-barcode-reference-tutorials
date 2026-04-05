---
date: 2026-04-05
description: 學習如何使用 Aspose.BarCode 在 Java 中產生條碼。本逐步指南展示動態條碼生成及將圖像儲存至串流。
keywords:
- how to generate barcode java
- dynamic barcode generation java
- save barcode image to streams
linktitle: 將條碼圖像儲存至串流
second_title: Aspose.BarCode Java API
title: 如何在 Java 中產生條碼：使用 Aspose.BarCode 儲存至串流
url: /zh-hant/java/advanced-settings-and-optimization/saving-barcode-image-streams/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.BarCode 將條碼圖像保存至串流

## 如何在 Java 中產生條碼 – 介紹

在本指南中，我們將向您展示 **如何在 Java 中產生條碼**，以高效應對不斷變化的 Java 程式開發環境。Aspose.BarCode for Java 作為一個強大的解決方案，提供在多種格式下無縫產生條碼的能力。本教學將帶領您將條碼圖像保存至串流，這是 **動態條碼產生 Java** 場景（如 Web API 與微服務）中的關鍵技術。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.BarCode for Java 將條碼圖像保存至 `ByteArrayOutputStream`。  
- **範例中使用哪種條碼類型？** CODE_128。  
- **示範的圖像格式為何？** JPEG。  
- **執行程式碼是否需要授權？** 免費試用可用於開發；商業授權則需於正式環境使用。  
- **我可以將此串流用於其他 API 嗎？** 可以，`ByteArrayOutputStream` 可傳遞給 Web 服務、儲存至資料庫，或寫入檔案。

## 前置條件

在深入本教學之前，請確保您已具備以下前置條件：

- Java 開發環境：在您的機器上設定 Java 開發環境。  
- Aspose.BarCode for Java：下載並安裝 Aspose.BarCode 程式庫。您可以在此找到程式庫 [here](https://releases.aspose.com/barcode/java/).

## 匯入命名空間

開始條碼產生之旅前，請匯入必要的命名空間：

```java
import java.io.ByteArrayOutputStream;
import java.io.IOException;

import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
```

## 步驟 1：建立條碼產生器

使用所需的編碼類型與資料，初始化 `BarcodeGenerator` 物件。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "123456");
```

## 步驟 2：產生條碼圖像

產生條碼圖像並將其保存至 `ByteArrayOutputStream`。

```java
ByteArrayOutputStream outStream = new ByteArrayOutputStream();
generator.save(outStream, BarCodeImageFormat.JPEG);
```

## 步驟 3：使用產生的條碼

此時，條碼圖像已存於 `ByteArrayOutputStream`（`outStream`）中。您現在可以在 Java 應用程式中依需求使用或進一步處理該圖像——無論是透過 HTTP 傳送、嵌入 PDF，或儲存至資料庫。

## 為何保存至串流？

將條碼保存至串流可讓其留在記憶體中，免除暫存檔案的需求。此方法特別適用於：

- **Web APIs** 需要直接在回應中返回條碼。  
- **Microservices** 必須盡量減少檔案 I/O 開銷。  
- **Dynamic content generation** 每個請求可能產生唯一條碼。

## 常見問題與技巧

- **OutOfMemoryError** – 若產生極大條碼，請考慮定期刷新串流或使用 `BufferedOutputStream`。  
- **Unsupported Format** – 確認所選的 `BarCodeImageFormat` 符合下游系統的支援（例如 PNG 用於無損需求）。  
- **License Exceptions** – 未使用有效授權執行可能會在產生的圖像上加上浮水印。

## 常見問答

### Q1：Aspose.BarCode 是否相容於所有 Java 開發環境？

A1：是的，Aspose.BarCode 設計為相容於各種 Java 開發環境。

### Q2：我可以自訂產生的條碼外觀嗎？

A2：當然！Aspose.BarCode 提供多種自訂選項，讓您依需求調整條碼外觀。

### Q3：是否提供 Aspose.BarCode for Java 的免費試用？

A3：是的，您可以在此探索免費試用 [here](https://releases.aspose.com/).

### Q4：如何取得 Aspose.BarCode for Java 的支援？

A4：請前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)。

### Q5：是否提供臨時授權給 Aspose.BarCode？

A5：是的，您可在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/).

### Q6：我可以將串流轉換為 Base64 字串以供 JSON API 使用嗎？

A6：是的，只需呼叫 `Base64.getEncoder().encodeToString(outStream.toByteArray())` 即可將圖像直接嵌入 JSON 載荷。

### Q7：此方法是否支援其他圖像格式，如 PNG 或 GIF？

A7：`save` 方法支援多種格式；請將 `BarCodeImageFormat.JPEG` 替換為 `BarCodeImageFormat.PNG` 或 `BarCodeImageFormat.GIF` 即可。

## 結論

Aspose.BarCode for Java 為 **如何在 Java 中產生條碼** 任務提供強大且彈性的解決方案。遵循本步驟指南，您即可輕鬆將條碼圖像保存至串流，實現動態條碼產生，並與現代 Java 應用程式無縫整合。

---

**Last Updated:** 2026-04-05  
**Tested With:** Aspose.BarCode 24.12 for Java  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}