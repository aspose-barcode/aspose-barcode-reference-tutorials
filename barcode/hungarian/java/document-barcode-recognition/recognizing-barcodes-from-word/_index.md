---
date: 2026-04-12
description: Ismerje meg, hogyan ismerhet fel vonalkódot Word‑dokumentumokból az Aspose.BarCode
  for Java használatával. Ez az útmutató bemutatja, hogyan adhat hozzá vonalkódot
  a Wordhöz, és hogyan nyerhet ki képeket a Wordből.
keywords:
- how to recognize barcode
- add barcode to word
- read barcode from image
- extract images from word
- barcode detection java
linktitle: Vonalkódok felismerése Word dokumentumokból
second_title: Aspose.BarCode Java API
title: Hogyan ismerjünk fel vonalkódot Word dokumentumokból – Java útmutató
url: /hu/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan ismerjük fel a vonalkódot Word dokumentumokból – Java útmutató

## Bevezetés

Ha **hogyan ismerhető fel a vonalkód** beágyazva egy Microsoft Word fájlba, jó helyen jársz. Ebben az útmutatóban végigvezetünk egy teljes, vég‑től‑végig példán, amely az Aspose.BarCode for Java-t használja vonalkód generálásához, annak Word dokumentumba való beszúrásához, a kép kinyeréséhez, és végül a vonalkód adatainak olvasásához. A végén meg is fogod látni, hogyan **add barcode to Word**, **extract images from Word**, és **barcode detection java**‑stílusú műveleteket hajts végre – mindezt csak néhány kódsorral.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.BarCode for Java (plus Aspose.Words for handling .docx files).  
- **Olvashatok vonalkódot képből?** Igen – a `BarCodeReader` képes dekódolni a Word-ből kinyert képeket.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges; ingyenes próba elérhető.  
- **Melyik Java verzió támogatott?** Bármely JDK 8 + futtatókörnyezet működik.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap prototípushoz.

## Mi a vonalkód felismerés egy Word dokumentumból?

A vonalkód felismerés azt jelenti, hogy beolvasunk egy képet, amely egy Word fájlban található, és a vizuális mintát visszaalakítjuk az eredeti adatkarakterláncba (pl. „test‑123”). Az Aspose.BarCode biztosítja a dekódoló motorját, míg az Aspose.Words lehetővé teszi a kép kinyerését a .doc/.docx konténerből.

## Miért használjuk az Aspose.BarCode for Java-t?

- **Magas pontosság** 60+ szimbólumon, beleértve a Code 39, QR, DataMatrix stb.  
- **Nincs külső függőség** – tiszta Java, nincs natív könyvtár.  
- **Zökkenőmentes integráció** az Aspose.Words-szal, ami egyszerűvé teszi a **extract images from Word** és aztán a **read barcode from image**.  
- **Robusztus licencelés**, amely működik asztali, szerver és felhő környezetekben.

## Előfeltételek

Mielőtt a kódba merülnénk, győződj meg róla, hogy rendelkezel:

- **Java Development Kit (JDK)** – a legújabb verzió ajánlott.  
- **Aspose.BarCode for Java** – töltsd le és telepítsd a könyvtárat a hivatalos oldalról [itt](https://releases.aspose.com/barcode/java/).  
- **IDE** – IntelliJ IDEA, Eclipse, vagy bármely kedvelt szerkesztő.

## Csomagok importálása

A Java projektedben importáld a szükséges Aspose.BarCode és Aspose.Words osztályokat:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## 1. lépés: Vonalkód kép generálása

Először hozz létre egy vonalkód képet, amelyet később a Word fájlba ágyazunk be.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## 2. lépés: Vonalkód hozzáadása Word dokumentumhoz

Most beillesztjük a frissen generált képet egy új Word dokumentumba. Ez bemutatja a **add barcode to word** esetet.

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## 3. lépés: Képek kinyerése és a vonalkód felismerése

A dokumentum mentése után kinyerhetjük az összes képet (beleértve a vonalkódot is), és minden egyes képen futtathatjuk a **barcode detection java**-t.

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Pro tip:** Ha **read barcode from image** fájlokra van szükséged, amelyek nem egy Word dokumentumban vannak, egyszerűen add át a fájl útvonalát a `BarCodeReader`-nek – ugyanaz a dekódoló logika érvényes.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` a `shape.getImageData()`-nél | A shape nem tartalmaz képet. | Adj hozzá egy `shape.hasImage()` ellenőrzést (már bemutatva). |
| Helytelen vonalkód típus visszaadva | Rossz `DecodeType` használata. | Egyeztesd a generáláskor használt `EncodeTypes`-et (pl. `CODE_39_STANDARD`). |
| A kép nem mentődik megfelelően | Hiányzó írási jogosultság a `dataDir`-ben. | Győződj meg arról, hogy a könyvtár létezik és írható. |
| Licenc nincs alkalmazva | Az értékelő mód korlátozza a funkcionalitást. | Töltsd be az Aspose licencet az alkalmazás indításakor: `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` |

## Gyakran ismételt kérdések

### Q: Használhatom az Aspose.BarCode for Java-t kereskedelmi projektekben?  
A: Igen, az Aspose.BarCode for Java kereskedelmi felhasználásra is elérhető. A licenc részleteket megtalálod [itt](https://purchase.aspose.com/buy).

### Q: Elérhető ingyenes próba az Aspose.BarCode for Java-hoz?  
A: Igen, a funkciókat ingyenes próba letöltésével is kipróbálhatod [itt](https://releases.aspose.com/).

### Q: Hogyan kaphatok támogatást az Aspose.BarCode for Java-hoz?  
A: Bármilyen segítség vagy kérdés esetén látogasd meg az Aspose.BarCode fórumot [itt](https://forum.aspose.com/c/barcode/13).

### Q: Elérhetők ideiglenes licencek az Aspose.BarCode for Java-hoz?  
A: Igen, ideiglenes licenceket szerezhetsz [itt](https://purchase.aspose.com/temporary-license/).

### Q: Hol találom az Aspose.BarCode for Java dokumentációját?  
A: Tekintsd meg a részletes dokumentációt [itt](https://reference.aspose.com/barcode/java/).

---  

**Utoljára frissítve:** 2026-04-12  
**Tesztelve:** Aspose.BarCode 24.11 for Java  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}