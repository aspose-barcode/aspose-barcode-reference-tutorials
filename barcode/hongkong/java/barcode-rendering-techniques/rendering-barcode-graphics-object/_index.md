---
date: 2025-12-17
description: 學習如何在 Java 中建立條碼圖形物件、產生條碼圖像，並使用 Aspose.BarCode 在 Java 中呈現條碼。本一步步指南涵蓋
  Code128 條碼產生器（Java）及自訂技巧。
linktitle: Rendering Barcode to Graphics Object
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 在 Java 中建立條碼圖形物件
url: /zh-hant/java/barcode-rendering-techniques/rendering-barcode-graphics-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.BarCode 建立條碼圖形物件

在現代的 Java 應用程式中，您常常需要 **create barcode graphics object** 以用於標籤、庫存或票務系統。Aspose.BarCode for Java 讓此工作變得簡單，讓您 **generate barcode image Java** 檔案並直接在圖形上下文中呈現。本文將逐步說明完整流程——從環境設定到在 Java `Canvas` 上顯示條碼。

## 快速解答
- **create barcode graphics object 是什麼意思？** 它指的是將條碼渲染到 Java 圖形表面（例如 `Canvas`、`Graphics2D`）。  
- **範例中使用的條碼類型是什麼？** CODE_128，一種常見的線性條碼。  
- **執行範例是否需要授權？** 開發時可使用免費試用版；正式上線需購買商業授權。  
- **可以自訂顏色或尺寸嗎？** 可以，Aspose.BarCode 提供豐富的樣式設定選項。  
- **此程式碼是否相容於 Java 8 及以上版本？** 當然相容，能在任何 Java 8+ 執行環境執行。

## 什麼是條碼圖形物件？
條碼圖形物件就是將條碼資料以視覺方式繪製到 Java 圖形元件上。透過在 `Graphics` 物件上渲染條碼，您可以將其嵌入自訂 UI 元件、PDF 或影像，而不必先將檔案儲存至磁碟。

## 為什麼要使用 Aspose.BarCode for Java？
- **Full‑featured API** – 支援數十種條碼類型，包括 CODE_128、QR、DataMatrix 等。  
- **No external dependencies** – 純 Java，無需本機函式庫。  
- **Easy customization** – 可程式化調整顏色、尺寸、邊距與文字。  
- **High performance** – 適用於桌面或伺服器環境的即時渲染。

## 前置條件
- Java 開發環境（JDK 8 或更新版本）。  
- Aspose.BarCode for Java 函式庫 – 從 [here](https://releases.aspose.com/barcode/java/) 下載。  
- IDE，例如 Eclipse、IntelliJ IDEA 或 NetBeans。

## 匯入套件
首先，匯入標準的 Java AWT 類別以及 Aspose.BarCode 命名空間。

```java
import java.awt.Dimension;
import java.awt.Frame;
import java.awt.Graphics;
import java.awt.Image;
import java.awt.MediaTracker;
import java.io.File;
import java.io.IOException;

import javax.imageio.ImageIO;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何在 Java 中建立條碼圖形物件
以下是逐步說明，展示如何建立視窗、產生 CODE_128 條碼、將其儲存為影像，最後在 `Canvas` 上繪製。

### 步驟 1：設定 Frame 並啟動 Canvas
`RenderBarcodeToGraphicsObject` 類別會建立一個簡易的 `Frame`，加入自訂的 `Canvas`（用來渲染條碼），並顯示視窗。

```java
//ExStart: RenderBarcodeToGraphicsObject
public class RenderBarcodeToGraphicsObject {
    public static void main(String[] args) {
        // Create frame instance
        Frame f = new Frame();
        // Set frame size
        f.setSize(300, 300);
        // Create and add barcode instance to frame
        f.add(new MyBarCode());
        // Display frame
        f.setVisible(true);
    }
}
```

### 步驟 2：在 Canvas 中實作條碼渲染
`MyBarCode` 繼承自 `java.awt.Canvas`。在 `paint` 方法中，我們產生 CODE_128 條碼，將其儲存為 `barcode.png`，載入影像，並繪製到 canvas 上。

```java
class MyBarCode extends java.awt.Canvas {
    public void paint(Graphics g) {
        // The path to the resource directory.
        String dataDir = "Your Document Directory";
        String fileName = dataDir + "barcode.png";

        BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
        try {
            bb.save(fileName);
        } catch (IOException e1) {
            e1.printStackTrace();
        }

        // Load and Draw the image on applet
        MediaTracker tr = new MediaTracker(this);

        File sourceimage = new File(fileName);
        Image image;
        try {
            image = ImageIO.read(sourceimage);
            tr.addImage(image, 0);
            g.drawImage(image, 0, 0, this);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    public Dimension getPreferredSize() {
        return new Dimension(300, 300);
    }
}
```

## 產生 Barcode Image Java – 內部運作原理
- **BarcodeGenerator** 依據選取的條碼類型（`CODE_128`）建立條碼資料。  
- **bb.save(fileName)** 將 PNG 檔寫入磁碟——這就是 **generate barcode image Java** 步驟。  
- **ImageIO.read** 載入 PNG，`Graphics.drawImage` 將其繪製到 canvas，完成 **create barcode graphics object** 流程。

## 常見問題與解決方案
| Issue | Solution |
|-------|----------|
| `barcode.png` 發生 `FileNotFoundException` | 確保 `dataDir` 指向已存在且可寫入的資料夾，或使用絕對路徑。 |
| 條碼在 canvas 上未顯示 | 在儲存影像後呼叫 `repaint()`，或確認影像尺寸與 canvas 大小相符。 |
| 生產環境出現 LicenseException | 在建立產生器之前套用 Aspose.BarCode 授權：`License lic = new License(); lic.setLicense("Aspose.BarCode.lic");` |

## 常見問答

### Aspose.BarCode 是否相容於所有 Java 開發環境？
是的，Aspose.BarCode 可在任何支援 Java 的 IDE 中使用，包括 Eclipse、IntelliJ IDEA 與 NetBeans。

### 我可以自訂產生的條碼外觀嗎？
當然可以！您可以使用 `BarcodeGenerator` 的屬性變更顏色、加入邊距，並修改文字。

### Aspose.BarCode 支援多種條碼類型嗎？
是的，它支援廣泛的條碼類型，例如 CODE_128、QR Code、DataMatrix、UPC 等等。

### 有提供 Aspose.BarCode 的試用版嗎？
有，您可以在此免費試用 [here](https://releases.aspose.com/)。

### 若遇到問題，我可以向哪裡尋求協助？
請前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 取得社群支援與官方協助。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}