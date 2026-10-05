---
category: general
date: 2026-09-10
description: Készíts PDF417 vonalkódot C#-ban gyorsan. Tanuld meg, hogyan engedélyezheted
  a kompakt módot, állíthatod be az oszlopok számát, és generálhatsz PNG-t a BarcodeGenerator
  segítségével.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: hu
lastmod: 2026-09-10
og_description: PDF417 vonalkód létrehozása C#-ban kompakt mód engedélyezésével, oszlopok
  beállításával és PNG formátumban mentéssel. Kövesse a teljes lépésről‑lépésre útmutatót.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: PDF417 vonalkód létrehozása C#-ban – kompakt mód útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hogyan hozhatunk létre PDF417 vonalkódot C#-ban kompakt móddal
url: /hu/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód létrehozása C#-ban kompakt móddal

Ha **PDF417 vonalkódot** kell létrehoznod egy .NET alkalmazásban, ez az útmutató pontosan megmutatja, hogyan teheted ezt. Meg fogod látni, hogyan **kapcsolhatod be a kompakt módot**, állíthatod be az oszlopok számát, és mentheted az eredményt PNG képként a BarcodeGenerator C# könyvtár segítségével.

Vonalkód generálása gyakori követelmény a készletkövetés, jegyrendszerek és mobil szkennelő alkalmazások számára. A tutorial végére egy önálló, futtatható példát kapsz, amely egy kompakt PDF417 vonalkódot állít elő, készen áll a termelésben való használatra.

## Előfeltételek

* .NET 6.0 vagy újabb telepítve (a kód .NET Framework 4.7+‑vel is működik)
* A **BarcodeGenerator** könyvtár legújabb verziója (pl. Aspose.BarCode for .NET)
* IDE vagy szerkesztő, például Visual Studio 2022 vagy VS Code
* Írási jogosultság egy olyan mappához, ahová a PNG-t menteni fogod

A vonalkód könyvtárán kívül nincs szükség további NuGet csomagokra.

## 1. lépés: PDF417 vonalkód generátor létrehozása

Az első lépés egy `BarcodeGenerator` objektum példányosítása a `EncodeTypes.Pdf417` enummal és a kódolni kívánt szöveggel. Ez az objektum irányítja a teljes generálási folyamatot.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Miért fontos*: A `EncodeTypes.Pdf417` érték azt mondja a könyvtárnak, hogy a PDF417 szimbólumot használja, míg a második argumentum adja meg a terhet. A `"Compact mode"` szöveget bármilyen alfanumerikus karakterláncra cserélheted, amelyet kódolni szeretnél.

## 2. lépés: X dimenzió beállítása (modul szélesség)

Az X dimenzió szabályozza a vonalkódban lévő minden apró négyzet (modul) szélességét. A kisebb értékek szorosabb képet eredményeznek, ami akkor hasznos, ha a hely korlátozott.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A `2` pixel érték jó egyensúlyt biztosít az olvashatóság és a kompakt méret között a legtöbb képernyőalapú szkenner számára.

## 3. lépés: Oszlopok számának meghatározása

A PDF417 adatokat sorok és oszlopok rácsában rendezhet. Az oszlopszám módosítása megváltoztatja a vonalkód képarányát.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

A **how to set columns** érték `3`‑ra állítása egy rövid, széles vonalkódot eredményez, amely jól illeszkedik egy címkére. Kísérletezhetsz `1` és `30` közötti értékekkel az adatmennyiség és a cél szkenner függvényében.

## 4. lépés: Kompakt mód engedélyezése

A kompakt mód eltávolítja a felesleges kitöltő sorokat, így a vonalkód kisebb lesz anélkül, hogy adatintegritást veszélyeztetne. Ez a kulcsfontosságú lépés egy **kompakt PDF417** esetén.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Ha a `Truncate` `true`, a könyvtár automatikusan kiszámítja a minimális sorok számát, amely szükséges az adatok tárolásához, ezért a végső kép „szoros” lesz.

## 5. lépés: A generált vonalkód mentése PNG képként

Végül írd a vonalkódot egy fájlba. A PNG megőrzi a tiszta éleket, amelyek a megbízható szkenneléshez szükségesek.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Cseréld le a `YOUR_DIRECTORY`-t egy abszolút vagy relatív útvonalra, amelyre az alkalmazásod írni tud. A futtatás után megtalálod a `CompactPdf417.png` fájlt, amely a vonalkódot tartalmazza.

### Teljes forráskód

Az összes lépés egyesítése egyetlen, azonnal futtatható programot eredményez:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

A program futtatása `CompactPdf417.png` fájlt hoz létre ugyanabban a mappában, mint a végrehajtható. Nyisd meg a képet bármely megjelenítővel; egy sűrű, nagy kontrasztú PDF417 vonalkódot kell látnod, amely készen áll a szkennelésre.

## Hogyan engedélyezd a kompakt módot más helyzetekben

* **Kötegelt generálás** – Sok vonalkód létrehozásakor állítsd be egyszer a `Truncate`-t a generátoron, és használd újra minden új payload esetén.
* **Különböző képformátumok** – Ugyanaz a `Save` metódus működik `BarCodeImageFormat.Jpeg` vagy `BarCodeImageFormat.Bmp` esetén, ha más fájltípust igényelsz.
* **Dinamikus oszlopszám** – Ha a kódolt karakterlánc hossza változik, számíts ki egy optimális oszlopszámot a karakterlánc hossza és a szkenner felbontása alapján.

## Hogyan állítsd be az oszlopokat specifikus felhasználási esetekhez

* **Címkenyomtatás** – Alacsony oszlopszámot (pl. `2`‑`5`) használj, hogy a vonalkód elég rövid legyen a keskeny címkékre.
* **Mobil szkennelés** – Magasabb oszlopszámok (`10`‑`15`) magasabb vonalkódot eredményeznek, amelyet a telefonkamerák könnyebben fókuszálnak.
* **Hibajavítás kompromisszum** – Több oszlop kevesebb sort jelent, ami befolyásolhatja a vonalkód beépített hibajavítását. Teszteld a cél szkennerrel, hogy megtaláld az optimális beállítást.

## Gyakori buktatók és profi tippek

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| A vonalkód olvashatatlan | X dimenzió túl alacsony (pl. `1` pixel) | Növeld a `XDimension.Pixels` értékét legalább `2`-re |
| A kép túl nagy | Az oszlopok száma túl magas egy rövid payload esetén | Csökkentsd a `Pdf417.Columns` értékét vagy engedélyezd a `Truncate`-t |
| A PNG fájl üres | A kimeneti mappa nem létezik vagy nincs írási jogosultság | Győződj meg róla, hogy a könyvtár létezik és a folyamatnak van írási joga |
| A szkenner “adat sérült” hibát jelez | A Truncate le van tiltva sok oszlop használata esetén | Engedélyezd a `Truncate`-t vagy csökkentsd az oszlopszámot |

## Az eredmény ellenőrzése

A vonalkódot ellenőrizheted bármely PDF417 szkenner alkalmazással (számos ingyenes Android/iOS app létezik). Nyisd meg a `CompactPdf417.png` fájlt az alkalmazásban, és ellenőrizd, hogy a dekódolt szöveg megegyezik-e az eredeti payload-del („Compact mode”). Ha a szöveg eltér, ellenőrizd újra a `Truncate` jelzőt és az oszlopszám beállításait.

## Következő lépések

* **Integrálás ASP.NET Core-val** – A PNG-t közvetlenül egy controller akcióból térítsd vissza a lemezre mentés helyett.
* **Emberi olvasható szöveg hozzáadása** – Használd a `barcodeGenerator.Parameters.Barcode.CodeTextParameters`-t, hogy a kódolt szöveget a vonalkód alá jelenítsd meg.
* **Más szimbólumok felfedezése** – Ugyanaz a `BarcodeGenerator` osztály támogatja a QR, Code128, DataMatrix és továbbiakat. Válts `EncodeTypes`-ra, hogy kipróbáld őket.

---

### Következtetés

Most már tudod, hogyan **hozz létre PDF417 vonalkódot** C#-ban, miközben **engedélyezed a kompakt módot**, szabályozod **az oszlopok beállítását**, és a **barcode generator C#** API-t használod **vonalkód generálásához**, amely megfelel a valós méretkorlátoknak. Alkalmazd ezeket a lépéseket bármely .NET projektre, amelynek kompakt, nagy sűrűségű vonalkódokra van szüksége, és bővítsd a mintát más vonalkód formátumokra is, ha szükséges. Jó kódolást!

## Mit érdemes következőként megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [PDF417 vonalkód létrehozása C#‑ban – Teljes lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Hogyan állítsd be a hibaszintet PDF417 vonalkódban – Teljes útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Hogyan mentsd el a vonalkódot C#‑ban – PDF417 vonalkódok generálása](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}