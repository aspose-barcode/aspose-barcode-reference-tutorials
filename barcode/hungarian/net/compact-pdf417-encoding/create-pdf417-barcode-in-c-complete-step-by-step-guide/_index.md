---
category: general
date: 2026-07-18
description: Készíts PDF417 vonalkódot gyorsan C#-ban. Tanuld meg, hogyan generálj
  vonalkódot, állíts be paramétereket, és mentsd el a képfájlokat – AI 10 kezeléssel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: hu
lastmod: 2026-07-18
og_description: PDF417 vonalkód létrehozása C#-ban teljes útmutatóval. Fedezd fel,
  hogyan generálj vonalkódot, állítsd be a beállításokat, és ments képeket, miközben
  kezeled az AI 10-et.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: PDF417 vonalkód létrehozása C#-ban – Gyors, rugalmas, teljes kódrészlet
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: PDF417 vonalkód létrehozása C#‑ban – Teljes lépésről‑lépésre útmutató
url: /hu/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód létrehozása C#‑ban – Teljes lépésről‑lépésre útmutató

Valaha szükséged volt **create pdf417 barcode** létrehozására, de nem tudtad, melyik könyvtárat vagy beállítást válaszd? Nem vagy egyedül – sok fejlesztő szembesül ezzel, amikor először kísérletezik a GS1‑Micro‑PDF417‑tel. A jó hír, hogy néhány C# sorral könnyedén előállíthatsz egy tökéletesen formázott vonalkódot, finomhangolhatod a megjelenését, és közvetlenül a lemezre mentheted a képet.

Ebben az útmutatóban végigvezetünk a **how to generate barcode** folyamatán az Aspose.BarCode könyvtár használatával, megmutatjuk, **how to set parameters** beállításait, mint az X‑dimension és az oszlopszám, és bemutatjuk, **how to save image** fájlok mentését mind az AI 10, mind az AI 21 változatokhoz. A végére egy újrahasználható kódrészletet kapsz, amelyet bármely .NET projektbe beilleszthetsz.

## Prerequisites

Mielőtt belevágnánk, győződj meg róla, hogy rendelkezel:

- .NET 6+ vagy .NET Framework 4.7.2 (bármely friss futtatókörnyezet működik)
- Visual Studio 2022 vagy a kedvenc C# szerkesztőd
- Az **Aspose.BarCode for .NET** NuGet csomag (`Install-Package Aspose.BarCode`)
- Egy írható mappa a lemezen, ahová a PNG fájlok kerülnek

Ennyi – nincs extra eszköz, nincs bonyolult konfiguráció. Készen állsz? Kezdjünk is.

## 1. lépés: PDF417 vonalkód létrehozása GS1‑Micro formátummal

Az első dolog, amit csinálunk, egy **create pdf417 barcode** objektum létrehozása és az első AI adatok betáplálása. A GS1‑Micro‑PDF417‑ben az AI 10 (tétel/lot szám) gyakran a kiindulási pont, ezért ezt azonnal kódoljuk.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Why this matters:** A `EncodeTypes.GS1MicroPdf417` azt mondja a könyvtárnak, hogy kövesse a GS1‑Micro specifikációt, amely automatikusan előállítja az AI zárójeleket. Ha kihagyod, egy általános PDF417-et kapsz, amely nem biztos, hogy olvasható a kiskereskedelmi környezetben.

## 2. lépés: Hogyan állítsuk be a vonalkód paramétereit

Most, hogy van egy vonalkód példányunk, finomhangolni kell a vizuális jellemzőit. Itt jön képbe a **how to set parameters**. Három gyakori beállítást módosítunk:

1. **X‑dimension** – szabályozza a legkisebb vonal szélességét (pixelben)
2. **Column count** – befolyásolja az általános alakot; kevesebb oszlop = magasabb vonalkód
3. **IsLinked** – engedélyezi a opcionális link modult, amely a vonalkódot az adatstringhez köti

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Pro tip:** Ha mobil szkennelést célozol, növeld az X‑dimension értékét 3‑4 pixelre; a nagyobb modulok jobban ellenállnak az alacsony felbontású kameráknak.

## 3. lépés: Kép mentése – Első verzió (AI 10)

A generátor beállítása után végre **how to save image**-t hajthatunk végre. A `Save` metódus a megadott formátumban írja a vonalkódot egy fájlba. Itt PNG-t használunk, mert megőrzi a tiszta éleket tömörítési hibák nélkül.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Ekkor egy `GS1MicroPdf417_AI10.png` nevű fájlt kell látnod az `outputDir` mappádban. Nyisd meg bármely képnézegetővel – egy tiszta, nagy kontrasztú PDF417-et látsz, amely készen áll a nyomtatásra.

## 4. lépés: Váltás egy másik AI‑ra (AI 21) és újra mentés

Gyakran szükség van egy másik alkalmazásazonosító (AI) kódolására, például az AI 21‑re (sorozatszám). Csak a `CodeText` tulajdonságot kell módosítani. Ez egyszerre mutatja be a **barcode ai 10** és a **barcode ai 21** kezelését.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **What if you need more AIs?** Egyszerűen fűzd össze őket ugyanabban a karakterláncban, pl. `"(10)ABCD(21)12345(240)XYZ"`. A könyvtár automatikusan feldolgozza a zárójeleket.

## Teljes működő példa

Összeállítva, itt egy önálló program, amelyet beilleszthetsz egy konzolos alkalmazásba:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Expected output:** Két PNG fájl jelenik meg a `C:\Barcodes\` könyvtárban – `GS1MicroPdf417_AI10.png` és `GS1MicroPdf417_AI21.png`. Mindkettő egy beolvasható PDF417-et tartalmaz; az első az AI 10‑et, a második az AI 21‑et kódolja.

## Gyakori hibák és elkerülésük

- **Hiányzó mappa jogosultságok:** Ha a `Save` `UnauthorizedAccessException`‑t dob, ellenőrizd, hogy az útvonal létezik-e, és az alkalmazásnak van‑e írási joga.
- **Helytelen AI formátum:** Ha elfelejted a zárójeleket (`(10)`), a vonalkód egyszerű adatként lesz kezelve, ami megsérti a GS1 validációt.
- **Túl kicsi X‑dimension:** Az 1 pixelnél vékonyabb vonalak eltűnhetnek a kép átméretezésekor. Képernyőn legalább 2 pixel legyen.

## Következő lépések és kapcsolódó témák

Most, hogy tudod, **how to generate barcode**, **how to set parameters**, és **how to save image**, érdemes lehet felfedezni:

- Olvasható szöveg hozzáadása a vonalkód alá (**human‑readable text**) (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exportálás **PDF**‑be PNG helyett (`BarCodeImageFormat.Pdf`)
- A vonalkód generálás integrálása egy **ASP.NET Core API**‑ba a valós‑időben történő képgeneráláshoz

Ezek a témák közvetlenül a jelen útmutatóban lefektetett alapokra épülnek.

---

### Gyors összefoglaló

- **Create pdf417 barcode** a `BarcodeGenerator` és `EncodeTypes.GS1MicroPdf417` használatával
- **How to set parameters** mint X‑dimension, oszlopok és linkelés
- **How to save image** PNG‑ként mind AI 10, mind AI 21 változatokhoz
- **barcode ai 10** kezelve és **barcode ai 21**‑re váltva egyetlen property módosítással

Próbáld ki, finomítsd a beállításokat, és máris egy robusztus vonalkód motorod lesz a produkcióhoz. Van kérdésed vagy mélyebb részletekre van szükséged? Írj kommentet alul – jó kódolást!

## Mit érdemes legközelebb megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre vonalkódot – Kompakt PDF417 az Aspose.BarCode segítségével](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan hozzunk létre nyugodt zónát az ITF-14 vonalkódhoz az Aspose.BarCode for .NET használatával](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hogyan hozzunk létre Aztec vonalkódot hibajavítással .NET‑ben](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}