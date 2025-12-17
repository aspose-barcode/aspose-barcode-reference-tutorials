---
date: 2025-12-17
description: 學習如何使用 Aspose.BarCode 在 Java 中生成條碼，涵蓋動態條碼生成、建立 EAN‑13 條碼以及儲存帶有補充資料的條碼圖像。
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: 如何在 Java 中生成帶有補充資料的條碼
url: /zh-hant/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中產生帶有補充資料的條碼

## 介紹

在當今快速變遷的數位生態系統中，**如何產生條碼**效率高是許多 Java 開發者面臨的問題。Aspose.BarCode for Java 提供功能強大且易於使用的 API，支援**動態條碼產生**，包括建立帶有補充資料的**EAN‑13 條碼**。無論您是構建庫存系統、零售 POS 應用程式，或是物流追蹤器，本教學都會一步步說明 **java 條碼產生器範例**，將條碼影像儲存至磁碟，並讓您自訂補充部分。

## 快速回答
- **哪個函式庫最適合在 Java 中產生條碼？** Aspose.BarCode for Java。  
- **哪種符號能產生 13 位數字條碼？** EAN‑13。  
- **我可以在 EAN‑13 條碼加入補充資料嗎？** 可以，使用 `Supplement` API。  
- **如何將產生的條碼儲存為影像？** 呼叫 `generator.save("path/filename.jpg")`。  
- **正式環境是否需要授權？** 需要商業授權；亦提供免費試用版。

## 什麼是 Java 中的條碼產生？

條碼產生是將資料（數字、字母或混合）轉換為掃描器可讀取的視覺圖案。使用 Aspose.BarCode，您可以即時產生**高解析度條碼影像**，非常適合**動態條碼產生**的情境，如即時票務或訂單履行。

## 為何使用 Aspose.BarCode 進行動態條碼產生？

- **完整控制** 符號、尺寸、顏色與補充資料。  
- **無外部相依** – 純 Java，適用於任何平台。  
- **內建支援** 數十種條碼類型，包含**create ean13 barcode**。  
- **簡易 API** 只需一行程式碼即可**save barcode image**。

## 前置條件

在開始之前，請確保您已具備：

- **Java Development Kit (JDK)** – 任意近期版本（8 或以上）。  
- **IDE** – IntelliJ IDEA、Eclipse，或您喜愛的編輯器。  
- **Aspose.BarCode for Java** – 從官方網站 **[此處](https://releases.aspose.com/barcode/java/)** 下載函式庫，並將 JAR 加入專案的 classpath。

## 匯入套件

引用函式庫後，匯入負責條碼產生的核心類別。

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步驟說明

### 步驟 1：定義文件目錄

設定產生的影像要存放的資料夾。

```java
String dataDir = "Your Document Directory";
```

### 步驟 2：建立 Barcode Generator 實例

以欲使用的 **codetext** 與 **symbology** 建立 `BarcodeGenerator`。此處我們使用數字字串 `"123456789123"` **create ean13 barcode**。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### 步驟 3：設定補充資料

加入 5 位數的補充字串。此功能適用於雜誌、期刊，或任何需要在主條碼後附加額外資訊的情境。

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### 步驟 4：設定補充間距

調整主條碼與補充條碼之間的間距。數值以點 (points) 為單位。

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### 步驟 5：儲存條碼影像

最後，將影像寫入磁碟。檔案格式會根據副檔名自動推斷（此例為 JPEG）。

```java
generator.save(dataDir + "supplementData.jpg");
```

> **專業提示：** 您可以將副檔名改為 `.png` 或 `.bmp`，即可在不修改程式碼的情況下取得不同的影像格式。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **影像未儲存** | `dataDir` 指向不存在的資料夾 | 確認目錄已存在，或以程式碼建立 (`new File(dataDir).mkdirs();`)。 |
| **補充長度無效** | EAN‑13 補充必須為 2 或 5 位 | 必須提供恰好 2 或 5 個字元，否則會拋出例外。 |
| **不支援的字元** | EAN‑13 codetext 含非數字字元 | EAN‑13 只能使用 0‑9，若需字母請改用其他符號。 |

## 常見問答

### Aspose.BarCode 是否相容所有 Java 版本？
Aspose.BarCode for Java 設計上相容多種 Java 版本。請參考 **[文件](https://reference.aspose.com/barcode/java/)** 取得詳細資訊。

### 我可以自訂產生條碼的外觀嗎？
可以，Aspose.BarCode 提供多種參數與設定，讓您自訂條碼外觀。請參閱文件以取得完整說明。

### 有提供試用版嗎？
有，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用版。

### 如何取得 Aspose.BarCode 的支援？
前往 **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** 向社群與專家尋求協助。

### 哪裡可以購買 Aspose.BarCode for Java？
您可於 **[此處](https://purchase.aspose.com/buy)** 購買。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}