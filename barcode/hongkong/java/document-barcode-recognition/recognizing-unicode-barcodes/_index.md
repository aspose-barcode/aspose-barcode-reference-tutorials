---
date: 2025-12-21
description: 學習如何使用 Aspose.BarCode Java 程式庫讀取條碼圖像，涵蓋 PDF417 條碼的 Java 產生與 Unicode 條碼辨識。
linktitle: Recognizing Unicode Barcodes
second_title: Aspose.BarCode Java API
title: 如何在 Java 中讀取帶有 Unicode 條碼的條碼圖像
url: /zh-hant/java/document-barcode-recognition/recognizing-unicode-barcodes/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中辨識 Unicode 條碼

## Introduction

如果您需要在 Java 應用程式中 **how to read barcode image**，尤其是條碼包含 Unicode 字元，您來對地方了。在本教學中，我們將逐步說明辨識 Unicode 條碼（如阿拉伯文、中文或西里爾文）的所有必要步驟，使用功能強大的 Aspose.BarCode 函式庫。完成後，您將能自信地產生與讀取這些條碼，將軟體的覆蓋範圍擴展至全球使用者。

## Quick Answers
- **哪個函式庫最適合在 Java 中讀取條碼？** Aspose.BarCode for Java.
- **我可以使用 Unicode 文字產生 PDF417 條碼嗎？** 是的，使用 `BarcodeGenerator` 類別。
- **在正式環境使用是否需要授權？** 需要有效的 Aspose.BarCode 授權。
- **支援哪個 Java 版本？** Java 8 及以上。
- **有免費試用嗎？** 有，您可以從 Aspose 官方網站下載試用版。

## What is “how to read barcode image” in Java?

在 Java 中，什麼是 “how to read barcode image”？  
讀取條碼影像是指將視覺圖案解碼回原始資料字串。當資料包含 Unicode 字元時，函式庫必須正確處理字元編碼與解碼，Aspose.BarCode 會在您將文字轉換為正確的代碼格式後自動完成此工作。

## 為何在 Java 中使用 Aspose.BarCode 產生 PDF417 條碼？

Aspose.BarCode 提供簡潔的 API 用於 **pdf417 barcode generation java**，支援廣泛的條碼類型，且內建支援 Unicode 編碼。這使其成為需要可靠高效條碼處理的企業級應用程式的理想選擇。

## 先決條件

- 具備 Java 程式設計的基礎知識。
- 已安裝 Aspose.BarCode for Java 函式庫。您可以在此處下載 [here](https://releases.aspose.com/barcode/java/)。
- 擁有有效的 Aspose.BarCode 授權。您可在此取得 [here](https://purchase.aspose.com/buy)。

## 匯入套件

開始之前，請在 Java 專案中匯入必要的套件。Aspose.BarCode 函式庫提供完整的條碼產生與辨識功能。

```java
import com.aspose.barcode.*;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
```

## 步驟 1：設定資源目錄

定義資源目錄的路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：設定 Aspose.BarCode 授權

載入 Aspose.BarCode 授權，以解鎖函式庫的全部功能。

```java
try {
    License lic = new License();
    lic.setLicense("aspose.barcode.lic");
} catch (Exception ex) {
    System.out.println(ex.getMessage());
}
```

## 步驟 3：產生 Unicode 條碼

使用提供的文字建立 Unicode 條碼。

```java
String file = dataDir + "pdf417_un.png";
String scodeText = "منحة";
System.out.println("codetext: " + scodeText);
String codeText = getCodeTextFromUnicode(scodeText);
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, codeText);
generator.save(file);
```

## 步驟 4：讀取 Unicode 條碼

讀取產生的 Unicode 條碼。

```java
BarCodeReader reader = new BarCodeReader(file, DecodeType.PDF_417);
for (BarCodeResult result : reader.readBarCodes()) {
    String rc = result.getCodeText();
    try {
        String s = getUnicodeFromCodeText(rc);
        System.out.println(s);
    } catch (UnsupportedEncodingException e) {
        e.printStackTrace();
    }
}
```

## 步驟 5：將 Unicode 轉換為代碼文字

實作將 Unicode 轉換為代碼文字的方法。

```java
private static String getCodeTextFromUnicode(String s) throws UnsupportedEncodingException {
    // Implementation details
}
```

## 步驟 6：將代碼文字轉換為 Unicode

實作將代碼文字轉換為 Unicode 的方法。

```java
private static String getUnicodeFromCodeText(String cs) throws UnsupportedEncodingException {
    // Implementation details
}
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 讀取後輸出亂碼 | 字元編碼錯誤 | 確保 `getUnicodeFromCodeText` 使用與 `getCodeTextFromUnicode` 相同的字元集（`UTF‑8`）。 |
| 讀取器回傳 `null` | `DecodeType` 設定不正確 | 對於 PDF417 條碼使用 `DecodeType.PDF_417`。 |
| 授權未套用 | 授權檔案路徑錯誤 | 將 `aspose.barcode.lic` 放置於專案根目錄或提供絕對路徑。 |

## 常見問答

### 是否需要 Aspose.BarCode 授權？
是的，使用 Aspose.BarCode 必須擁有有效的授權。您可以在此取得 [here](https://purchase.aspose.com/buy)。

### 哪裡可以找到 Aspose.BarCode 的文件說明？
文件說明可於此取得 [here](https://reference.aspose.com/barcode/java/)。

### 我可以免費試用 Aspose.BarCode 嗎？
可以，您可在此取得免費試用版 [here](https://releases.aspose.com/)。

### 如何取得 Aspose.BarCode 的臨時授權？
臨時授權可於此取得 [here](https://purchase.aspose.com/temporary-license/)。

### 需要支援或有任何問題？
請造訪 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)。

## 常見問題

**Q: 我可以將此程式碼用於其他條碼類型嗎？**  
A: 當然可以。將 `EncodeTypes.PDF_417` 改為任何支援的類型，例如 `EncodeTypes.CODE_128`，並相應調整 `DecodeType`。

**Q: 如果輸入文字包含表情符號會怎樣？**  
A: 表情符號屬於 Unicode 字元；只要轉換方法支援 UTF‑8，就會正確編碼。

**Q: 有沒有辦法從串流而非檔案讀取條碼？**  
A: 有，`BarCodeReader` 也接受 `InputStream` 作為第一個參數。

**Q: 如何提升大量批次的辨識速度？**  
A: 重複使用單一的 `BarCodeReader` 實例，於迴圈中處理影像，並及時釋放每個結果。

**Q: Aspose.BarCode 是否支援多頁 PDF 條碼擷取？**  
A: 支援。使用 `BarCodeReader` 並提供 PDF 檔案路徑，函式庫會自動遍歷所有頁面。

## 結論

恭喜！您已掌握在 Java 中使用 Aspose.BarCode **how to read barcode image** 的完整流程，從產生 Unicode PDF417 條碼到將其解碼回原始文字。此功能讓您能開發國際化應用、多語言庫存系統，以及任何需要全球字元集的情境。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}