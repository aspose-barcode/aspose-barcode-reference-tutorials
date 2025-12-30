---
date: 2025-12-30
description: 學習如何使用 Aspose.BarCode 於 Java 產生條碼。本分步指南將示範如何設定自訂條碼文字、調整寬度，並儲存影像。
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 生成條碼 Java：使用 Aspose.BarCode 設定條碼文字
url: /zh-hant/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生條碼 Java：使用 Aspose.BarCode 設定條碼文字

## 介紹

在本教學中，您將學習如何使用 Aspose.BarCode Java 函式庫 **產生條碼 Java**。無論您是在建構庫存系統、文件追蹤解決方案，或任何需要條碼的應用程式，本指南都會一步步帶您完成——從建立 **Code128** 條碼，到自訂條碼文字與調整條寬。完成後，您將得到一張可直接嵌入任意位置的圖像。

## 快速回答
- **應該使用哪個函式庫？** Aspose.BarCode for Java。
- **示範的條碼類型是什麼？** CODE_128。
- **如何設定自訂條碼文字？** 使用 `BarcodeGenerator` 建構子或 `setCodeText` 方法。
- **可以調整條寬嗎？** 可以，透過以毫米為單位的 `XDimension` 設定。
- **正式環境需要授權嗎？** 需要，必須購買商業授權。

## 前置條件

在開始教學之前，請確保您已具備以下條件：

- 基本的 Java 程式設計知識。  
- 已安裝可運作的 Java 開發環境。  
- Aspose.BarCode for Java 函式庫。您可以在 **[此處](https://releases.aspose.com/barcode/java/)** 下載。  
- 文字編輯器，例如 IntelliJ IDEA 或 Eclipse。  

## 匯入套件

先在 Java 專案中匯入必要的套件。這些套件是使用 Aspose.BarCode 所必需的。

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

接下來，我們將說明如何在 Java 中使用 Aspose.BarCode 設定條碼文字。請依照以下步驟操作：

## 條碼產生器教學：建立 Code128 條碼

### 步驟 1：建立 `BarcodeGenerator` 實例

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

此處，我們建立一個 `BarcodeGenerator` 實例，指定條碼符號 (**CODE_128**) 與 **自訂條碼文字** `"12345678"`。

### 步驟 2：為自訂條碼文字調整條寬

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

依需求調整條寬。在此範例中，我們將條碼寬度 **調整為** `0.5` mm，這在大多數標籤尺寸下都相當適合。

### 步驟 3：儲存條碼影像

```java
generator.save(dataDir + "setCodeText.jpg");
```

將產生的條碼影像儲存至指定目錄。此例中，檔案會以 **`setCodeText.jpg`** 的名稱儲存在您的文件目錄下。

## 為什麼選擇 Aspose.BarCode for Java？

- **完整的 API** – 支援超過 60 種條碼符號，包括 Code128、QR、DataMatrix 等。  
- **高品質渲染** – 可產生 PNG、JPEG、SVG、PDF 等清晰影像。  
- **簡易客製化** – 只需幾行程式碼即可變更文字、尺寸、顏色，甚至加入可讀文字說明。  
- **跨平台** – 可在 Windows、Linux、macOS 上執行，支援任何 Java 8+ 執行環境。

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| **條碼模糊** | 提高影像解析度或匯出為向量格式（SVG、PDF）。 |
| **文字被截斷** | 確認 `XDimension`（條寬）與 `BarHeight` 足夠容納所選符號。 |
| **授權未套用** | 將授權檔案 (`Aspose.BarCode.lic`) 放置於專案根目錄，並使用 `License license = new License(); license.setLicense("Aspose.BarCode.lic");` 載入。 |

## 常見問答 (FAQs)

### 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？
可以，Aspose.BarCode for Java 為商業產品。授權資訊請參閱 **[此處](https://purchase.aspose.com/buy)**。

### 有提供免費試用嗎？
有，您可以在 **[此處](https://releases.aspose.com/)** 取得免費試用版。

### 哪裡可以找到 Aspose.BarCode for Java 的文件？
文件位於 **[此處](https://reference.aspose.com/barcode/java/)**。

### 如何取得 Aspose.BarCode for Java 的技術支援？
請前往 **[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)** 取得支援。

### 可以使用臨時授權進行測試嗎？
可以，臨時授權可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得。

## 其他常見問答

**Q:** *`CODE_128` 與其他 Code128 變體有何差異？*  
**A:** `CODE_128` 為標準符號，會根據輸入文字自動選擇最有效的編碼方式（A、B 或 C）。

**Q:** *我可以將輸出格式改為 PNG 而非 JPEG 嗎？*  
**A:** 當然可以。使用 `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`。

**Q:** *能否在條碼下方加入可讀文字說明？*  
**A:** 可以。設定 `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` 並指定說明文字。

**Q:** *Aspose.BarCode 支援 Unicode 字元嗎？*  
**A:** 支援。請以 UTF‑8 提供文字，並確保所選符號支援該字元集。

**Q:** *如何在迴圈中產生多筆條碼？*  
**A:** 在迴圈內建立新的 `BarcodeGenerator`，為每次迭代設定文字，並以唯一檔名呼叫 `save`。

---

**最後更新：** 2025-12-30  
**測試環境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}