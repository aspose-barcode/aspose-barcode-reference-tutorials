---
category: general
date: 2026-09-29
description: GS1 vonalkód létrehozása C#‑ban és vonalkód PNG képek generálása a BarcodeGenerator
  használatával. Kövesse a lépésről‑lépésre útmutatót a vonalkód kép hatékony exportálásához.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: hu
lastmod: 2026-09-29
og_description: Készíts GS1 vonalkódot C#-ban, és generálj vonalkód PNG fájlokat a
  BarcodeGenerator segítségével. Kövesd ezt a teljes útmutatót a vonalkód kép gyors
  exportálásához.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: GS1 vonalkód létrehozása C#-ban – export PNG formátumban percek alatt
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: GS1 vonalkód létrehozása C#‑ban és exportálása PNG formátumban
url: /hu/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 vonalkód létrehozása C#-ban és exportálása PNG-ként

Ha **GS1 vonalkódot** kell létrehoznod egy .NET alkalmazásban, ez az útmutató pontosan megmutatja, hogyan teheted meg. Egy tömör megoldást láthatsz, amely egy vonalkód PNG képet generál, és a vonalkód képet lemezre exportálja, mindezt az Aspose.BarCode `BarcodeGenerator` osztállyal.

A GS1 vonalkód generálása gyakori igény a készletkezelés, szállítás és értékesítési pont rendszerek számára. A tutorial végére képes leszel egy kis C# programot írni, amely GS1‑kompatibilis MicroPDF417 vonalkódot hoz létre, és magas minőségű PNG fájlként menti el.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy a következők telepítve vannak:

* **.NET 6** (vagy bármely későbbi .NET verzió).
* **Visual Studio 2022** vagy bármely C#‑ot támogató IDE.
* Az **Aspose.BarCode for .NET** NuGet csomag (`Aspose.BarCode`) – ez biztosítja a példákban használt `BarcodeGenerator` API‑t.
* Alapvető ismeretek a C# szintaxisáról.

> **Pro tipp:** Kísérletezéshez használd az Aspose.BarCode ingyenes közösségi kiadását; a teljes verzió eltávolítja a kiértékelési vízjelet.

## 1. lépés – GS1 vonalkód létrehozása a BarcodeGenerator‑rel

Az első dolog, amit tenned kell, hogy példányosítod a `BarcodeGenerator`‑t a *MicroPDF417* formátumhoz, és betáplálod egy GS1 adatkarakterlánccal. A GS1 Alkalmazásazonosítók (AI‑k) zárójelben vannak, pl. `(01)` a GTIN‑14‑hez és `(21)` egy sorozatszámhoz.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Miért fontos:**  
`EncodeTypes.MicroPdf417` automatikusan GS1 adatként kezeli a bemenetet, ha a karakterlánc érvényes AI‑kat tartalmaz. Ez biztosítja, hogy a generált vonalkód a GS1 specifikációnak megfeleljen további konfiguráció nélkül.

## 2. lépés – A vonalkód méretének beállítása az optimális mérethez

A vonalkód vizuális méretét az **X‑dimenzió** (egy modul szélessége) szabályozza. Az `XDimension.Pixels` módosításával finomhangolhatod a végső képméretet, miközben megőrzöd az olvashatóságot.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Hogyan generáljunk vonalkód PNG‑t** – Az X‑dimenzió nem befolyásolja a kódolt adatot; csak a generált kép fizikai méretét változtatja. Ha nagyobb vonalkódra van szükséged nagy felbontású nyomtatáshoz, növeld ezt az értéket (pl. `3` vagy `4`).

## 3. lépés – Vonalkód PNG generálása és a kép exportálása

Most már renderelheted a vonalkódot, és PNG fájlba írhatod. A `Save` metódus megkapja a célútvonalat és a kívánt képformátumot.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Mi történik a háttérben:**  
`BarcodeGenerator.Save` rasterizálja a vonalkódot egy bitmapre, alkalmazza a korábban beállított X‑dimenziót, és PNG fájlként kódolja a bitmapet. A kapott fájl közvetlenül használható weboldalakon, címkén nyomtatva, vagy PDF‑ekbe beágyazva.

## Teljes forráskód példa

Az alábbiakban egy komplett, önálló konzolalkalmazás látható, amelyet másolhatsz, beilleszthetsz és futtathatsz. Bemutatja, **hogyan generáljunk vonalkód PNG‑t**, **hogyan exportáljuk a vonalkód képet**, és tartalmaz alapvető hibakezelést.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Várt kimenet

A program futtatásakor a következőt kell látnod:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

A PNG fájl megnyitása egy tiszta **GS1 MicroPDF417** vonalkódot mutat, amely a GTIN‑14 `12345678901234` és a sorozatszám `ABC123` adatokat kódolja. Bármely GS1‑kompatibilis szkennerrel beolvasva visszaadja az eredeti adatkarakterláncot.

## Gyakori hibák és legjobb gyakorlatok

| Probléma | Miért fordul elő | Hogyan kerüld el |
|----------|------------------|------------------|
| **Helytelen AI formátum** | Hiányzó zárójelek vagy rossz sorrend miatt a vonalkód nem GS1‑kompatibilis. | Mindig zárójelek közé tedd az AI‑kat, pl. `(01)`. |
| **Túl kicsi X‑dimenzió** | A vonalkód olvashatatlanná válik alacsony felbontású eszközökön. | Tartsd az `XDimension.Pixels` értékét ≥ 2 a legtöbb nyomtatóhoz; nagy DPI‑hoz növeld. |
| **A kimeneti mappa nem létezik** | A `Save` `DirectoryNotFoundException`‑t dob. | Hívd meg a `Directory.CreateDirectory`‑t a `Save` előtt. |
| **Rossz EncodeType használata** | Néhány típus (pl. `Code128`) nem támogatja a GS1 adatot alapból. | Válaszd a `EncodeTypes.MicroPdf417`‑t vagy bármely GS1‑kompatibilis típust. |
| **Hiányzó NuGet hivatkozás** | Fordítási hibák, mint például `The type or namespace name 'Aspose' could not be found`. | Telepítsd az `Aspose.BarCode` csomagot a NuGet‑en keresztül. |

## A példa kibővítése

* **Különböző képformátumok** – Cseréld le a `BarCodeImageFormat.Png`‑t `Jpeg`, `Gif` vagy `Bmp` értékre, ha más formátumra van szükséged.
* **Nagy felbontású kimenet** – Állítsd be a `generator.Parameters.ImageResolution.DpiX` és `DpiY` értékeket a mentés előtt.
* **Beágyazás PDF‑be** – Használd az `Aspose.Pdf`‑t a PNG PDF‑számla vagy címke helyére való elhelyezéséhez.

## Összegzés

Most már tudod, **hogyan hozhatsz létre GS1 vonalkódot** C#‑ban az Aspose.BarCode `BarcodeGenerator`‑rel, **hogyan generálj vonalkód PNG‑t**, és **hogyan exportáld a vonalkód képet** a fájlrendszerbe. Az útmutató minden lépést lefedett – a generátor GS1 adatokkal való inicializálásától, az X‑dimenzió beállításán át a végső PNG fájl mentéséig – miközben a gyakori hibákat is bemutatta és bővítési ötleteket kínált.

Nyugodtan kísérletezz más GS1 Alkalmazásazonosítókkal, különböző vonalkód szimbólumokkal vagy nagy felbontású képekkel. Amikor elsajátítod ezeket az alapokat, a készlet, szállítás vagy kiskereskedelmi vonalkódok generálása rutinszerű része lesz a .NET eszköztáradnak.

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek az API további funkcióinak elsajátításában és alternatív megvalósítási megközelítések felfedezésében saját projektjeidben.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}