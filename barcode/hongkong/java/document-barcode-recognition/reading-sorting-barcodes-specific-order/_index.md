---
date: 2025-12-19
description: 了解如何使用 Aspose.BarCode for Java 讀取條碼，將它們按特定順序排序，並查看完整的條碼偵測 Java 範例。
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: 如何在 Java 中讀取條碼並按特定順序排序
url: /zh-hant/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中讀取條碼並按特定順序排序

## Introduction

在現代的 Java 應用程式中，**如何有效讀取條碼**是一個常見問題。無論您是在處理庫存清單、運送標籤或活動票券，可靠的條碼解決方案都能為您節省大量人工時間。在本教學中，我們將示範如何使用 **Aspose.BarCode for Java** 讀取條碼並按特定順序排序。您將獲得一個完整、可直接執行的範例，展示條碼偵測、提取條碼文字以及自訂排序邏輯。

## Quick Answers
- **我應該使用哪個函式庫？** Aspose.BarCode for Java
- **讀取條碼後我可以排序嗎？** 可以 – 只要將結果儲存起來並套用 comparator
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權
- **支援哪個 Java 版本？** Java 8 及以上
- **這是條碼偵測的 Java 範例嗎？** 當然 – 程式碼會讀取 CODE_128 條碼並進行排序

## What is “how to read barcodes” in Java?

在 Java 中「如何讀取條碼」是指將條碼影像的視覺圖樣解碼為其底層文字值。Aspose.BarCode 提供高效能的 **barcode reading aspose** 引擎，支援數十種條碼類型，包括 CODE_128、QR、DataMatrix 等。

## Why use Aspose.BarCode for barcode reading aspose?
- **高精度** – 即使在低解析度影像下亦能正常運作
- **簡易 API** – 幾行程式碼即可從影像取得文字
- **跨平台** – 可在任何相容 JVM 的環境執行
- **內建排序支援** – 可輕鬆將讀取結果與 Java 集合結合

## Prerequisites

在深入程式碼之前，請確保您已具備以下前置條件：

- Java Development Kit (JDK)：Aspose.BarCode for Java 需要一個可正常運作的 JDK。您可以在 [此處](https://www.oracle.com/java/technologies/javase-downloads.html) 下載最新版本。

- Aspose.BarCode Library：請確保已取得 Aspose.BarCode 函式庫。您可以從 [下載連結](https://releases.aspose.com/barcode/java/) 取得。

## Import Packages

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

現在，讓我們將程式碼拆解為一步一步的教學：

## Step 1: Set up the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為實際的文件目錄路徑。

## Step 2: Specify Barcode Image Path and Initialize Reader

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Step 3: Read Barcodes and Store Results

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Step 4: Define Comparator for Sorting

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Step 5: Sort Barcodes

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Step 6: Display Sorted Barcodes

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

## Common Issues and Solutions

| 問題 | 為何發生 | 解決方法 |
|------|----------|----------|
| **未偵測到條碼** | `DecodeType` 設定錯誤或影像品質低 | 確認影像中包含 CODE_128 條碼，並使用正確的 `DecodeType`。也可嘗試 `DecodeType.ALL` 進行自動偵測。 |
| **排序順序不正確** | Comparator 以字串字典序比較 | 若需數值排序，請在比較前將 `CodeText` 轉換為 `int`。 |
| **`BarCodeRegion` 發生 NullPointer** | 影像路徑錯誤或檔案不存在 | 確保 `path` 指向有效的 PNG 檔案，且該檔案可被 JVM 讀取。 |

## Frequently Asked Questions

**Q: 在哪裡可以找到 Aspose.BarCode for Java 的文件說明？**  
A: 文件說明可於 [此處](https://reference.aspose.com/barcode/java/) 取得。

**Q: 我要如何下載 Aspose.BarCode for Java？**  
A: 您可從 [下載連結](https://releases.aspose.com/barcode/java/) 取得。

**Q: 有提供免費試用嗎？**  
A: 有，您可以在 [此處](https://releases.aspose.com/) 申請免費試用。

**Q: 如何取得暫時授權資訊？**  
A: 暫時授權可於 [此處](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 我可以到哪裡尋求支援或提問？**  
A: 請前往支援論壇 [此處](https://forum.aspose.com/c/barcode/13)。

## Additional FAQs (AI‑Optimized)

**Q: 我可以將此程式碼用於其他條碼類型嗎？**  
A: 當然可以。將 `DecodeType.CODE_128` 改為任何支援的條碼類型，例如 `DecodeType.QR` 或 `DecodeType.DATA_MATRIX`。

**Q: Aspose.BarCode 是否支援批次處理多張影像？**  
A: 支援。只要遍歷檔案路徑集合，並在每張影像上重複使用相同的 `BarCodeReader` 邏輯即可。

**Q: 如何提升大量影像集合的處理效能？**  
A: 盡可能重複使用 `BarCodeReader` 實例，並利用 Java 的 `ExecutorService` 以平行方式處理影像。

## Conclusion

在本教學中，我們示範了如何使用 Aspose.BarCode for Java **讀取條碼**、儲存每筆結果，並以自訂方式排序清單。依循一步一步的指引，您即可將穩健的條碼偵測與排序功能整合至任何 Java 應用程式——無論是庫存管理、物流或活動票務。

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}