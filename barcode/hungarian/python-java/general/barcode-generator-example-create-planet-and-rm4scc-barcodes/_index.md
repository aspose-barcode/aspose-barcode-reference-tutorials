---
category: general
date: 2026-10-24
description: Vonalkód-generátor példa, amely bemutatja, hogyan lehet Planet vonalkódot
  létrehozni, és hogyan állítható be a vonalkód magassága Python használatával. Kövesse
  a lépésről‑lépésre útmutatót.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: hu
lastmod: 2026-10-24
og_description: Vonalkód-generátor példa, amely bemutatja, hogyan lehet Planet vonalkódot
  létrehozni és hogyan állítható be a vonalkód magassága Pythonban. Szerezzen egy
  teljes, futtatható megoldást.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Vonalkód-generátor példa – Planet és RM4SCC vonalkódok létrehozása
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Vonalkód-generátor példa – Planet és RM4SCC vonalkódok létrehozása egyedi magassággal
url: /hu/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód-generátor példa – Planet és RM4SCC vonalkódok létrehozása egyedi magassággal

Ha **barcode generator example**-t keres, ez az útmutató egy teljes, azonnal futtatható megoldást nyújt. Meg fogja látni, **hogyan hozhat létre planet vonalkód** képeket, megtanulja **hogyan állítható be a vonalkód magassága**, és megérti a kis különbségeket az automatikus és a kézi méretezés között.

Az útmutató két reális forgatókönyvet mutat be: egy Planet vonalkódot, amely az alapértelmezett (automatikus) magasságot használja, és egy RM4SCC vonalkódot, ahol a magasságot 100 px‑re kényszerítik. A végére képes lesz PNG fájlokat generálni bármely támogatott vonalkódtípushoz egyetlen, konzisztens API‑val.

## Előkövetelmények

* Python 3.8 vagy újabb telepítve.
* Az `aspose-barcode` csomag (vagy bármely könyvtár, amely biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` osztályokat). Telepítse a következővel:  

  ```bash
  pip install aspose-barcode
  ```
* Írási jogosultság egy mappához, ahol a PNG fájlok mentésre kerülnek.

Nem szükséges további rendszerfüggőség.

## A megoldás áttekintése

A **barcode generator example** magja három újrahasználható lépésből áll:

1. **Instantiate** egy `BarcodeGenerator`‑t a kívánt `EncodeTypes` értékkel és az adatstringgel.
2. **Configure** az X‑dimenziót (modul szélesség) és, ha szükséges, a vonalkód magasságát.
3. **Save** a képet PNG formátumban a lemezre.

Mindkét példa az 1. és 3. lépést közösen használja; csak a 2. lépés különbözik, mivel a Planet vonalkód a könyvtár automatikus magasságkalkulációjára támaszkodik, míg az RM4SCC vonalkód **hogyan állítható be a vonalkód magassága**‑t mutatja be manuálisan.

Az alábbi magas szintű diagram szemlélteti a folyamatot:

![Vonalkód-generátor példa, amely a Planet és RM4SCC vonalkódokat mutatja különböző magasságokkal](barcode-example.png)

*Alt szöveg: Vonalkód-generátor példa, amely a Planet és RM4SCC vonalkódokat mutatja különböző magasságokkal.*

## Hogyan hozhatunk létre planet vonalkódot – automatikus magasság

A Planet vonalkód a postai család része, amelyet sok nemzeti postaszolgálat használ. A legtöbb esetben hagyja, hogy az SDK döntse el a magasságot, ami a változó adathosszúságoknál is helyes vizuális arányokat biztosít.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Miért működik ez**

* `EncodeTypes.Planet` azt mondja a könyvtárnak, hogy a Planet szimbólumot használja.
* `x_dimension.pixels` 4‑re állítása minden modulnak 4 px szélességet ad, ami gyakori alapértelmezett nyomtatott címkékhez.
* Nincs explicit magasság beállítva; az SDK a adat és az X‑dimenzió alapján számítja ki az optimális magasságot, ezért ez a legegyszerűbb **barcode generator example** a postai kódokhoz.

**Várt eredmény**

Egy 2‑D PNG fájl `PostalPlanetBarHeightAuto.png` néven, amely egy tiszta Planet vonalkódot tartalmaz. A magasság körülbelül 30 px lesz (a könyvtár verziójától függően), a szélesség pedig 4 px × modulok száma.

## Hogyan állítsuk be a vonalkód magasságát – egyedi RM4SCC példa

Az RM4SCC egy másik postai vonalkód, amely gyakran fix magasságot igényel a címkesablonokhoz. Ennek a résznek a célja, hogy **hogyan állítható be a vonalkód magassága**‑t pontos pixelértékre állítsuk.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Miért működik ez**

* `EncodeTypes.RM4SCC` kiválasztja az RM4SCC szimbólumot.
* Az X‑dimenzió 4 px marad, hogy a modulméret mindkét vonalkódban konzisztens legyen.
* `bar_height.pixels = 100` kényszeríti a vonalkódot, hogy pontosan 100 px magas legyen, felülbírálva az automatikus számítást. Ez a javasolt módja **how to set barcode height**-nek, ha a layout egy adott méretet igényel.

**Várt eredmény**

Egy PNG fájl `PostalRM4SCCBarHeight100Pixels.png` néven, amely egy magas RM4SCC vonalkódot jelenít meg. A szélesség továbbra is az X‑dimenziótól függ, míg a magasság 100 px‑re van rögzítve, így alkalmas nagy felbontású címkenyomtatókhoz.

## Teljes szkript – mindkét példa egyesítése

Ha egyetlen szkriptet szeretne, amely mindkét képet generálja, másolja a következő kódot a `generate_barcodes.py` fájlba, és futtassa.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**A szkript magyarázata**

* Két segédfüggvény tartja a kódot DRY (Don’t Repeat Yourself) módon, és megkönnyíti a szkript kiterjesztését más szimbólumokra.
* Az `if __name__ == "__main__":` guard lehetővé teszi, hogy a fájlt modulként importálják anélkül, hogy a generálási logikát végrehajtanák, ami hasznos egységteszteléshez.
* Minden paraméter (adatstring, X‑dimenzió, magasság) explicit, így a szkript referencia **barcode generator example**-ként szolgál a jövőbeli projektekhez.

## Gyakori kérdések és szélhelyzetek

| Kérdés | Válasz |
|----------|--------|
| *Mi van, ha más X‑dimenzióra van szükségem?* | Módosítsa a `x_dimension.pixels` értékét a kívánt modul szélességre. A nagyobb értékek arányosan növelik a teljes vonalkód méretét. |
| *Generálhatok más képformátumokat?* | Igen. Cserélje le a `BarCodeImageFormat.Png`-t `Jpg`, `Bmp` vagy `Gif` értékre a könyvtár enumja szerint. |
| *Mi történik, ha az adatstring érvénytelen karaktereket tartalmaz?* | A generátor `ArgumentException`-t dob. Ellenőrizze az adatot a szimbólum karakterkészlete szerint, mielőtt meghívná a konstruktort. |
| *Lehet-e minimális magasságot beállítani, miközben az automatikus méretezés megmarad?* | Használja a `gen.parameters.barcode.bar_height.min_pixels = <value>` kifejezést (ha az SDK rendelkezik `min_pixels` tulajdonsággal). Ez megakadályozza, hogy a vonalkód a olvasható méretnél kisebbre zsugorodjon. |
| *Szükséges-e a generátort felszabadítani?* | A `BarcodeGenerator` osztály .NET-ben `IDisposable`-t valósít meg; Pythonban a szemétgyűjtő kezeli, de hívhatja a `gen.dispose()`-t, ha egy ciklusban sok példányt hoz létre. |

## Tippek a termeléshez

* **Pro tipp:** Tárolja az X‑dimenzió és magasság értékeket egy konfigurációs fájlban, hogy újrafordítás nélkül módosíthassa őket.
* **Figyeljen:** Túl alacsony magasság használata a kiválasztott szimbólumhoz; a szkennerek esetleg nem olvassák be a vonalkódot.
* **Teljesítmény megjegyzés:** Nagy mennyiségű vonalkód generálása gyorsabb, ha egyetlen `BarcodeGenerator` példányt újrahasznál, és csak a `code_text` tulajdonságát változtatja a mentések között.

## Következtetés

Ez a **barcode generator example** bemutatja mind a **hogyan hozhatunk létre planet vonalkód** képeket automatikus méretezéssel, mind a **hogyan állítható be a vonalkód magassága** manuálisan az RM4SCC kódoknál. A lépésről‑lépésre útmutató követésével beépítheti a vonalkód-generálást bármely Python‑alkalmazásba, testreszabhatja a méreteket, és PNG fájlokat állíthat elő nyomtatásra vagy digitális megjelenítésre.

### Következő lépések

* Fedezzen fel további szimbólumokat, például `EncodeTypes.Postnet` vagy `EncodeTypes.Code128` – ugyanaz a minta érvényes.
* Kísérletezzen a **how to set barcode height**‑el QR kódok vagy DataMatrix szimbólumok esetén; a legtöbb könyvtár hasonló `bar_height` tulajdonságot biztosít.
* Kombinálja a generátort egy PDF könyvtárral, hogy a vonalkódokat közvetlenül számlákba vagy szállítási címkékbe ágyazza.

Nyugodtan módosítsa a szkriptet, ossza meg eredményeit, és tudassa velünk, mely vonalkód típusokat adja hozzá legközelebb!

## Mit érdemes még megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra építenek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan menthetünk PNG-t egy vonalkód-generátor példából Pythonban](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Hogyan hozzunk létre planet vonalkód PNG-t Pythonban](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Hogyan használjunk C# vonalkód-generátort egy Planet vonalkód létrehozásához](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}