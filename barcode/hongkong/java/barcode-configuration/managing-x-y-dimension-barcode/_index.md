---
date: 2025-12-14
description: 學習如何在 Java 中使用 Aspose.BarCode 設定條碼尺寸。此一步一步的指南展示如何自訂條碼、產生 Java 條碼圖像，以及使用
  Aspose 建立條碼。
linktitle: Managing X and Y Dimensions of Barcode
second_title: Aspose.BarCode Java API
title: 如何在 Java 中設定條碼的 X 與 Y 尺寸
url: /zh-hant/java/barcode-configuration/managing-x-y-dimension-barcode/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中設定條碼 X 與 Y 尺寸

在 Java 開發中，**如何設定條碼**尺寸是一項常見需求，當您需要為標籤、票證或庫存標籤產生清晰、易讀的條碼時。本教學將指導您如何使用 Aspose.BarCode Java API 來控制 X（窄條的寬度）與 Y（條碼的高度）兩個尺寸。完成後，您將能夠 **customize barcode**、產生 **barcode image java**，並自信地 **create barcode with aspose** 於任何專案中。

## 快速解答
- **什麼程式庫最適合條碼尺寸控制？** Aspose.BarCode for Java.
- **哪個方法設定 X‑dimension？** `getXDimension().setMillimeters(...)`.
- **哪個方法設定 Y‑dimension（條碼高度）？** `getBarHeight().setMillimeters(...)`.
- **生產環境是否需要授權？** 是的，需要商業授權。
- **我可以產生 PNG、JPG 或 BMP 圖片嗎？** 支援所有常見的點陣圖格式。

## 在 Aspose.BarCode 中「如何設定條碼」是什麼意思？
設定條碼尺寸是指定義每根條的實體大小（X‑dimension）以及條碼的整體高度（Y‑dimension）。適當的尺寸設定可確保條碼在不同印表機與掃描器上均能可靠掃描。

## 為何使用 Aspose.BarCode for Java 來自訂條碼尺寸？
- **Precision control** – 毫米級的調整可提供精確的尺寸。
- **Wide format support** – 支援 PNG、JPG、BMP、GIF 等多種格式。
- **No external dependencies** – 純 Java 程式庫，易於整合至任何 IDE。
- **Comprehensive documentation** – 提供實用範例與 API 參考。

## 前置條件

- 已在機器上安裝 Java Development Kit (JDK)。
- 從 [here](https://releases.aspose.com/barcode/java/) 下載 Aspose.BarCode for Java 程式庫。
- 使用 Eclipse 或 IntelliJ IDEA 等 Java IDE。

## 匯入套件

在您的 Java 類別中，匯入 Aspose.BarCode 產生套件：

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

現在我們將一步步說明每個尺寸設定。

## 步驟 1：設定 X‑Dimension（條寬）

X‑dimension 控制最窄條的寬度。典型值介於 0.2 mm 至 0.5 mm 之間。

```java
public static void setXDimension() throws IOException {
    // The path to the resource directory.
    String dataDir = "Your Document Directory";

    // Create a BarcodeGenerator with CODE_128 encoding and data "12345678"
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");

    // Set the x-dimension for the bars of the barcode
    generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);

    // Save the Barcode image to file
    generator.save(dataDir + "xDimension.jpg");
}
```

在此程式碼片段中，我們：

1. 使用 **CODE_128** 符號實例化 `BarcodeGenerator`。
2. 呼叫 `setMillimeters(0.5f)` 以定義 0.5 mm 的條寬。
3. 將結果儲存為 **xDimension.jpg**。

## 步驟 2：設定 Y‑Dimension（條高）

Y‑dimension（亦稱條高）決定每根條的高度。可依據資料量與掃描距離進行調整。

```java
public static void setYDimension() throws IOException {
    // The path to the resource directory.
    String dataDir = "Your Document Directory";

    // Create a BarcodeGenerator with PDF_417 encoding and data "12345678"
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, "12345678");

    // Set the Y-Dimension for the bars of the barcode
    generator.getParameters().getBarcode().getBarHeight().setMillimeters(4);

    // Save the Barcode image to file
    generator.save(dataDir + "yDimension.jpg");
}
```

在此範例中，我們：

1. 使用 **PDF_417** 符號，該符號通常需要較高的條。
2. 將條高設定為 **4 mm**。
3. 將輸出儲存為 **yDimension.jpg**。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 條碼顯示過細或過粗 | X‑dimension 不適合印表機 DPI | 調整 `setMillimeters` 的數值（例如，高解析度印表機使用 0.3 mm）。 |
| 掃描器無法讀取條碼 | Y‑dimension 對該符號而言太低 | 使用 `setMillimeters` 增加條高（例如，PDF_417 使用 5 mm）。 |
| 影像檔案損毀 | 輸出路徑不存在或沒有寫入權限 | 確認 `dataDir` 指向已存在且可寫入的資料夾。 |

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？**  
A: 可以，需要商業授權。請於 [here](https://purchase.aspose.com/buy) 購買授權。

**Q: 是否提供免費試用？**  
A: 當然，您可於 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: 完整的 API 文件在哪裡可以找到？**  
A: 文件可於 [here](https://reference.aspose.com/barcode/java/) 取得。

**Q: 若遇到問題，如何取得支援？**  
A: 您可在 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 提問。

**Q: 我可以取得測試用的臨時授權嗎？**  
A: 可以，請於 [here](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

## 結論

使用 Aspose.BarCode for Java 管理 X 與 Y 尺寸相當簡單。透過調整 X‑dimension 以設定條寬、Y‑dimension 以設定條高，您即可 **customize barcode**、**generate barcode image java**，以及 **create barcode with aspose**，滿足任何掃描需求。請嘗試不同的數值，以找到最適合您特定使用情境的平衡點。

---

**最後更新:** 2025-12-14  
**測試環境:** Aspose.BarCode for Java 24.8  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}