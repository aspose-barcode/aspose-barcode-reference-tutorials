---
category: general
date: 2026-11-14
description: C#-os vonalkódgenerátor oktatóanyag, amely bemutatja, hogyan lehet DataBar
  Omnidirectional vonalkódokat létrehozni, beállítani az X‑dimenziót, és pixelben
  módosítani a vonalmagasságot.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: hu
lastmod: 2026-11-14
og_description: A C# vonalkód-generátor oktatóanyag lépésről lépésre bemutatja, hogyan
  generáljunk DataBar Omnidirectional vonalkódot, hogyan definiáljuk az X-dimenziót
  pixelekben, és hogyan változtassuk meg a vonalmagasságot PNG kimenethez.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Vonalkód-generátor C# oktatóanyag – DataBar vonalkódok létrehozása
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Vonalkód generátor C# oktatóanyag: DataBar omnidirekcionális'
url: /hu/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generátor C# oktató – DataBar Omnidirectional vonalkódok létrehozása

Ha **barcode generator C# tutorial**-t keresel, a megfelelő helyen jársz. Ez az útmutató végigvezet a DataBar Omnidirectional vonalkód létrehozásán, a XDimension pixelben történő beállításán, valamint a vonalmagasság módosításán PNG képek előállításához.

Megmutatunk egy teljes, futtatható példát, amely mindent lefed az generátor inicializálásától a különböző vonalmagasságú képek mentéséig. Nem szükséges külső dokumentáció – másold be a kódot, futtasd, és már két használatra kész vonalkód fájlod lesz.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy:

* .NET 6.0 vagy újabb telepítve van  
* Van hivatkozás a vonalkód könyvtárra, amely biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` osztályokat (például Aspose.BarCode for .NET)  
* Alapvető ismeretekkel rendelkezel a C# szintaxisról és a Visual Studio‑ról vagy a kedvenc IDE‑dről  

> **Pro tipp:** Ha az Aspose.BarCode‑ot használod, add hozzá a `Aspose.BarCode` NuGet csomagot a projektedhez.

## Barcode generator C# tutorial – 1. lépés: a generátor létrehozása

Az első lépés egy `BarcodeGenerator` példányosítása a `DatabarOmniDirectional` kódolási típussal és a kódolandó adatokkal.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Miért fontos:* Az `EncodeTypes.DatabarOmniDirectional` azt mondja a könyvtárnak, hogy olyan vonalkódot állítson elő, amely bármely irányból olvasható, ami ideális a kiskereskedelmi csomagoláshoz és a logisztikához.

## XDimension pixel beállítása a vonalkódhoz

Az X‑dimenzió határozza meg a legkisebb modul (a „pixel”) szélességét a vonalkódban. Pixelben megadva pontos kontrollt biztosít a vonalkód vizuális sűrűsége felett.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Magyarázat:* A `2` pixel érték olyan vonalkódot eredményez, amely a legtöbb szkenner számára elég éles, miközben a képfájl mérete is alacsony marad.

## Vonalmagasság módosítása és képek mentése

A vonalmagasság határozza meg, hogy milyen magasak a vonalak. Több képet generálhatsz különböző magasságokkal a `BarHeight.Pixels` tulajdonság módosításával és a `Save` újbóli meghívásával.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

A `BarCodeImageFormat.Png` enum érték biztosítja, hogy a kimenet veszteségmentes PNG fájl legyen, ami a vonalkód grafikákhoz ajánlott formátum, mivel megőrzi a pontos méreteket.

## Vonalmagasság változtatása több kép létrehozásához

Gyakran szükség van ugyanarra a vonalkódra különböző méretekben – például egy kis címkéhez és egy nagy poszthoz. Változtasd meg a vonalmagasságot, és használd újra ugyanazt a generátor példányt:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Szélsőséges eset:* Ha a vonalmagasság túl alacsonyra (pl. 10 px alá) van állítva, egyes szkennerek nehezen olvashatják a kódot. Mindig teszteld a generált képeket a célzott szkennerrel.

## Teljes forráskód

Az alábbiakban a teljes program látható, amelyet beilleszthetsz egy új konzolos projektbe. Tartalmazza az összes szükséges `using` direktívát, és bemutatja a vonalmagasság változatosságát.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Futtasd a programot, cseréld le a `YOUR_DIRECTORY`‑t egy érvényes mappára, és két PNG fájlt találsz majd:

* `DatabarBarHeight30Pixels.png` – 30 px magas vonalak  
* `DatabarBarHeight60Pixels.png` – 60 px magas vonalak  

![barcode generátor C# oktató kimenete](images/databar-example.png "Barcode generátor C# oktató – két DataBar kép megjelenítése")

## Gyakori kérdések

| Kérdés | Válasz |
|----------|--------|
| **Megváltoztathatom a képformátumot?** | Igen. Cseréld le a `BarCodeImageFormat.Png`‑t `Jpeg`, `Bmp` vagy `Gif` értékre igény szerint. A PNG a veszteségmentes minőség miatt ajánlott. |
| **Mi a teendő, ha más XDimension‑t szeretnék?** | Állítsd a `generator.Parameters.Barcode.XDimension.Pixels`‑t tetsző egész számra. A nagyobb értékek növelik a vonalkód teljes szélességét. |
| **Alkalmas a DataBar Omnidirectional mobil szkennelésre?** | Igen, feltéve hogy a nyomtatott méret megfelel a szkenner minimális modulméretének (általában 0,33 mm). A pixel‑alapú XDimension segít ezt elérni. |
| **Hogyan ágyazhatom be a vonalkódot PDF‑be?** | A PNG mentése után használj egy PDF könyvtárat (pl. iTextSharp) a kép PDF‑oldalra való beszúrásához. |

## Összegzés

Ez a **barcode generator C# tutorial** megmutatta, hogyan hozhatsz létre DataBar Omnidirectional vonalkódot, állíthatod be az XDimension‑t pixelekben, és generálhatsz PNG fájlokat különböző vonalmagasságokkal. Most már van egy újrahasználható kódrészlet, amelyet bármely C# projektben alkalmazhatsz, ahol vonalkód generálásra van szükség.

### Mi a következő lépés?

* Fedezd fel a többi `EncodeTypes`‑t, például a `Code128` vagy `QR` típusokat, hogy bővítsd a vonalkód repertoárodat.  
* Kombináld a generált PNG‑t egy PDF generáló könyvtárral, hogy nyomtatható számlákat készíts.  
* Kísérletezz a `generator.Parameters.Barcode.Color` beállításával, hogy egyedi színeket adj hozzá, miközben a szkenner specifikációinak megfelelsz.

Nyugodtan módosítsd a példát, próbálj ki további vonalmagasságokat, vagy változtasd meg a kimeneti formátumot. Jó kódolást!

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek az API további funkcióinak elsajátításában és alternatív megvalósítási megközelítések felfedezésében saját projektjeidben.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}