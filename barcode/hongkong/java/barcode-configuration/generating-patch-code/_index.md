---
date: 2025-12-13
description: 學習如何使用 Aspose.BarCode 於 Java 建立補丁條碼 – 這是一個 Java 條碼產生器範例，示範如何產生補丁碼並設定補丁格式。
linktitle: Generating a Patch Code in Java
second_title: Aspose.BarCode Java API
title: 在 Java 中建立補丁條碼 – 使用 Aspose.BarCode 產生補丁碼
url: /zh-hant/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 建立 Java Patch 條碼

## 介紹

在本完整指南中，您將使用 Aspose.BarCode for Java 快速且可靠地 **create patch barcode java**（建立 Java Patch 條碼）。無論您是構建文件管理系統，或需要在紙張上以緊湊方式儲存資料，產生 Patch Code 都是實用的解決方案。我們將示範一個 **java barcode generator example**（Java 條碼產生器範例），說明 **how to generate patch code**（如何產生 Patch Code），並展示 **how to set patch format**（如何設定 Patch 格式），讓您依需求自訂輸出。

## 快速回答
- **什麼函式庫最適合 Patch Code？** Aspose.BarCode for Java
- **需要多少行程式碼？** 基本範例約 20 行
- **我需要授權嗎？** 開發可使用免費試用版；正式上線需購買商業授權
- **可以變更頁面尺寸嗎？** 可以，使用 `PatchFormat`（例如 US_LETTER、A4）
- **支援的影像格式？** BMP、PNG、JPEG、GIF 等

## 什麼是 Patch Code？

Patch Code 是由四個獨立面板組成的二維條碼，可印在同一頁面上。由於每個面板可獨立掃描，它非常適合用於大量文件的索引。

## 為什麼使用 Aspose.BarCode for Java？

- **功能完整的 API** – 支援所有主要條碼類型，包括 Patch Code。
- **輕鬆自訂** – 只需簡單屬性呼叫即可變更尺寸、格式、邊距等。
- **跨平台** – 可在任何支援 Java 的環境中運行，從桌面應用程式到 Web 服務皆可。

## 前置條件

在開始之前，請確保您具備以下項目：

- **Java 開發環境** – 已安裝 JDK 8 或更新版本。
- **Aspose.BarCode for Java** – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。
- **IDE 或文字編輯器** – 任意支援 Java 的編輯器（IntelliJ IDEA、Eclipse、VS Code 等）。

## 匯入套件

首先，匯入必要的類別。以下程式碼片段正好示範您需要的內容：

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

### 步驟 1：產生基本 Patch Code

此 **java barcode generator example** 會建立簡易的 Patch Code，並儲存為 BMP 影像。

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

此方法中，我們會：

1. 定義輸出資料夾（`dataDir`）。
2. 使用 `EncodeTypes.PATCH_CODE` 及文字 `"Patch T"` 來實例化 `BarcodeGenerator`。
3. 將產生的影像儲存至磁碟。

### 步驟 2：如何設定 Patch 格式

若需要特定紙張尺寸，可在儲存前設定格式。以下示範 **how to set patch format** 為 US Letter。

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

### 步驟 3：產生整頁（組合所有面板）

以下為完整程式，會建立每個面板、組合成完整頁面，並寫入最終的 PNG 檔案。此處示範 **how to generate patch code** 用於多面板布局。

```java
public static void generateWholePage() throws IOException {
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    // Set image width, padding, and other parameters
    // ... (refer to the provided code for details)

    // Generate different parts of the Patch Code
    BufferedImage topImg = generator.generateBarCodeImage();
    // ... (similar steps for leftImg, bottomImg, and rightImg)

    // Create a frame and assemble the Patch Code
    BufferedImage frameImg = new BufferedImage(topImg.getWidth(), rightImg.getHeight() + 2 * topImg.getHeight(),
            rightImg.getType());
    // ... (refer to the provided code for details)

    // Save the Patch Code frame
    File outputfile = new File("Your Document Directory");
    ImageIO.write(frameImg, "png", outputfile);
}
```

#### 常見問題與技巧
- **目錄路徑不正確** – 確認 `dataDir` 以檔案分隔符結尾（`/` 或 `\\`）。
- **缺少權限** – 應用程式必須具備寫入目標資料夾的權限。
- **影像品質** – 如有需要，可透過 `generator.getParameters().getImageInfo().setResolutionX/Y()` 調整 DPI。

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？**  
A: 可以，正式上線需購買商業授權。您可於 [Aspose's purchase page](https://purchase.aspose.com/buy) 購買。

**Q: 有提供免費試用嗎？**  
A: 當然有。請從 [Aspose's release page](https://releases.aspose.com/) 下載試用版。

**Q: 我要如何取得支援？**  
A: 前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群協助與官方支援管道。

**Q: 臨時授權可以嗎？**  
A: 可以，臨時授權可於 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 我在哪裡可以找到完整的 API 參考文件？**  
A: 文件可於 [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/) 取得。

---

**最後更新：** 2025-12-13  
**測試環境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}