---
category: general
date: 2026-07-30
description: 在 Python 中建立 Databar 堆疊全向條碼。請依照此步驟指南設定長寬比、XDimension，並使用 Python 條碼產生器匯出
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: zh-hant
lastmod: 2026-07-30
og_description: 在 Python 中建立 Databar 堆疊全向條碼。本教學示範如何設定 X 尺寸、微調 DataBar 長寬比，並以 BarCodeImageFormat
  儲存為 PNG。
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: 創建 Databar Stacked 全方向條碼 – Python 教學
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: 在 Python 中建立堆疊全向 DataBar 條碼
url: /zh-hant/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中建立 Databar Stacked Omnidirectional 條碼

是否曾需要在 Python 中**建立 databar stacked omnidirectional** 條碼，但不知從何開始？你並不孤單——許多開發者在第一次使用 `BarcodeGenerator` 類別時都會卡住。好消息是，一旦了解關鍵屬性，整個流程其實相當簡單。

本指南將逐步說明一個完整且可執行的範例，使用**python barcode generator** 來設定 XDimension、微調 DataBar 長寬比，最後匯出兩個 PNG 檔案。完成後，你將能熟練產生高品質的 stacked omnidirectional 符號，適用於任何庫存或物流專案。

## 你將學會

- 如何使用 GTIN‑14 負載實例化一個 **databar stacked omnidirectional** 產生器。  
- 為何 **XDimension pixel size** 會影響掃描可靠性。  
- **DataBar aspect ratio** 對列寬與高度的影響。  
- 如何將結果儲存為 **BarCodeImageFormat PNG** 檔案。  
- 重新使用同一個產生器物件以產生多種變體的技巧，且不會增加額外記憶體負擔。

### 先決條件

- Python 3.8+（我們使用的函式庫為純 Python，無需編譯的 wheel）。  
- `barcode-generator` 套件（透過 `pip install barcode-generator` 安裝）。  
- 可寫入的資料夾——腳本會在其中輸出兩個 PNG 圖片。

如果你已熟悉基本的 Python 匯入與物件導向程式碼，就可以開始了。

## 建立 Databar Stacked Omnidirectional 條碼 – 步驟概覽

以下我們將工作流程分為六個小步驟。每個步驟都是獨立的程式碼片段，你可以直接複製貼上到 REPL 或腳本檔案中。隨意嘗試——變更長寬比或 XDimension 即可立即得到不同的視覺風格。

---

## 步驟 1：建立 Databar Stacked Omnidirectional 產生器

首先，我們**建立 databar stacked omnidirectional** 產生器實例，傳入相應的 `EncodeTypes` 列舉以及資料字串。

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **為何重要：** `EncodeTypes.DatabarStackedOmniDirectional` 旗標告訴函式庫產生 stacked omnidirectional 符號，這是唯一能編碼至 14 位數且從任何角度皆可讀取的 DataBar 變體。

---

## 設定 XDimension 像素大小

**XDimension pixel size** 控制最小模組（最細的黑條）。`2` 像素的值在大多數螢幕顯示情境下表現良好。

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **專業提示：** 若打算以高 DPI 列印條碼，請將此值提升至 3 或 4，以避免邊緣模糊。

---

## 調整 DataBar 長寬比 (15)

**DataBar aspect ratio** 決定每列相對於高度的寬度。`15` 的長寬比會產生較寬的列，許多掃描器在快速移動捕捉時較為偏好此設定。

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **為何選 15？** 官方 GS1 規範建議 stacked omnidirectional 符號的長寬比介於 10 至 20 之間。我們選擇 `15` 作為平衡的預設值。

---

## 使用 BarCodeImageFormat 匯出 PNG 條碼

現在產生器已設定完成，我們將圖像寫入檔案。`BarCodeImageFormat.Png` 列舉確保無損輸出，適合後續處理。

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **你會看到：** 開啟產生的 PNG；你會看到乾淨且高對比度的條碼，且列相對較寬。

---

## 將 DataBar 長寬比改為 30

有時你需要較高的列而非較寬——可能是為了適配窄標籤。將 **DataBar aspect ratio** 改為 `30` 會使每列變高。

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **邊緣情況：** 非常高的長寬比（例如 >40）可能導致條碼超過一般標籤高度，請在實際印表機上測試後再決定。

---

## 再次以新長寬比匯出條碼

最後，我們重新使用相同的 `barcode_generator` 物件寫入第二個 PNG。無需重新建立產生器——只要變更屬性並再次呼叫 `Save` 即可。

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **結果：** 你現在擁有兩個 PNG 檔案——一個是寬列 (`AR15`)，另一個是高列 (`AR30`)。將它們並排比較，以決定哪個最適合你的掃描器配置。

---

## 完整範例程式

把所有步驟整合起來，以下是可立即執行的完整腳本。將 `YOUR_DIRECTORY` 替換為你機器上的絕對路徑。

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**預期輸出**（在你的主控台）：

```
✅ Two PNG files created – AR15 and AR30
```

兩個圖像檔案會出現在目標資料夾中，準備進行掃描測試。

---

## 結論

我們剛剛在 Python 中**建立了 databar stacked omnidirectional** 條碼，調整了 **XDimension pixel size**，試驗了兩種不同的 **DataBar aspect ratio** 設定，並將結果匯出為 **BarCodeImageFormat PNG** 檔案。整個工作流程僅需數行程式碼，卻能讓你完整掌控對掃描器最重要的視覺特性。

接下來可以做什麼？嘗試將負載換成其他 GTIN、透過將 PNG 轉為調色盤圖像來玩顏色，或產生一個 PDF 報告將兩個 PNG 並排嵌入。`BarcodeGenerator` 類別足夠彈性，能處理上述所有情境，盡情實驗吧。

對特定使用情境有疑問或遇到錯誤嗎？在下方留言，我很樂意協助。祝編程愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在此處示範的技巧之上。每個資源都提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}