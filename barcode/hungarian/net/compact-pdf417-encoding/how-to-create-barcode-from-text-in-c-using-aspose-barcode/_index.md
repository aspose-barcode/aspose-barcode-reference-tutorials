---
category: general
date: 2026-10-28
description: Készítsen vonalkódot szövegből C#‑ban az Aspose.BarCode segítségével.
  Tanulja meg, hogyan generáljon PDF417 vonalkód képet, állítson be oszlopokat, módosítsa
  az X‑dimenziót, és engedélyezze a kompakt módot.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: hu
lastmod: 2026-10-28
og_description: Készítsen vonalkódot szövegből C#-ban az Aspose.BarCode használatával.
  Ez az útmutató bemutatja, hogyan generáljon PDF417 vonalkód képet, testreszabja
  a méretet, az oszlopok számát és a kompakt módot.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Készítsen vonalkódot szövegből C#‑ban – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Hogyan készítsünk vonalkódot szövegből C#-ban az Aspose.BarCode használatával
url: /hu/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre vonalkódot szövegből C#-ban az Aspose.BarCode használatával

Ha **vonalkódot szeretne létrehozni szövegből** egy .NET alkalmazásban, ez az útmutató egy azonnal futtatható megoldást nyújt. Megmutatjuk, hogyan **generálhat PDF417 vonalkód** képeket, szabályozhatja a modul szélességét, az oszlopszámot, és engedélyezheti a kompakt módot anélkül, hogy elhagyná a fejlesztői környezetet.

Az útmutató mindent lefed, ami a **generate barcode C#** kódhoz szükséges, a könyvtár telepítésétől a végső PNG fájl mentéséig. A végére beágyazhat egy nagy sűrűségű PDF417 vonalkódot jelentésekbe, jegyekbe vagy készletcímkékbe.

## Előfeltételek

* .NET 6.0 SDK vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely .NET-et támogató szerkesztő)  
* Internetkapcsolat az Aspose.BarCode for .NET NuGet csomag letöltéséhez  

Ezek az elemek elegendőek a példa lefordításához és futtatásához Windows, Linux vagy macOS rendszeren.

## 1. lépés: Az Aspose.BarCode NuGet csomag telepítése

A vonalkód generálásáért felelős könyvtár a **Aspose.BarCode for .NET**. Telepítse a .NET CLI-val:

```bash
dotnet add package Aspose.BarCode
```

A csomag hozzáadja az `Aspose.BarCode` névteret, amely tartalmazza a `BarcodeGenerator` osztályt, amelyet az egész útmutatóban használunk.

## 2. lépés: Konzolos projekt létrehozása és a kód hozzáadása

Hozzon létre egy új konzolos projektet, és cserélje le a generált `Program.cs` fájlt az alábbi kóddal. A program bemutatja, hogyan **create barcode from text** és mentse **PDF417 barcode image** formátumban.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Miért fontos minden sor

* **`EncodeTypes.Pdf417`** a PDF417 szimbólumot választja, amely ideális nagy mennyiségű adat két dimenziós formátumban történő kódolásához.  
* **`XDimension.Pixels = 2`** csökkenti a modul szélességét, így a vonalkód sűrűbb és a korlátozott helyhez jobban illeszkedik.  
* **`Pdf417.Columns = 3`** szabályozza a függőleges adatoszlopok számát; alacsonyabb érték magasabb, de keskenyebb vonalkódot eredményez.  
* **`Pdf417.Truncate = true`** aktiválja a kompakt módot, levágva a jobb oldalon lévő nem használt oszlopokat. Ez a kulcsfontosságú beállítás, amely egy szabályos PDF417-et **compact PDF417 barcode image**-é alakít.

## 3. lépés: A projekt felépítése és futtatása

Futtassa a következő parancsokat a projekt könyvtárában:

```bash
dotnet build
dotnet run
```

Amikor a program befejeződik, egy konzolos üzenetet fog látni, amely megerősíti a fájl helyét. Nyissa meg a `CompactPdf417.png` fájlt bármely képnézegetővel a végeredmény ellenőrzéséhez.

**Várható kimenet** – egy nagy kontrasztú PNG, amely egy kompakt PDF417 vonalkódot mutat, amely a `Åspóse.Barcóde©` karakterláncot kódolja. A kép beolvasása egy szabványos vonalkódolvasóval visszaadja az eredeti szöveget, ezzel megerősítve, hogy a **generate pdf417 barcode** sikeres volt.

## 4. lépés: A vonalkód testreszabása különböző helyzetekhez

Bár a példa rögzített oszlopszámot és X‑dimenziót használ, a generátort más igényekhez is igazíthatja:

| Forgatókönyv | Módosítás |
|--------------|-----------|
| Nagyobb adat terhelés | Növelje a `Pdf417.Columns` értékét, vagy állítsa be manuálisan a `Pdf417.Rows`‑t |
| Magasabb beolvasási megbízhatóság | Emelje a `XDimension.Pixels` értékét 3‑ra vagy 4‑re |
| Eltérő képformátum | Cserélje le a `BarCodeImageFormat.Png`‑t `Jpeg` vagy `Bmp`‑re |
| Átlátszó háttér | Állítsa be a `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` értéket |

Ezek a lehetőségek lehetővé teszik, hogy **generate barcode C#** megoldásokat készítsen, amelyek megfelelnek mobilalkalmazásoknak, asztali jelentéseknek vagy webszolgáltatásoknak.

## 5. lépés: Szélsőséges esetek kezelése és legjobb gyakorlatok

* **Unicode támogatás** – A generátor automatikusan kódolja a Unicode karaktereket, de győződjön meg arról, hogy a forráskarakterlánc UTF‑8 kódolású, ha fájlból olvassa.  
* **Nagy szöveg** – A PDF417 legfeljebb 1 850 alfanumerikus karaktert képes kódolni. Ha ezt a határt meghaladja, a könyvtár kivételt dob; ossza fel az adatot több vonalkódra, vagy válasszon nagyobb kapacitású szimbólumot.  
* **Hibakezelés** – A generálási kódot helyezze `try/catch` blokkba, hogy elkapja a `BarCodeException`‑t, és barátságos hibaüzenetet jelenítsen meg.  
* **Teljesítmény** – Több vonalkód ciklusban történő generálása esetén előnyös egyetlen `BarcodeGenerator` példány újrahasználata, és csak a `CodeText` frissítése az iterációk között.  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Teljes forráskód

Az alábbiakban a teljes, önálló program látható, amelyet átmásolhat a `Program.cs` fájlba. További fájlokra nincs szükség.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

A program futtatása létrehozza a **pdf417 barcode image**-et, amely az alábbi ábrán látható.

![Kompakt PDF417 vonalkód, amely szövegből készült C# használatával](/images/compact-pdf417.png){.img-fluid alt="példa a szövegből létrehozott vonalkódról, amely egy kompakt PDF417 vonalkód képet mutat"}

*Kép leírása: A PNG fájl egy kompakt PDF417 vonalkódot mutat, amely a “Åspóse.Barcóde©” karakterláncot kódolja.*

## Következtetés

Most már tudja, hogyan **create barcode from text** C#-ban, és hogyan állítson elő egy **PDF417 barcode image**-et egyedi méretekkel és kompakt móddal. A példa bemutatja a **generate barcode C#** alapvető lépéseit, a Unicode adatok kezelését, valamint a vizuális paraméterek különböző telepítési forgatókönyvekhez való beállítását.

Ezután fedezze fel a kapcsolódó témákat, például **generate QR code in C#**, **add barcode to PDF documents**, vagy **embed barcodes in ASP.NET Core APIs**. Mindegyik az itt bemutatott `BarcodeGenerator` alapokra épül.

Boldog kódolást, és élvezze a vonalkódok .NET megoldásaiba való integrálását!

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [PDF417 vonalkód generálása C#‑ban – PDF417 vonalkód létrehozása C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Hogyan generáljunk PDF417 vonalkódot az Aspose.BarCode segítségével C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Hogyan hozzunk létre PDF417 vonalkód képet C#‑ban – teljes útmutató](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}