---
date: 2025-12-08
description: 學習如何使用 Aspose.BarCode 在 Java 中建立 PDF 文件並加入條碼。一步一步的指南，教您在 PDF 中產生與嵌入條碼。
language: zh-hant
linktitle: Adding Barcode to PDF Document
second_title: Aspose.BarCode Java API
title: 如何使用 Aspose.BarCode 在 Java 中建立帶條碼的 PDF 文件
url: /java/barcode-basics/adding-barcode-to-pdf-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 建立含條碼的 PDF Java 文件

## 介紹

在庫存系統、運送標籤與安全文件工作流程中，建立包含機器可讀條碼的 PDF Java 文件是常見需求。在本教學中，你將學會 **如何建立 PDF Java 文件**，並使用 **Aspose.BarCode for Java** 直接將條碼嵌入檔案。我們會一步步說明——從產生條碼影像到插入至既有 PDF——讓你在數分鐘內為 Java 應用程式加入條碼功能。

## 快速回答
- **需要哪個函式庫？** Aspose.BarCode for Java（加上處理 PDF 的 Aspose.PDF）。  
- **可以產生任何條碼類型嗎？** 可以——Aspose.BarCode 支援超過 50 種符號，包括 Code 39、QR、DataMatrix 等。  
- **開發時需要授權嗎？** 評估期間可使用臨時授權；正式上線需購買完整授權。  
- **程式碼相容於 Java 8+ 嗎？** 完全相容——API 目標為 Java 8 及以上版本。  
- **實作大約需要多久？** 基本的「將條碼加入 PDF」情境約需 10‑15 分鐘。

## 前置條件

開始之前，請確保已具備以下項目：

- **Java Development Kit (JDK)** – 已安裝最新穩定版。  
- **Aspose.BarCode for Java** – 從[下載頁面](https://releases.aspose.com/barcode/java/)取得。  
- **Aspose.PDF for Java** – 用於操作 PDF 檔案（隨 BarCode 套件一起提供）。  

## 匯入命名空間

首先，匯入所需的類別。此步驟會為條碼產生與 PDF 操作建立環境。

```java
// Import Aspose.BarCode namespaces
import com.aspose.pdf.*;
import com.aspose.pdf.facades.*;

import com.aspose.barcode.generation.*;
import com.aspose.barcode.*;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.barcode.EncodeTypes;
```

## 第一步：設定 Java 專案

在你慣用的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）建立新 Java 專案。將下載的 **Aspose.BarCode.jar**（及其相依檔案）加入專案的建置路徑，確保編譯器能找到上述類別。

## 第二步：產生條碼影像 – *如何加入條碼*

建立 `BarcodeGenerator` 實例，選擇符號類型，並設定條碼文字。這裡會 **設定條碼符號** 並 **產生條碼 Java 物件**。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD, "1234567");
generator.save(dataDir + "barcodeToPDF.bmp", BarCodeImageFormat.BMP);
```

> **小技巧：** 將 `EncodeTypes.CODE_39_STANDARD` 替換為其他 `EncodeTypes` 值（例如 `QR`、`DATA_MATRIX`）即可產生不同的條碼格式。

## 第三步：建立 PDF 文件 – *加入影像 pdf java*

接下來 **建立 PDF 文件**，用來放置條碼影像。Aspose.PDF 讓這個動作相當簡單。

```java
Document doc = new Document();
doc.getPages().add();
```

此時你已擁有一個空的 PDF，準備寫入內容。

## 第四步：將條碼影像加入 PDF 文件 – *加入條碼至既有 pdf*

若需將條碼嵌入 **既有 PDF**，可使用 `PdfFileMend` 開啟檔案。以下程式碼會綁定 PDF、插入條碼影像，並儲存結果。

```java
PdfFileMend mender = new PdfFileMend();
mender.bindPdf(doc);
mender.addImage(in, 1, 100, 600, 200, 700);
mender.save(dataDir + "AddImage_out.pdf");
mender.close();
```

- `in` 為指向先前產生的條碼影像的 `InputStream`。  
- 數值參數 (`1, 100, 600, 200, 700`) 代表頁碼與定位（X、Y 座標、寬度、高度），請依版面需求調整。

## 常見問題與解決方案

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **影像未顯示** | 座標或頁碼設定錯誤。 | 確認頁碼（第一頁為 `1`）且確保在 `addImage` 前未關閉影像串流。 |
| **不支援的條碼類型** | 使用了授權未涵蓋的符號。 | 檢查授權檔案，必要時升級授權。 |
| **FileNotFoundException** | `dataDir` 路徑不正確。 | 使用絕對路徑或 `System.getProperty("user.dir")` 動態組合目錄。 |

## 常見問答

**Q: 我可以自訂條碼在 PDF 文件中的外觀嗎？**  
A: 可以。Aspose.BarCode 允許你變更顏色、字型、邊距，甚至加入可讀文字。於儲存前調整 `BarcodeGenerator` 的屬性即可。

**Q: Aspose.BarCode 支援哪些條碼符號？**  
A: 完全支援。超過 50 種符號皆可使用，包括 Code 128、QR、DataMatrix、PDF417 等。

**Q: 如何取得 Aspose.BarCode 的臨時授權？**  
A: 前往 Aspose 官方網站的[臨時授權頁面](https://purchase.aspose.com/temporary-license/)，申請 30 天評估授權。

**Q: 我可以在哪裡尋求 Aspose.BarCode 相關的協助與支援？**  
A: 造訪 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)，那裡有活躍的社群可提供問題解答與解決方案。

**Q: 在購買前，我可以免費試用 Aspose.BarCode for Java 嗎？**  
A: 可以，從[發行頁面](https://releases.aspose.com/)下載免費試用版，所有功能皆可在未授權情況下體驗。

## 結論

現在你已掌握 **如何建立 PDF Java 文件** 並使用 Aspose.BarCode 嵌入條碼。此功能可簡化如產生運送標籤、製作安全發票或建置庫存追蹤系統等工作流程。請嘗試不同的符號、調整影像位置，並將程式碼整合至更大型的 Java 服務中，充分發揮條碼技術的威力。

---

**最後更新日期：** 2025-12-08  
**測試環境：** Aspose.BarCode 24.11 for Java、Aspose.PDF 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}