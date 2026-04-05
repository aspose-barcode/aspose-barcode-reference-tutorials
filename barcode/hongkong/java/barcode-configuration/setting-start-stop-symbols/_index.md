---
date: 2026-02-17
description: 學習如何使用 Aspose Barcode Java 來建立條碼圖像、設定 CODABAR 起始與終止符號，並產生不含浮水印的 PNG 檔案。
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose 條碼 Java – 建立帶有起始/終止符號的條碼圖像
url: /zh-hant/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – 建立帶有起始/結束符號的條碼圖像

## 介紹

在本完整教學中，您將使用 **Aspose Barcode Java** **建立條碼圖像（Java）** 檔案，並學習 **如何設定符號** 於 Codabar 條碼。無論您是構建銷售點系統、物流應用程式，或任何需要可靠條碼產生的解決方案，客製化起始與結束符號都能讓您完整掌控條碼格式。我們將逐步說明每個步驟，解釋每項設定的原因，並示範如何產生可直接使用的 PNG 圖像——不含試用水印。

## 快速解答
- **什麼程式庫可以在 Java 中產生條碼圖像？** Aspose.BarCode for Java.  
- **我可以自訂起始/結束符號嗎？** 可以，使用 `setCodabarStartSymbol` 和 `setCodabarStopSymbol`。  
- **此範例使用哪種條碼類型？** CODABAR.  
- **生產環境需要授權嗎？** 非試用使用需購買商業授權。  
- **產生的輸出格式為何？** PNG 圖像，儲存至磁碟.

## Aspose Barcode Java 是什麼？

Aspose Barcode Java 是一個功能強大、無相依性的程式庫，讓您能以程式方式產生各種條碼符號。它抽象化低階編碼邏輯，讓您專注於業務規則，同時確保輸出符合業界標準。

## 為何使用 Aspose Barcode Java 產生無水印條碼？

- **生產環境無水印** – 只要套用有效授權，圖像即為純淨。  
- **支援廣泛的符號** – 從傳統 1D 代碼如 CODABAR 到 2D 代碼如 QR 與 DataMatrix。  
- **細緻的控制** – 您可以設定起始/結束符號、顏色、尺寸，甚至直接將圖像輸出至串流供 Web 應用使用。  
- **跨平台** – 可在任何 Java 執行環境上運行，亦支援 Android（需手動處理相依性）。

## 前置條件

在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 從 [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) 下載最新的 JDK。  
2. **Aspose.BarCode for Java 程式庫** – 從 [download link](https://releases.aspose.com/barcode/java/) 下載。

備妥上述項目即可確保您能 **產生條碼圖像（Java）**，不會缺少任何元件。

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的類別：

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步驟指南

### 步驟 1：定義文件目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您希望儲存條碼圖像的絕對或相對路徑。請記得在路徑末端加上適當的檔案分隔符（`/` 或 `\`），或使用 `Paths.get` 以取得跨平台的處理方式。

### 步驟 2：建立條碼產生器實例

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

此處告訴 Aspose.BarCode 使用 **CODABAR** 符號並以資料字串 `"12345678"` 產生條碼。

### 步驟 3：設定 Codabar 起始符號

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

`setCodabarStartSymbol` 方法可讓您 **設定條碼符號** 作為起始字元。本例中我們選擇 `A`。

### 步驟 4：設定 Codabar 結束符號

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

同樣地，`setCodabarStopSymbol` 定義結束字元。使用 `D` 完成許多舊系統所需的 CODABAR 格式。

### 步驟 5：儲存產生的圖像

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

`save` 呼叫會將條碼寫入 PNG 檔案，檔名為 **startAndStopSymbols.png**，儲存於先前指定的目錄中。

## 常見問題與技巧

- **目錄路徑不正確** – 確保 `dataDir` 以檔案分隔符（`/` 或 `\`）結尾，或使用 `Paths.get` 進行串接。  
- **不支援的起始/結束符號** – CODABAR 只接受 `A、B、C、D` 作為起始/結束符號。使用其他值會拋出例外。  
- **未套用授權** – 試用模式下產生的圖像可能會有水印。於部署至生產環境前套用授權，以實現 **條碼產生無水印**。

## 常見問答

### 我可以在商業專案中使用 Aspose.BarCode for Java 嗎？

可以。若用於商業用途，請考慮在此處購買授權 [here](https://purchase.aspose.com/buy)。

### 是否提供免費試用？

可以，您可於此處取得免費試用版 [here](https://releases.aspose.com/)。

### 如何取得 Aspose.BarCode for Java 的支援？

請前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 取得支援或諮詢。

### 如何取得臨時授權？

如有需要，可於此處取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### Aspose.BarCode for Java 是否支援更多條碼符號？

是的，Aspose.BarCode 支援多種條碼符號。請參考文件取得完整清單。

## 其他問答（AI 友善）

**Q:** 除了 PNG，我還能匯出哪些影像格式？  
**A:** Aspose.BarCode 支援 PNG、JPEG、BMP、GIF 與 TIFF。請在 `save` 方法中使用相對應的副檔名。

**Q:** 我可以在記憶體中產生條碼圖像而不寫入磁碟嗎？  
**A:** 可以，呼叫 `generator.save(OutputStream)` 可直接寫入串流，適用於 Web 回應。

**Q:** 此程式庫能在 Android 上使用嗎？  
**A:** Java 版相容於 Android，但需自行手動加入必要的相依性。

## 結論

您現在已學會如何使用 **Aspose Barcode Java** **建立條碼圖像（Java）** 檔案，並精確 **設定條碼符號** 於 Codabar 條碼。此技巧讓您能靈活符合產業特定的條碼規範，同時保持程式碼簡潔易於維護。欲探索更多客製化選項，例如變更顏色、加入可讀文字，或切換其他符號，請參考官方 API 文件於 [documentation](https://reference.aspose.com/barcode/java/)。

---

**最後更新：** 2026-02-17  
**測試環境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}