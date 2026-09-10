---
category: general
date: 2026-09-10
description: Kódolj nem ASCII karaktereket egy QR-kódban, és mentsd el a QR-kód képet
  egy egyszerű Python építővel. Kövesd a lépésről‑lépésre útmutatót az ExtCodetextBuilder
  és a BarcodeGenerator használatával.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: hu
lastmod: 2026-09-10
og_description: Kódolja a nem ASCII karaktereket QR-kódban, és mentse a QR-kód képét
  Python segítségével. Ez az útmutató bemutatja, hogyan építsen kiterjesztett kódszöveget,
  generáljon QR-kódot, és tárolja a képet.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Nem ASCII karakterek kódolása QR-kódban és QR-kód kép mentése – lépésről
  lépésre Python útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Nem ASCII karakterek kódolása QR-kódban és a QR-kód képének mentése
url: /hu/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nem ASCII karakterek kódolása QR-kódban és QR-kód kép mentése

Ha **nem ASCII karakterek kódolása** egy QR-kódban, ez az útmutató pontosan megmutatja, hogyan teheted meg, majd **QR-kód kép mentése** a lemezre. Akár orosz, kínai vagy emoji adatokat kezelsz, az ExtCodetextBuilder lehetővé teszi, hogy egyszerű szöveget és ECI‑kódolt szegmenseket keverj anélkül, hogy manuálisan kellene bájtokat manipulálni.

Megtanulod, hogyan hozz létre egy kiterjesztett kódszöveg (extended codetext) karakterláncot, hogyan generálj egy QR-kódot, amely érti ezt a karakterláncot, és végül hogyan írd ki a vonalkód képet egy fájlba. Az útmutató feltételezi az alap Python ismereteket, és hogy telepítve van a `barcode` SDK.

## Előkövetelmények

* Python 3.8+ telepítve.
* A `barcode` Python csomag (vagy a megfelelő SDK), amely biztosítja az `ExtCodetextBuilder`, `CodetextEncodingType` és `BarcodeGenerator` osztályokat.
* Írási jogosultság a könyvtárban, ahová **QR-kód képet** szeretnéd menteni.

A SDK-t pip-pel telepítheted (cseréld le a `barcode-sdk`-t a tényleges csomagnévre):

```bash
pip install barcode-sdk
```

## 1. lépés: Kiterjesztett kódszöveg építő létrehozása

Az első lépés az `ExtCodetextBuilder` példányosítása. Ez az objektum több szövegszegmenst gyűjt össze, és egyetlen karakterláncot állít elő, amelyet a QR-kód szimbólumrendszer értelmezni tud.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Miért fontos*: A QR-kódok támogatják a **kiterjesztett kódszöveget**, ami azt jelenti, hogy több kódolási módot (egyszerű, ECI, stb.) is beágyazhatsz egy vonalkódban. Az építő elrejti a QR specifikáció által megkövetelt alacsony szintű formázást.

## 2. lépés: Egyszerű szövegszegmens hozzáadása

Az egyszerű szöveg az alapértelmezett mód, és ASCII karakterekhez működik. Először hozzáadva olvasható tartalékot biztosít a szkennereknek, amelyek figyelmen kívül hagyják az ECI-t.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Ha kihagyod ezt a lépést, a QR-kód csak az ECI szegmenst tartalmazná, amit egyes régebbi olvasók nem tudnak helyesen dekódolni.

## 3. lépés: ECI‑kódolt szegmens hozzáadása nem‑ASCII karakterekhez

Az ASCII tartományon kívüli karakterek – például cirill, kínai vagy emoji – belefoglalásához meg kell adni egy ECI (Extended Channel Interpretation) kódolást. Itt a orosz „Привет” szóhoz UTF‑8-at használunk.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Miért működik*: A QR specifikáció definiálja az ECI értékeket, amelyek megmondják a szkennernek, melyik karakterkészletet kell alkalmazni. Az ECI jelző nélkül a nyers bájtok ISO‑8859‑1‑ként lennének értelmezve, ami torz kimenetet eredményez.

## 4. lépés: Kombinált kiterjesztett kódszöveg karakterlánc lekérése

A kívánt szegmensek hozzáadása után hívd meg a `get_extended_codetext()` metódust, hogy megkapd a végső karakterláncot, amelyet a vonalkód generátor elvár.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

A kiírt érték úgy néz ki, mint egy sor vezérlőkarakter, amelyet a tényleges szöveg követ, de soha nem kell manuálisan feldolgoznod.

## 5. lépés: QR-kód generálása a kiterjesztett kódszöveg használatával

Most hozd létre a `BarcodeGenerator`-t, állítsd be a szimbólumot QR-re (az egyetlen általános 2‑D szimbólum, amely támogatja a kiterjesztett kódszöveget), és add meg a kombinált karakterláncot.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tipp*: Ha ugyanazt a folyamatot Code‑128 vagy DataMatrix esetén próbálod, az SDK kivételt dob, mivel ezek a formátumok nem tudják értelmezni az ECI jelzőket.

## 6. lépés: QR-kód kép mentése

Végül írd ki a vonalkódot egy PNG fájlba. Itt **QR-kód képet** mented el későbbi használatra.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Győződj meg róla, hogy az `output` mappa létezik, vagy hozd létre a `os.makedirs('output', exist_ok=True)` paranccsal a `save` hívása előtt.

### Teljes futtatható példa

Az összes lépés egyesítésével egy önálló szkriptet kapsz, amelyet azonnal futtathatsz:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Várható kimenet** (konzol):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

A `qr_extended.png` megnyitása bármely QR-szkennerrel `HelloWorldПривет`-t jelenít meg. Az ECI-t értő szkennerek helyesen jelenítik meg a cirill karaktereket; a többi csak az ASCII részt mutatja.

## Gyakori kérdések és szélhelyzetek

| Kérdés | Válasz |
|----------|--------|
| *Használhatok más kódolásokat, például Shift‑JIS‑t?* | Igen. Cseréld le a `CodetextEncodingType.UTF_8`-t `CodetextEncodingType.SHIFT_JIS`-re, és add meg a megfelelő szöveget. |
| *Mi van, ha a kombinált adat meghaladja a QR kapacitását?* | A QR-kódok verziókorlátokkal rendelkeznek (max. 177 × 177 modul). Ha az építő méretkivételt dob, növeld a hibajavítási szintet, vagy oszd szét az adatot több QR-kódra. |
| *Szükséges-e egy adott QR verziót beállítani?* | Az SDK automatikusan a legkisebb, az adatot befogadó verziót választja. Szükség esetén a `qr_generator.set_qr_version(10)` paranccsal kényszerítheted a verziót. |
| *Átlátszó lesz a kép?* | Alapértelmezés szerint az SDK fehér háttérrel írja a PNG-t. Ha átlátszóságra van szükséged, a `save` előtt használd a `qr_generator.set_background_color(Color.Transparent)`-t. |

## Összegzés

Ebben az útmutatóban megtanultad, hogyan **kódolj nem ASCII karaktereket** egy QR-kódban az `ExtCodetextBuilder` használatával, majd hogyan **QR-kód képet** menthetsz a `BarcodeGenerator`-rel. A folyamat magában foglalja egy kiterjesztett kódszöveg karakterlánc felépítését, egyszerű és ECI‑kódolt szegmensek hozzáadását, a QR-szimbólum generálását, és végül a kép fájlba írását.

Innen tovább felfedezheted:

* További ECI szegmensek hozzáadása (különböző nyelvek vagy emoji‑k).
* A QR hibajavítási szintek módosítása a nagyobb megbízhatóság érdekében.
* A generált PNG beágyazása PDF‑ekbe vagy weboldalakba.

Boldog kódolást, és élvezd a többnyelvű QR-kódok létrehozását!

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk QR-kód képet Pythonban az Aspose.Barcode segítségével – Teljes útmutató](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Code128 vonalkód generálása Aspose.Barcode Python – Teljes útmutató](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Termék nevének megjelenítése Python vonalkód könyvtárral – lépésről‑lépésre útmutató](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}