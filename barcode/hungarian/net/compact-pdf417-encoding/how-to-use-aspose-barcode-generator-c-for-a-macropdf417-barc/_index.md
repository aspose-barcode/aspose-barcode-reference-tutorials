---
category: general
date: 2026-10-05
description: Az Aspose Barcode Generator C# lehetővé teszi, hogy makróadatokat adj
  hozzá, és könnyedén generálj PDF417 vonalkódokat. Tanulj meg lépésről lépésre makró
  metaadatokat hozzáadni és PDF417 képet létrehozni.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: hu
lastmod: 2026-10-05
og_description: Az Aspose Barcode Generator C# megmutatja, hogyan adhat hozzá makró
  metaadatokat, és néhány sor kóddal generálhat PDF417 vonalkódot.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – makró hozzáadása és PDF417 vonalkód generálása
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Hogyan használjuk az Aspose Barcode Generator C#-t a MacroPdf417 vonalkódhoz
url: /hu/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjuk az Aspose Barcode Generator C#-t MacroPdf417 vonalkódhoz

Ha C#-ban kell MacroPdf417 vonalkódot létrehoznia, a **Aspose Barcode Generator C#** egy tömör API-t biztosít, amely kezeli a vonalkód képet és a szükséges makró metaadatokat is. Ez az útmutató pontosan megmutatja, hogyan adhat hozzá makróinformációkat, és hogyan generálhat PDF417 vonalkód képet néhány lépésben.

Megtanulja, hogyan konfigurálja a vizuális paramétereket, ágyazza be a makrómezőket, például a fájlazonosítót és az időbélyeget, és mentse az eredményt PNG formátumban. Külső eszközök nem szükségesek – csak az Aspose.BarCode könyvtár és egy .NET fejlesztői környezet.

## Előkövetelmények

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

* .NET 6.0 vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely C# IDE)  
* Licencelt vagy értékelő példány a **Aspose.BarCode for .NET**‑ből  

A kód Windows, Linux és macOS rendszereken is működik, mivel a könyvtár platform‑független.

## 1. lépés: Az Aspose.BarCode NuGet csomag telepítése

Nyissa meg a projektet a Visual Studio-ban, majd futtassa a következő parancsot a **Package Manager Console**‑ban:

```powershell
Install-Package Aspose.BarCode
```

Ez hozzáadja az `Aspose.BarCode` összeállítást és annak függőségeit a projektjéhez.

## 2. lépés: A vonalkód generátor példány létrehozása

Az első sor egy `BarcodeGenerator` objektumot hoz létre a **MacroPdf417** szimbólumhoz, és megadja a kódolni kívánt szöveget.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Miért fontos*: Az `EncodeTypes.MacroPdf417` érték azt jelzi a könyvtárnak, hogy makró‑kapcsolódó mezőkre számít, amelyeket a következő lépésben állít be.

## 3. lépés: A vizuális megjelenés meghatározása

A modulok (a legkisebb fekete vagy fehér négyzet) méretét és a PDF417 mátrix oszlopainak számát szabályozhatja. Az `XDimension` módosítása befolyásolja a kép teljes felbontását.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

A `Columns` növelése csökkenti a vonalkód magasságát, míg a nagyobb `XDimension` tisztább képet eredményez a nagy DPI‑jú képernyőkön.

## 4. lépés: Makró metaadatok hozzáadása (hogyan adjon hozzá makrót)

A MacroPdf417 több további mezőt igényel, amelyek leírják a forrásfájlt és annak szegmentálását. Az alábbi tulajdonságok közvetlenül a PDF417 makró specifikációknak felelnek meg:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Miért fontosak ezek a mezők*:  
* `MacroPdf417FileID` összekapcsolja az összes szegmenst, biztosítva, hogy a szkenner újra összeállíthassa az eredeti dokumentumot.  
* `MacroPdf417SegmentID` és `MacroPdf417SegmentsCount` tájékoztatják a dekódert a sorrendről és a részek teljes számáról.  
* `MacroPdf417FileSize` és `MacroPdf417Checksum` integritás-ellenőrzéseket biztosítanak, amelyek nagy adatátvitelek esetén értékesek.

## 5. lépés: A vonalkód kép mentése (hogyan generáljon PDF417-et)

Végül írja a vonalkódot a lemezre. A `Save` metódus egy fájlútvonalat és egy képfájltípust fogad. A PNG megőrzi a vonalkód éles széleit a tömörítési hibák nélkül.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

A program futtatásakor a **ExtPDF417Meta.png** fájlt megtalálja a kimeneti mappában. A kép megnyitása egy tiszta MacroPdf417 vonalkódot mutat, amely készen áll a nyomtatásra vagy PDF-be ágyazásra.

### Várható kimenet

| Fájlnév            | Formátum | Méretek (kb.) |
|--------------------|----------|----------------------|
| ExtPDF417Meta.png  | PNG      | 300 × 150 px (a `XDimension`‑tól függően) |

A kép PDF417‑kompatibilis olvasóval (például ZXing, Aspose.BarCode for .NET) történő beolvasása visszaadja az eredeti **„Åspóse.Barcóde©”** szöveget az összes makrómezővel együtt.

## Gyakori hibák és elkerülésük módjai

| Probléma | Miért fordul elő | Megoldás |
|----------|-------------------|----------|
| **Helytelen `EncodeTypes`** | `EncodeTypes.Pdf417` használata `EncodeTypes.MacroPdf417` helyett letiltja a makrómezőket. | Mindig a generátort `EncodeTypes.MacroPdf417`‑el hozza létre. |
| **Hiányzó makrómezők** | Néhány szkenner figyelmen kívül hagyja a vonalkódot, ha a kötelező makrómezők hiányoznak. | Töltse ki legalább a `FileID`, `SegmentID`, `SegmentsCount` és `Terminator` mezőket. |
| **Túl kicsi `XDimension`** | Az 1 pixel alatti érték olvashatatlan vonalkódot eredményezhet alacsony felbontású képernyőkön. | Tartsa az `XDimension` értékét ≥ 2 pixelben a legtöbb képernyő- és nyomtatási esetben. |
| **Fájlútvonal hibák** | Relatív útvonal megadása, amely nem létezik, kivételt dob. | Használja a `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` vagy egy abszolút útvonalat. |

## Teljes forráskód

Az alábbiakban a teljes, futtatható példát találja, amelyet egy új konzolprojektbe másolhat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Futtassa a programot (`dotnet run`). A végrehajtás után a konzol egy sikerüzenetet ír ki, és a PNG fájl megjelenik a projekt kimeneti mappájában.

## Következő lépések

* **Nagyobb adatok kódolása** – Növelje a `Columns` értékét vagy állítsa be a `Rows`‑t (a `Pdf417.Rows`‑on keresztül), hogy több karaktert futhasson el.  
* **Beágyazás PDF-be** – Használja az Aspose.PDF‑et a generált PNG dokumentumba helyezéséhez.  
* **Beolvasás ellenőrzése** – Használja az `Aspose.BarCode.Reader`‑t a vonalkód dekódolásához és a makrómezők programozott ellenőrzéséhez.  

Ezeknek a témáknak a felfedezése elmélyíti a **PDF417 vonalkódok generálásának** megértését gazdag makróinformációval, és felkészíti a valós világban előforduló felhasználási esetekre, például kötegelt dokumentumfeldolgozásra vagy biztonságos adatcserére.

---

*Boldog kódolást! Ha hasznosnak találta ezt az útmutatót, ossza meg csapattársaival, vagy adjon csillagot az Aspose.BarCode tárolónak a GitHub‑on.*

## Mit érdemes következőként megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [Hogyan hozzunk létre macro PDF417 vonalkódot C#-ban az Aspose.BarCode használatával](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hogyan generáljunk PDF417 vonalkódot C#-ban a Barcode Generator segítségével](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose vonalkód példa: Macro PDF417 generálása C#-ban](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}