---
category: general
date: 2026-11-20
description: Tanulja meg, hogyan használja az ECI-t, hogyan generáljon QR-kódot szövegből,
  hogyan törölje a buildert, és hogyan mentse el a QR-képet a Python vonalkód könyvtár
  segítségével.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: hu
lastmod: 2026-11-20
og_description: Hogyan használjuk az ECI-t szövegből QR-kód generálásához, töröljük
  a QR-építőt, és mentjük a QR-képet – egy teljes lépésről‑lépésre útmutató.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Hogyan használjuk az ECI-t QR‑kód generálásához Pythonban
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Hogyan használjuk az ECI-t a QR‑kód generálásához Pythonban
url: /hu/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjuk az ECI-t QR-kód generálásához Pythonban

Ha **how to use eci**-re van szükséged QR-kódok létrehozásakor, ez az útmutató bemutatja a pontos lépéseket. Meg fogod látni, hogyan generálj QR-kódot szövegből, hogyan töröld a builder-t, és végül hogyan mentsd el a QR-képet – mindezt néhány Python sorral.

A többnyelvű adatot tartalmazó QR-kódok gyakran igényelnek egy Extended Channel Interpretation (ECI) szegmenst, hogy a szkennerek tudják, melyik karakterkészletet kell alkalmazni. Ez az oktatóanyag végigvezet a kiterjesztett kódszöveg felépítésén, a builder törlésén újrafelhasználáskor, és az eredmény PNG fájlként való mentésén.

## Előfeltételek

- Python 3.8+ telepítve.
- Az Aspose.BarCode for Python via .NET csomag (vagy bármely kompatibilis `barcode` könyvtár, amely biztosítja az `ExtCodetextBuilder` és `BarcodeGenerator` osztályokat).
- Alapvető ismeretek a QR-kód koncepcióiról.

Telepítsd a könyvtárat pip-pel:

```bash
pip install aspose-barcode
```

> **Pro tipp:** Használj virtuális környezetet a verzióütközések elkerülése érdekében.

## 1. lépés: A szükséges osztályok importálása

Az elsődleges osztályok, amelyekkel dolgozni fogsz, a `ExtCodetextBuilder` a kiterjesztett kódszöveg felépítéséhez, és a `BarcodeGenerator` a QR-kód megjelenítéséhez.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Ezek az importok hozzáférést biztosítanak a builder metódusaihoz (`add_plain_codetext`, `add_eci_codetext`, stb.) és a generátor `set_code_text`, `set_symbology`, valamint `save` függvényeihez.

## 2. lépés: Az ExtCodetextBuilder létrehozása és konfigurálása

Új builder példány létrehozása az első konkrét példa a **how to use eci**-re. Később is törölheted a builder-t, ha újra szeretnéd használni.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

A `clear()` hívása biztosítja, hogy a builder tiszta állapottal induljon, ami elengedhetetlen több QR-kód ciklikus generálásakor.

## 3. lépés: Egyszerű (nem‑ECI) kódszöveg hozzáadása

Az egyszerű szövegnek nincs szüksége ECI szegmensre. Használd a `add_plain_codetext`-et ASCII‑kompatibilis karakterláncokhoz.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

A builder most már tartalmazza az egyszerű szegmenst: "HelloWorld".

## 4. lépés: ECI‑kódolt szegmens hozzáadása

Itt van a **how to use eci** lényege: megadod az ECI értéket (26 az UTF‑8-hoz), és megadod a kódolni kívánt Unicode karakterláncot. Ez lehetővé teszi, hogy a QR-kód orosz, kínai vagy bármely más, az alapértelmezett ISO‑8859‑1 készletben nem szereplő nyelvet tartalmazzon.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

**Miért fontos:** Az ECI jelző nélkül a szkenner az alapértelmezett karakterkészletet használja, és torz karaktereket jelenít meg a nem‑ASCII szövegek esetén.

## 5. lépés: Az egyesített kiterjesztett kódszöveg lekérése

Miután hozzáadtad az összes szükséges szegmenst, kérd le a végső karakterláncot, amelyet a QR-generátornak adsz át.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

A kiírt érték valahogy így néz ki:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

A pontos formátum a könyvtártól függ, de a lényeg, hogy az ECI jelző (`[ECI26]`) megelőzi az UTF‑8 payload-ot.

## 6. lépés: QR-kód generálása az egyesített szöveggel

Most már **generate QR from text**-t tudsz végrehajtani az kiterjesztett kódszöveg `BarcodeGenerator`-nek átadásával.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Amikor megnyitod a `qr_extended.png` fájlt, egy QR-kód jelenik meg, amely kódolja az egyszerű angol sztringet és az orosz üdvözletet is. Modern QR-szkennerrel beolvasva helyesen jeleníti meg a „HelloWorld” és a „Привет” szöveget.

### Miért kell a `clear()`-t meghívni a builder újrafelhasználása előtt

Ha egy ciklusban több QR-kódot generálsz, és elfelejted a builder törlését, akkor a régi szegmensek újakkal fognak összefűződni, ami érvénytelen kódot eredményez. Íme egy gyors minta:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Ez a kódrészlet bemutatja a **how to clear builder** és a **how to generate QR from text** ismételt használatát.

## Szélsőséges esetek és gyakori buktatók

| Situation | What to watch for | How to handle |
|-----------|-------------------|---------------|
| **Unsupported ECI value** | A könyvtár `InvalidArgumentException`-t dob. | Csak a specifikációban felsorolt ECI értékeket használd (pl. 26 az UTF‑8-hoz, 20 a Shift‑JIS-hez). |
| **Very long combined text** | A QR verzió meghaladhatja a maximális kapacitást. | Növeld a QR verziót automatikusan (`qr_generator.set_qr_version(QRVersion.AUTO)`) vagy oszd szét az adatot több QR-kódra. |
| **File‑system permission errors** | `save` hibát ad `IOError`-val. | Győződj meg róla, hogy a célkönyvtár létezik és a folyamatnak írási joga van. |
| **Incorrect charset display** | A szkenner torz karaktereket mutat. | Ellenőrizd, hogy a megfelelő ECI érték egyezik a karakterlánc tényleges kódolásával. |

## Teljes futtatható példa

Az alábbi önálló szkriptet másolhatod, beillesztheted és futtathatod. Tartalmazza az összes importot, a hibakezelést és a magyarázó megjegyzéseket.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

A szkript futtatása `output/qr_extended.png` fájlt hoz létre, egy QR-kódot, amely helyesen kódolja az angol és az orosz szöveget.

## Összegzés

Most már tudod, hogyan kell **how to use eci** QR-kódok építésekor, hogyan **clear the QR builder**-t a újrafelhasználás előtt, hogyan **generate QR from text**, és a pontos lépéseket a **save QR image** Pythonban történő mentéséhez. A fenti mintát követve bármilyen Unicode karakterláncot beágyazhatsz egy QR-kódba, miközben a builder állapota előre látható marad.

### Mi a következő?

- Fedezz fel más ECI értékeket olyan nyelvekhez, mint a kínai (ECI 20) vagy az ISO‑8859‑5.
- Állítsd be a hibajavítási szinteket (`qr_generator.set_error_correction_level`) a beolvasási megbízhatóság javítása érdekében.
- Kombinálj több ECI szegmenst egyetlen QR-kódban vegyes nyelvű üzenetekhez.

Boldog kódolást, és élvezd a többnyelvű QR-kódok létrehozását!

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode Python használatával](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Hogyan generáljunk QR-kód képet Pythonban az Aspose.Barcode segítségével – Teljes útmutató](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Hogyan generáljunk vonalkódot Pythonban – teljes lépésről‑lépésre útmutató](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}