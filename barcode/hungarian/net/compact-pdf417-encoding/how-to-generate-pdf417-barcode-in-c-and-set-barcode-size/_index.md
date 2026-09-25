---
category: general
date: 2026-08-22
description: Ismerje meg, hogyan generálhat PDF417 vonalkódot C#-ban az Aspose.BarCode
  segítségével, állítsa be a vonalkód méretét, módosítsa az oszlopokat, és engedélyezze
  a kompakt módot.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: hu
lastmod: 2026-08-22
og_description: PDF417 vonalkód generálása C#-ban az Aspose.BarCode segítségével.
  Ez az útmutató bemutatja, hogyan állítható be a vonalkód mérete, szabályozhatók
  az oszlopok, és engedélyezhető a kompakt mód a kisebb képhez.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: PDF417 vonalkód generálása C#-ban – méret, oszlopok és kompakt mód beállítása
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Hogyan generáljunk PDF417 vonalkódot C#-ban, és állítsuk be a vonalkód méretét
url: /hu/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk PDF417 vonalkódot C#-ban és állítsuk be a vonalkód méretét

Ha **PDF417 vonalkódot** kell generálnod egy .NET alkalmazásban, ez az útmutató végigvezet a teljes folyamaton. Megmutatjuk pontosan, **hogyan generáljunk PDF417**-et az Aspose.BarCode segítségével, hogyan állítsuk be a **vonalkód méretét**, és hogyan hozzunk létre egy kompakt PNG-t, amely beágyazható jelentésekbe vagy mobilalkalmazásokba.

Vonalkód létrehozásához nem szükséges külön grafikus szerkesztő. A tutorial végére egy teljesen működő C# metódusod lesz, amely a szükséges pontos méretekkel ellátott PDF417 képet állít elő, készen áll a további feldolgozásra.

## Mit fogsz megtanulni

* Az Aspose.BarCode könyvtár telepítése és hivatkozása.
* PDF417 vonalkód generátor létrehozása és a kódolt szöveg megadása.
* **Set barcode size** beállítása az X‑dimenzió és az oszlopszám konfigurálásával.
* Kompakt (truncált) mód engedélyezése a szimbólum méretének csökkentéséhez.
* Az eredmény mentése PNG fájlként.
* Gyakori problémák hibaelhárítása, például olvashatatlan kódok és túl nagy képek.

### Előfeltételek

* .NET 6.0 vagy újabb (az API a .NET Framework 4.6+ verzióval is működik).
* Alapvető ismeretek C#-ban és a Visual Studio-ban (vagy bármely C# IDE-ben).
* Érvényes Aspose.BarCode licenc (az ingyenes értékelés teszteléshez használható).

> **Pro tipp:** Ha sok vonalkódot szeretnél generálni egy ciklusban, használd újra ugyanazt a `BarcodeGenerator` példányt, és csak a `CodeText` tulajdonságot módosítsd. Ez csökkenti a memóriafoglalásokat.

## PDF417 vonalkód generálása az Aspose.BarCode segítségével

Az első lépés a `BarcodeGenerator` példányosítása a PDF417 szimbólumhoz. Ez az objektum a belépési pont minden vonalkód művelethez.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Miért fontos*: `EncodeTypes.Pdf417` azt mondja a könyvtárnak, hogy a PDF417 szabványt használja, amely nagy adatvolumeneket és hibajavítást támogat. A konstruktor egyben elfogadja a kódolni kívánt adatot, így később nem kell külön `CodeText` értéket beállítani.

## Vonalkód méretének és oszlopszámának beállítása

A PDF417 szimbólumok sorokból és oszlopokból álló kis téglalap alakú modulokból állnak. A modul szélességének (X‑dimenzió) és az oszlopok számának szabályozásával finoman hangolhatod a teljes méreteket.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Magyarázat*:  
* **X‑dimension** (`Pixels`) határozza meg, milyen széles egy modul. A kisebb értékek szorosabb vonalkódot eredményeznek, míg a nagyobb értékek javítják az olvashatóságot alacsony felbontású szkennereknél.  
* **Columns** szabályozza a vízszintes elrendezést. Kevesebb oszlop magasabb, több oszlop szélesebb vonalkódot eredményez. Ezeket a beállításokat együtt módosítva érheted el a pontos **set barcode size**-t, amelyre szükséged van.

## Kompakt mód engedélyezése a kisebb vonalkódhoz

A PDF417 tartalmaz egy “compact” (vagy truncált) módot, amely eltávolítja a felesleges kitöltést és csökkenti a teljes lábnyomot. Ez különösen hasznos, ha korlátozott a képernyőhely.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Miért engedélyezzük a truncálást?*  
Amikor a `Truncate` értéke `true`, a generátor kihagyja a stop mintát és néhány hibajavító kódszót, amelyek a legtöbb szkennelési helyzetben nem szükségesek. Az eredményül kapott kép körülbelül 15‑20 %-kal kisebb, anélkül, hogy a tipikus felhasználási eseteknél adat integritást veszélyeztetne.

## Vonalkód mentése PNG képként

A méret és mód beállítása után írd a vonalkódot a lemezre. A PNG veszteségmentes, így a modulok élei élesek maradnak.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

A `CompactPdf417.png` fájl egy éles PDF417 szimbólumot fog tartalmazni, amely megegyezik a korábbi lépésekben beállított méretekkel.

### Várt kimenet

A mentett PNG megnyitása egy függőlegesen orientált PDF417 vonalkódot kell, hogy mutasson, három oszlopból áll, minden modul 2 px széles, és a teljes méret körülbelül **120 × 240 px** (szélesség × magasság). A kép beolvasása bármely szabványos PDF417 olvasóval visszaadja az eredeti szöveget: „Sample text for PDF417”.

## Gyakori buktatók és elkerülésük módja

| Szimbólum | Valószínű ok | Javítás |
|-----------|--------------|---------|
| A vonalkód olvashatatlan | Az X‑dimenzió túl kicsi a szkennerhez | `XDimension.Pixels` növelése 3‑ra vagy 4‑re |
| A kép túl széles a felhasználói felülethez | Túl sok oszlop van beállítva | `Pdf417.Columns` csökkentése vagy a `Truncate` engedélyezése |
| Kivétel `ArgumentOutOfRangeException` | Negatív vagy nulla oszlopszám | Győződj meg róla, hogy a `Columns` pozitív egész szám (minimum 1) |
| A PNG fájl üres | A kimeneti útvonal nem létezik vagy nincs írási jogosultság | Ellenőrizd, hogy a könyvtár létezik és az alkalmazásnak van írási joga |

> **Pro tipp:** Használd a `barcodeGenerator.ValidateParameters()` metódust a `Save()` hívása előtt, hogy korán elkapd a konfigurációs hibákat.

## Teljes, futtatható példa

Az alábbi önálló konzolprogram tartalmazza a fenti összes lépést. Másold be egy új C# projektbe, állítsd vissza az Aspose.BarCode NuGet csomagot, és futtasd, hogy lásd az eredményt.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**A program futtatása** `CompactPdf417.png` fájlt hoz létre a végrehajtható munkakönyvtárában. Olvasd be a képet egy mobilalkalmazással (pl. „Barcode Scanner”), hogy ellenőrizd, a kódolt szöveg megegyezik a forráskarakterlánccal.

## Következő lépések és kapcsolódó témák

* **Increase error correction level** – állítsd be a `Pdf417.ErrorLevel`-t zajos szkennelési környezetekhez.  
* **Change orientation** – állítsd a `Pdf417.Rotate`-t `RotationAngle.Rotate90`-ra, ha vízszintes elrendezésre van szükség.  
* **Embed the barcode in a PDF** – kombináld az Aspose.PDF-et az Aspose.BarCode-dal, hogy a képet közvetlenül egy dokumentumba helyezd.  
* **Generate other 2‑D barcodes** – ugyanaz a `BarcodeGenerator` osztály támogatja a DataMatrix, QR és Aztec kódokat; csak cseréld le a `EncodeTypes.Pdf417`-t a kívánt szimbólumra.

A **generate PDF417 barcode** technikák elsajátításával automatizálhatod a jegykezelést, a készletcímkézést és a biztonságos adatátvitelt a .NET alkalmazások széles skálájában.

## Következtetés

Most már tudod, hogyan **generate PDF417 barcode** C#-ban, pontosan **set barcode size**, hogyan konfiguráld az oszlopokat, engedélyezd a kompakt módot, és mentsd el az eredményt PNG-ként. Alkalmazd ezeket a beállításokat bármilyen UI korláthoz vagy szkennelési követelményhez, és szükség szerint bővítsd a megközelítést más vonalkódformátumokra. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}