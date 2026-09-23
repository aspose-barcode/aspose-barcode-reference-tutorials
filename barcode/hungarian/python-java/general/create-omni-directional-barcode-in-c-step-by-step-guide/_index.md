---
category: general
date: 2026-07-15
description: Készítsen minden irányba olvasható vonalkódot C#-ban gyorsan az Aspose.BarCode
  segítségével – tanulja meg, hogyan generáljon vonalkódot C#-ban állítható vonalmagassággal
  és X‑dimenzióval.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: hu
lastmod: 2026-07-15
og_description: hozzon létre minden irányban olvasható vonalkódot C#-ban az Aspose.BarCode
  segítségével. Tanulja meg, hogyan generáljon vonalkódot C#-ban az XDimension és
  BarHeight finomhangolásával a tökéletes eredményért.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Többirányú vonalkód létrehozása C#-ban – Teljes programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Többirányú vonalkód létrehozása C#-ban – Lépésről lépésre útmutató
url: /hu/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# omni-directional vonalkód létrehozása C#‑ban – Lépésről‑lépésre útmutató

Gondolkodtál már azon, hogyan lehet C#‑ban olyan vonalkódot generálni, amely megfelel a GS1 DataBar Omni‑Directional szimbólumnak? Nem vagy egyedül. Ebben az útmutatóban **omni-directional vonalkód** képeket hozunk létre a semmiből, finomhangoljuk az X‑dimenziót, és játszunk a vonalmagassággal – mindezt az Aspose.BarCode könyvtár segítségével.

Egy valós példán keresztül vezetünk végig: egy kompakt, nagy sűrűségű vonalkódra van szükséged egy kiskereskedelmi címkén, és teljes ellenőrzést szeretnél a vizuális mérete felett. A végére két PNG fájlod lesz – egy 30 px magasságú, egy 60 px magasságú – készen állva bármely nyomtatási folyamatba.

## Előkövetelmények

- .NET 6 (vagy bármely friss .NET futtatókörnyezet) telepítve van a gépeden.  
- Visual Studio 2022 vagy VS Code—bármely kedvenc IDE‑d megfelel.  
- Egy ingyenes Aspose.BarCode for .NET NuGet csomag (`Aspose.BarCode`).

Más függőség nem szükséges. Ha még sosem használtad a NuGet‑et, egyszerűen nyisd meg a Package Manager Console‑t és futtasd:

```powershell
Install-Package Aspose.BarCode
```

## omni-directional vonalkód – Az alapok megértése

A **GS1 DataBar Omni‑Directional** szimbólum úgy lett tervezve, hogy bármilyen orientációban beolvasható legyen, így tökéletes a polcszegély címkékhez. Amikor meghívod a `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` kódot, a könyvtár elvégzi a nehéz munkát: kódolja az adatot, alkalmazza a szimbólum szabályait, és előkészíti a raszteres képet.

> **Pro tipp:** Mindig csomagold be a nyers adatot a megfelelő Alkalmazási Azonosító (AI) formátumba, pl. `"(01)12345678901231"` egy GTIN‑14‑hez. Ez tájékoztatja a szkennert arról, hogy a számjegyek mit jelentenek.

## 1. lépés – A Barcode Generator beállítása (how to generate barcode c#)

Először létrehozzuk a generátor objektumot. Ez az alapja a **how to generate barcode c#** használatának az Aspose‑szal.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

A `EncodeTypes.DatabarOmniDirectional` enum érték megmondja a motornak, melyik szimbólumot használja. A második argumentum a nyers adat string, már beágyazva a GTIN AI‑ba.

## 2. lépés – Az X‑dimenzió beállítása (barcode XDimension)

A **barcode XDimension** szabályozza a legkisebb vonal szélességét. A 2 px érték jó egyensúlyt biztosít az olvashatóság és a kompakt méret között a legtöbb címkenyomtató számára.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ha finomabb vagy durvább megjelenésre van szükséged, egyszerűen módosítsd a számot. Ne feledd: az X‑dimenzió az alapegység; minden más vonalszélesség ennek a szorzata.

## 3. lépés – Az első kép létrehozása 30 px vonalmagassággal (barcode BarHeight)

Most beállítjuk a **barcode BarHeight** értékét 30 px‑re, és elmentjük a képet. Ez egy közepes méretű vonalkódot eredményez, amely szépen elfér egy szabványos címkén.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

A `Save` metódus PNG fájlt ír a lemezre. Ha JPEG kimenetet szeretnél, cseréld le a `BarCodeImageFormat.Jpeg`‑re.

## 4. lépés – A vonalmagasság növelése 60 px‑re nagyobb címkékhez (barcode BarHeight)

Néha nagyobb vonalkódra van szükség – például egy polc címkéhez, amely távolabb van a szkennertől. Növeljük meg a magasságot duplájára.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Vedd észre, hogy **nem** kell újra létrehozni a generátort; csak módosítjuk a paramétert és újra felhasználjuk ugyanazt az objektumot. Ez memóriát takarít meg és rendezetten tartja a kódot.

## 5. lépés – A második kép mentése (how to generate barcode c#)

Végül elmentjük a második PNG‑t. Most már két fájlod van, amelyek csak a vonalmagasságban különböznek.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Várt kimenet

- `DatabarBarHeight30Pixels.png` – egy 30 px magas omni‑directional vonalkód.  
- `DatabarBarHeight60Pixels.png` – ugyanaz az adat, de 60 px magas vonalkóddal.

Nyisd meg a fájlokat bármely képnézőben; tiszta, beolvasható vonalakat látsz, amelyek megfelelnek a GS1 DataBar Omni‑Directional specifikációnak.

## Gyakori kérdések és szélhelyzetek

### Mi van, ha más X‑dimenzióra van szükségem?

Egyszerűen rendelj egy új értéket a `Save` hívása előtt. Ultra‑magas sűrűségű nyomtatáshoz akár 1 px‑re is lecsökkenhetsz, de előbb teszteld a szkennereddel – egyes eszközök nehezen olvasnak 2 px alatti vonalakat.

### Hozzáadhatok emberi olvasásra szánt szöveget a vonalkód alá?

Igen. Állítsd be a `barcodeGenerator.Parameters.Barcode.CodeText` értékét egy stringre, és opcionálisan módosítsd a `barcodeGenerator.Parameters.Barcode.CodeLocation`‑t `BarCodeTextLocation.Below`‑ra. Ez hasznos a kiskereskedelmi környezetben, ahol a numerikus GTIN‑nek láthatónak kell lennie.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### A PNG a legjobb formátum a nyomtatáshoz?

A PNG veszteségmentes, ami megőrzi a vonalkódolvasók számára szükséges éles éleket. Ha a downstream rendszered más formátumot (TIFF, BMP) vár, egyszerűen változtasd meg a `BarCodeImageFormat` enum‑ot.

## Teljes működő példa (create omni-directional barcode)

Az alábbiakban a teljes, azonnal futtatható program található. Másold be egy új konzolprojektbe, és nyomd meg a **F5**‑öt.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Futtasd a programot, ellenőrizd a kimeneti mappát, és pontosan a leírt két PNG fájlt fogod látni.

## Összefoglalás

Bemutattuk, hogyan **generate barcode C#** kódot készíthetünk, amely **create omni-directional barcode**-t hoz létre az Aspose.BarCode használatával. A **barcode XDimension** és **barcode BarHeight** beállításával finomhangolt vizuális méretet érhetsz el anélkül, hogy a beolvasási megbízhatóságot veszélyeztetnéd.

## Mi a következő lépés?

- Kísérletezz más **GS1 DataBar Omni-Directional** beállításokkal, például `Color` vagy `Margin`.  
- Több vonalkód kombinálása egyetlen vásznon a `Graphics` használatával összetett címketervekhez.  
- Integráld a generátort egy web API‑ba, hogy az e‑commerce platformod igény szerint tudjon vonalkódot generálni.

Van egy ötleted, amit meg szeretnél osztani? Írj egy megjegyzést, és folytassuk a beszélgetést. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes működő kódpéldákat lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk vonalkódot – Code 39 konfiguráció az Aspose.BarCode‑dal](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hogyan hozzunk létre vonalkód csendes zónát ITF-14‑hez az Aspose.BarCode for .NET használatával](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hogyan hozzunk létre vonalkód csendes zónát Code 16K‑hoz az Aspose.BarCode for .NET használatával](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}