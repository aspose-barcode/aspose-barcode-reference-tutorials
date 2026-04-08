---
date: 2026-04-08
description: 學習如何使用 Aspose.BarCode for Java 讀取條碼並按特定順序排序。此一步一步的指南展示如何使用 Aspose、Java
  條碼閱讀器，並解碼 Code128 條碼。
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: 按特定順序讀取及排序條碼
second_title: Aspose.BarCode Java API
title: 如何使用 Java 按特定順序讀取條碼
url: /zh-hant/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Java 以特定順序讀取條碼


## 介紹

如果您需要**如何讀取條碼**，並將它們按特定順序排列，Aspose.BarCode for Java 為您提供一個簡潔且高效的解決方案。在許多 Java 應用程式——庫存系統、運輸解決方案或銷售點終端——中，讀取多個條碼並依其文字值排序是常見需求。本教學將帶您完整了解從環境設定到顯示排序結果的全過程，讓您能快速且有信心地整合條碼處理功能。

## 快速解答
- **什麼程式庫負責條碼讀取？** Aspose.BarCode for Java  
- **範例中使用的條碼類型是什麼？** CODE_128  
- **開發時需要授權嗎？** 臨時授權可用於測試；正式環境需要完整授權。  
- **可以依其他條件排序嗎？** 可以——修改 comparator 以依位置、信心等排序。  
- **需要哪個 Java 版本？** Java 8 或更新版本（任何支援 Aspose 程式庫的 JDK）。

## 在 Java 中什麼是「如何讀取條碼」？

讀取條碼是指將視覺圖案解碼為原始資料字串。Aspose.BarCode 提供 `BarCodeReader` 類別，將底層影像處理抽象化，讓您專注於排序或驗證等業務邏輯。

## 為什麼使用 Aspose.BarCode for Java？

- **強韌的解碼** – 支援超過 50 種條碼，包括 Code 128、QR、DataMatrix 等。  
- **高精度** – 最佳化演算法降低誤讀，即使在低解析度影像上亦如此。  
- **簡易 API** – 幾行程式碼即可將影像轉為文字。  
- **跨平台** – 可在任何 Java 執行環境上運作，從桌面到伺服器皆可。

## 前置條件

在深入程式碼之前，請確保您具備以下前置條件：

- Java Development Kit (JDK)：Aspose.BarCode for Java 需要一個可運作的 JDK。您可以在 [此處](https://www.oracle.com/java/technologies/javase-downloads.html) 下載最新版本。

- Aspose.BarCode Library：請確保已取得 Aspose.BarCode 程式庫。您可以從 [下載連結](https://releases.aspose.com/barcode/java/) 取得。

## 匯入套件

首先在您的 Java 專案中匯入必要的套件。這些套件提供處理條碼所需的核心類別與方法。

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

現在，讓我們將程式碼分解為逐步說明：

## 步驟 1：設定資源目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為實際的文件目錄路徑。

## 步驟 2：指定條碼影像路徑並初始化 Reader

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## 步驟 3：讀取條碼並儲存結果

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## 步驟 4：定義排序 Comparator

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## 步驟 5：排序條碼

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## 步驟 6：顯示已排序的條碼

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## 常見陷阱與技巧

- **影像路徑不正確** – 請確認 `dataDir` 以檔案分隔符 (`/` 或 `\\`) 結尾，以確保完整路徑正確解析。  
- **不支援的條碼類型** – 若需解碼其他條碼，請將 `DecodeType.CODE_128` 改為相應的 enum 值（例如 `DecodeType.QR`）。  
- **以數值排序** – 預設 comparator 以字典順序排序。若需數值排序，請在 comparator 內將 `CodeText` 轉為整數。  
- **資源清理** – `BarCodeReader` 實作 `Closeable`。在正式程式碼中，使用 try‑with‑resources 以確保底層串流釋放。

## 常見問答

### Q: 在哪裡可以找到 Aspose.BarCode for Java 的文件？
文件可於 [此處](https://reference.aspose.com/barcode/java/) 取得。

### Q: 如何下載 Aspose.BarCode for Java？
您可以從 [下載連結](https://releases.aspose.com/barcode/java/) 取得。

### Q: 是否提供免費試用？
是的，您可以在 [此處](https://releases.aspose.com/) 探索免費試用。

### Q: 如何取得臨時授權資訊？
臨時授權可於 [此處](https://purchase.aspose.com/temporary-license/) 取得。

### Q: 在哪裡可以取得支援或提問？
請前往支援論壇 [此處](https://forum.aspose.com/c/barcode/13)。

---

**最後更新：** 2026-04-08  
**測試環境：** Aspose.BarCode 24.10 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}