---
title: Több vonalkód generálása egyetlen képen Java nyelven az Aspose.BarCode segítségével
linktitle: Több vonalkód generálása egyetlen képen
second_title: Aspose.BarCode Java API
description: Az Aspose.BarCode for Java segítségével könnyedén generálhat több vonalkódot egyetlen képen. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
weight: 19
url: /hu/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több vonalkód generálása egyetlen képen Java nyelven az Aspose.BarCode segítségével

## Bevezetés

A Java programozás dinamikus világában a vonalkódok hatékony létrehozása és kezelése kulcsfontosságú a különféle alkalmazások számára. Az Aspose.BarCode for Java leegyszerűsíti ezt a folyamatot, lehetővé téve a fejlesztők számára, hogy több vonalkódot zökkenőmentesen generáljanak egyetlen képen. Ez az oktatóanyag végigvezeti Önt az Aspose.BarCode Java környezetben való használatához szükséges lépéseken.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- A Java programozás alapvető ismerete.
- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.BarCode for Java könyvtár letöltve és beállítva. Letöltheti[itt](https://releases.aspose.com/barcode/java/).
- Integrált fejlesztői környezet (IDE), például az Eclipse vagy az IntelliJ IDEA.

## Névterek importálása

Java-projektjében importálja a szükséges névtereket az Aspose.BarCode funkció eléréséhez. Adja hozzá a következő importálási utasításokat a Java osztály elejéhez:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## 1. lépés: Állítsa be az erőforrás-könyvtárat

Határozza meg annak az erőforrás-könyvtárnak az elérési útját, ahová a generált vonalkódok mentésre kerülnek. Ez a könyvtár döntő fontosságú a vonalkódképek rendszerezéséhez és kezeléséhez.

```java
// Az erőforrás-könyvtár elérési útja.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 2. lépés: Hozzon létre egy vonalkód-gyűjteményt

A vonalkód adatok tárolásához inicializáljon egy HashMap-et. A gyűjtemény minden bejegyzése egy vonalkódot képvisel a megfelelő kódolási típussal.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 3. lépés: Vonalkódképek generálása

Ismételje meg a gyűjteményt, és állítson elő vonalkódképeket az Aspose.BarCode könyvtár segítségével. Tárolja a képeket egy ArrayList-ben további feldolgozás céljából.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 4. lépés: Hozzon létre egy kombinált képet

Határozza meg a vonalkód képek maximális szélességét és teljes magasságát. Hozzon létre egy BufferedImage-et, hogy az egyes vonalkódképeket egyetlen kimeneti képpé egyesítse.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```
## 5. lépés: Mentse el az eredményt

Mentse el a végső kombinált képet egy megadott fájlhelyre.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Következtetés

Gratulálunk! Sikeresen generált több vonalkódot egyetlen képen az Aspose.BarCode for Java használatával. Ez a hatékony könyvtár leegyszerűsíti a vonalkódkezelést, így felbecsülhetetlen értékű eszköz a Java fejlesztők számára.

## GYIK

### 1. kérdés: Testreszabhatom az egyes vonalkódok megjelenését a generált képen?

1. válasz: Igen, az Aspose.BarCode kiterjedt testreszabási lehetőségeket biztosít a vonalkód megjelenéséhez, lehetővé téve, hogy az egyes vonalkódok stílusát saját igényei szerint szabja.

### 2. kérdés: Az Aspose.BarCode kompatibilis a különböző vonalkód szimbólumokkal?

A2: Abszolút! Az Aspose.BarCode a szimbólumok széles skáláját támogatja, beleértve a CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 és AZTEC kódokat, amint az ebben az oktatóanyagban látható.

### 3. kérdés: Hogyan integrálhatom az Aspose.BarCode-ot a Java projektembe?

 3. válasz: Egyszerűen töltse le az Aspose.BarCode for Java könyvtárat innen[itt](https://releases.aspose.com/barcode/java/) és kövesse a dokumentációban található telepítési utasításokat.

### 4. kérdés: Használhatom az Aspose.BarCode-ot kereskedelmi alkalmazásokhoz?

 V4: Igen, engedélyt szerezhetsz innen[itt](https://purchase.aspose.com/buy) hogy az Aspose.BarCode-t kereskedelmi célokra használja.

### 5. kérdés: Vannak-e próbaverziók az Aspose.BarCode számára?

 A5: Természetesen! Az Aspose.BarCode szolgáltatásait ingyenes próbalicenc beszerzésével fedezheti fel[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
