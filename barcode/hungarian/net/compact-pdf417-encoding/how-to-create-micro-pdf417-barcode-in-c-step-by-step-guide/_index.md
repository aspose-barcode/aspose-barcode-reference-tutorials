---
category: general
date: 2026-08-22
description: Tanulja meg, hogyan hozhat létre micro PDF417 vonalkódot C#-ban, és generálhat
  egy vonalkód PNG képet. Tartalmazza a vonalkód méreteinek beállítását és a fájl
  mentését.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: hu
lastmod: 2026-08-22
og_description: Készíts micro PDF417 vonalkódot C#-ban, és exportáld PNG formátumban.
  Kövesd ezt az útmutatót a vonalkód méreteinek beállításához és a vonalkód kép gyors
  generálásához.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Micro PDF417 vonalkód létrehozása C#‑ban – teljes kódolási útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Hogyan készítsünk micro PDF417 vonalkódot C#‑ban – lépésről‑lépésre útmutató
url: /hu/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre micro PDF417 vonalkódot C#‑ban – lépésről‑lépésre útmutató

Ha **micro PDF417 vonalkódot** kell létrehoznod egy jegyrendszerhez, készletcímkéhez vagy mobilos beolvasáshoz, ez az útmutató pontosan megmutatja, hogyan. Megtekintheted a teljes C# programot, amely vonalkód PNG‑t generál, megtanulod beállítani a vonalkód méreteit, és megérted az egyes konfigurációs beállításokat.

A útmutató végére képes leszel magas felbontású vonalkód képet generálni, testre szabni az X‑dimenziót, kiválasztani az oszlopszámot, és PNG fájlként menteni az eredményt – mindezt néhány kódsorral.

## Amire szükséged lesz

- .NET 6.0 SDK vagy újabb (a kód működik .NET Core‑ral és .NET Framework‑kel)
- Visual Studio 2022 vagy bármely C#‑kompatibilis IDE
- A **Aspose.BarCode for .NET** NuGet csomag (vagy bármely könyvtár, amely támogatja a `EncodeTypes.MicroPdf417`‑t)
- Alapvető ismeretek a C# szintaxisról

> **Pro tipp:** Az Aspose.BarCode ingyenes közösségi kiadása elegendő fejlesztéshez és teszteléshez. Gyártásra licencet kell beszerezni a kiértékelési vízjelek eltávolításához.

## 1. lépés: A vonalkód könyvtár telepítése

Nyiss egy terminált a projekt mappádban, és futtasd:

```bash
dotnet add package Aspose.BarCode
```

Ez hozzáadja az `Aspose.BarCode` assembly‑t, amely biztosítja a `BarcodeGenerator` osztályt, amelyet **create barcode image C#** alkalmazások létrehozásához használnak.

## 2. lépés: A generátor inicializálása – micro PDF417 vonalkód létrehozása

Az első végrehajtható sor egy `BarcodeGenerator` példányt hoz létre, amely a Micro PDF417 szimbólumra van beállítva, és megadja a kódolni kívánt adatot.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Miért fontos*: Az `EncodeTypes.MicroPdf417` enum azt mondja a könyvtárnak, hogy a PDF417 kompakt változatát használja, ami ideális kis címkékhez és mobil képernyőkhöz.

## 3. lépés: Hogyan állítsuk be a vonalkód méreteit C#‑ban

A modul szélességének (X‑dimenzió) finomhangolása szabályozza a vonalkód vizuális sűrűségét. A kisebb érték élesebb képet eredményez, míg a nagyobb érték könnyebbé teszi a vonalkód távolabbról történő beolvasását.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Miért kell beállítani a méreteket**: Az X‑dimenzió beállítása nélkül az alapértelmezett érték elmosódott vonalkódot eredményezhet magas DPI‑nél. 2 pixelre állítása jó egyensúlyt biztosít a legtöbb képernyőalapú beolvasáshoz.

## 4. lépés: Oszlopszám kiválasztása – a vonalkód szélességének szabályozása

A Micro PDF417 1 és 4 oszlop között engedélyezett. Több oszlop vízszintesen tömöríti az adatot, csökkentve a kép teljes szélességét.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Szélsőséges eset*: Ha 5 oszlopot kérsz, a könyvtár `ArgumentOutOfRangeException`‑t dob. Mindig tartsd be a dokumentált tartományt.

## 5. lépés: Hogyan generáljunk barcode PNG‑t – a kép mentése

Most exportálhatod a generált vonalkódot PNG fájlba. A PNG veszteségmentes minőséget őriz meg, ami elengedhetetlen a megbízható beolvasáshoz.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

A program futtatásakor egy konzolüzenetet látsz, amely megerősíti a fájl helyét. A kapott `MicroPdf417.png` így néz ki:

![Képernyőkép, amely egy C#‑ban létrehozott micro PDF417 vonalkódot mutat](micro-pdf417-example.png "Létrehozott micro PDF417 vonalkód")

*Kép alternatív szöveg*: **micro PDF417 barcode generated in C#** – bemutatja a végső kimenetet a méretek és oszlopszámok alkalmazása után.

## 6. lépés: Futtatás és a kimenet ellenőrzése

1. A projekt felépítése: `dotnet build`.
2. Futtatás: `dotnet run`.
3. Nyisd meg a `MicroPdf417.png` fájlt az asztalodon, és olvasd be egy mobil vonalkódolvasó alkalmazással.

A **“Sample text”** szöveget kell látnod dekódolva. Ha a szkenner hibát jelez, ellenőrizd újra az X‑dimenziót és az oszlopszámot – extrém értékek túl sűrűvé tehetik a vonalkódot egyes eszközök számára.

## Gyakori variációk és hibaelhárítás

| Situation | Adjustment |
|-----------|------------|
| **Nagyobb vonalkódra van szükség alacsony felbontású nyomtatókhoz** | Increase `XDimension.Pixels` to 3 or 4. |
| **Magasabb vonalkód kívánt szélesség változtatása nélkül** | Set `generator.Parameters.Barcode.Pdf417.Rows` (rows range 3‑90). |
| **Több vonalkód generálása egy ciklusban** | Re‑use the same `BarcodeGenerator` instance and only change `CodeText` before each `Save`. |
| **Mentés JPEG‑ként PNG helyett** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. |
| **Futtatás .NET Framework 4.7‑en** | The same code works; just reference the appropriate `Aspose.BarCode.dll`. |

## Teljes forráskód (futtatható)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Várt kimenet** – egy 200 × 100‑pixel méretű PNG fájl, amely egy éles Micro PDF417 vonalkódot tartalmaz, és a “Sample text” szöveget dekódolja.

## Következtetés

Most már tudod, hogyan **hozz létre micro PDF417 vonalkódot** C#‑ban, **állítsd be a vonalkód méreteit**, és **generálj barcode PNG** képet. A teljes példa bemutatja az összes szükséges lépést – a könyvtár telepítésétől a végső fájl mentéséig –, így közvetlenül beágyazhatod a vonalkód generálást saját alkalmazásaidba.

Ezután fedezd fel a kapcsolódó témákat, például **QR kódok létrehozása az Aspose.BarCode‑dal**, **színek testreszabása**, vagy **vonalkódok beágyazása PDF dokumentumokba**. Mindegyik a itt bemutatott `BarcodeGenerator` alapokra épül.

Nyugodtan kísérletezz különböző adatkarakterláncokkal, oszlopszámokkal és X‑dimenzió értékekkel, hogy a saját beolvasási környezetedhez igazodjanak. Jó kódolást!

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódpéldákat lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre vonalkódot – Compact PDF417 az Aspose.BarCode‑dal](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan generáljunk PDF417 vonalkódot – Compact PDF417 kódolás](/barcode/english/net/compact-pdf417-encoding/)
- [Hogyan hozzunk létre Aztec vonalkódot az Aspose.BarCode for .NET‑tel](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}