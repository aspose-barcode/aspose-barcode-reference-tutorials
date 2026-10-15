---
category: general
date: 2026-10-08
description: Tanulja meg, hogyan méretezheti át a vonalkód képeket egy C# vonalkód-generátor
  példával, a vonalmagasságot 30 px‑ről 60 px‑re állítva, mindössze néhány kódsorral.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: hu
lastmod: 2026-10-08
og_description: Hogyan méretezzünk gyorsan vonalkódot egy C# vonalkód-generátor példával.
  Állítsuk be a vonalmagasságot, mentsünk PNG fájlokat, és kerüljük el a gyakori hibákat.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Hogyan méretezhetünk át egy vonalkódot C#‑ban – lépésről‑lépésre generátor
  példa
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Hogyan méretezhetünk át egy vonalkódot C#-os vonalkódgenerátor példával
url: /hu/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan méretezhetünk át vonalkódot egy vonalkód‑generátor példával C#‑ban

Ha **hogyan méretezzen át vonalkód** képeket egy .NET projektben, ez az útmutató bemutatja a teljes megoldást. Egy tömör **vonalkód‑generátor példa C#**‑t láthat, amely a vonal magasságát 30 px‑ről 60 px‑re változtatja, és minden verziót PNG fájlként ment.

A vonalkód átméretezése gyakran szükséges, amikor ugyanazt az adatot kell megjeleníteni nyugtákon, címkéken vagy termékoldalakon különböző vizuális méretekben. Ahelyett, hogy a raszter képet egy külső szerkesztővel módosítaná, programozottan állíthatja be a vonalkód méreteit, miközben az adat integritása érintetlen marad.

Ebben az oktatóanyagban Ön:

* Beállít egy DataBar Omni‑Directional vonalkód‑generátort.
* Módosítja az X‑dimenziót és a vonalmagasság paramétereit.
* Két képet ment különböző magasságokkal.
* Megérti, miért működik a vonalmagasság változtatása, és milyen széljegyekre kell figyelni.

> **Prerequisite** – Van egy .NET fejlesztői környezet (Visual Studio 2022 vagy újabb) és a vonalkód‑könyvtár, amely biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` osztályokat. A kód a könyvtár legújabb, 2026. októberi verziójával működik.

## A vonalkód‑generátor példa C# előfeltételei

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

| Elem | Indok |
|------|-------|
| .NET 6.0 SDK vagy újabb | Biztosítja a futtatókörnyezetet és a mintában használt nyelvi funkciókat. |
| Vonalkód könyvtár (pl. Aspose.BarCode, Dynamsoft, vagy bármelyik, amely `BarcodeGenerator`‑t biztosít) | Szolgáltatja a `EncodeTypes.DatabarOmniDirectional` enumerációt és a képexportálási metódusokat. |
| Írási jogosultsággal rendelkező mappa (pl. `C:\Temp\Barcodes\`) | A minta PNG fájlokat ebbe a helyre menti. |
| Alapvető C# ismeretek | Az oktatóanyag feltételezi, hogy ismeri az osztályokat, tulajdonságokat és a string interpolációt. |

Telepítse a könyvtárat a NuGet‑en keresztül, ha még nem tette meg:

```bash
dotnet add package Aspose.BarCode
```

Cserélje le a csomagnévét arra, amelyet valójában használ; az alább bemutatott API felület a legtöbb vonalkód‑SDK‑nél közös.

## Hogyan méretezzen át vonalkód – 1. lépés: hozza létre a generátort

Az első lépés egy `BarcodeGenerator` példányosítása a kívánt szimbólummal és adatpayload‑dal. Ebben a példában egy **DataBar Omni‑Directional** vonalkódot generálunk, amely egy GTIN‑14 értéket kódol.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Miért fontos:** A `EncodeTypes.DatabarOmniDirectional` enumeráció megmondja a könyvtárnak, melyik vonalkód‑szabványt használja. Az adatstring a GS1 Alkalmazási Azonosítót `(01)` követi egy 14‑jegyű GTIN‑hez, biztosítva, hogy a vonalkód megfeleljen a globális kereskedelmi szabványoknak.

## Hogyan méretezzen át vonalkód – 2. lépés: határozza meg a modul szélességét és a kezdeti vonalmagasságot

A vonalkód vizuális mérete két paramétertől függ:

* **X‑dimenzió** – a legkisebb vonal (modul) szélessége. Pixelben vagy milliméterben mérve.
* **Vonalmagasság** – a vonalak függőleges hossza.

Ezeknek az értékeknek a mentés előtt történő beállítása garantálja, hogy a renderelt kép megfeleljen a kívánt méreteknek.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Magyarázat:** A 2 px X‑dimenzió kompakt vonalkódot eredményez, amely még mindig megbízhatóan beolvasható. A 30 px magasság gyakori alapértelmezés kis címkékhez. Az X‑dimenziót a magasságtól függetlenül állíthatja, ha sűrűbb vagy lazább mintázatot szeretne.

## Hogyan méretezzen át vonalkód – 3. lépés: mentse az első képet (30 px magasság)

Most exportálja a vonalkódot PNG fájlba. A `Save` metódus egy fájlútvonalat és egy képformátum enumerációt vár.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Eredmény:** A `DatabarBarHeight30Pixels.png` egy 30 px magas vonalkódot tartalmaz. Bármely képnézőben megnyithatja a fájlt a méretek ellenőrzéséhez.

## Hogyan méretezzen át vonalkód – 4. lépés: változtassa meg a vonalmagasságot 60 px‑re

Egy nagyobb verzió létrehozásához egyszerűen módosítsa a `BarHeight` tulajdonságot. A generátor ugyanazt az adatot és X‑dimenziót használja, így a vonalkód mintázata változatlan marad – csak a vizuális méret változik.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Miért működik:** A vonalkód renderelő motor minden vonal geometriáját igény szerint számítja ki. A magasság tulajdonság frissítése a következő `Save` hívás előtt újraszintetizálja a képet az új méretekkel.

## Hogyan méretezzen át vonalkód – 5. lépés: mentse a második képet (60 px magasság)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Most már két PNG fájlja van, egy kis (30 px) és egy nagyobb (60 px) változat, készen állva a különböző címkeméretekhez.

## Teljes forráskód a vonalkód‑generátor példa C#‑hez

Az alábbiakban a teljes, futtatható program látható. Másolja be egy új konzolos projektbe, és azonnal tesztelheti.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Várható konzolkimenet:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

A futtatás után nyissa meg a két PNG fájlt, hogy lássa a vizuális különbséget. Mindkét vonalkód ugyanazt a GTIN‑14 értéket kódolja, és magasságtól függetlenül azonos módon olvasható.

## Miért biztonságos a vonalmagasság módosítása a beolvasás szempontjából

A vonalkód‑olvasók a fény‑ és sötétség modulok mintázatát olvassák, nem pedig a pixel számát. Amíg az **X‑dimenzió** a scanner toleranciáján belül marad (általában 0,5 mm és 2 mm között fizikai egységekben), a magasság változtatása nem befolyásolja az olvashatóságot. A könyvtár automatikusan skálázza a modulokat, megőrizve a szükséges nyugalmi zónákat és igazítási mintákat.

## Gyakori hibák és elkerülésük módja

| Hiba | Hogyan javítsuk |
|------|-----------------|
| **A kimeneti mappa nem létezik** | Hívja meg a `Directory.CreateDirectory(outputPath)` metódust a mentés előtt. |
| **Helytelen X‑dimenzió, ami elmosódott beolvasást okoz** | Tartsa a `XDimension.Pixels` értéket 1 px és 4 px között a legtöbb nyomtatóhoz; tesztelje fizikai scannerrel. |
| **Raszter formátum használata nagyon nagy vonalkódokhoz** | Váltson `BarCodeImageFormat.Svg`‑re a végtelen skálázhatóságért pixeláció nélkül. |
| **Elfelejtett `BarHeight` visszaállítás a második mentés előtt** | Győződjön meg róla, hogy az új magasságot **a** `Save` újrahívása előtt állítja be. |

## Pro tipp: több méret generálása ciklusban

Ha különböző magasságokra van szüksége (pl. 30 px, 45 px, 60 px), egy egyszerű `foreach` ciklus csökkenti a duplikációt:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Ez a minta jól skálázható termékkatalógusok tömeges feldolgozásához.

## Szélső esetek: különböző képformátumok és DPI beállítások

* **SVG kimenet** – Használja a `BarCodeImageFormat.Svg`‑t, hogy vektoros fájlt kapjon, amely minőségveszteség nélkül átméretezhető.
* **Magas DPI‑jú PNG** – Állítsa be a `generator.Parameters.Image.DpiX` és `DpiY` értékeket 300‑ra vagy 600‑ra nyomtatásra kész képekhez; a vonalmagasság továbbra is pixelben mérhető, ezért arányosan növelje.
* **Nem szabványos szimbólumok** – Egyes vonalkódtípusok (pl. QR Code) külön `Size` tulajdonsággal rendelkeznek a `BarHeight` helyett. Tekintse meg a könyvtár dokumentációját ezekhez az esetekhez.

## A méretezett vonalkód tesztelése

1. Nyissa meg minden PNG‑t egy képnézőben, és ellenőrizze a pixelméreteket (pl. 150 × 30 px vs. 150 × 60 px).  
2. Nyomtassa ki a képeket 100 % méretben.  
3. Olvassa be egy kézi vonalkód‑olvasóval vagy mobilalkalmazással. A dekódolt adatnak a következőnek kell lennie


## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Vonalkód‑generátor példa C# – szélesség és magasság beállítása](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Hogyan méretezzen át vonalkódot C#‑ban az Aspose.BarCode használatával – lépésről‑lépésre útmutató](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Hogyan mentse a vonalkód képeket a Barcode Generator C#‑vel – lépésről‑lépésre útmutató](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}