---
category: general
date: 2026-07-27
description: Készítsen többirányú vonalkód képet az Aspose.BarCode használatával.
  Ismerje meg, hogyan generáljon vonalkódot az Aspose-szal, állítsa be a képarányt,
  és mentse PNG fájlokként.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: hu
lastmod: 2026-07-27
og_description: Készítsen mindenirányú vonalkód képet az Aspose segítségével. Kövesse
  ezt az útmutatót a vonalkód generálásához az Aspose-val, állítsa be az arányokat,
  és exportálja PNG formátumban.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Omnidirekcionális vonalkód kép létrehozása az Aspose segítségével – lépésről
  lépésre
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Omnidirekcionális vonalkód kép létrehozása Aspose-szal – Teljes útmutató
url: /hu/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Omnidirekcionális vonalkód kép létrehozása Aspose-szal – Teljes útmutató

Valaha szükséged volt **omnidirekcionális vonalkód kép** létrehozására, de nem tudtad, melyik könyvtárat válaszd? Nem vagy egyedül. Sok logisztikai és kiskereskedelmi projektben a DataBar Stacked Omnidirectional formátum a titkos összetevő a kompakt, nagy sűrűségű kódoláshoz.  

A jó hír? A **Aspose.BarCode** segítségével néhány sor kóddal generálhatod a vonalkódot, finomhangolhatod a képarányt, és közvetlenül lementheted a PNG‑t a lemezre. Az alábbiakban pontosan láthatod, hogyan **generálj vonalkódot Aspose-szal**, miért fontos minden beállítás, és mire kell figyelni a képarány módosításakor.

---

## Mit fed le ez az útmutató

Áttekintjük a teljes életciklust:

1. Kimeneti mappa beállítása.
2. DataBar Stacked Omnidirectional generátor példányosítása.
3. Képpontméretek és képarányok konfigurálása.
4. A vonalkód mentése PNG fájlként.
5. A példa kiterjesztése más formátumokra és speciális esetekre.

A végére egy futtatható C# konzolalkalmazásod lesz, amely két különböző vonalkód képet hoz létre. Nincs szükség külső eszközökre, csak tiszta Aspose kód.

**Előfeltételek**

- .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.7.2‑n is működik).
- Aspose.BarCode for .NET NuGet csomag (`Install-Package Aspose.BarCode`).
- Egy mappa a lemezen, ahová a képek íródhatnak.

Ha már megvannak ezek, vágjunk bele.

---

## 1. lépés: Kimeneti mappa előkészítése

Először is mondd meg a programnak, hová helyezze a PNG fájlokat. Egy keménykódolt útvonal működik a demóhoz, de éles környezetben valószínűleg a konfigurációból olvasnád be.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Miért fontos:* A `Directory.CreateDirectory` idempotens; ha a mappa már létezik, nem dob kivételt, így elkerülheted a try‑catch blokkot.

---

## 2. lépés: DataBar Stacked Omnidirectional generátor létrehozása

Most elindítjuk a generátort a megfelelő kódolási típussal és mintadatokkal. A `"(01)12345678901231"` string a GS1 Alkalmazási Azonosító szintaxisát követi egy 14‑jegyű GTIN‑hez.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Magyarázat:* Az `EncodeTypes.DatabarStackedOmniDirectional` azt mondja az Aspose‑nak, hogy az omnidirekcionális változatot használja, amely bármely irányból olvasható – tökéletes kis címkékhez, amelyek elfordulhatnak.

---

## 3. lépés: Közös vonalkód paraméterek beállítása

Mielőtt bármit renderelnénk, definiáljuk a legkisebb elemméretet (X‑Dimension). A **2 pixel** érték éles képet ad anélkül, hogy a fájlméret felrobbanna.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tippek:* Ha nagyobb felbontásra van szükség nyomtatáshoz, növeld 3‑ra vagy 4‑re. Ne feledd, hogy a nagyobb X‑Dimension arányosan növeli a szélességet és a magasságot is.

---

## 4. lépés: Generálás és mentés 15‑ös képaránnyal

A DataBar család lehetővé teszi a **képarány** beállítását, amely a magasság‑szélesség arányt szabályozza. A **15**‑ös képarány gyakori alapértelmezett az omnidirekcionális vonalkódoknál.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Mit látsz majd:* Viszonylag magas vonalkód, amely még mindig kényelmesen elfér egy 2 × 1 cm-es címkén. A PNG formátum veszteségmentes minőséget biztosít, ami ideális további feldolgozáshoz vagy nyomtatáshoz.

---

## 5. lépés: Képarány módosítása 30‑ra és újra mentés

Szeretnél egy laposabb vonalkódot? Csak állítsd be az `AspectRatio` tulajdonságot, és hívd meg újra a `Save`‑t. Nem kell újra létrehozni a generátort.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Miért használjuk újra ugyanazt a generátort?* Az Aspose objektumok könnyűek; egy tulajdonság módosítása és újra mentés gyorsabb, mint egy új példány építése, és garantálja, hogy a korábbi beállítások (pl. X‑Dimension) változatlanok maradjanak.

---

## Teljes működő példa

Összeállítva, itt a komplett, önálló program, amelyet egyszerűen beilleszthetsz egy új konzolprojektbe.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Várt kimenet**

A program futtatása létrehoz egy `Barcodes` alkönyvtárat, amely a következőket tartalmazza:

- `DatabarAspectRatio15.png` – magasabb, klasszikus megjelenés.
- `DatabarAspectRatio30.png` – laposabb, széles címkékhez alkalmasabb.

Mindkét kép ugyanazt a GTIN adatot jeleníti meg; csak a vizuális arányok különböznek.

---

## A példa kiterjesztése (szélsőséges esetek és variációk)

### 1. Különböző képformátumok

Az Aspose támogatja a BMP, JPEG, TIFF és SVG formátumokat a PNG‑n kívül is. Cseréld ki az enum értékét:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

Az SVG vektor‑alapú, ami azt jelenti, hogy méretezheted anélkül, hogy elveszítenéd a pontosságot – hasznos reszponzív webalkalmazásokhoz.

### 2. Színek testreszabása

Lehet, hogy fehér vonalkódra van szükséged sötét háttéren. Állítsd be a `ForeColor` és `BackColor` értékeket:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Érvénytelen képarányok kezelése

Az Aspose ellenőrzi a tartományt (általában 5‑50). Ha egy tartományon kívüli értéket adsz meg, `ArgumentException` keletkezik. A mentési hívást tedd try‑catch blokkba, hogy barátságos üzenetet kapj:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Kötetes generálás

Ha GTIN‑ek listája áll rendelkezésedre, iterálj rajtuk, frissítsd a `CodeText`‑et, és mentsd el minden fájlt egyedi névvel. A generátor objektum újrahasználható, így alacsony a memóriahasználat.

---

## Gyakori hibák és profi tippek

- **Soha ne felejtsd el beállítani az `XDimension`‑t** mentés előtt; az alapértelmezett (0,33 mm) elmosódott képet eredményezhet alacsony felbontású kijelzőkön.
- **A képarány a magasság‑szélesség arány**, nem fordítva. A nagyobb szám a vonalkódot *magasabban* rövidíti.
- **Fájlutak:** Használd a `Path.Combine`‑t, hogy elkerüld a platform‑specifikus elválasztó problémákat – különösen, ha a kód Linux konténerekben fut.
- **Licencelés:** Az Aspose.BarCode kereskedelmi termék. Próbaverzió esetén vízjel jelenik meg a képen. Regisztrálj licencet időben, hogy elkerüld a meglepetéseket éles környezetben.

---

## Összegzés

Most már tudod, hogyan **hozz létre omnidirekcionális vonalkód képet** az Aspose‑szal, hogyan állítsd be a képarányt, és hogyan exportáld PNG‑ként – mindezt kevesebb, mint 30 sor C#‑ban. Ez az útmutató lépésről‑lépésre bemutatta a folyamatot, elmagyarázta, miért fontos minden beállítás, és bemutatta a kiterjesztéseket, mint a különböző formátumok, színek és kötegelt feldolgozás.

Készen állsz a következő kihívásra? Próbálj meg QR‑kódokat generálni, beágyazni a vonalkódot PDF‑be, vagy integrálni a kimenetet egy ASP.NET Core API‑ba. A **generate barcode with Aspose** elvek minden vonalkódtípusra érvényesek, így újra felhasználhatod a ma tanultakat.

Van kérdésed, vagy szeretnéd megosztani a saját trükkjeidet? Hagyj egy megjegyzést lent – jó kódolást!

## Mit érdemes még tanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek további API‑funkciók elsajátításában és alternatív megvalósítási megközelítések felfedezésében a saját projektjeidben.

- [Hogyan generáljunk Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hogyan hozzunk létre vonalkódot Aspose Java‑val – Képminőség beállítása](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Hogyan generáljunk vonalkód képet Java‑ban az Aspose.BarCode segítségével](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}