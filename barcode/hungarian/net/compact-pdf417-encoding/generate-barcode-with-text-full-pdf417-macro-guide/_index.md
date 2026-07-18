---
category: general
date: 2026-07-18
description: Készítsen vonalkódot szöveggel az Aspose.BarCode for .NET segítségével.
  Ismerje meg, hogyan generálhat PDF417 vonalkódokat, állíthat be makróbeállításokat,
  és exportálhat PNG képeket.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: hu
lastmod: 2026-07-18
og_description: Generáljon vonalkódot szöveggel C#‑ban gyorsan. Ez a lépésről‑lépésre
  útmutató bemutatja, hogyan lehet PDF417 vonalkódokat generálni, makróbeállításokat
  konfigurálni, és PNG‑ként menteni.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Vonalkód generálása szöveggel – PDF417 makrók mesteri létrehozása
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Vonalkód generálása szöveggel – Teljes PDF417 makró útmutató
url: /hu/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód generálása szöveggel – Teljes PDF417 Macro útmutató

Valaha is elgondolkodtál **hogyan generálj PDF417** vonalkódot, amely egyedi szöveget is beágyaz? Ebben az útmutatóban pontosan megmutatjuk, hogyan **generálj vonalkódot szöveggel** az Aspose.BarCode for .NET segítségével, és végigvezetünk minden beállításon, amelyre egy Macro PDF417 szimbólumhoz szükséged van. Nincs felesleges részlet, csak egy teljes, futtatható példa, amelyet még ma beilleszthetsz a projektedbe.

A következőket fogjuk lefedni:

* A szükséges NuGet csomag és a using direktívák.
* Hogyan hozzunk létre egy vonalkód-generátort, amely Unicode karaktereket tartalmaz.
* A modulméret, oszlopszám és macro‑specifikus azonosítók beállítása.
* Az eredmény PNG fájlként való mentése és a kimenet ellenőrzése.

A végére egy kész‑használatra készen álló PNG képet kapsz egy Macro PDF417 vonalkódról, amelyet beágyazhatsz számlákba, jegyekbe vagy bármilyen dokumentumba, amelynek géppel olvasható szegmensre van szüksége.

---

## Előkövetelmények

Mielőtt belemerülnénk, győződj meg róla, hogy rendelkezel a következőkkel:

| Requirement | Reason |
|-------------|--------|
| **.NET 6.0** or later | Az Aspose.BarCode támogatja a .NET Standard 2.0+ verziókat, így a .NET 6 a legújabb futtatókörnyezetet biztosítja. |
| **Visual Studio 2022** (or any C# IDE) | Könnyű szerkesztéshez és hibakereséshez. |
| **Aspose.BarCode for .NET** NuGet package | Az a könyvtár, amely ténylegesen létrehozza a vonalkódot. Telepítsd a `dotnet add package Aspose.BarCode` paranccsal. |
| **Write permission** to the output folder | A `Save` metódusnak írási jogosultságra van szüksége a PNG fájl létrehozásához. |

Ha bármelyik ismeretlennek tűnik, állj meg és szerezd be őket – különben a kód nyilvánvaló kivételeket fog dobni.

## 1. lépés – A könyvtár telepítése és importálása

Először add hozzá a NuGet csomagot a projektedhez:

```bash
dotnet add package Aspose.BarCode
```

Ezután hozd be a szükséges névtereket a láthatóságba:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Pro tipp:** Ha Visual Studio-t használsz, jobb‑klikk a projektre → *Manage NuGet Packages* → keresd meg az *Aspose.BarCode* csomagot és telepítsd a legújabb stabil verziót.

## 2. lépés – Vonalkód-generátor létrehozása egyedi szöveggel

Az *elsődleges* feladat **vonalkód generálása szöveggel**, amely speciális karaktereket, például “Å” és “©” tartalmaz. A konstruktor az enkódolás típusát és a nyers adatstringet veszi át:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Miért fontos: a `EncodeTypes.MacroPdf417` azt jelzi az Aspose-nak, hogy a macro verziót szeretnénk, amely lehetővé teszi egy nagy üzenet több szimbólumra bontását. A szövegstring lehet bármilyen UTF‑8 sorozat; az Aspose belsőleg kezeli a konverziót.

## 3. lépés – Az alap megjelenés beállítása (modulméret)

A vonalkód “modulja” a legkisebb fekete‑vagy‑fehér négyzet. A pixelméretének beállítása szabályozza a teljes kép méretét anélkül, hogy az adat sűrűségét változtatná:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ha nagyobb képre van szükséged nyomtatáshoz, növeld ezt az értéket 4‑re vagy 6‑ra. Csak ne feledd, hogy a nagyobb modulok növelik a végső PNG méretét.

## 4. lépés – Macro PDF417 specifikus beállítások konfigurálása

Macro PDF417 két azonosítót ad hozzá, amelyek lehetővé teszik a szkenner számára, hogy több szimbólumot egyesítsen. Általában ezeket állítod be:

| Property | What it does |
|----------|--------------|
| `Columns` | Az egy szimbólumra jutó adat oszlopok száma (a szélességet befolyásolja). |
| `MacroPdf417FileID` | Az egész macro fájl egyedi azonosítója (≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Az aktuális szegmens indexe (0‑254). |

Itt a kód:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Észrevétel szél esetben:** A `MacroPdf417FileID`-nek minden szegmensnél ugyanolyannak kell lennie ugyanabban a logikai fájlban. Ha több szegmenst generálsz, használd újra ugyanazt az azonosítót, különben olyan nem kapcsolódó szimbólumok jönnek létre, amelyeket nem lehet összefűzni.

## 5. lépés – Vonalkód mentése PNG képként

Miután minden be van állítva, írd a képet a lemezre:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

A `Save` metódus automatikusan létrehozza a PNG-t, kezelve a DPI-t és a színmélységet. A futtatás után nyisd meg a fájlt, hogy valami ilyesmit láss:

![Generate barcode with text example](/images/barcode-example.png){.center alt="Generate barcode with text example"}

Ha nem látsz vonalkódot, ellenőrizd, hogy a mappa létezik-e, és hogy az alkalmazásodnak van‑e írási joga.

## Teljes, futtatható példa

Másold az alábbi teljes kódrészletet egy új konzolos alkalmazásba (`dotnet new console`), és futtasd. A PNG a `C:\Barcodes` mappába kerül (előbb hozd létre a mappát).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Várható kimenet** (konzol):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

És a PNG egy kompakt Macro PDF417 szimbólumot jelenít meg, amely a “Åspóse.Barcóde©” szöveget tartalmazza.

## Gyakori kérdések és buktatók

| Question | Answer |
|----------|--------|
| *Can I use a different image format?* | Természetesen—cseréld le a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp` vagy `Gif`-re. A PNG veszteségmentes, ezért alapértelmezett. |
| *What if I need more than one segment?* | Hozz létre egy új `BarcodeGenerator`-t minden szegmenshez, tartsd azonosnak a `MacroPdf417FileID`-t, és növeld a `MacroPdf417SegmentID`-t (0‑254). |
| *My text contains emojis—will they work?* | Az Aspose.BarCode támogatja az UTF‑8-at, így a legtöbb emoji rendben van. Csak győződj meg róla, hogy a cél szkenner képes dekódolni őket; sok ipari szkenner csak alfanumerikus adatot kezel. |
| *The barcode is too wide for my label.* | Csökkentsd a `Columns` értékét vagy növeld a modulméretet. Kevesebb oszlop szűkebb szimbólumot eredményez, de lehet, hogy nagyobb DPI‑ű nyomtatóra lesz szükség. |
| *Do I need a license?* | Az ingyenes értékelő licenc teszteléshez működik, de egy kis vízjelet ad hozzá. Gyártásra vásárolj licencet a vízjel eltávolításához és a teljes funkciók eléréséhez. |

## Következő lépések

Most, hogy tudod, **hogyan generálj PDF417** vonalkódot egyedi szöveggel, lehet, hogy szeretnéd:

* **Dekódold** a vonalkódot egy mobilalkalmazásban az Aspose.BarCode `BarCodeReader`-ével.  
* **Kombináld** a több macro szegmenst egyetlen PDF dokumentumba kötegelt nyomtatáshoz.  
* **Fedezd fel** a többi szimbólumot (QR, DataMatrix) hasonló paramétermintákkal.  
* **Állítsd be** a hibajavítási szintet a `Pdf417.ErrorCorrectionLevel` segítségével a nehezebb környezetekhez.  

Minden ilyen téma az általad most tanult alapvető koncepciókra épül, így a átmenet zökkenőmentes lesz.

## Következtetés

Végigvezettünk egy teljes, vég‑végi megoldáson, amely lehetővé teszi, hogy **vonalkódot generálj szöveggel**, és konkrétan, **hogyan generálj PDF417** macro szimbólumokat az Aspose.BarCode for .NET használatával. Az X‑dimenzió, oszlopszám és macro azonosítók beállításával teljes irányítást kapsz a méret, elrendezés és több‑szegmens kezelés felett. Az eredményül kapott PNG nyomtatható, PDF‑be ágyazható, vagy küldhető egy szkennernek további konverzió nélkül.

Próbáld ki, finomítsd a paramétereket, és hagyd, hogy a vonalkód a te üzleti esetedben működjön. Ha elakadnál, az Aspose dokumentáció és a közösségi fórumok kiváló további források. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódpéldákat lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk PDF417 vonalkódot – Kompakt PDF417 kódolás](/barcode/english/net/compact-pdf417-encoding/)
- [Hogyan generáljunk DataMatrix vonalkódot az Aspose.BarCode for .NET segítségével](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Hogyan generáljunk vonalkódot – Egydimenziós vonalkód típusok](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}