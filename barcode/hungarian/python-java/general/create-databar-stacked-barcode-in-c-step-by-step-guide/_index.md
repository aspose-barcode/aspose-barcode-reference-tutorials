---
category: general
date: 2026-08-06
description: Készíts gyorsan DataBar stacked vonalkódot C#-ban. Tanuld meg beállítani
  az X-dimenziót, módosítani az oldalarányt, és PNG-fájlokat exportálni a DataBar
  Stacked Omnidirectional generátorral.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: hu
lastmod: 2026-08-06
og_description: Készítsen databar stacked vonalkódot C#-ban az Aspose.BarCode segítségével.
  Ez az útmutató bemutatja, hogyan állítható be az X-dimenzió, hogyan változtatható
  meg a képarány, és hogyan menthetők PNG képek.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Databar stacked vonalkód létrehozása C#‑ban – teljes programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Databar stacked vonalkód készítése C#-ban – lépésről lépésre útmutató
url: /hu/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar stacked vonalkód létrehozása C#‑ban – lépésről‑lépésre útmutató

Ha C#‑ban **databar stacked vonalkód** képeket kell létrehoznod, ez az útmutató pontosan megmutatja, hogyan teheted ezt meg az Aspose.BarCode könyvtár segítségével. Megtanulod beállítani az X dimenziót, módosítani a vonalkód képarányát, és elmenteni az eredményt PNG fájlokként – mindezt néhány tömör lépésben.

DataBar Stacked vonalkód generálása gyakori, amikor GS1‑128 adatot kell kódolni kiskereskedelmi beolvasáshoz vagy logisztikai nyomon követéshez. Az alábbi szakaszokban mindent lefedünk a projekt beállításától a kimenet ellenőrzéséig, így a megoldást bármely .NET alkalmazásba integrálhatod anélkül, hogy bármit is kihagynál.

## Előfeltételek

* **.NET 6.0** (vagy újabb) telepítve – a kód a modern SDK‑ra céloz.
* **Licencelt** példány a **Aspose.BarCode for .NET**‑ből. Az ingyenes értékelő verzió teszteléshez működik, de vízjelet ad hozzá.
* Olyan IDE, mint a **Visual Studio 2022** vagy a **VS Code** a C# kiegészítővel.
* Alapvető ismeretek a **C#** szintaxisról és a GS1 Alkalmazási Azonosítók koncepciójáról.

> **Pro tipp:** Ha a NuGet csomagkezelőt használod, a `dotnet add package Aspose.BarCode` parancs automatikusan megoldja az összes függőséget.

## 1. lépés: Új konzolprojekt létrehozása

Nyiss egy terminált vagy a Package Manager Console‑t, és futtasd:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

A `dotnet new console` parancs egy minimális **Program.cs** fájlt hoz létre. Az **Aspose.BarCode** csomag hozzáadása elérhetővé teszi a `BarcodeGenerator` osztályt.

## 2. lépés: A DataBar Stacked Omnidirectional generátor inicializálása

Nyisd meg a **Program.cs** fájlt, és cseréld le az alapértelmezett tartalmat a következő kóddal. Az első sor egy **BarcodeGenerator**‑t hoz létre, amely a **DataBar Stacked Omnidirectional** szimbólumra van konfigurálva, és egy GS1‑128 payload‑ot ad meg.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Miért fontos:** A `EncodeTypes.DatabarStackedOmniDirectional` enum érték azt mondja a könyvtárnak, hogy **databar stacked vonalkód**-ot állítson elő, ami a DataBar omnidirekcionális család stacked változata. Ez a szimbólum legfeljebb 14 numerikus karaktert képes tárolni, így ideális GTIN‑14 kódokhoz.

## 3. lépés: Az X dimenzió beállítása (modul szélesség)

Az X dimenzió szabályozza a legkisebb vonal (a modul) szélességét. A túl kicsi érték rosszul jelenhet meg alacsony felbontású nyomtatókon, míg a túl nagy érték meghaladhatja a címke helyét.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tipp:** A `Pixels` tulajdonság kényelmes képernyőalapú teszteléshez. Nyomtatásra fókuszáló esetekben használd inkább a `generator.Parameters.Barcode.XDimension.Millimeters`‑t.

## 4. lépés: A képarány módosítása és az első kép mentése

A **képarány** befolyásolja a stacked vonalkód magasság‑szélesség arányát. A DataBar Stacked Omnidirectional típus 10‑30 közötti arányokat támogat. Két képet fogunk generálni, hogy bemutassuk a vizuális hatást.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

A `generator.Save` hívás egy **PNG** fájlt ír a jelenlegi munkakönyvtárba. A `BarCodeImageFormat.Png` enum veszteségmentes tömörítést biztosít, ami ideális további feldolgozáshoz vagy PDF‑ekbe ágyazáshoz.

## 5. lépés: A képarány 30‑ra változtatása és a második kép mentése

Most a stacked vonalak magasságát növeljük a képarány **30**‑ra változtatásával. Ez magasabb vonalkódot eredményez anélkül, hogy az X dimenziót módosítaná.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

A program futtatása most két PNG fájlt hoz létre:

* **DatabarAspectRatio15.png** – egy kompakt vonalkód, amely kis címkékhez alkalmas.
* **DatabarAspectRatio30.png** – egy magasabb vonalkód, amely javítja a beolvasás megbízhatóságát alacsony kontrasztú felületeken.

A képeket bármely megjelenítővel megnyithatod, hogy ellenőrizd, a vonalak helyesen vannak-e stacked, és hogy a kódolt adat megegyezik-e az eredeti GS1 karakterlánccal.

## 6. lépés: A kódolt érték ellenőrzése (opcionális)

Ha meg kell erősítened, hogy a vonalkód valóban a bemeneti karakterláncot reprezentálja, dekódolhatod ugyanazzal a könyvtárral:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

A dekódernek a `(01)12345678901231` értéket kell kiadnia, bizonyítva, hogy a **databar stacked vonalkód létrehozása** folyamat megőrizte az adatot.

## Gyakori buktatók és hogyan kerüld el őket

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| A vonalkód elmosódott | Az X dimenzió túl alacsonyra van beállítva a kimeneti felbontáshoz | Növeld a `XDimension.Pixels` értékét, vagy nyomtatáshoz használd a `Millimeters`‑t |
| A szkenner azt jelzi, hogy “szimbólum nem található” | A képarány kívül esik a támogatott 10‑30 tartományon | Tartsd a képarányt 10 és 30 között; a 15 és 30 biztonságos alapértelmezések |
| A PNG vízjelet tartalmaz | Az Aspose.BarCode ingyenes értékelő licencének használata | Vásárolj teljes licencet, vagy csak teszteléshez használd a próbaverziót |
| A dekódolás sikertelen a második képen | A dekódert a helytelen szimbólumra konfigurálták | Használd a `DecodeType.DatabarStackedOmniDirectional`‑t stacked vonalkódok olvasásakor |

## Következő lépések

Most, hogy képes vagy **databar stacked vonalkód** képeket létrehozni, esetleg a következőket szeretnéd:

* **A PNG‑ket PDF számlákba ágyazni** egy PDF könyvtár, például az **Aspose.PDF** segítségével.
* **Vonalkódok generálása menet közben egy web API‑ban** – a PNG bájtokat közvetlenül egy ASP.NET Core vezérlőből adja vissza.
* **Kísérletezni más DataBar változatokkal** (pl. `DatabarExpanded`, `DatabarLimited`) az `EncodeTypes` enum módosításával.
* **Színek beállítása** a `generator.Parameters.Barcode.ForeColor` és `BackColor` beállításával a márkaspecifikus tervezéshez.

Ezek a témák mind ugyanazokra az alapvető koncepciókra épülnek, amelyeket itt bemutattunk: a `BarcodeGenerator` inicializálása, a vizuális paraméterek konfigurálása, és az eredmény mentése a `BarCodeImageFormat`‑tal.

---

### Következtetés

Ez az útmutató bemutatta, hogyan lehet **databar stacked vonalkód** képeket létrehozni C#‑ban az Aspose.BarCode használatával. Megtanultad beállítani az **X dimenziót**, módosítani a **vonalkód képarányát**, és exportálni az eredményt **PNG** fájlokként a `BarcodeGenerator`‑rel. Az opcionális dekódolási lépéssel ellenőrizheted is, hogy a kódolt GS1 adatok pontosak-e. Alkalmazd ezeket a mintákat saját készletkezelési, szállítási vagy értékesítési alkalmazásaidban, és fedezd fel a könyvtár által kínált számos testreszabási lehetőséget. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Egy-dimenziós Databar vonalkód magasság beállítása](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Vonalkód kép generálása – GS1 Kupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}