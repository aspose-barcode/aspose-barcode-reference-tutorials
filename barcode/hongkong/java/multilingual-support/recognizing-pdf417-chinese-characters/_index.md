---
date: 2025-12-25
description: 學習如何從條碼圖像中提取文字，特別是包含中文字符的 PDF417，使用 Aspose.BarCode for Java。請參考我們的逐步指南，有效讀取條碼資料。
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 從條碼提取文字：Java 中的 PDF417 中文字符
url: /zh-hant/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從條碼提取文字：Java 中的 PDF417 中文字符

## 介紹

將條碼識別整合到 Java 應用程式中是一項寶貴的技能，特別是當您需要 **從條碼提取文字** 並且圖像包含多語言資料時。在本教學中，我們將帶您使用 Aspose.BarCode for Java 來辨識含有中文字符的 PDF417 條碼。完成後，您將清楚知道如何讀取條碼資料並將其解碼為可讀的文字。

## 快速回答
- **哪個函式庫支援含中文字符的 PDF417？** Aspose.BarCode for Java.  
- **中文解碼需要使用哪種字元集？** MS936（GBK）。  
- **正式環境是否需要授權？** 是，需要商業授權。  
- **可以在任何 Java 版本上執行嗎？** 可在 Java 8 及更新版本上執行。  
- **是否提供免費試用？** 當然可以——可從 Aspose 官方網站下載。

## 什麼是「從條碼提取文字」？

從條碼提取文字是指將編碼資料轉換回原始的可供人類閱讀的形式。對於儲存中文字符的 PDF417 條碼，還需要選擇正確的字元編碼，以確保位元組對應到正確的字形。

## 為什麼使用 Aspose.BarCode for Java？

Aspose.BarCode 為廣泛的條碼符號（包括 PDF417）提供強大的支援，且能直接處理複雜的字元集。它抽象化了底層的影像處理，讓您專注於業務邏輯，而不必糾結於解碼的細節。

## 前置條件

在開始之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 建議使用最新版本。  
2. **Aspose.BarCode for Java** – 從 [此處](https://releases.aspose.com/barcode/java/) 下載。  
3. **一張包含中文字符的 PDF417 條碼影像**（例如 `barcode.png`）。

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的類別：

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 步驟 1：設定文件目錄

指定條碼影像所在的資料夾：

```java
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您機器上的實際路徑。

## 步驟 2：載入條碼影像

建立指向 PNG 檔案的 `BarCodeReader` 實例，並告訴讀取器搜尋 PDF417 符號：

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## 步驟 3：讀取條碼

遍歷偵測結果，取得原始位元組陣列，並使用 GBK（MS936）字元集進行解碼：

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

此迴圈 **從條碼提取文字**，並將解碼後的中文字符印至主控台。

## 如何使用 PDF417 讀取條碼？

上述程式碼示範了 **如何逐步讀取條碼** 資料：

1. **初始化** 讀取器，使用正確的 `DecodeType`。  
2. **遍歷** 每個返回的 `BarCodeResult`。  
3. **轉換** 原始位元組，使用相應的字元集（中文使用 `MS936`）。

如果條碼包含其他語言，只需將字元集切換為符合您資料的相應編碼即可。

## 常見問題與解決方案

| 問題 | 解決方案 |
|------|----------|
| 解碼後出現亂碼 | 確認使用正確的字元集（GBK 使用 `MS936`）。 |
| 未偵測到條碼 | 確保影像品質良好且條碼未旋轉；如有需要可先行前處理影像。 |
| 返回多個結果 | PDF417 可儲存多段資料；如示範般遍歷所有結果。 |

## 常見問答 (FAQs)

### 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？

是的，您可以在商業專案中使用 Aspose.BarCode for Java。授權細節請參閱 [此處](https://purchase.aspose.com/buy)。

### 是否提供免費試用？

是的，您可於 [此處](https://releases.aspose.com/) 取得 Aspose.BarCode for Java 的免費試用版。

### 如何取得 Aspose.BarCode 的支援？

請前往 Aspose.BarCode 論壇 [此處](https://forum.aspose.com/c/barcode/13) 獲得支援或諮詢。

### 我可以取得測試用的臨時授權嗎？

可以，請至 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 文件在哪裡可以找到？

文件可於 [此處](https://reference.aspose.com/barcode/java/) 取得。

**Additional Q&A**

**問：如果我的條碼影像是 JPEG 格式怎麼辦？**  
答：`BarCodeReader` 支援 JPEG、PNG、BMP 及其他常見影像格式——只需相應更改檔案副檔名即可。

**問：我可以從串流而非檔案解碼條碼嗎？**  
答：可以，您可以將 `InputStream` 傳入 `BarCodeReader` 建構子，以即時解碼。

**問：Aspose.BarCode 支援其他字元集嗎？**  
答：當然支援。使用 `Charset.forName("<your‑charset>")` 來解碼 UTF‑8、ISO‑8859‑1 等字元集的位元組。

## 結論

您現在已學會如何使用 Aspose.BarCode for Java **從條碼影像提取文字**，尤其是含有中文字符的 PDF417 條碼。此功能可應用於多語言庫存系統、文件自動化等多種情境。歡迎嘗試其他符號與字元集，以擴大應用範圍。

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}