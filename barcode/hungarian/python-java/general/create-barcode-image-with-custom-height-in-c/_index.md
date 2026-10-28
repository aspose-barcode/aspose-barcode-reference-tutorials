---
category: general
date: 2026-10-28
description: Készítsen vonalkód képet C#-ban, és tanulja meg, hogyan állíthatja be
  a magasságot a BarcodeGenerator API segítségével. Lépésről‑lépésre útmutató az egyedi
  vonalkódmagasság és a vonalmagasság módosításához.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: hu
lastmod: 2026-10-28
og_description: Készítsen vonalkód képet C#-ban, és azonnal lássa, hogyan állíthatja
  be a magasságot. Kövesse ezt a teljes példát, hogy egyedi vonalkódmagasságot állítson
  be a BarcodeGenerator segítségével.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Barcode kép létrehozása egyedi magassággal C#‑ban – teljes útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Barcode kép létrehozása egyéni magassággal C#‑ban
url: /hu/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód kép létrehozása egyedi magassággal C#-ban

Ha **vonalkód képet** kell létrehoznod és a méreteit szabályoznod, ez az útmutató pontosan megmutatja, hogyan. Az Aspose.BarCode .NET könyvtár segítségével generálhatsz egy GS1‑Databar Omni‑Directional vonalkódot, majd **hogyan állítsd be a magasságot**, hogy megfeleljen bármilyen elrendezési követelménynek.

Egy teljes, futtatható programon keresztül mutatjuk be a **c# barcode generator** használatát, elmagyarázzuk minden beállított tulajdonságot, és két különböző kimenetet is megjelenítünk – egyet 30 pixel sávmagassággal, egyet 60 pixel sávmagassággal. A végére képes leszel **programból módosítani a vonalkód magasságát** bármely, a könyvtár által támogatott vonalkódtípus esetén.

## Előfeltételek

- .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.6+ esetén is működik)
- Visual Studio 2022 vagy bármely szerkesztő, amely képes C# projektek építésére
- Aspose.BarCode for .NET NuGet csomag (`Install-Package Aspose.BarCode`)
- Alapvető ismeretek a C# szintaxisról

> **Pro tipp:** Ha CI pipeline-t használsz, add hozzá a NuGet csomagot a `csproj` fájlodhoz, hogy a build automatikusan helyreállítsa.

## 1. lépés: Projekt létrehozása és névterek importálása

Hozz létre egy új konzolos projektet, és add hozzá a szükséges `using` utasításokat. A névterek hozzáférést biztosítanak a `BarcodeGenerator`, `EncodeTypes` és a képformátum segédfüggvényekhez.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Miért fontos:** A megfelelő névterek importálása megakadályozza a fordítási hibákat, és az API könnyen felfedezhető az IntelliSense-ben.

## 2. lépés: **c# barcode generator** inicializálása egy GS1‑Databar Omni‑Directional kódhoz

A konstruktor két argumentumot vár: a vonalkódtípust (`EncodeTypes.DatabarOmniDirectional`) és az adatkarakterláncot. Az adatkarakterláncnak a GS1 Alkalmazásazonosító formátumnak kell megfelelnie, pl. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Magyarázat:** A `BarcodeGenerator` objektum a belépési pont minden vonalkód‑kapcsolódó beállításhoz. Miután megvan ez a példány, módosíthatod a méreteket, színeket és a kimeneti formátumot.

## 3. lépés: Közös X‑dimenzió (a legkeskenyebb sáv pixel szélessége) definiálása

A 2 pixel X‑dimenzió jó kiindulási pont a legtöbb képernyőn megjelenő szituációhoz.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Miért állítsuk be az X‑dimenziót?** Ez szabályozza a vonalkód teljes szélességét. Ha konzisztens marad, a sávmagasság változtatása nem torzítja el a vizuális egyensúlyt.

## 4. lépés: **Vonalkód kép létrehozása** 30 pixel sávmagassággal

Most beállítjuk a sávmagasságot, elmentjük az első képet, majd a másodikhoz megváltoztatjuk a magasságot.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Eredmény:** Egy PNG fájlt kapsz, ahol minden függőleges sáv 30 pixel magas. Az X‑dimenzió továbbra is 2 pixel, így a teljes szélesség változatlan marad.

## 5. lépés: **Hogyan állítsuk be a magasságot** – a sávmagasság 60 pixelre változtatása

A **testreszabott vonalkód magasság** demonstrálásához egyszerűen rendelj egy új értéket ugyanahhoz a tulajdonsághoz, majd mentsd el újra.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Kulcsfontosságú megfigyelés:** A `BarHeight` tulajdonság módosítható; nem kell újra létrehozni a `BarcodeGenerator` példányt. Ez olcsóvá teszi több méret generálását egy ciklusban vagy kötegelt folyamatban.

## 6. lépés: Kimenet ellenőrzése

Futtasd a konzolos programot (`dotnet run`). A végrehajtás után két PNG fájlt kell látnod a projekt kimeneti mappájában:

- `DatabarBarHeight30Pixels.png` – rövid sávok (30 px)
- `DatabarBarHeight60Pixels.png` – hosszú sávok (60 px)

Mindkét kép ugyanazt a kódolt adatot tartalmazza, de a vizuális magasság eltér, ami hasznos a vonalkódok űrlapokba, termékcímkékbe vagy különböző helykorlátokkal rendelkező UI komponensekbe való integrálásakor.

![Vonalkód kép létrehozása egyedi magassággal](barcode-example.png){.align-center width="600" alt="Vonalkód kép létrehozása egyedi magassággal"}

> **Tipp:** Nyisd meg a PNG fájlokat bármely képnéző programmal. A magasabb vonalkódnak pontosan duplája kell lennie a rövidebb magasságúnak, míg a vízszintes távolságok változatlanok maradnak.

## 7. lépés: Gyakori variációk és szélsőséges esetek

| Helyzet | Ajánlott beállítás |
|-----------|---------------------|
| **Nyomtatás nagy felbontású címkenyomtatón** | Használj nagyobb X‑dimenziót (pl. 4 px), és növeld a `BarHeight`-t arányosan. |
| **Megjelenítés alacsony DPI-s képernyőn** | `XDimension`-t tartsd 1 px‑en, és a `BarHeight`-t 20‑40 px között a olvashatóság érdekében. |
| **QR kódok vagy 2‑D vonalkódok generálása** | A `BarHeight` tulajdonság figyelmen kívül marad; használd a `EncodeTypes.QR`-t és állítsd be helyette az `ImageHeight`-t. |
| **Tömeges generálás több magassággal** | Iterálj egy magasságok tömbön, és a ciklusban hívd meg a `Save`-t; nem szükséges minden iterációban újra létrehozni a generátort. |

### Érvénytelen magasságok kezelése

A könyvtár `ArgumentOutOfRangeException` kivételt dob, ha a `BarHeight`-t nem pozitív értékre állítod. Védd meg ezt egy egyszerű ellenőrzéssel:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Teljes forráskód (kész a másoláshoz)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Miért működik:** Minden szükséges beállítás (`EncodeTypes`, `XDimension`, `BarHeight`) a `Save` hívás előtt alkalmazásra kerül. Ugyanazt a `BarcodeGenerator` példányt használjuk újra, ami memóriahatékony és könnyen olvasható.

## Összegzés

Most már tudod, hogyan **hozz létre vonalkód képeket** C#-ban, és hogyan **változtasd meg pontosan a vonalkód magasságát** a `BarcodeGenerator` API segítségével. A `BarHeight.Pixels` módosításával **egyedi vonalkód magasságot** érhetsz el anélkül, hogy újraépítenéd a generátort, így a megoldás ideális dinamikus címkeléshez, UI rendereléshez vagy kötegelt feldolgozási csővezetékekhez.

Ezután fedezd fel a kapcsolódó témákat, például **a szélesség módosítását**, **emberi olvasható szöveg hozzáadását**, vagy **SVG exportálását skálázható webes használathoz**. Ugyanez a minta – egy tulajdonság beállítása, `Save` hívása – minden ilyen esetben alkalmazható, így magabiztosan bővítheted ezt a példát.

## Mi legyen a következő tanulnivalód?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy könnyedén elsajátíthasd az API további funkcióit, és alternatív megvalósítási megközelítéseket is kipróbálhass saját projektjeidben.

- [Hogyan változtassuk meg a vonalkód magasságát C#-ban – Teljes útmutató](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Vonalkód generátor példa – Planet és RM4SCC vonalkódok létrehozása egyedi magassággal](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Hogyan hozzunk létre rm4scc vonalkódot és szabályozzuk annak magasságát C#-ban](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}