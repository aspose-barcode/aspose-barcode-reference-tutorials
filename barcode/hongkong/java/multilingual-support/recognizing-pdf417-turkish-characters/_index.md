---
date: 2026-04-23
description: 學習如何在 Java 中使用 Aspose.BarCode 讀取含有土耳其字元的 PDF417 條碼。本指南展示快速的 PDF417 條碼讀取器
  Java 設定，確保可靠的解碼。
keywords:
- how to read pdf417
- pdf417 barcode reader java
- Turkish characters barcode
- Aspose.BarCode Java
linktitle: 辨識含土耳其字符的 PDF417 條碼
second_title: Aspose.BarCode Java API
title: 在 Java 中讀取含土耳其字元的 PDF417 條碼
url: /zh-hant/java/multilingual-support/recognizing-pdf417-turkish-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中讀取含有土耳其字元的 PDF417 條碼

## 介紹

如果您需要 **讀取 PDF417** 條碼且其中包含土耳其字元，您來對地方了。在本教學中，我們將透過 Aspose.BarCode for Java 示範完整的端對端範例。您將看到如何建立 **PDF417 barcode reader Java** 專案、載入影像，並解碼資料，使特殊的土耳其字元正確顯示。

## 快速解答
- **建議使用哪個函式庫？** Aspose.BarCode for Java  
- **哪個方法讀取 PDF417？** `BarCodeReader` 搭配 `DecodeType.PDF_417`  
- **土耳其字元如何處理？** 使用 `windows-1254` 字元集解碼位元組陣列  
- **生產環境需要授權嗎？** 是 – 必須取得商業授權  
- **可以免費試用嗎？** 可從 Aspose 取得免費試用版  

## 什麼是 PDF417 以及為何在土耳其字元中使用它？

PDF417 是一種堆疊式線性條碼格式，可儲存大量資料，包括 Unicode 文字。它常用於登機證、身分證與物流標籤。當編碼的文字包含土耳其字元（ğ、ş、İ 等）時，必須使用正確的代碼頁解碼位元組，否則字元會顯示為亂碼。

## 前置條件

在深入程式碼之前，請確保您已具備：

- **Java 開發環境** – 已安裝 JDK 8 或以上版本。  
- **Aspose.BarCode for Java** – 從官方網站 **[here](https://releases.aspose.com/barcode/java/)** 下載函式庫。  
- 含有土耳其字元編碼的 PDF417 條碼影像檔 (`barcode.png`)。

## 匯入套件

在您的 Java 專案中，加入使用 Aspose.BarCode 所需的套件：

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 設定 PDF417 條碼讀取器 Java 專案

### 步驟 1：建立新的 Java 專案並加入函式庫

如果尚未加入 Aspose.JAR 檔案，請從 **[this link](https://releases.aspose.com/barcode/java/)** 下載，並將其加入專案的 classpath。

### 步驟 2：載入條碼影像

定義保存條碼影像的資料夾路徑，並實例化讀取器：

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

### 步驟 3：讀取並解碼條碼

遍歷偵測到的條碼，使用 Windows‑1254 字元集（土耳其的代碼頁）將原始位元組轉換為字串，並輸出結果：

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("windows-1254").decode(bytebuf).toString());
}
```

上述程式碼片段讀取 PDF417 條碼，並正確顯示土耳其字元，例如 **ç、ğ、ş、İ**。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| 字元亂碼 | 使用了錯誤的字元集 | 使用 `windows-1254` 以支援土耳其語，或若條碼以 UTF-8 編碼則使用 `UTF-8` |
| 未偵測到條碼 | 影像品質過低 | 確保影像為高解析度且未模糊 |
| `NullPointerException` | 檔案路徑不正確 | 確認 `dataDir` 指向正確的資料夾 |

## 常見問答

### Aspose.BarCode 是否相容於不同的條碼類型？

是的，Aspose.BarCode 支援多種條碼類型，包括 PDF417。

### 我可以在商業專案中使用 Aspose.BarCode 嗎？

當然可以。Aspose.BarCode 提供彈性的授權模式，適用於個人與商業使用。請前往 **[here](https://purchase.aspose.com/buy)** 了解授權選項。

### 是否提供免費試用？

是的，您可以在 **[here](https://releases.aspose.com/)** 取得免費試用版。

### 如何取得 Aspose.BarCode 的支援？

前往 **[Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13)** 取得社群支援，或參考文件 **[here](https://reference.aspose.com/barcode/java/)**。

### 我可以在開發期間使用臨時授權嗎？

可以，您可在 **[here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

### 如果我要解碼其他語言該怎麼辦？

在呼叫 `Charset.forName(...)` 時，選擇適當的字元集（例如 `windows-1252` 用於西歐語系，`UTF-8` 用於 Unicode）。

## 結論

使用 Aspose.BarCode for Java，**如何讀取 PDF417** 含有土耳其字元的條碼變得相當簡單。只要建立 **PDF417 barcode reader Java** 專案、載入影像，並以正確的字元集解碼位元組，即可在任何業務流程中可靠地擷取多語言資料。

---

**最後更新：** 2026-04-23  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}