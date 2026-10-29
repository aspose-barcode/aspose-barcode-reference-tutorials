---
category: general
date: 2026-10-28
description: Hogyan generáljunk egyedi szöveges vonalkódot az Aspose.BarCode használatával
  – lépésről lépésre útmutató .NET fejlesztőknek a vonalkód Aspose képek létrehozásához.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: hu
lastmod: 2026-10-28
og_description: Hogyan generáljunk egyedi szöveges vonalkódot .NET-ben az Aspose.BarCode
  használatával. Kövesse ezt a teljes útmutatót a Macro PDF417 vonalkód létrehozásához
  és mentéséhez.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Hogyan generáljunk vonalkódot egyedi szöveggel – Aspose.BarCode útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Hogyan generáljunk vonalkódot egyedi szöveggel az Aspose.BarCode for .NET használatával
url: /hu/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkódot egyedi szöveggel az Aspose.BarCode for .NET használatával

A vonalkód egyedi szöveggel történő generálása gyakori követelmény, amikor azonosítókat, időbélyegeket vagy egyéb metaadatokat kell közvetlenül egy vizuális kódban elhelyezni. Ez a bemutató megmutatja, hogyan generáljunk Macro PDF417 vonalkódot, amely egyedi szöveget és a teljes metaadatkészletet tartalmazza, az **Aspose.BarCode** .NET könyvtár használatával.

Megtanulja, hogyan konfigurálja a generátort, alkalmazza az egyedi szöveget, állítsa be a Macro PDF417 specifikus mezőket, és mentse az eredményt PNG képként. Külső eszközök nem szükségesek – csak az Aspose.BarCode NuGet csomag és egy .NET fejlesztői környezet.

## Előkövetelmények

* .NET 6.0 SDK vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely .NET-et támogató IDE)  
* **Aspose.BarCode for .NET** NuGet csomag (`Install-Package Aspose.BarCode`)  

Ezek az előkövetelmények biztosítják, hogy a kód lefordul és futtatható legyen további konfiguráció nélkül.

## 1. lépés: Az Aspose.BarCode csomag telepítése

Nyisson egy terminált a projekt mappájában, és futtassa:

```bash
dotnet add package Aspose.BarCode
```

A parancs hozzáadja az Aspose.BarCode legújabb stabil verzióját a projekthez, így hozzáfér a `BarcodeGenerator` osztályhoz és minden kapcsolódó paraméterhez.

## 2. lépés: Új konzolalkalmazás létrehozása

Hozzon létre egy minimális konzolalkalmazást, amely a vonalkód generálási logikát tartalmazza:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Miért fontos minden sor

* **EncodeTypes.MacroPdf417** – a Macro PDF417 szimbólumot választja, amely támogatja a szegmentált adatokat és metaadatokat.  
* **XDimension.Pixels** – szabályozza az egyes modulok méretét; a 2 pixel érték tiszta, beolvasható képet eredményez.  
* **Pdf417.Columns** – csökkenti a teljes szélességet, így a vonalkód kompaktabb lesz nyomtatott címkékhez.  
* **MacroPdf417* properties** – fájlszintű információkat (azonosító, szegmens száma, időbélyegek stb.) ágyaz be közvetlenül a vonalkódba. Ez a képesség egyedülálló a Macro PDF417 esetében, és gyakran használják logisztikai vagy dokumentumkezelő rendszerekben.  
* **Save(..., BarCodeImageFormat.Png)** – veszteségmentes PNG fájlt ír, megőrizve a vonalkód éles széleit a megbízható beolvasás érdekében.

## 3. lépés: A program futtatása és a kimenet ellenőrzése

Építse és futtassa a konzolalkalmazást:

```bash
dotnet run
```

A program létrehozza a `ExtPDF417Meta.png` fájlt a projekt munkakönyvtárában. A fájl megnyitása egy Macro PDF417 vonalkódot mutat, amely a **“Åspóse.Barcóde©”** szöveget kódolja a megadott metaadatokkal együtt.

**Várható kimenet** – egy PNG kép, amely hasonló az alábbihoz:

![hogyan generáljunk vonalkód példakimenet PNG kép Macro PDF417 vonalkóddal](ExtPDF417Meta.png)

*A kép alt szövege („hogyan generáljunk vonalkód példakimenet PNG kép”) erősíti az elsődleges kulcsszót a hozzáférhetőség és a SEO érdekében.*

## Gyakori változatok és szélhelyzetek

### Másik vonalkódtípus használata

Ha **vonalkód egyedi szöveg generálására** QR kód esetén van szükség a Macro PDF417 helyett, cserélje le a `EncodeTypes.MacroPdf417`-t `EncodeTypes.QR`-ra. A paraméterstruktúra többi része változatlan marad, de a QR kódok nem támogatják a Macro metaadatmezőket.

### Unicode karakterek kezelése

A példa már tartalmaz Unicode karaktereket (`Å`, `ó`, `©`). Az Aspose.BarCode alapból kezeli a UTF‑8 bemenetet, de biztosítani kell, hogy a forrásfájl UTF‑8 kódolással legyen mentve a fordítási figyelmeztetések elkerülése érdekében.

### Mentés más képformátumokba

Az Aspose.BarCode támogatja a BMP, JPEG, TIFF és SVG formátumokat is a PNG mellett. Ennek megfelelően módosítsa a `BarCodeImageFormat` enum értékét:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Nagy adatállományok

A Macro PDF417 képes az adatot több szegmensre bontani. Ha a szöveg meghaladja egy szegmens kapacitását, növelje a `MacroPdf417SegmentID` értékét, és tartsa a `MacroPdf417SegmentsCount` értékét konzisztensen az összes generált részben. Ez a megközelítés elengedhetetlen a **create barcode aspose** szcenáriókhoz, ahol a payload nagyobb, mint egyetlen vonalkód képes tárolni.

### Hibakezelés

Tegye a generálási logikát try‑catch blokkba, hogy a futásidejű problémákat, például érvénytelen fájlutakat vagy nem támogatott karaktereket, fel tudja fedni:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Profi tippek a megbízható vonalkód generáláshoz

* **Érvényesítse a vonalkódot** a létrehozás után a `BarCodeReader` használatával. Ez a további lépés megerősíti, hogy a kódolt adatok megfelelnek az elvárásainak.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Tartsa az X‑dimenziót 2 – 4 pixel között** a legtöbb szkennerhez. A kisebb értékek olvashatatlan képeket eredményezhetnek alacsony felbontású eszközökön.

* **Kerülje a túl hosszú fájlneveket** a `MacroPdf417FileName` mezőben. A specifikáció 32 karakterre korlátozza a mezőt.

* **Használjon konzisztens időbélyegeket** (UTC) több szegmens generálásakor, hogy egyszerűsítse a további feldolgozást.

## Összegzés

Most már tudja, **hogyan generáljunk vonalkódot** egyedi szöveggel az Aspose.BarCode for .NET használatával, hogyan konfigurálja a Macro PDF417 metaadatokat, és hogyan mentse az eredményt PNG képként. A teljes, futtatható példa bemutatja a szükséges lépéseket – a NuGet csomag telepítésétől a Unicode karakterek kezeléséig és a kimenet mentéséig.

Innen kezdve a következőket teheti:

* **Generáljon egyedi szöveges vonalkódot** más szimbólumokhoz (QR, DataMatrix stb.)  
* **Create barcode Aspose** munkafolyamatok, amelyek tömegesen feldolgoznak több ezer képet  
* Integrálja a vonalkód generálási kódot ASP.NET Core szolgáltatásokba, Windows szolgáltatásokba vagy Azure Functions-be  

Kísérletezzen különböző paraméterekkel, fedezze fel a további metaadatmezőket, és építse be a vonalkódot a dokumentum‑automatizálási folyamatokba. Boldog kódolást!

## Mit érdemes következőként megtanulni?

A következő bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan hozzunk létre PDF417 vonalkódot az Aspose segítségével – Teljes lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Vonalkód generálása szövegből az Aspose.BarCode használatával – C# útmutató](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Hogyan használjuk az Aspose.BarCode-ot DataMatrix kód szöveg létrehozásához .NET-ben](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}