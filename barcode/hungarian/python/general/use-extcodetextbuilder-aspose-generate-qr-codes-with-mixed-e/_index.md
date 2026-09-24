---
category: general
date: 2026-07-18
description: Használd az extcodetextbuilder aspose-t QR-kódok létrehozásához, amelyek
  egyszerű ASCII‑t és UTF‑8 orosz szöveget kombinálnak. Ismerd meg az Aspose.Barcode
  QR-kód generálását Pythonban.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: hu
lastmod: 2026-07-18
og_description: Az extcodetextbuilder használatával az Aspose lehetővé teszi, hogy
  egyszerű és UTF‑8 kódolt fragmentumokat keverjünk egy QR‑kódban. Kövesse ezt a lépésről‑lépésre
  útmutatót az Aspose.Barcode Pythonban.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: használja az extcodetextbuilder aspose – QR-kódok létrehozása vegyes ECI
  szöveggel
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Használja az ExtCodeTextBuilder-t az Aspose-ban: QR‑kódok generálása vegyes
  ECI szöveggel'
url: /hu/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – QR kódok építése vegyes ECI szöveggel

Gondolkodtál már azon, hogyan **use extcodetextbuilder aspose**-t használva egyszerre ágyazhatunk be egyszerű angol és cirill karaktereket egyetlen QR kódban? Nem vagy egyedül. Sok fejlesztő akad el, amikor ASCII‑t és nem‑ASCII adatot kell keverni, különösen, ha a célolvasó megfelelő ECI (Extended Channel Interpretation) jelzőket vár.  

Ebben az útmutatóban lépésről lépésre végigvezetünk egy QR kód létrehozásán, amely a “HELLO123” **és** a orosz “Привет” szót tartalmazza, mindezt az Aspose.Barcode Python API‑jával. A végére egy azonnal futtatható szkriptet kapsz, megérted, miért fontos minden hívás, és tudni fogod, hogyan állíthatod be a folyamatot más nyelvek vagy adatformátumok esetén.

## Mit fogsz megtanulni

- Hogyan **initialize ExtCodetextBuilder**-t inicializáljuk, és adjunk hozzá egyszerű valamint ECI‑kódolt töredékeket.  
- Miért felel meg az **ECI encoding** érték `3` az UTF‑8‑nak, és ez hogyan befolyásolja a beolvasást.  
- A pontos lépéssorozat egy **QR Code generator** beállításához az Aspose.Barcode‑dal.  
- Hogyan mentjük el a kapott képet és ellenőrizzük a vegyes tartalmat.  

**Prerequisites** – szükséged van Python 3.8+ verzióra, a `aspose-barcode` csomagra telepítve (`pip install aspose-barcode`), valamint egy mappára, ahová képeket írhatsz. Egyéb semmi.

---

## use extcodetextbuilder aspose vegyes kódszöveg építéséhez

Az első dolog, amire szükségünk van, egy `ExtCodetextBuilder` példány. Tekintsd úgy, mint egy builder mintát, amely különböző szövegrészeket fűz össze, miközben automatikusan beilleszti a megfelelő ECI jelzőket a háttérben.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Miért fontos ez:**  
- `add_plain_codetext` változatlanul hagyja az adatot, ami tökéletes számok vagy angol betűk esetén.  
- `add_eci_codetext` egy ECI szegmenst (`[ECI:3]`) szúr be a megadott karakterlánc elé, jelezve minden kompatibilis olvasónak, hogy a következő bájtok UTF‑8‑akódolásúak. Enélkül a szkenner a cirill bájtokat szemétnek tekintené.

> **Pro tipp:** Ha más karakterkészletre van szükséged, módosítsd az `eci_encoding` értékét az ECI táblázat szerint (pl. `26` az ISO‑8859‑1‑hez).  

---

## QR kód generálás inicializálása az Aspose.Barcode‑dal

Miután megvan a megfelelően formázott `extended_codetext`, átadhatjuk a QR kód generátornak. Az Aspose.Barcode elrejti az alacsony szintű QR mátrix létrehozást, így az adatokra koncentrálhatsz.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Mi történik itt?**  
- `BarcodeGenerator()` egy új generátor objektumot hoz létre alapértelmezett beállításokkal (méret, felbontás, stb.).  
- `set_symbology` megmondja a motornak, hogy QR kódot szeretnénk, nem például Code128-at.  

Ha magasabb hibajavítási szintre van szükséged, a `qr_generator.parameters.barcode.qr_error_level = ...` hívást a kódszöveg hozzárendelése előtt alkalmazhatod.

---

## A kiterjesztett kódszöveg hozzárendelése a QR generátorhoz

Miután a generátor készen áll, a következő lépés egyszerűen a korábban épített vegyes karakterlánc betáplálása.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Miért ne használjuk a `set_codetext`-et?**  
`set_codetext` a bemenetet egyszerű szövegként kezeli, eltávolítva minden ECI jelzőt. A `set_extended_codetext` megőrzi a nyers bájtokat, beleértve az ECI szegmenst is, biztosítva, hogy a szkenner a megfelelő nyelvváltást lássa.

---

## QR kód kép mentése és az eredmény ellenőrzése

Végül a QR kódot leírjuk a lemezre. Az Aspose.Barcode támogatja a PNG, JPEG, BMP és további formátumokat; a PNG egy biztonságos alapértelmezés, mivel veszteségmentes adatot őriz.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Most már kell, hogy legyen egy PNG fájlod a megadott helyen. Nyisd meg bármelyik ECI‑t támogató QR szkenner alkalmazással (a legtöbb modern okostelefon ezt támogatja). Olvasd be egyszer – a “HELLO123” szöveget fogod látni. Olvasd be újra (vagy használj olyan szkennert, amely nyers adatot mutat) – a “Привет” is megjelenik. A két rész egyetlen payloadként jelenik meg, pontosan úgy, ahogy építettük.

![use extcodetextbuilder aspose QR kód példa](YOUR_DIRECTORY/qr_extended.png)

*Kép alt szöveg: use extcodetextbuilder aspose QR kód példa, amely vegyes ECI szöveget mutat*

---

## Teljes, azonnal futtatható szkript

Mindent összevonva, itt a teljes program, amelyet beilleszthetsz egy `qr_mixed_eci.py` nevű fájlba:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Futtasd a következővel:

```bash
python qr_mixed_eci.py
```

A konzolon egy üzenetet látsz, amely megerősíti a mentési helyet, és a PNG a megadott helyen jelenik meg.

---

## Gyakori kérdések és szélhelyzetek

### Mi van, ha a szkenner nem ismeri fel a cirill részt?
Győződj meg arról, hogy a szkenner alkalmazás ECI támogatást hirdet. Régebbi hardverek figyelmen kívül hagyhatják az ECI szegmenst, és a bájtokat ISO‑8859‑1‑ként értelmezhetik, ami torz karakterekhez vezet.

### Hozzáadhatok több mint két töredéket?
Természetesen. Hívd meg annyiszor a `add_plain_codetext` vagy `add_eci_codetext` metódust, ahányszor szükséged van rá. A builder a metódusok meghívási sorrendjében fűzi össze őket.

### Hogyan változtathatom meg a QR kód méretét vagy az előtér színét?
Használd a `qr_generator.parameters` objektumot:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Van mód bináris adat (pl. egy kis fájl) beágyazására a szöveg mellé?
Igen. Használd a `add_binary_codetext`-et egy bájt tömbbel, és párosítsd egy megfelelő ECI-vel, ha a bináris egy adott karakterkészletet képvisel. A builder kezeli a szükséges módváltásokat.

---

## Következtetés

Most már tudod, **hogyan használjuk a extcodetextbuilder aspose‑t**, hogy QR kódokat készítsünk, amelyek zökkenőmentesen keverik az egyszerű ASCII‑t és az UTF‑8‑kódolt orosz szöveget. Az `ExtCodetextBuilder` használatával, a megfelelő **ECI encoding** beállításával, és az eredmény egy **Aspose.Barcode QR Code generator**‑ba való betáplálásával egyetlen, szabványosnak megfelelő képet kapsz, amely modern szkennereken működik.  

Innen kezdve próbáld megcserélni a `eci_encoding=3`-at más nyelvi azonosítókra, vagy kísérletezz további egyszerű töredékekkel többnyelvű payloadok építéséhez. Érdemes megvizsgálni a `BarCodeImageFormat` opciókat is, ha SVG vagy PDF kimenetre van szükséged vektoros grafikához.  

Boldog kódolást, és nyugodtan hagyj megjegyzést, ha elakadsz – a visszajelzésed segít jobbá tenni ezeket az útmutatókat!

## Mit érdemes még megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Generálj vonalkódot Java - Kód szöveg beállítása az Aspose.BarCode használatával](/barcode/english/java/text-and-styling/setting-code-text/)
- [Készíts vonalkódot aspose .net - DataMatrix kódszöveg konfigurálása](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec kódszöveg kódolása Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}