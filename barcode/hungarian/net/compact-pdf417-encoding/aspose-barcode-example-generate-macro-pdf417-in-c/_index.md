---
category: general
date: 2026-08-09
description: Aspose vonalkód példa, amely bemutatja, hogyan használjuk a C# vonalkódgenerátort
  Macro PDF417 teljes metaadat‑támogatással történő létrehozásához.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: hu
lastmod: 2026-08-09
og_description: Az Aspose vonalkód példa bemutatja, hogyan használható egy C#-os vonalkód-generátor
  a Macro PDF417 vonalkód előállításához, amely tartalmazza a fájlazonosítót, a szegmensadatokat,
  az időbélyeget és egyéb metaadatokat.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose vonalkód példa – Macro PDF417 létrehozása C#‑ban
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Aspose vonalkód példa: Macro PDF417 generálása C#‑ban'
url: /hu/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose vonalkód példa: Macro PDF417 generálása C#-ban

Ha **aspose barcode példára** van szükséged, amely Macro PDF417 vonalkódot hoz létre, ez az útmutató megmutatja, hogyan teheted ezt **barcode generator C#** segítségével. Meg fogod látni az összes szükséges beállítást, az alapméretektől a Macro PDF417 metaadatmezők teljes készletéig, és egy PNG képet kapsz, amely készen áll a további feldolgozásra.

Az oktatóanyag lefedi a teljes munkafolyamatot, elmagyarázza, miért fontos minden paraméter, és egy azonnal futtatható kódmintát biztosít. Külső hivatkozásokra nincs szükség; a kódot másolhatod, módosíthatod az értékeket, és azonnal futtathatod.

## Előfeltételek

- .NET 6.0 (vagy újabb) telepítve  
- Visual Studio 2022 vagy bármely C#‑kompatibilis IDE  
- Érvényes licenc a **Aspose.BarCode for .NET**-hez (az ingyenes próba verzió is működik ebben a példában)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## 1. lépés: A barcode generator C# példány létrehozása

Az első lépés a `BarcodeGenerator` példányosítása a `EncodeTypes.MacroPdf417` enum értékkel és a kódolni kívánt szöveggel. A szöveg tartalmazhat Unicode karaktereket, amelyeket a könyvtár automatikusan kezel.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Miért fontos*: `EncodeTypes.MacroPdf417` azt mondja a motornak, hogy Macro PDF417 szimbólumot állítson elő, amely támogatja a szegmentált adatokat és a további fájlszintű metaadatokat. A `using` utasítás garantálja, hogy a nem kezelt erőforrások felszabadulnak a kép mentése után.

## 2. lépés: Alapvető vonalkód megjelenés meghatározása

A Macro PDF417 vonalkód négyzetes modulokból áll. A modulméret és az oszlopszám szabályozása befolyásolja az olvashatóságot és a fájlméretet.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Miért fontos*: `XDimension.Pixels` meghatározza a vizuális sűrűséget; a 2 pixel érték jól működik a képernyőn való megjelenítéshez, miközben a képet kicsi tartja. Állítsd be az oszlopszámot a layout korlátaidhoz – több oszlop szélesebb, rövidebb vonalkódot eredményez.

## 3. lépés: Macro PDF417 specifikus metaadatok beállítása

A Macro PDF417 kibővíti a standard PDF417 formátumot olyan mezőkkel, amelyek lehetővé teszik nagy fájlok rekonstrukcióját több vonalkódszegmensből. Minden mező opcionális, de azok beállítása bemutatja az API teljes képességeit.

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
- `MacroPdf417FileID` összekapcsolja az összes szegmenst, amely ugyanahhoz a logikai fájlhoz tartozik.  
- `MacroPdf417SegmentID` és `MacroPdf417SegmentsCount` lehetővé teszi a dekóder számára, hogy a töredékeket helyesen újrarendezze.  
- `MacroPdf417Checksum` gyors integritás-ellenőrzést biztosít a teljes payload dekódolása nélkül.  
- `MacroPdf417FileSize` és `MacroPdf417TimeStamp` lehetővé teszik a downstream rendszerek számára, hogy ellenőrizzék, a rekonstruált fájl megegyezik-e az eredetivel.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` hasznosak logisztikai vagy dokumentumcsere helyzetekben.  
- A `MacroPdf417Terminator` `Set` értékre állítása jelzi, hogy ez a vonalkód az utolsó szegmens, ami egyszerűsíti a rekonstrukciós algoritmust.

## 4. lépés: A generált vonalkód kép mentése

Végül írd a vonalkódot egy PNG fájlba. Bármely támogatott formátumot választhatod (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Miért fontos*: A PNG veszteségmentes pixel adatokat őriz, biztosítva, hogy a szkennerek pontosan a beállított modulmintát olvassák. A formátum megváltoztatása befolyásolhatja a vizuális minőséget és a fájlméretet.

### Várható kimenet

A teljes program futtatása létrehoz egy **ExtPDF417Meta.png** nevű fájlt. A kép megnyitása egy téglalap alakú Macro PDF417 vonalkódot mutat, amely a “Åspóse.Barcóde©” szöveget kódolja, és a vizuális sűrűség megegyezik a beállított 2‑pixel X dimenzióval. A képet PDF417‑kompatibilis olvasóval beolvasva visszakapja a 3. lépésben definiált összes metaadatmezőt.

## Teljes működő példa

Másold az alábbi kódot egy új konzolos projektbe (`dotnet new console`), és cseréld le a `YOUR_DIRECTORY`-t egy abszolút vagy relatív útvonalra, amely a gépeden létezik.

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

Futtasd a programot (`dotnet run`). A végrehajtás után ellenőrizd, hogy a PNG fájl megjelenik-e a megadott helyen. Használj bármilyen vonalkód‑olvasó alkalmazást, amely támogatja a Macro PDF417-et, hogy megerősítsd, a metaadatok helyesen be vannak ágyazva.

## Gyakori változatok és szélsőséges esetek

- **Különböző képformátumok**: Cseréld le a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp` vagy `Tiff`-re, ha a downstream rendszer más formátumot részesít előnyben.  
- **Modulméret módosítása**: Nagyobb `XDimension.Pixels` értékek javítják a beolvasás megbízhatóságát alacsony felbontású szkennereknél, de növelik a kép méretét.  
- **Több szegmens**: Több szegmensből álló fájl előállításához generálj egy sor vonalkódot, minden egyeshez növeld a `MacroPdf417SegmentID`-t, és tartsd állandóan a `MacroPdf417FileID`-t. Csak az utolsó szegmensnek kell beállítania a `MacroPdf417Terminator`-t.  
- **Unicode támogatás**: A generátor automatikusan kódolja a Unicode karaktereket; győződj meg róla, hogy a forráskarakterlánc UTF‑8 kódolást használ, ha külső fájlból olvasod.  
- **Hibakezelés**: Tedd a `using` blokkot try‑catch-be, hogy elkapd a `BarCodeException`-t érvénytelen paraméterek esetén (pl. az oszlopszám tartományon kívül).

## Pro tippek

- **Teljesítmény**: Használj egyetlen `BarcodeGenerator` példányt sok vonalkód létrehozásához ugyanazzal a beállítással; csak a `CodeText` tulajdonságot változtasd a mentések között.  
- **Fájlméret becslés**: A `MacroPdf417FileSize` mezőnek meg kell egyeznie az eredeti payload bájt számával; a eltérések downstream validációs hibákat okozhatnak.  
- **Tesztelés**: Validáld a generált vonalkódokat az Aspose beépített dekóderével (`BarCodeReader`) és egy harmadik fél szkennerrel is, hogy biztosítsd az interoperabilitást.

## Összegzés

Ez az **aspose barcode példa**

## Mit kellene legközelebb megtanulnod?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljesen működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre vonalkódot – Compact PDF417 Aspose.BarCode használatával](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan hozzunk létre vonalkód csendes zónát a Code 16K-hoz az Aspose.BarCode for .NET használatával](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hogyan hozzunk létre vonalkód csendes zónát ITF-14-hez az Aspose.BarCode for .NET használatával](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}