---
category: general
date: 2026-10-09
description: Ismerje meg, hogyan hozhat létre PDF417 vonalkódot C#-ban az Aspose.BarCode
  használatával – generáljon Macro PDF417-et teljes metaadat-támogatással.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Ismerje meg, hogyan hozhat létre PDF417 vonalkódot C#-ban az Aspose.BarCode
  használatával – generáljon Macro PDF417-et teljes metaadat-támogatással, beleértve
  a fájlazonosítót, szegmensadatot, időbélyeget és egyebeket.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Hogyan készítsünk PDF417 vonalkódot C#-ban az Aspose.BarCode segítségével
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Hogyan készítsünk PDF417 vonalkódot C#-ban az Aspose.BarCode segítségével
url: /hu/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre PDF417 vonalkódot C#-ban az Aspose.BarCode segítségével

Ha gyorsan és megbízhatóan szeretne **PDF417 vonalkódot C#-ban** létrehozni, ez az útmutató végigvezeti a teljes folyamaton az Aspose.BarCode használatával. Meg fogja látni az összes szükséges beállítást, az alapméretektől a Macro PDF417 metaadatmezők teljes készletéig, és egy PNG képpel fejeződik be, amely készen áll a további feldolgozásra.

## Gyors válaszok
- **Melyik könyvtár generál PDF417 vonalkódokat?** Aspose.BarCode for .NET.
- **Milyen formátumot ad a példa?** Egy veszteségmentes PNG kép.
- **Szükségem van licencre?** Egy ingyenes próba működik a példához; a gyártási környezethez kereskedelmi licenc szükséges.
- **Melyik .NET verzió támogatott?** .NET 6.0 vagy újabb.
- **Hozzáadhatok metaadatokat a vonalkódhoz?** Igen – a Macro PDF417 támogatja a fájlazonosítót, szegmens számot, időbélyegeket és egyebeket.

## Mi az a PDF417 vonalkód?
A PDF417 vonalkód egy egymásra helyezett lineáris szimbólum, amely egy szimbólumon körülbelül 1 KB adatot képes kódolni, és opcionális makró metaadatokat támogat több szegmensből álló fájlokhoz. Több sorból álló egymásra helyezett lineáris mintákból áll, ami nagy adatkapacitást biztosít, miközben a szabványos 2‑D szkennerek által olvasható marad. A formátum tartalmaz hibajavítási szinteket a megbízhatóság növelésére, és az opcionális makró funkció lehetővé teszi nagy fájlok felosztását több vonalkódra, a metaadatok pedig segítik azok újraösszeállítását.

## Miért használjuk az Aspose.BarCode-ot PDF417-hez?
Az Aspose.BarCode **több mint 50 vonalkód szimbólumot** támogat, és képes Macro PDF417 vonalkódokat generálni akár **2 000 oszlop**-ig, így 10 MB-nál nagyobb fájlokat is kezel anélkül, hogy a teljes adatot memóriába töltené. Ez a kvantifikált képesség biztosítja, hogy a nagy áteresztőképességű vállalati forgatókönyvek zökkenőmentesen működjenek, és kiterjedt testreszabási lehetőségeket kínál.

## Előkövetelmények

- .NET 6.0 (vagy újabb) telepítve  
- Visual Studio 2022 vagy bármely C#-kompatibilis IDE  
- Érvényes licenc a **Aspose.BarCode for .NET**-hez (az ingyenes próba működik ehhez a példához)  

Adja hozzá az Aspose.BarCode NuGet csomagot a projektjéhez:

```bash
dotnet add package Aspose.BarCode
```

## Hogyan hozzunk létre PDF417 vonalkódot C#-ban?

`BarcodeGenerator` a fő osztály a vonalkód képek létrehozásához.  
`EncodeTypes.MacroPdf417` a Macro PDF417 szimbólumot választja a vonalkód generálásához.  
`Save` a generált vonalkódot egy képfájlba írja.

Töltse be a `BarcodeGenerator`-t a `EncodeTypes.MacroPdf417` enummal és a cél szöveggel, majd hívja meg a `Save`-et – ez a teljes létrehozási folyamat három sorban. A generátor automatikusan kezeli a Unicode-ot, és a `using` utasítás garantálja, hogy a nem kezelt erőforrások felszabadulnak a kép mentése után.

### 1. lépés: a barcode generator C# példány létrehozása

A `BarcodeGenerator` osztály vonalkód képeket hoz létre és konfigurál.  

Példányosítsa a `BarcodeGenerator`-t a `EncodeTypes.MacroPdf417` enum értékével és a kódolni kívánt szöveggel. A szöveg tartalmazhat Unicode karaktereket, amelyeket a könyvtár automatikusan kezel.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Miért fontos*: `EncodeTypes.MacroPdf417` azt mondja a motornak, hogy Macro PDF417 szimbólumot állítson elő, amely támogatja a szegmentált adatot és további fájlszintű metaadatokat. A `using` utasítás garantálja, hogy a nem kezelt erőforrások felszabadulnak a kép mentése után.

### 2. lépés: az alapvető vonalkód megjelenés meghatározása

`XDimension.Pixels` állítja be a vonalkód moduljának méretét pixelben.

A Macro PDF417 vonalkód négyzetes modulokból áll. A modulméret és az oszlopszám szabályozása befolyásolja az olvashatóságot és a fájlméretet.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Miért fontos*: `XDimension.Pixels` meghatározza a vizuális sűrűséget; a 2 pixel érték jól működik a képernyőn való megjelenítéshez, miközben a képet kicsi tartja. Állítsa be az oszlopszámot a layout korlátaihoz – több oszlop szélesebb, rövidebb vonalkódot eredményez.

### 3. lépés: Macro PDF417 specifikus metaadatok beállítása

`MacroPdf417FileID` azonosítja azt a fájlt, amelyhez az összes vonalkód szegmens tartozik.

A Macro PDF417 kibővíti a standard PDF417 formátumot olyan mezőkkel, amelyek lehetővé teszik nagy fájlok több vonalkódszegmensből történő rekonstruálását. Minden mező opcionális, de beállításuk bemutatja az API teljes képességeit.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Miért fontos*:  
- `MacroPdf417FileID` összekapcsolja az összes szegmenst, amelyek ugyanahhoz a logikai fájlhoz tartoznak.  
- `MacroPdf417SegmentID` és `MacroPdf417SegmentsCount` lehetővé teszi a dekóder számára, hogy a fragmentumokat helyesen újrarendezze.  
- `MacroPdf417Checksum` gyors integritás-ellenőrzést biztosít a teljes payload dekódolása nélkül.  
- `MacroPdf417FileSize` és `MacroPdf417TimeStamp` lehetővé teszi a downstream rendszereknek, hogy ellenőrizzék, a rekonstruált fájl megegyezik-e az eredetivel.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` hasznosak logisztikai vagy dokumentumcsere-szcenáriókban.  
- A `MacroPdf417Terminator` `Set` értékre állítása jelzi, hogy ez a vonalkód az utolsó szegmens, ami egyszerűsíti a rekonstruálási algoritmust.

### 4. lépés: a generált vonalkód kép mentése

`Save` a vonalkód képet a megadott fájlútra írja.

Végül írja a vonalkódot egy PNG fájlba. Bármely támogatott formátumot választhat (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Miért fontos*: A PNG megőrzi a veszteségmentes pixel adatokat, biztosítva, hogy a szkennerek a pontosan beállított modulmintát olvassák. A formátum megváltoztatása befolyásolhatja a vizuális minőséget és a fájlméretet.

#### Várható kimenet

A teljes program futtatása létrehozza a **ExtPDF417Meta.png** nevű fájlt. A kép megnyitása egy téglalap alakú Macro PDF417 vonalkódot mutat, amely a “Åspóse.Barcóde©” szöveget kódolja, és a vizuális sűrűség megegyezik a beállított 2‑pixel X dimenzióval. A képet PDF417‑kompatibilis olvasóval beolvasva visszakapja a 3. lépésben definiált összes metaadatmezőt.

## Teljes működő példa

Másolja az alábbi kódot egy új konzolprojektbe (`dotnet new console`), és cserélje le a `YOUR_DIRECTORY`-t egy abszolút vagy relatív útvonalra, amely létezik a gépén.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Futtassa a programot (`dotnet run`). A végrehajtás után ellenőrizze, hogy a PNG fájl megjelenik-e a megadott helyen. Használjon bármilyen vonalkód‑olvasó alkalmazást, amely támogatja a Macro PDF417-et, hogy megerősítse, a metaadatok helyesen be vannak ágyazva.

## Gyakori variációk és szélsőséges esetek

- **Különböző képformátumok**: Cserélje a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp` vagy `Tiff`-re, ha a downstream rendszer más formátumot preferál.  
- **Modulméret módosítása**: A nagyobb `XDimension.Pixels` értékek javítják a szkennelés megbízhatóságát alacsony felbontású szkennereknél, de növelik a kép méretét.  
- **Több szegmens**: Több szegmensből álló fájl előállításához generáljon sorozatot vonalkódokból, növelje minden egyesnél a `MacroPdf417SegmentID`-t, és tartsa állandóan a `MacroPdf417FileID`-t. Csak az utolsó szegmensnek kell beállítania a `MacroPdf417Terminator`-t.  
- **Unicode támogatás**: A generátor automatikusan kódolja a Unicode karaktereket; győződjön meg róla, hogy a forrás karakterlánc UTF‑8 kódolást használ, ha külső fájlból olvassa.  
- **Hibakezelés**: Tegye a `using` blokkot try‑catch-be, hogy elkapja a `BarCodeException`-t érvénytelen paraméterek (pl. oszlopszám a tartományon kívül) esetén.

## Pro tippek

- **Teljesítmény**: Használjon egyetlen `BarcodeGenerator` példányt sok vonalkód létrehozásához ugyanazzal a beállítással; csak a `CodeText` tulajdonságot változtassa a mentések között.  
- **Fájlméret becslés**: A `MacroPdf417FileSize` mezőnek meg kell egyeznie az eredeti payload bájt számával; a eltérések downstream validációs hibákat okozhatnak.  
- **Tesztelés**: Ellenőrizze a generált vonalkódokat az Aspose beépített dekóderével (`BarCodeReader`) és egy harmadik fél szkennerrel, hogy biztosítsa az interoperabilitást.

## Következtetés

Ez a **Aspose.BarCode** példa megmutatja, hogyan **hozzunk létre PDF417 vonalkódot C#-ban** teljes Macro metaadat támogatással, ami szilárd alapot nyújt a robusztus vonalkód‑alapú adatcsere csővezetékek felépítéséhez.

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes működő kódpéldákat lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan hozzunk létre vonalkódot – Compact PDF417 az Aspose.BarCode segítségével](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan hozzunk létre csendes zónát a Code 16K-hoz az Aspose.BarCode for .NET használatával](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hogyan hozzunk létre vonalkód csendes zónát az ITF-14-hez az Aspose.BarCode for .NET használatával](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---


**Last Updated:** 2026-10-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan generáljunk Pdf417 vonalkód képet C#-ban az Aspose segítségével](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hogyan hozzunk létre vonalkódot – Compact PDF417 az Aspose.BarCode segítségével](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Vonalkód Generátor Oktatóanyag – Hogyan generáljunk Pdf417 vonalkódot](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}