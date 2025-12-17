---
date: 2025-12-17
description: 學習如何使用 Java 建立條碼圖像以及如何使用 Aspose.BarCode 設定符號。本分步指南將示範如何產生帶有自訂起始/終止符號的
  Codabar 條碼。
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: 在 Java 中建立條碼圖像 – 設定起始與終止符號
url: /zh-hant/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立條碼圖像 Java – 設定起始與停止符號

## 簡介

在本完整教學中，您將使用 Aspose.BarCode for Java **create barcode image java** 檔案，並學習 **how to set symbols** 於 Codabar 條碼。無論您是在構建銷售點系統、物流應用程式，或任何需要可靠條碼產生的解決方案，客製化起始與結束符號都能讓您完整掌控條碼格式。我們將逐步說明每個步驟，解釋每項設定的原因，並示範如何產生可直接使用的 PNG 圖像。

## 快速回答
- **什麼程式庫可在 Java 中產生條碼圖像？** Aspose.BarCode for Java.
- **我可以自訂起始/停止符號嗎？** Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
- **此範例使用哪種條碼類型？** CODABAR.
- **在正式環境需要授權嗎？** A commercial license is required for non‑trial use.
- **產生的輸出格式為何？** PNG image saved to disk.

## 什麼是「create barcode image java」？

在 Java 中產生條碼圖像是指以程式方式產生條碼符號的視覺表示（通常為 PNG、JPG 或 BMP），可供標準讀取器掃描。Aspose.BarCode 提供流暢的 API，抽象化低層編碼細節，讓您專注於業務邏輯。

## 為何使用 Aspose.BarCode 產生條碼？

Aspose.BarCode offers:
- **廣泛的符號支援**（包括 CODABAR、QR、DataMatrix 等）。
- **細緻的控制** 於外觀、尺寸與編碼選項。
- **跨平台相容性** 與任何 Java 執行環境。
- **無外部相依性**，使部署變得簡單。

## 先決條件

在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 從 [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) 下載最新的 JDK。
2. **Aspose.BarCode for Java library** – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。

具備上述項目即可確保您能 **generate barcode image java**，不會缺少任何元件。

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的類別：

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 逐步指南

### 步驟 1：定義文件目錄

將 `"Your Document Directory"` 替換為您希望儲存條碼圖像的絕對或相對路徑。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：建立條碼產生器實例

在此我們告訴 Aspose.BarCode 使用 **CODABAR** 符號集，並以資料字串 `"12345678"` 為內容。

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### 步驟 3：設定 Codabar 起始符號

`setCodabarStartSymbol` 方法讓您 **how to set symbols** 起始字元。在此範例我們選擇 `A`。

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### 步驟 4：設定 Codabar 結束符號

同理，`setCodabarStopSymbol` 定義結束字元。使用 `D` 完成許多舊系統所需的 CODABAR 格式。

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### 步驟 5：儲存產生的圖像

`save` 呼叫會將條碼寫入 PNG 檔案，檔名為 **startAndStopSymbols.png**，儲存在先前指定的目錄中。

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

### 常見陷阱與技巧

- **目錄路徑不正確** – 確保 `dataDir` 以檔案分隔符 (`/` 或 `\`) 結尾，或使用 `Paths.get` 進行串接。
- **不支援的起始/結束符號** – CODABAR 只支援 A、B、C、D 作為起始/結束符號。使用其他值會拋出例外。
- **未套用授權** – 試用模式下產生的圖像可能會有浮水印。請在部署至正式環境前套用授權。

## 結論

您現在已學會如何 **create barcode image java** 檔案，並精確 **how to set symbols** Codabar 條碼。此技巧讓您能靈活符合行業特定的條碼規範，同時保持程式碼簡潔且易於維護。欲探索更多客製化選項（例如變更顏色、加入可讀文字，或切換至其他符號集），請參考官方 API 文件於 [documentation](https://reference.aspose.com/barcode/java/)。

## 常見問題

### 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？
可以，您可以使用。若為商業用途，請考慮於 [here](https://purchase.aspose.com/buy) 購買授權。

### 是否提供免費試用？
可以，您可於 [here](https://releases.aspose.com/) 下載免費試用版。

### 如何取得 Aspose.BarCode for Java 的支援？
請前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 取得支援或諮詢。

### 如何取得臨時授權？
如有需要，您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Aspose.BarCode for Java 是否支援更多條碼符號集？
是的，Aspose.BarCode 支援多種條碼符號集。請參考文件取得完整清單。

**Additional Q&A**

**Q: 除了 PNG，我可以匯出哪些影像格式？**  
A: Aspose.BarCode 支援 PNG、JPEG、BMP、GIF 與 TIFF。請在 `save` 方法中使用相對應的副檔名。

**Q: 我可以在記憶體中產生條碼圖像而不寫入磁碟嗎？**  
A: 可以，呼叫 `generator.save(OutputStream)` 直接寫入串流，適用於 Web 回應。

**Q: 此函式庫能在 Android 上運作嗎？**  
A: Java 版相容於 Android，但需手動加入必要的相依性。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}