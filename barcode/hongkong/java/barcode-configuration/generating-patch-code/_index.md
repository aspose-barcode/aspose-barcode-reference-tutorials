---
date: 2026-07-28
description: 了解如何使用 Aspose.BarCode 建立 Patch 條碼 Java – 這是一個 Java 條碼產生器範例，展示如何產生 Patch
  代碼並設定 Patch 格式。
keywords:
- create patch barcode java
- java barcode generator example
- aspose.barcode patch code
- generate patch code java
lastmod: 2026-07-28
linktitle: 在 Java 中產生 Patch 代碼
og_description: 使用 Aspose.BarCode 建立 Patch 條碼 Java。本指南展示 Java 條碼產生器範例，說明如何在數分鐘內產生
  Patch 代碼並設定 Patch 格式。
og_image_alt: 'Developer guide: Create Patch Barcode Java using Aspose.BarCode'
og_title: 建立 Patch 條碼 Java – Aspose.BarCode 範例
schemas:
- author: Aspose
  dateModified: '2026-07-28'
  description: Learn how to create patch barcode java using Aspose.BarCode – a java
    barcode generator example that shows how to generate patch code and set patch
    format.
  headline: Create Patch Barcode Java – Aspose.BarCode Example
  type: TechArticle
- description: Learn how to create patch barcode java using Aspose.BarCode – a java
    barcode generator example that shows how to generate patch code and set patch
    format.
  name: Create Patch Barcode Java – Aspose.BarCode Example
  steps:
  - name: Generate a Basic Patch Code
    text: This **java barcode generator example** creates a simple Patch Code and
      saves it as a BMP image. **What happens here?** 1. `dataDir` points to the folder
      where the image will be written. 2. `BarcodeGenerator` is instantiated with
      `EncodeTypes.PATCH_CODE` and the text `"Patch T"`. 3. `save` writes th
  - name: Set the Patch Format (Paper Size)
    text: If you need a specific paper size, you can set the format before saving.
      This demonstrates **how to set patch format** to US Letter. **Why set the format?**
      Patch Code panels are arranged based on the chosen page size. Using `PatchFormat.US_LETTER`
      ensures the panels fit correctly on a standard lett
  - name: Generate a Whole Page (Assemble All Panels)
    text: Below is the full routine that creates each panel, assembles them into a
      complete page, and writes the final PNG file. This shows **how to generate patch
      code** for a multi‑panel layout. **Key points to note** - The method generates
      four separate images (`topImg`, `leftImg`, `bottomImg`, `rightImg`)
  type: HowTo
- questions:
  - answer: Yes, a commercial license is required for production use. You can purchase
      one from the [Aspose's purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.BarCode for Java in commercial projects?
  - answer: Absolutely. Download a trial version from the [Aspose's release page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community help and official support channels.
    question: How do I get support?
  - answer: Yes, temporary licenses are offered via the [Aspose's temporary license
      page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses an option?
  - answer: The documentation is available at the [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find the full API reference?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create patch barcode
- aspose.barcode
- java barcode
- 2d barcode
- patch code
title: 建立 Patch 條碼 Java – Aspose.BarCode 範例
url: /zh-hant/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 建立 Patch 條碼（Java）

## 介紹

在本完整指南中，您將 **create patch barcode java** 快速且可靠地使用 Aspose.BarCode for Java。無論您是構建文件管理系統、需要在紙張上以緊湊方式儲存中繼資料，或是尋找高密度 2‑D 條碼解決方案，產生 Patch Code 都是實用的選擇。我們將示範一個 **java barcode generator example**，說明 **how to generate patch code**，並展示 **how to set patch format**，讓您能依照精確需求自訂輸出。

## 快速回答
- **哪個函式庫最適合 Patch Code？** Aspose.BarCode for Java  
- **需要多少行程式碼？** 基本範例大約 20 行  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權  
- **可以變更頁面尺寸嗎？** 可以，使用 `PatchFormat`（例如 US_LETTER、A4）  
- **支援的影像格式？** BMP、PNG、JPEG、GIF 等  

## 什麼是 Patch Code？
Patch Code 是一種由四個獨立面板組成的二維條碼，可印於同一頁面。每個面板皆可獨立掃描，適合在保持實體占用面積小的情況下，對大量文件進行索引。**Patch Code 提供緊湊且高密度的編碼方式，每個面板最多可編碼 50 個字元，整張紙可容納最多 200 個字元。**

## 為什麼使用 Aspose.BarCode for Java？
Aspose.BarCode 支援 **30 多種條碼符號**，包括 Patch Code、QR Code、Data Matrix 等。其完整功能的 API 讓您只需一次呼叫即可產生任何支援的條碼，並提供尺寸、顏色、邊距、DPI 等輕鬆自訂，此外亦具跨平台相容性與完整文件說明。  
- **完整功能的 API** – 只需一次方法呼叫即可產生 30 多種支援的條碼。  
- **簡易自訂** – 透過簡單的屬性設定即可變更尺寸、格式、邊距、顏色與 DPI。  
- **跨平台** – 可在任何支援 Java 的環境中運作，從桌面應用程式到雲端服務皆可。  
- **效能測試** – 在標準工作站上可於 150 ms 以下產生 4 面板的 Patch Code 頁面。  

## 前置條件

- **Java 開發環境** – 已安裝 JDK 8 或更新版本。  
- **Aspose.BarCode for Java** – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。  
- **IDE 或文字編輯器** – 任意支援 Java 的編輯器（IntelliJ IDEA、Eclipse、VS Code 等）。  
- **寫入權限** – 需要對您計畫儲存產生影像的資料夾具有寫入權限。  

## 匯入套件

`BarcodeGenerator`、`EncodeTypes` 與 `PatchFormat` 類別是核心組件。  
`BarcodeGenerator` 是 Aspose.BarCode 用於建立條碼的主要類別。  
`EncodeTypes` 提供所有支援條碼類型的列舉。  
`PatchFormat` 定義 Patch Code 面板的頁面佈局。

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

## 如何建立 Patch 條碼 Java – 步驟說明

首先載入開發環境，設定必要參數（如資料字串、條碼類型），然後呼叫 `save` 方法。此簡易工作流程包含三個步驟：產生基本的 Patch Code、調整頁面格式以符合紙張尺寸，最後將四個面板拼接成單一可列印的影像。

### 步驟 1：產生基本的 Patch Code

此 **java barcode generator example** 會建立簡單的 Patch Code，並以 BMP 影像儲存。

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

**此處發生什麼？**  
1. `dataDir` 指向將寫入影像的資料夾。  
2. 使用 `EncodeTypes.PATCH_CODE` 與文字 `"Patch T"` 來實例化 `BarcodeGenerator`。  
3. `save` 將條碼寫入 `patch.bmp`。  

### 步驟 2：設定 Patch 格式（紙張尺寸）

如果需要特定的紙張尺寸，可在儲存前設定格式。此範例示範 **how to set patch format** 為 US Letter。

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

**為什麼要設定格式？**  
Patch Code 面板會依所選頁面尺寸排列。使用 `PatchFormat.US_LETTER` 可確保面板正確適配標準信紙尺寸，避免掃描時被裁切。

### 步驟 3：產生完整頁面（組合所有面板）

以下為完整程式碼，會建立每個面板、組合成完整頁面，並寫入最終的 PNG 檔案。此範例展示 **how to generate patch code** 用於多面板佈局。

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
- 此方法會產生四個獨立影像（`topImg`、`leftImg`、`bottomImg`、`rightImg`），分別代表每個面板。  
- 會建立較大的 `frameImg` 畫布以拼接這些面板。  
- 最終的 PNG 會寫入您指定的資料夾。  

## 常見問題與技巧

- **目錄路徑不正確** – 確認 `dataDir` 以檔案分隔符結尾（`/` 或 `\\`）。  
- **缺少權限** – 應用程式必須對目標資料夾具有寫入權限。  
- **影像品質** – 如需更高掃描解析度，可透過 `generator.getParameters().getImageInfo().setResolutionX/Y()` 調整 DPI。  
- **記憶體使用** – 產生大型頁面時，儲存後可考慮呼叫 `System.gc()` 釋放影像緩衝區。  

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？**  
A: 可以，正式環境需購買商業授權。您可於 [Aspose's purchase page](https://purchase.aspose.com/buy) 購買。

**Q: 有提供免費試用嗎？**  
A: 當然有。可從 [Aspose's release page](https://releases.aspose.com/) 下載試用版。

**Q: 我要如何取得支援？**  
A: 前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 獲取社群協助與官方支援管道。

**Q: 臨時授權是可行的嗎？**  
A: 可以，臨時授權可透過 [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 我可以在哪裡找到完整的 API 參考文件？**  
A: 文件可於 [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/) 取得。

## 其他資源

- **範例專案** – 探索官方 Aspose.BarCode GitHub 倉庫以取得完整範例。  
- **效能技巧** – 使用 `generator.getParameters().getImageInfo().setResolutionX(300)` 以獲得高解析度掃描。  
- **後續步驟** – 熟悉 Patch Code 後，可使用相同的產生器類別嘗試其他 2‑D 條碼，如 QR Code 或 Data Matrix。  

**最後更新：** 2026-07-28  
**測試環境：** Aspose.BarCode for Java 24.12（最新）  
**作者：** Aspose

## 相關教學

- [使用 Aspose 建立條碼 - 在 Java 中設定 X 與 Y 尺寸](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [產生 Java 條碼 – 使用 Aspose.BarCode 設定影像解析度](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [如何在 Java 中使用 Aspose.BarCode 建立 code128 條碼影像](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}