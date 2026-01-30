---
date: 2026-01-30
description: Tanulja meg, hogyan használja a vonalkód minőségi mutatót a vonalkód
  leolvasási eredmények validálásához Java-ban az Aspose.Barcode segítségével. Lépésről‑lépésre
  útmutató a felismerési minőségi százalék lekéréséhez.
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Vonalkód minőségi metrika – Aspose.Barcode Java
url: /hu/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód Minőségi M **Mi jelent a „olvas%), amelyet a könyvtár minden dekódolt vonalkódhoz szükséges?** Bármely friss Aspose.Barcode Java kiadás (a példában a legújabb 24.x sorozatot használjuk).  
- **Szükségem van licencre?** Ideiglenes licenc a teszteléshez elegendő; a termeléshez teljes licenc szükséges Igen – a `DecodeType.ALL_SUPPORTED_TYPES` jelző engedély támogatott összes formátumot.  
- **A minőségi érték megbízható a QR‑D és 2‑D szimbólumokra is.

## Mi az a Vonalkód Minőségi Metrika és hogyan értékelhető az Aspose.Barcode Java-val?

** teszi aását és elemzését külső függőségek nélkül. Ennek egyik leghasznosabb diagnosztikai funkciója a **vonalkód minőségi metrika**, amely megmutatja, milyen magabiztosan dekódolta a motor a szimbólumot. Ez a metrika elengedhetetlen, amikor el kell dönteni, hogy elfogadjukikát kell indítani.

## Miért használjuk az Asposeához?

- **Következetes bizalmi pontszámok** az összes támogatott szimbólely JVM‑kompatibilis platformon működik.  
- **Finomhangolt vezérlés**: a minőséget egyenkjük le, nem csak globális siker/hiba értéket.  
- **Teljesítmény‑optimalizált** olvasó motor, amely a asztali gépektől a felhőszolgáltatásokig skálázható.

## Hogyan validáljuk a vonalkód beolvasást a Vonalkód Minőségi Metrikával?

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- **Java fejlesztői környezet** – JDK 8 vagy újabb, kedvenc IDE‑vel (IntelliJ, Eclipse, VS Code, stb.).  
- **Aspose.Barcode Java könyvtár** – töltsd le a legújabb JAR‑t a hivatalos oldalról: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Minta vonalkód kép** – a bemutató a `code39Extended.jpg` fájlt használja, amely a `BarcodeReader/advanced_features/` mappában található.

Miután minden előkészítve van, vágjunk bele a kódba.

## Importálási névterek

A következő importok biztosítják a hozzáférést a minőség kinyeréséhez szükséges olvasó- és eredményosztályokhoz.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### 1. lépés: Állítsd be az erőforrás könyvtár útvonalát

inta képet tartalmazza. A `Utils.getDataDir` egy segédfüggvény, amely a jelenlegi projekthez abszolút útvonalat ad.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### 2. lépés: Inicializáld a BarCodeReader objektumot

Hozz létre egy `BarCodeReader` példányt, amely a képfájlra mutat, és beállítja, hogy **minden támogatott vonalkódtípust** próbáljon meg.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### 3. lépés: Olvasd be a vonalkódokat és szerezd meg a minőségi százalékot

Iterálj végig minden észlelt vonalkódon, írd ki a szövegét, típusát, és a `getReadingQuality()` által visszaadott **olvasási minőség** százalékot.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**Mi történik itt?**  
- `readBarCodes()` egy `BarCodeResult` objektumok gyűjteményét adja vissza, egyet minden megtalált vondouble` értéket ad, amely a bizalmi szintet jelzi – a **vonalkód minőségi metrika**.  
- Ezt az értéket felhasználhatod annak eldöntésére, hogy a beolvasás elfogadható-e, vagy fel kell-e kérned a felhasználót egy újabb próbálkozásra, ezzel **validálva a vonalkód beolvasást**.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|-------|-------|-----|
| **A minőség mindig 0** | A kép alacsony felbontású vagy erősen el nagyobb felbontású forrást, vagy alkalmazz képelőfeldolgozást (pl. élesítés). |
| **Nem található vonalkód** | Hibás `DecodeType` jelző. | Győződj meg róla, hogy `DecodeType.ALL_SUPPORTED_TYPES`-t használsz, vagy add meg a pontosan várt típust. |
| **Kivétel a `Utils.getDataDir`-nél** | A projekt struktúrája eltér a példától. | Cseréld le a segédfüggvényt egy kézzel megadott abszolút vagy relatív útvonalra, amely megfelel a saját felépítésednek. |

## Gyakran Ismételt Kérdések

### Q1: Az Aspose.Barcode kompatibilis minden vonalk Az Aspose.Barcode széles körű vonalkód szimbólumot támogat, beleértve az 1‑D (Code‑39, Code‑128, UPC) és 2‑D (QR, DataMatrix, PDF417) szabványokat.

### Q2: Használhatom az Aspose.Barcode-ot kereskedelmi célben egyaránt használhatod. A licenc részletei [itt](https://purchase.aspose.com/buy) érhetők el.

### Q3: Hogyan szerezhetek ideiglenes licencet tesztelési célra?

A3: Ideiglenes licencet a Aspose portálon szerezhetsz [itt](https://purchase.aspose.com/temporary-license/).

### Q4: Hol találok további támogatást és közösségi megbeszéléseket?

A4: Látogasd meg az [Aspose.Barcode fórumot](https://forum.aspose.com/c/barcode/13) a közösségi támogatás és hivatalos segítség érdekében.

### Q5: Van-e kódrészlet a dokumentációban?

A5: Igen, átfogó kópminták állnak rendelkezésre a hivatalos dokumentációban [itt](https).

## Összegzés

Az **Aspose.Barcode Java** használatával könnyedén lekérely beolvasott szimbólumhoz. Ez a metrika lehetővé teszi, hogy intelligensebb validálási logikát építs, javítsd a felhasználói élményt, és magas adatintegritást tarts fenn Java alkalmazásaidban.

---

 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}