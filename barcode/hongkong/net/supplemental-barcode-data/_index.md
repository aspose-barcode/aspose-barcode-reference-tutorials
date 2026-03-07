---
date: 2026-03-07
description: 學習如何使用 Aspose.BarCode for .NET 建立 EAN-2 條碼並執行 .NET 條碼產生，立即掌握補充條碼資料的自訂技巧！
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 建立 EAN-2 條碼
url: /zh-hant/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 建立 EAN-2 條碼

## 簡介

如果你是一位 .NET 開發人員，想要 **建立 EAN-2 條碼** 並發掘補充條碼資料的威力，你來對地方了。在本完整指南中，我們將帶領你了解所有必須掌握的內容——從基本設定到微調符號周圍的間距。無論你是要建置全新的庫存系統，或是強化現有的銷售點應用程式，精通這些功能都能讓你的 .NET 條碼產生專案更具彈性與可靠性。

## 快速答覆
- **我可以產生什麼？** EAN‑2 與 EAN‑5 補充條碼。  
- **我需要授權嗎？** 免費試用可用於開發；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **需要多少程式碼？** 只要幾行——Aspose.BarCode 會處理繁重的工作。  
- **我可以自訂間距嗎？** 可以，您可直接控制 X‑dimension 與 supplement space。

## 什麼是補充條碼資料？

補充條碼資料指的是出現在主條碼旁邊的較小附加符號（EAN‑2、EAN‑5），通常用於期號、價格延伸或其他輔助資訊。Aspose.BarCode for .NET 讓您能以程式方式產生這些符號，並完整掌控其外觀與位置。

## 為什麼要使用 Aspose.BarCode for .NET？

- **完整的 .NET 整合** – 支援 C#、VB.NET 與 F#。  
- **高品質渲染** – 能在任何解析度下產生可掃描的條碼。  
- **廣泛的自訂功能** – 從符號類型到 X‑dimension、quiet zone 與 supplement space。  
- **無外部相依性** – 純受控程式庫，部署簡單。

## 補充條碼資料設定

讓我們從探討補充條碼資料設定的領域開始。Aspose.BarCode for .NET 為您提供輕鬆產生補充條碼的工具，讓您能完整掌控 EAN‑2 與 EAN‑5 條碼。但要如何著手呢？

首先，下載並安裝 Aspose.BarCode for .NET。您可以使用免費試用版先行測試，親自體驗其強大功能。設定完成後，依照我們的逐步指南操作，即可輕鬆掌握補充條碼資料的設定流程。

本節結束時，您將對如何建立 EAN‑2 與 EAN‑5 條碼有扎實的了解，成為更具彈性的 .NET 開發人員。

## 如何建立 EAN-2 條碼？（設定步驟）

1. **建立條碼產生器實例** – 選擇 `BarcodeGenerator` 類別，並將 symbology 設為 `EncodeTypes.EAN13`（或其他主類型）。  
2. **啟用補充部份** – 將 `SupplementData` 屬性設定為所需的數字字串（例如，`"12"` 為 EAN‑2 補充）。  
3. **調整視覺設定** – 可選地修改 `XDimension`、`BarHeight` 與 `QuietZone` 以符合您的版面需求。  
4. **儲存或渲染** – 呼叫 `Save` 將影像寫入檔案或串流。  

> *專業提示：* 補充資料長度必須正好為 2 位數（EAN‑2）或 5 位數（EAN‑5），否則條碼可能無法辨識。

## 補充條碼間距自訂

在條碼的世界裡，可自訂性是關鍵，而 Aspose.BarCode for .NET 正是在此發光發熱。現在，我們來聚焦於補充條碼間距的自訂。這部分主要是控制條碼中的 X‑Dimension 與 supplement space。

同樣地，您需要先安裝 Aspose.BarCode for .NET 並利用免費試用版。接著，依照我們的指引調整條碼間距。此自訂對於各種應用相當有用，從庫存管理到銷售點系統皆適用。

能依需求客製化條碼是一項寶貴技能，本節將確保您具備完整的能力。

## 如何自訂補充間距？

- **X‑Dimension** – 定義單一模組的寬度；數值越大，條碼整體尺寸越大。  
- **Supplement Space** – 主條碼與補充部份之間的間隙；可透過 `SupplementSpace` 屬性調整。  
- **Quiet Zone** – 整個條碼周圍的必備空白邊界；為確保掃描可靠性，至少保留 10 X‑Dimension 單位。  

在測試專案中嘗試這些設定，直到達到符合掃描硬體需求的視覺平衡為止。

## 常見使用案例

| 情境 | 補充資料的好處 |
|----------|------------------------------|
| **零售價格延伸** | EAN‑5 可直接在標籤上編碼價格資訊。 |
| **雜誌期號** | EAN‑2 用於辨識期號，方便快速分類。 |
| **物流與追蹤** | 在主條碼上加入小型補充，可提供額外的路由資訊，且不會增加標籤尺寸。 |

## 補充條碼資料教學
### [補充條碼資料設定](./supplemental-barcode-data-configuration/)
使用 Aspose.BarCode for .NET 產生補充條碼資料。輕鬆自訂 EAN-2 與 EAN-5 條碼。提供給 .NET 開發人員的逐步指南。

### [補充條碼間距自訂](./supplemental-barcode-space-customization/)
使用 Aspose.BarCode for .NET 輕鬆自訂條碼。控制 X-Dimension 與 supplement space。立即試用免費版！

## 常見問題

**Q: 我可以用同一段程式碼產生 EAN‑2 與 EAN‑5 嗎？**  
A: 可以。只要將 `SupplementData` 長度改為相應的位數（EAN‑2 為 2 位，EAN‑5 為 5 位），函式庫就會渲染正確的符號。

**Q: 我需要自行計算補充部分的檢查碼嗎？**  
A: 不需要。Aspose.BarCode 會自動計算並附加所需的檢查碼。

**Q: 在迴圈中產生條碼的數量有限制嗎？**  
A: 函式庫已針對大量產生進行最佳化；但在處理極大量影像集合時需留意記憶體使用情況。

**Q: 我要如何將條碼嵌入 PDF 或 Word 文件？**  
A: 先將條碼儲存為影像（PNG、JPEG 等），再使用您偏好的文件產生 API（例如 Aspose.PDF 或 Aspose.Words）插入。

**Q: 如果掃描器無法讀取補充部份怎麼辦？**  
A: 請確認 `SupplementSpace` 至少為 2 X‑Dimension 單位，且 quiet zone 符合掃描器規格。

---

**最後更新：** 2026-03-07  
**測試環境：** Aspose.BarCode for .NET 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}