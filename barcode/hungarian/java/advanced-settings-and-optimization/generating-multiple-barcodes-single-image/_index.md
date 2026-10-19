---
date: 2026-10-19
description: Ismerje meg, hogyan hozhat létre QR code java-t, és generálhat több barcode-t
  egyetlen képen az Aspose.BarCode for Java segítségével. Tartalmaz setup, code, és
  troubleshooting.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Több barcode generálása egyetlen képen
og_description: QR code java létrehozása és több barcode típus egyetlen képre kombinálása
  az Aspose.BarCode for Java segítségével. Kövesse a lépésről‑lépésre útmutatót, tekintse
  meg a code snippets-et, és tanulja meg a troubleshooting tippeket.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR code java létrehozása – több barcode generálása egy képen
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR code java létrehozása – több barcode generálása egy képen
url: /hu/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR kód létrehozása Java‑ban – több vonalkód generálása egy képen

## Bevezetés

Ebben az oktatóanyagban megtanulja, hogyan hozhat létre QR kódot Java‑ban, és hogyan egyesítheti több különböző vonalkódtípust egyetlen vásznon az **Aspose.BarCode for Java** segítségével. Akár egy kompakt QR címkét, egy termék vonalkódot, vagy a 2‑D és lineáris szimbólumok keverékét igényli, ez az útmutató minden lépésen végigvezeti – a projekt beállításától a végső kombinált kép mentéséig –, így azonnal elkezdheti a vonalkód-generálás integrálását Java‑alkalmazásaiba.

## Gyors válaszok
- **Melyik könyvtárat használjam?** Az Aspose.BarCode for Java a legteljesebb szimbólumkészletet biztosítja.  
- **Generálhatok különböző vonalkódtípusokat együtt?** Igen, egyetlen vásznon keverhet CODE_39, QR, AZTEC és egyéb típusokat.  
- **Szükségem van licencre a fejlesztéshez?** A ingyenes próba verzió teszteléshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik Java verzió támogatott?** A Java 8 és újabb verziók teljesen kompatibilisek.  
- **A kimeneti formátum konfigurálható?** A kombinált képet exportálhatja PNG, JPEG, BMP vagy TIFF formátumban.

## Mi az a QR kód létrehozása Java‑ban?

`create QR code java` a folyamatra utal, amely során egy szöveges karakterláncot két‑dimenziós mátrixszá alakítanak, amelyet okostelefonok vagy vonalkódolvasók tudnak beolvasni. Az Aspose.BarCode for Java végzi a kódolást és a megjelenítést, így a pixel‑szintű képfeldolgozás helyett az üzleti logikára koncentrálhat.

## Miért használja az Aspose.BarCode Java‑t vonalkódok generálásához Java‑ban?

Az Aspose.BarCode **több mint 50 vonalkód szimbólumot** támogat – beleértve a QR, Data Matrix, Code 128, AZTEC és a hagyományos lineáris kódokat – így a legváltozatosabb Java vonalkód könyvtár. **Antialiasinggal renderelt képeket** akár 1200 dpi felbontásban készít, ami éles beolvasást biztosít képernyőn és nyomtatásban egyaránt. Az API csak a JVM‑et igényli, és egy folyékony konfigurációs modellt kínál a méret, szín, margók és hibajavítás testreszabásához néhány kódsorral.

## Előfeltételek

- Alapos Java alapismeretek.  
- JDK 8 vagy újabb telepítve és a PATH‑ban beállítva.  
- Az Aspose.BarCode for Java JAR (letölthető a hivatalos Aspose.BarCode for Java letöltési oldalról).  
- Egy IDE, például IntelliJ IDEA vagy Eclipse a minta szerkesztéséhez és futtatásához.  

## Névterek importálása

Az importálási utasítások beviszik az Aspose.BarCode osztályokat, mint a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat`, a láthatóságba, lehetővé téve, hogy teljesen kvalifikált nevek nélkül hivatkozzon rájuk.  
A `BarcodeGenerator` a fő osztály a vonalkód képek konfigurálásához és generálásához.  
Az `EncodeTypes` egy enumeráció az Aspose.BarCode‑ban, amely meghatározza a generálandó vonalkód szimbólumát.  
A `BarCodeImageFormat` a generált vonalkód kimeneti képformátumát definiálja.

## 1. lépés: erőforrás könyvtár beállítása

A **erőforrás könyvtár** az a mappa a fájlrendszerén, ahová az összes generált vonalkód kép kerül mentésre. Egyszeri definiálása rendezetten tartja a projektet, és egyszerűvé teszi a régi fájlok tisztítását.

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

## 2. lépés: vonalkódok gyűjteményének létrehozása

A `HashMap<String, EncodeTypes>` tárolja minden vonalkód adatkarakterláncát a használni kívánt szimbólummal együtt. A `HashMap` egy Java gyűjtemény, amely kulcsokat értékekhez rendel. Ez a gyűjtemény hajtja végre a következő generálási ciklust. Az `EncodeTypes` egy enumeráció, amely meghatározza, melyik vonalkódtípust kell generálni.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 3. lépés: vonalkód képek generálása

A generálási ciklus végigiterál a `HashMap`‑en, minden bejegyzéshez létrehozza a `BarcodeGenerator`‑t, és meghívja a `generateBarCodeImage()`‑t, hogy egy `BufferedImage`‑et kapjon. A `generateBarCodeImage()` egy renderelt vonalkódot tartalmazó `BufferedImage`‑et hoz létre. A `BufferedImage` egy Java osztály, amely memóriában tárolt képet képvisel. Minden képet egy `ArrayList<BufferedImage>`‑hez adunk hozzá a későbbi összerendezéshez. Az `ArrayList` egy dinamikusan méretezhető lista implementáció Java‑ban.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 4. lépés: kombinált kép létrehozása

Először az algoritmus kiszámítja az összes vonalkód kép **maximális szélességét** és a **teljes magasságot**, amely a képek függőleges egymásra helyezéséhez szükséges opcionális távolsággal. Ezután létrehoz egy ilyen méretű `BufferedImage`‑et, és a `Graphics2D` objektum segítségével minden vonalkódot a vászonra rajzol. A `Graphics2D` egy Java osztály, amely 2D renderelési képességeket biztosít alakzatok és képek rajzolásához.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 5. lépés: az eredmény mentése

Végül a kombinált képet az `ImageIO.write` segítségével írja a lemezre, a megadott formátumban (PNG, JPEG, BMP vagy TIFF). Az `ImageIO.write` egy `BufferedImage`‑et ír a fájlba a megadott formátumban. A fájl útvonala a korábban definiált erőforrás könyvtárhoz relatív.

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

## Gyakori felhasználási esetek több vonalkód generálásához

- **Csomagolási címkék** – egyetlen címkén kombinálja a termék, tétel és szállítási kódokat a nyomtatási költségek csökkentése érdekében.  
- **Rendezvényjegyek** – QR, Data Matrix és Code 128 azonosítókat ágyaz be a helyszín különböző beolvasó állomásaihoz.  
- **Készletkezelés** – SKU, RFID címke adat és sorozatszámok együttes megjelenítése a gyors ellenőrzés és nyomonkövetés érdekében.  

## Hibakeresés és tippek

- **Képméret problémák** – állítsa a `offset` változót a vonalkódok közötti távolság növeléséhez vagy csökkentéséhez.  
- **Nem támogatott szimbólum** – ellenőrizze, hogy az Aspose.BarCode verziója támogatja-e a kívánt vonalkódtípust; az újabb kiadások további 2‑D kódokat adnak hozzá.  
- **Teljesítmény** – egyetlen `Graphics2D` objektum újrafelhasználása sok kép generálásakor egy ciklusban csökkenti az objektumok allokációjának terhelését.  

## Gyakran feltett kérdések

**Q: Testreszabhatom az egyes vonalkódok megjelenését a generált képen?**  
A: Igen. Használja a `BarcodeGenerator` tulajdonságait, például `setBarColor`, `setBackgroundColor` és `setXDimension`, hogy minden vonalkódot önállóan formázzon a vászonra helyezés előtt.

**Q: Az Aspose.BarCode kompatibilis különböző vonalkód szimbólumokkal?**  
A: Teljes mértékben. A könyvtár több mint 50 szimbólumot támogat, beleértve a CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 és AZTEC típusokat, ahogy ebben az oktatóanyagban is látható.

**Q: Hogyan integráljam az Aspose.BarCode‑t a Java projektbe?**  
A: Töltse le a JAR‑t az Aspose.BarCode for Java könyvtár letöltési oldaláról, adja hozzá a projekt osztályútvonalához, és importálja a szükséges névtereket, ahogy a „Névterek importálása” szakaszban látható.

**Q: Használhatom az Aspose.BarCode‑t kereskedelmi alkalmazásokhoz?**  
A: Igen. Vásároljon licencet az Aspose.BarCode licenc vásárlási oldaláról, hogy eltávolítsa a próba korlátokat és teljes termelési támogatást kapjon.

**Q: Elérhetők próba lehetőségek az Aspose.BarCode‑hoz?**  
A: Természetesen. Egy ingyenes próba licenc elérhető az Aspose.BarCode ingyenes próba letöltési oldaláról, amely teljes API hozzáférést biztosít a kiértékeléshez.

**Q: Hogyan generálhatok nagy felbontású QR kódot nyomtatáshoz?**  
A: Állítsa be a `setResolutionDpi` tulajdonságot a `BarcodeGenerator`‑on, mielőtt meghívná a `generateBarCodeImage()`‑t, majd mentse az eredményt veszteségmentes formátumban, például PNG‑ben.

**Q: Mit tegyek, ha a kombinált kép levágottnak tűnik?**  
A: Ellenőrizze, hogy a `offset` és a vászon méret számítások helyesen figyelembe veszik-e az összes vonalkód magasságát; a vászon magasságának növelése vagy az egyes vonalkódok méretének csökkentése megoldja a legtöbb levágási problémát.

**Utolsó frissítés:** 2026-10-19  
**Tesztelt verzió:** Aspose.BarCode for Java 24.11  
**Szerző:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Kapcsolódó oktatóanyagok

- [Hogyan hozhat létre vonalkód képet Java‑ban – Keret hozzáadása az Aspose‑szal](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Hogyan generáljon vonalkódot Java‑ban: mentés stream‑ekbe az Aspose.BarCode‑dal](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Hogyan generáljon vonalkódot Java‑ban és nyomtasson vonalkódot az Aspose‑szal](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}