---
category: general
date: 2026-09-16
description: Tanulja meg, hogyan állíthat be vonalkód oszlopokat C#‑ban a BarcodeGenerator
  segítségével, és hogyan állíthat be vonalkód sorokat a DataBar Expanded Stacked
  vonalkódokhoz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: hu
lastmod: 2026-09-16
og_description: Állítsd be gyorsan a vonalkód oszlopokat C#-ban. Ez az útmutató megmutatja,
  hogyan konfigurálhatod az oszlopokat, sorokat és a képformátumot a BarcodeGenerator
  segítségével.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Állíts be vonalkód oszlopokat és sorokat C#-ban – a teljes BarcodeGenerator
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan állítsuk be a vonalkód oszlopait és sorait a C# BarcodeGenerator segítségével
url: /hu/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a vonalkód oszlopait és sorait C# BarcodeGenerator használatával

Ha C# alkalmazásban kell beállítania a vonalkód oszlopait, ez a bemutató pontosan bemutatja a szükséges lépéseket. Megmutatjuk, hogyan konfigurálhatja az oszlopokat és sorokat egy DataBar Expanded Stacked vonalkódban, majd hogyan mentheti az eredményt PNG képként.

A vonalkódok programozott generálása megkímél a manuális tervezéstől, és biztosítja a konzisztenciát a jelentések, számlák és termékcímkék között. Az alábbi példa lefedi a teljes munkafolyamatot, a könyvtár telepítésétől két kép előállításáig – az egyik egy egyedi oszlopszámmal, a másik egy egyedi sorok számával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6.0 vagy újabb telepítve.  
* Hivatkozás a **Aspose.BarCode for .NET** NuGet csomagra. Telepítse a következővel:

```bash
dotnet add package Aspose.BarCode
```

* Írási jogosultság egy mappához, ahová a generált PNG fájlok mentésre kerülnek.

Ezek a követelmények biztosítják, hogy a kód fordítható és futtatható legyen további konfiguráció nélkül.

## Hogyan állítsuk be a vonalkód oszlopait C#-ban

Az első fontos lépés egy `BarcodeGenerator` példány létrehozása a **DataBar Expanded Stacked** szimbólumhoz, és a kívánt oszlopszám beállítása.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Miért működik ez:**  
`EncodeTypes.DatabarExpandedStacked` megmondja a könyvtárnak, melyik szimbólumot kell megjeleníteni. A `Parameters.Barcode.DataBar.Columns` beállítása megváltoztatja a belső modul elrendezését, ami közvetlenül befolyásolja a vonalkód vizuális szélességét. A `Save` metódus a kért `BarCodeImageFormat` szerint írja a képet a lemezre.

### Várt eredmény
Nyissa meg a `C:\Barcodes\DatabarCols4.png` fájlt bármely képmegjelenítőben. Egy DataBar Expanded Stacked vonalkódot kell látnia, amely szélesebb az alapértelmezettnél, mivel négy oszlopot használ.

## Hogyan állítsuk be a vonalkód sorait C#-ban

Miután elmentette az oszlop‑alapú képet, előfordulhat, hogy egy magasságban változó vonalkódra van szüksége a sorok módosításával. A folyamat az oszlop‑konfigurációhoz hasonló, de a `Rows` tulajdonságot használja.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Miért működik ez:**  
A generátor újrainicializálása biztosítja, hogy az előző oszlopszám beállítás ne zavarja a sor‑konfigurációt. A `Parameters.Barcode.DataBar.Rows` módosítása a vonalkód magasságát változtatja, így magasabb képet kap, ha a sorok száma meghaladja az alapértelmezettet.

### Várt eredmény
Nyissa meg a `C:\Barcodes\DatabarRows3.png` fájlt. A vonalkód magasabb lesz, tükrözve a három‑soros beállítást.

## Teljes vég‑től‑vég példája

Az alábbi egyetlen program, amely egy futtatás során létrehozza mindkét képet. A kód egy fájlban tartása bemutatja, hogyan válthat oszlop‑ és sor‑beállítások között az alkalmazás újraindítása nélkül.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

A program futtatása két PNG fájlt hoz létre:

* **DatabarCols4.png** – vonalkód négy oszloppal.  
* **DatabarRows3.png** – vonalkód három sorral.

Mindkét fájl a **barcode image format** PNG‑t használja, amely megőrzi a szép éleket és támogatja a veszteségmentes tömörítést – ideális nyomtatáshoz és digitális megjelenítéshez.

## Gyakori kérdések és tippek

| Kérdés | Válasz |
|----------|--------|
| *Használhatok JPEG-et PNG helyett?* | Igen. Cserélje le a `BarCodeImageFormat.Png`‑t `BarCodeImageFormat.Jpeg`‑re. A JPEG kisebb, de tömörítési hibákat okozhat, amelyek befolyásolhatják a szkenner megbízhatóságát. |
| *Mi a maximális oszlop- vagy sorok száma?* | A könyvtár ellenőrzi az értékeket a DataBar specifikációval szemben. A megengedett tartományon kívüli értékek `ArgumentException`‑t dobnak. Nézze meg az Aspose.BarCode dokumentációt a pontos korlátokért. |
| *Szükséges-e felszabadítani a `BarcodeGenerator`‑t?* | Az osztály implementálja az `IDisposable` interfészt. Tegye a generátort `using` blokkba, ha egy ciklusban sok példányt hoz létre, hogy a nem kezelt erőforrások gyorsan felszabaduljanak. |
| *Hogyan változtathatom meg a vonalkód méretét anélkül, hogy módosítanám az oszlopokat/sorokat?* | Használja a `barcodeGenerator.Parameters.Image.Width` és `Height` értékeket a kimeneti kép méretezéséhez, miközben a modul elrendezés változatlan marad. |

**Pro tipp:** Ha nagy felbontású nyomtatáshoz generál vonalkódokat, növelje a kimeneti kép méreteit (`Width`/`Height`) az oszlop‑ vagy sor‑szám helyett. Ez a megközelítés megőrzi a szimbólum által definiált szabványos modulméretet, miközben élesebb képet biztosít.

## Következtetés

Most már tudja, hogyan állítsa be a vonalkód oszlopait és sorait C#‑ban a **BarcodeGenerator** osztály segítségével. Az útmutató bemutatta a generátor inicializálását, az oszlop‑ és sor‑számok konfigurálását, a vonalkód PNG formátumban történő mentését, valamint a gyakori variációk kezelését, például a képformátum módosítását és az erőforrások felszabadítását.

Ezután fedezze fel a kapcsolódó témákat, például a **vonalkód színek testreszabását**, a **emberi olvasásra szánt szöveg hozzáadását**, és a **vonalkódok PDF dokumentumokba ágyazását**. Ezek a kiterjesztések ugyanazon konfigurációs mintára épülnek, amelyet itt bemutattunk, lehetővé téve, hogy teljes körű vonalkód‑megoldásokat hozzon létre bármely .NET alkalmazáshoz.

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a bemutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Barcode Generator példa C#-ban – oszlopok, sorok beállítása és kép exportálása](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked vonalkód útmutató – hogyan generáljuk és méretezzük C#-ban](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator példa C#-ban – szélesség és magasság beállítása](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}