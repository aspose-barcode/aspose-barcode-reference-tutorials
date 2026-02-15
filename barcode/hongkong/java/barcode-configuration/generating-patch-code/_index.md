---
date: 2026-02-15
description: 學習如何使用 Aspose.BarCode 在 Java 中建立補丁條碼 – 這是一個 Java 條碼產生器範例，展示如何產生補丁碼並設定補丁格式。
linktitle: Generating a Patch Code in Java
second_title: Aspose.BarCode Java API
title: 建立補丁條碼 Java – 使用 Aspose.BarCode 產生補丁碼
url: /zh-hant/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 建立 Patch 條碼 Java

## 介紹

在本完整指南中，您將使用 Aspose.BarCode for Java 快速且可靠地 **create patch barcode java**。無論您是建立文件管理系統、需要在紙張上以緊湊方式儲存中繼資料，或是尋找高密度 2‑D 條碼解決方案，產生 Patch Code 都是一個實用的選擇。我們將示範一個 **java barcode generator example**，說明 **how to generate patch code**，並展示 **how to set patch format**，讓您能依照精確需求自訂輸出。

## 快速解答
- **什麼函式庫最適合 Patch Code？** Aspose.BarCode for Java
- **需要多少行程式碼？** 基本範例大約 20 行
- **需要授權嗎？** 免費試用版可用於開發；正式環境需購買商業授權
- **可以變更頁面尺寸嗎？** 可以，使用 `PatchFormat`（例如 US_LETTER、A4）
- **支援的影像格式？** BMP、PNG、JPEG、GIF 等

## 什麼是 Patch Code？

Patch Code 是由四個獨立面板組成的二維條碼，可列印於同一頁面上。每個面板皆可獨立掃描，適合在保持實體佔用面積小的情況下，對大量文件進行索引。

## 為什麼使用 Aspose.BarCode for Java？

- **完整功能 API** – 支援所有主要條碼類型，包括 Patch Code。
- **輕鬆自訂** – 只需簡單屬性呼叫即可變更尺寸、格式、邊距等。
- **跨平台** – 可在任何支援 Java 的環境中運作，從桌面應用程式到 Web 服務皆可。
- **完善文件** – 豐富的範例與 API 參考可協助您快速上手。

## 前置條件

- **Java 開發環境** – 已安裝 JDK 8 或更新版本。
- **Aspose.BarCode for Java** – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。
- **IDE 或文字編輯器** – 任意支援 Java 的編輯器（IntelliJ IDEA、Eclipse、VS Code 等）。
- **寫入權限** – 需對儲存產生影像的資料夾具有寫入權限。

## 匯入套件

要開始，請匯入必要的類別。以下程式碼片段正好示範您需要的內容：

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

## 如何建立 patch barcode java – 步驟說明

以下提供清晰的編號步驟說明，將每個程式碼區塊對應到具體操作。請直接複製程式碼片段，於替換佔位資料夾路徑後即可執行。

### 步驟 1：產生基本 Patch Code

此 **java barcode generator example** 會建立簡易的 Patch Code，並以 BMP 影像儲存。

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

**此程式碼的作用是什麼？**
1. `dataDir` 指向將寫入影像的資料夾。
2. `BarcodeGenerator` 以 `EncodeTypes.PATCH_CODE` 及文字 `"Patch T"` 進行實例化。
3. `save` 將條碼寫入 `patch.bmp`。

### 步驟 2：設定 Patch 格式（紙張尺寸）

若需特定紙張尺寸，可在儲存前設定格式。以下示範 **how to set patch format** 為 US Letter。

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

**為什麼要設定格式？**  
Patch Code 的面板會依所選頁面尺寸排列。使用 `PatchFormat.US_LETTER` 可確保面板正確放置於標準信紙尺寸上。

### 步驟 3：產生完整頁面（組合所有面板）

以下為完整流程，會建立每個面板、將其組合成完整頁面，並寫入最終的 PNG 檔案。此處示範 **how to generate patch code** 用於多面板版面配置。

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

**重點說明**
- 此方法會產生四個獨立影像（`topImg`、`leftImg`、`bottomImg`、`rightImg`），分別代表各面板。
- 會建立較大的 `frameImg` 畫布，以拼接各面板。
- 最終的 PNG 會寫入您指定的資料夾。

## 常見問題與技巧

- **目錄路徑不正確** – 確認 `dataDir` 以檔案分隔符結尾（`/` 或 `\\`）。
- **缺少權限** – 應用程式必須具備目標資料夾的寫入權限。
- **影像品質** – 若需更高掃描解析度，可透過 `generator.getParameters().getImageInfo().setResolutionX/Y()` 調整 DPI。
- **記憶體使用** – 產生大型頁面時，儲存後可呼叫 `System.gc()` 釋放影像緩衝。

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？**  
A: 可以，正式環境需購買商業授權。您可於 [Aspose's purchase page](https://purchase.aspose.com/buy) 購買。

**Q: 有提供免費試用嗎？**  
A: 當然有。可從 [Aspose's release page](https://releases.aspose.com/) 下載試用版。

**Q: 我要如何取得支援？**  
A: 前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群協助與官方支援管道。

**Q: 臨時授權可以嗎？**  
A: 可以，臨時授權可於 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 我在哪裡可以找到完整的 API 參考文件？**  
A: 文件可於 [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/) 取得。

## 其他資源

- **範例專案** – 前往官方 Aspose.BarCode GitHub 倉庫，探索完整功能範例。  
- **效能技巧** – 使用 `generator.getParameters().getImageInfo().setResolutionX(300)` 以取得高解析度掃描。  
- **下一步** – 熟悉 Patch Code 後，可使用相同的產生器類別嘗試其他 2‑D 條碼，如 QR Code 或 Data Matrix。

---

**最後更新日期：** 2026-02-15  
**測試環境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}