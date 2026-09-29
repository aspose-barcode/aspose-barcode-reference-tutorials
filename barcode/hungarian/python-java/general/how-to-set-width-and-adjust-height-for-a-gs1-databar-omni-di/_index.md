---
category: general
date: 2026-09-29
description: Hogyan állítsuk be egy GS1 DataBar Omni‑Directional vonalkód szélességét,
  és hogyan változtassuk meg a magasságát C#‑ban. Kövess egy lépésről‑lépésre útmutatót
  teljes kóddal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: hu
lastmod: 2026-09-29
og_description: Hogyan állítsuk be egy GS1 DataBar Omni‑Directional vonalkód szélességét,
  és hogyan változtassuk meg a magasságát C#‑ban. Ismerje meg a pontos API‑hívásokat,
  és tekintse meg a teljesen futtatható példát.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Hogyan állítsuk be a GS1 DataBar vonalkód szélességét – C# útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Hogyan állítsuk be a szélességet és a magasságot egy GS1 DataBar Omni‑Directional
  vonalkódhoz C#-ban
url: /hu/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a szélességet és módosítsuk a magasságot egy GS1 DataBar Omni‑Directional vonalkód esetén C#‑ban

A GS1 DataBar Omni‑Directional vonalkód **szélességének beállítása** gyakori feladat, ha pontos méretezésre van szükség a szkennelő berendezésekhez. Ebben az útmutatóban megtanulod, hogyan **változtasd meg a magasságot** is, hogy a vonalkód tökéletesen illeszkedjen a layoutodba. A leírás végigvezet a teljes folyamaton, a projekt beállításától egy teljesen futtatható kódmintáig.

Kitérünk a következőkre:

* A szükséges NuGet csomag és a .NET verzió.
* Miért fontos az X‑dimenzió (modul szélesség) a vonalkód olvashatósága szempontjából.
* A pontos API hívások a **szélesség beállításához** és a **magasság módosításához**.
* Szélsőséges esetek kezelése, például minimális modul szélesség és nagy felbontású renderelés.
* Egy teljes, másolás‑beillesztés példakód, amely két PNG fájlt hoz létre különböző vonalkódmagasságokkal.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

| Követelmény | Indoklás |
|------------|----------|
| .NET 6.0 SDK vagy újabb | A példa modern C# funkciókat használ, és Windows, Linux vagy macOS rendszeren fut. |
| Visual Studio 2022 (vagy bármely C# IDE) | IntelliSense-t biztosít az Aspose.Barcode API-hoz. |
| **Aspose.Barcode for .NET** NuGet csomag | Tartalmazza a `BarcodeGenerator`, `EncodeTypes` és a képformátum támogatást. Telepítsd a `dotnet add package Aspose.Barcode` paranccsal. |
| Írási jogosultság egy olyan mappához, ahová a PNG fájlok mentésre kerülnek | A generátor a kimeneti képeket a lemezre írja. |

## Hogyan állítsuk be a vonalkód szélességét

A **szélesség beállítása** a vonalkód paramétereinek `XDimension` tulajdonságának konfigurálásával történik. Az `XDimension` a modul szélességet (a legkisebb vonal vagy szóköz) pixelben, pontban vagy milliméterben adja meg. Helyes beállítása biztosítja, hogy a vonalkód megfeleljen a szkenner specifikációinak.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Miért fontos az X‑dimenzió

* **Szkenner tolerancia** – A legtöbb szkenner minimális modul szélességet vár; túl kis érték olvasási hibákat okozhat.
* **Nyomtatási felbontás** – 300 dpi‑nél egy 2 px modul körülbelül 0,17 mm‑nek felel meg, ami a GS1 DataBar ajánlott tartományában van.
* **Képméret** – Nagyobb X‑dimenzió értékek növelik a teljes vonalkód szélességét, ami befolyásolhatja a layout korlátait.

### Tippek a megbízható szélesség beállításhoz

* **Soha ne állítsd az XDimension‑t 1 px alá** – a könyvtár levágja az értéket, de a kapott vonalkód olvashatatlan lehet.
* **Illeszd a cél DPI‑hoz** – ha magas felbontású formátumba renderelsz (pl. TIFF 600 dpi‑nél), növeld arányosan az XDimension‑t.
* **Teszteld valódi szkennerrel** – a szélesség módosítása után ellenőrizd a vonalkódot azon eszközön, amely használni fogja.

## Hogyan változtassuk meg a vonalkód magasságát

Miután a szélesség definiálva van, a függőleges méretet a `BarHeight` tulajdonsággal szabályozhatod. Az alábbi kód bemutatja, **hogyan változtassuk meg a magasságot** 30 px‑ről 60 px‑re, és hogyan mentsünk két különálló képet.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### A vonalmagasság megértése

* **Vizuális egyensúly** – Magasabb vonalak javítják az olvashatóságot alacsony kontrasztú háttéren, de növelik a kép függőleges lábnyomát.
* **Szabályozási korlátok** – Egyes szabványok (pl. kiskereskedelmi címkézés) maximális vonalmagasságot határoznak meg; ennek megfelelően állítsd be.
* **Képarány** – A magasság módosítása nem érinti a modul szélességet; mindkettőt függetlenül finomhangolhatod.

### Szélsőséges esetek kezelése magasság módosításakor

| Helyzet | Ajánlott megközelítés |
|--------|-----------------------|
| Magasság < 10 px | Növeld legalább 10 px-re; a nagyon rövid vonalak a szkennerek figyelmen kívül hagyhatják. |
| Nagyon magas vonalak (≥ 100 px) | Ellenőrizd, hogy a kimeneti hordozó (papír, címke) elbírja-e a plusz helyet. |
| Arányos skálázás szükséges | Számold ki a `BarHeight = XDimension * kívántArány` képletet a vizuális konzisztencia megőrzéséhez. |

## Teljes, futtatható példa

Az alábbi program egyesíti a **szélesség beállítása** és a **magasság módosítása** lépéseit. Másold a kódot egy új konzolprojektbe, állítsd vissza az Aspose.Barcode NuGet csomagot, és futtasd. Két PNG fájl jelenik meg a `bin/Debug/net6.0` mappában.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Várható kimenet**

A program futtatása két PNG fájlt hoz létre:

* `DatabarBarHeight30Pixels.png` – 30 px magas, 2 px széles modulokkal rendelkező vonalkód.
* `DatabarBarHeight60Pixels.png` – ugyanaz a vonalkód, de a függőleges mérete duplája.

Nyisd meg bármelyik képet egy megjelenítőben; egy tiszta GS1 DataBar Omni‑Directional szimbólumot látsz, amely készen áll a szkennelésre.

## Gyakran feltett kérdések

| Kérdés | Válasz |
|--------|--------|
| *Használhatok millimétert pixel helyett?* | Igen. Állítsd be a `generator.Parameters.Barcode.XDimension.Millimeters` és a `BarHeight.Millimeters` értékeket. A könyvtár a kép DPI-ja alapján konvertálja őket eszközpixelre. |
| *Mi van, ha másik vonalkódtípust szeretnék?* | Cseréld le az `EncodeTypes.DatabarOmniDirectional` értéket bármely más `EncodeTypes` értékre (pl. `EncodeTypes.QR`). A szélesség és magasság tulajdonságok ugyanúgy működnek. |
| *Létrehozhatok SVG‑t PNG helyett?* | Használd a `BarCodeImageFormat.Svg` értéket a `Save` hívásban. A szélesség/magasság beállítások továbbra is érvényesek. |
| *Kell hívni a `generator.Dispose()`‑t?* | A `BarcodeGenerator` implementálja az `IDisposable` interfészt. Konzolos alkalmazásban beburkolhatod egy `using` blokkba, de rövid életű példák esetén ez opcionális. |

## Összegzés

Most már tudod, **hogyan állítsd be a szélességet** egy GS1 DataBar Omni‑Directional vonalkód esetén, és **hogyan változtasd meg a magasságot** az Aspose.Barcode API segítségével C#‑ban. A teljes példakód bemutatja a generátor létrehozását, az `XDimension` és a `BarHeight` konfigurálását, valamint a PNG fájlok különböző függőleges méretekkel való mentését.  

Innen tovább:

* Kísérletezz más `EncodeTypes` értékekkel (pl. QR, Code128).
* Renderelj nagy felbontású formátumokba, például TIFF‑be nyomtatáshoz.
* Integráld a generátort egy web‑API‑ba, amely futásidőben ad vissza vonalkódokat.

Boldog kódolást, és legyenek a vonalkódjaid mindig tisztán olvashatóak!

## Mit tanulj meg legközelebb?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket és lépésről‑lépésre magyarázatokat tartalmaz, hogy további API‑funkciókat saját projektjeidben is könnyedén alkalmazhasd.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}