---
category: general
date: 2026-10-18
description: Tanulja meg, hogyan hozhat létre PDF417 vonalkódot C#-ban az Aspose.BarCode
  segítségével. Ez az útmutató lefedi az alap, kompakt, makró és mikro PDF417 generálást
  teljes kóddal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: hu
lastmod: 2026-10-18
og_description: PDF417 vonalkód létrehozása C#-ban az Aspose.BarCode segítségével.
  Kövesse ezt az útmutatót, hogy lépésről lépésre generáljon alap, kompakt, makro
  és mikro PDF417 vonalkódokat.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: PDF417 vonalkód létrehozása C#-ban – teljes Aspose.BarCode útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: PDF417 vonalkód létrehozása C#‑ban az Aspose.BarCode használatával – lépésről‑lépésre
  útmutató
url: /hu/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód létrehozása C#-ban az Aspose.BarCode használatával – lépésről‑lépésre útmutató

Ha **PDF417 vonalkódot** kell létrehoznod egy .NET alkalmazásban, ez az útmutató végigvezet a teljes folyamaton. Megmutatjuk, hogyan generálj egy alap vonalkódot, engedélyezd a kompakt módot, adj hozzá makró metaadatokat, és készíts egy mikro változatot – mindezt világos magyarázatokkal és futtatható kóddal.

A PDF417 vonalkódok generálása gyakori a logisztikában, jegyértékesítésben és dokumentumkezelésben. A útmutató végére képes leszel a vonalkód létrehozását bármely C# projektbe integrálni külső eszközök nélkül.

## Előkövetelmények

* .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
* Visual Studio 2022 vagy bármely C# IDE
* **Aspose.BarCode for .NET** NuGet csomag  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Írási jogosultság egy mappához, ahová a generált PNG fájlok mentésre kerülnek

Nem szükséges további konfiguráció; a könyvtár kezeli az összes alacsony szintű kódolási részletet.

## 1. lépés: Alap PDF417 vonalkód létrehozása

Az első lépés egy szabványos PDF417 vonalkód létrehozása egyedi mérettel és oszlopszámmal.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Miért fontosak ezek a beállítások**

* `XDimension.Pixels` szabályozza a vonalkód egyes elemeinek fizikai méretét. A 2 érték tiszta képet eredményez a legtöbb képernyőn és nyomtatón.
* `Pdf417.Columns` meghatározza, hány adatoszlopot tartalmaz a vonalkód. Kevesebb oszlop csökkenti a szélességet; több oszlop növeli az adatkapacitást.

A kód futtatása létrehozza a `Pdf417Basic.png` fájlt, amely egy tipikus PDF417 szimbólumot mutat három adatoszloppal és egy teljes metaadat oszloppal a jobb oldalon.

## 2. lépés: Kompakt (csonkított) mód engedélyezése

A kompakt mód eltávolítja a jobb oldali metaadat oszlopot, így a vonalkód keskenyebb lesz. Ez akkor hasznos, ha a hely korlátozott, de az adat a maradék sorokból rekonstruálható.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Miért csonkítunk?**  
Ha a `Truncate` értéke `true`, a generátor kihagyja a opcionális jobb oldali oszlopot, amely hibajavítást és fájlszintű metaadatokat tárol. Az eredményül kapott vonalkód kevesebb oszlopot foglal, miközben a legtöbb PDF417 olvasó számára továbbra is beolvasható.

## 3. lépés: Macro PDF417 vonalkód létrehozása fájlszintű metaadatokkal

A Macro PDF417 kibővíti a szabványos formátumot szegmensazonosítókkal, lehetővé téve egy nagy dokumentum több vonalkódra bontását. Ez hasznos hosszú karakterláncok vagy többoldalas fájlok kódolásához.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**A makró mezők magyarázata**

| Tulajdonság | Cél |
|-------------|-----|
| `MacroPdf417FileID` | A teljes fájl egyedi azonosítója; minden szegmens ezt az értéket használja. |
| `MacroPdf417SegmentID` | Az aktuális szegmens indexe (1‑től kezdődik). |
| `MacroPdf417SegmentsCount` | A teljes adatkészletet alkotó szegmensek összes száma. |

Egy Macro PDF417-et értő szkenner az összes szegmens beolvasásával és ezeknek az azonosítóknak a felhasználásával újra összeállíthatja az eredeti adatot.

## 4. lépés: Micro PDF417 vonalkód létrehozása rövid adatokhoz

A Micro PDF417 egy kompakt változat, amely kis mennyiségű adat (legfeljebb 90 karakter) számára készült. Az oszloptartományt 1‑4-re korlátozza, így a vonalkód alkalmas apró címkékhez vagy korlátozott kijelzőfelülettel rendelkező eszközökhöz.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Mikor használjuk a Micro PDF417-et**  
Használd ezt a változatot, ha az adatmenyiség rövid, és a lehető legkisebb vonalkódra van szükséged. Ideális készletcímkékhez, belépőkártyákhoz vagy bármilyen olyan helyzetben, ahol a képernyő felülete korlátozott.

## Teljes működő példa

Az alábbi önálló konzolalkalmazás egy futtatás során generálja mind a négy vonalkód típust. Másold a kódot egy új C# projektbe, cseréld le a `YOUR_DIRECTORY`‑t egy létező mappa útvonalára, és futtasd.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Várt kimenet**

A program futtatása négy PNG fájlt hoz létre a megadott mappában:

* `Pdf417Basic.png` – szabványos vonalkód három oszloppal
* `CompactPdf417.png` – ugyanaz az adat, csonkított jobb oldali oszloppal
* `MacroPdf417.png` – makró vonalkód szegmens metaadatokkal
* `MicroPdf417.png` – kompakt mikro vonalkód rövid karakterláncokhoz

Nyiss meg bármelyik képet egy képnézővel; láthatod a jellegzetes PDF417 mintákat. A mobil vonalkódolvasóval (pl. ZXing, Scandit) történő beolvasásuk visszaadja az eredeti szöveges karakterláncokat.

## Gyakori kérdések és tippek

* **Mi van, ha a vonalkód elmosódott?**  
  Növeld a `XDimension.Pixels` értékét 3‑ra vagy 4‑re. A nagyobb modulméret magasabb felbontású képet eredményez, de nagyobb fájlmérettel.

* **Kimenetként SVG-t kérhetek PNG helyett?**  
  Igen. Cseréld le a `BarCodeImageFormat.Png`-t `BarCodeImageFormat.Svg`-re a `Save` hívásokban.

* **Kell kézzel beállítanom a hibajavítási szintet?**  
  Az Aspose.BarCode automatikusan optimális szintet választ. Speciális esetekben módosíthatod a `Pdf417.ErrorCorrectionLevel` értékét.

* **Hogyan ágyazzam be a vonalkódot egy PDF dokumentumba?**  
  Használd az `Aspose.Pdf`‑t, hogy a generált PNG vagy SVG képet képelemként hozzáadd egy PDF oldalhoz.

* **A könyvtár szálbiztos?**  
  Minden `BarcodeGenerator` példány független; több szálon is létrehozhatsz generátorokat megosztott állapot nélkül.

## Összegzés

Most már tudod, hogyan **hozz létre PDF417 vonalkódot** C#-ban az Aspose.BarCode használatával, lefedve az alap, kompakt, makró és mikro változatokat.

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljesen működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre pdf417 vonalkódot C#‑ban – lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Hogyan hozzunk létre PDF417 vonalkódot C#‑ban kompakt móddal](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hogyan hozzunk létre macro PDF417 vonalkódot C#‑ban az Aspose.BarCode használatával](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}