---
date: 2026-04-08
description: Ismerje meg, hogyan olvashat be vonalkódot PDF‑ből Java‑ban az Aspose.BarCode
  használatával. Ez az útmutató azt is bemutatja, hogyan generálhat vonalkód képet
  Java‑ban, és hogyan nyerhet ki képeket PDF‑ből Java‑ban.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Vonalkódok felismerése PDF-ből
second_title: Aspose.BarCode Java API
title: Hogyan olvassunk be vonalkódot PDF-ből Java-ban az Aspose.BarCode segítségével
url: /hu/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Olvassa be a vonalkódot PDF-ből Java-ban

## Bevezetés

Üdvözöljük lépésről‑lépésre útmutatónkban, amely **bemutatja, hogyan olvassuk be a vonalkódot PDF-ből Java-ban** az Aspose.BarCode segítségével. A vonalkódok elengedhetetlenek az adatgyűjtés automatizálásához, és az Aspose.BarCode segítségével könnyedén felismerhetők a PDF‑dokumentumokban. Ebben a bemutatóban mindent végigvezetünk – a licencek beállításától a vonalkód kép generálásáig Java, a PDF‑hez való hozzáadáson, a PDF‑ből képek kinyeréséig Java, egészen a vonalkód visszaolvasásáig.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.BarCode for Java (plus Aspose.PDF a PDF‑kezeléshez).  
- **Generálhatok vonalkód képet Java-ban?** Igen – a `BarcodeGenerator` osztály lehetővé teszi PNG/JPEG képek létrehozását.  
- **Hogyan nyerhetők ki képek egy PDF‑ből?** Az Aspose.PDF `PdfExtractor` osztályával.  
- **Melyik vonalkód típust mutatja be a példa?** CODE‑39 (standard).  
- **Szükség van licencre?** Érvényes Aspose.BarCode és Aspose.PDF licenc szükséges a termelési használathoz.

## Miért használja az Aspose.BarCode-ot Java-ban?
- **Magas pontosság** – több tucat szimbólumot támogat, és alacsony felbontású képeken is működik.  
- **Nincs külső függőség** – tisztán Java, natív könyvtárak nélkül.  
- **Teljes PDF integráció** – kombinálható az Aspose.PDF‑vel a vonalkódok közvetlen olvasásához vagy beágyazásához PDF‑fájlokba.

## Előfeltételek

Mielőtt a kódba merülnél, győződj meg róla, hogy a következőkkel rendelkezel:

1. **Aspose.BarCode for Java licenc** – szerezd be a [Aspose Purchase](https://purchase.aspose.com/buy) oldalon.  
2. **Aspose.PDF licenc** – a PDF‑manipulációhoz szükséges; licencet igényelhetsz [itt](https://purchase.aspose.com/temporary-license/).  
3. **Aspose.BarCode könyvtár** – töltsd le a legújabb JAR‑t [innen](https://releases.aspose.com/barcode/java/).  

Miután megvannak a szükséges előfeltételek, importáljuk a szükséges csomagokat és kezdjünk kódolni.

## Csomagok importálása

A Java projektedben add hozzá az Aspose.BarCode és Aspose.PDF importokat. Ez a blokk változatlan az eredeti bemutatóból:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## 1. lépés: Vonalkód kép generálása Java

Először létrehozunk egy vonalkód képet, amelyet később beágyazunk egy PDF‑be. Ez bemutatja a **generate barcode image java** képességet.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## 2. lépés: PDF létrehozása és a vonalkód kép hozzáadása

Ezután felépítünk egy új PDF dokumentumot, és beillesztjük a korábban generált vonalkód képet.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## 3. lépés: Képek kinyerése a PDF‑ből Java

Miután a PDF készen áll, ki kell nyernünk a beágyazott képet, hogy a vonalkódot fel tudjuk olvasni. Ehhez használjuk a **extract images from pdf java** módszert.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## 4. lépés: A vonalkód felismerése a kinyert képekből

Végül minden kinyert képet átadunk a `BarCodeReader`‑nek, hogy visszanyerjük a kódolt szöveget.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Ismételd meg ezeket a lépéseket szükség szerint, a fájlneveket és útvonalakat a projekted struktúrájához igazítva.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Nem észlelhető vonalkód** | A kép minősége túl alacsony vagy a vonalkód túl kicsi. | Növeld a kép felbontását mentéskor (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` kivételt dob** | A PDF fájl nem található vagy az útvonal helytelen. | Ellenőrizd, hogy a `strPdfDoc` egy létező fájlra mutat, és hogy az alkalmazásnak van olvasási joga. |
| **Licenc nincs alkalmazva** | Az Aspose komponensek próbaverzióban futnak, ami korlátozza a kimenetet. | Töltsd be a licencfájlokat a program elején: `new License().setLicense("Aspose.BarCode.lic");` és hasonlóan az Aspose.PDF‑hez. |

## Gyakran Ismételt Kérdések (GYIK)

### K: Használhatom az Aspose.BarCode-ot Java-ban licenc nélkül?
Bár az Aspose.BarCode használható licenc nélkül, a teljes funkcionalitás és a licencfeltételek betartása érdekében ajánlott licencet beszerezni.

### K: Hogyan szerezhetek ideiglenes licencet az Aspose.BarCode for Java-hoz?
Ideiglenes licencet kaphatsz [itt](https://purchase.aspose.com/temporary-license/).

### K: Vannak korlátozások a támogatott vonalkód típusokra vonatkozóan?
Az Aspose.BarCode széles körű vonalkód típusokat támogat. A teljes listáért tekintsd meg a dokumentációt.

### K: Elérhető-e próbaverzió az Aspose.BarCode for Java-hoz?
Igen, a próbaverzió letölthető [innen](https://releases.aspose.com/).

### K: Hol kérhetek támogatást vagy tehetek fel kérdéseket az Aspose.BarCode for Java‑ról?
Látogass el az Aspose.BarCode [fórumára](https://forum.aspose.com/c/barcode/13) támogatás és megbeszélések céljából.

## Következtetés

Gratulálunk! Megtanultad, hogyan **olvass be vonalkódot PDF‑ből Java-ban** az Aspose.BarCode segítségével, hogyan **generálj vonalkód képet Java-ban**, és hogyan **nyerj ki képeket PDF‑ből Java-ban** további feldolgozáshoz. Fedezz fel további funkciókat, például kötegelt feldolgozást, különböző vonalkód szimbólumok kezelését, vagy integráld más Aspose termékekkel. A részletes információkért tekintsd meg a hivatalos [dokumentációt](https://reference.aspose.com/barcode/java/).

---

**Legutóbb frissítve:** 2026-04-08  
**Tesztelve:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}