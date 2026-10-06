---
category: general
date: 2026-08-19
description: Készítsen databar PNG fájlokat C#-ban az Aspose.BarCode segítségével.
  Tanulja meg, hogyan generáljon databar képeket, állítsa be a databar paramétereket,
  és mentse el a PNG kimenetet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: hu
lastmod: 2026-08-19
og_description: Hozzon létre Databar PNG fájlokat C#-ban az Aspose.BarCode használatával.
  Ez az útmutató végigvezet a Databar képek generálásán, a Databar paraméterek, például
  az X‑dimenzió és a képarány beállításán, valamint a nyomtatáshoz vagy webes használatra
  alkalmas magas minőségű PNG fájlok mentésén.
og_image_alt: create databar PNG example
og_title: Databar PNG képek létrehozása C#‑ban – lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Hogyan készítsünk databar PNG képeket C#-ban és az Aspose.BarCode segítségével
url: /hu/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre databar PNG képeket C#-val és az Aspose.BarCode segítségével

Ha **databar PNG** fájlokat kell létrehoznod egy .NET alkalmazásban, ez az útmutató pontosan megmutatja, hogyan. Egy teljes, futtatható példát láthatsz, amely halmozott omnidirekcionális DataBar kódokat generál, kulcsfontosságú paramétereket konfigurál, és két PNG fájlt ment különböző képarányokkal.

A DataBar kép generálása nem csak egyetlen metódus meghívásából áll. **Databar paramétereket** is konfigurálnod kell, például az X‑dimenziót (modul szélességét) és a képarányt, hogy megfeleljenek a nyomtatási vagy szkennelési specifikációknak. A tutorial végére megérted, **hogyan generálj databar** grafikákat, amelyek megbízhatóan működnek a valós környezetben.

## Előfeltételek

- .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
- Visual Studio 2022 vagy bármely C#‑kompatibilis IDE
- Érvényes licenc az **Aspose.BarCode for .NET**‑hez (az ingyenes értékelés teszteléshez elegendő)
- Alapvető C# szintaxis ismeret

> **Pro tip:** Ha még nincs licenced, kérhetsz ideiglenes értékelő kulcsot az Aspose portálról. Az API viselkedése ugyanaz; csak a vízjel változik.

## 1. lépés: Telepítsd az Aspose.BarCode NuGet csomagot

Nyisd meg a projektet a Visual Studio-ban, kattints jobb gombbal a megoldásra, és válaszd a **Manage NuGet Packages** lehetőséget. Keresd meg a `Aspose.BarCode`‑t, és telepítsd a legújabb stabil verziót.

```bash
dotnet add package Aspose.BarCode
```

Ez a parancs hozzáadja az `Aspose.BarCode` assembly‑t a projektedhez, és elérhetővé teszi a `BarcodeGenerator` osztályt.

## 2. lépés: Inicializáld a vonalkódgenerátort egy halmozott omnidirekcionális DataBar-hoz

A `BarcodeGenerator` konstruktor két argumentumot kap: a vonalkódtípust és a nyers adatkarakterláncot. Halmozott omnidirekcionális DataBar esetén a `EncodeTypes.DatabarStackedOmniDirectional`‑t használod.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Miért fontos:** A `EncodeTypes.DatabarStackedOmniDirectional` állandó azt mondja a könyvtárnak, hogy olyan vonalkódot állítson elő, amely bármely orientációból olvasható, ami ideális a kiskereskedelmi polc címkékhez.

## 3. lépés: Állítsd be az X‑dimenziót (modul szélesség) pixelekben

Az X‑dimenzió szabályozza a legkisebb vonal elem méretét. Pixelekben megadva pontos kontrollt biztosít a végső kép mérete felett.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A **2 pixel** érték jó egyensúlyt jelent az olvashatóság és a kompakt méret között a legtöbb címkenyomtató esetén. Módosítsd ezt az értéket, ha nagyobb vagy kisebb modulokra van szükséged.

## 4. lépés: Állítsd be az első képarányt, és mentsd el a PNG‑t

A képarány befolyásolja a halmozott DataBar magasságát. A **15** képarány viszonylag rövid vonalkódot eredményez, míg a **30** magasabbat.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

A `Save` metódus a generált vonalkódot PNG fájlba írja. A PNG veszteségmentes, ami megőrzi a vonalkód szkennerekhez szükséges éles éleket.

## 5. lépés: Változtasd meg a képarányt, és ments egy második PNG‑t

Ugyanazt a `BarcodeGenerator` példányt újra felhasználhatod a variációk előállításához, egyszerűen a képarány módosításával.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Most már két PNG fájlod van – `DatabarAspectRatio15.png` és `DatabarAspectRatio30.png` – mindegyik más vizuális sűrűséggel.

## 6. lépés: Ellenőrizd a kimenetet

Nyisd meg a generált PNG fájlokat bármely képnézőben. Egy tiszta, nagy kontrasztú DataBar vonalkódot kell látnod. A képek okostelefonos vonalkódszkennerrel történő beolvasása megerősíti, hogy mindkét képarány a `12345678901231` eredeti GTIN értéket dekódolja.

![databar PNG példa létrehozása](databar_example.png)

*Az előző kép a két PNG fájlt mutatja egymás mellett. A bal oldali kép 15‑ös képarányt, a jobb oldali pedig 30‑as képarányt használ.*

## Gyakori variációk és szélsőséges esetek

| Szenárió | Mit kell módosítani | Ok |
|----------|---------------------|----|
| **Eltérő adat** | Cseréld le a `(01)12345678901231` karakterláncot bármely érvényes GS1 Alkalmazási Azonosítóra és adatra | Lehetővé teszi termékazonosítók, sorozatszámok stb. kódolását |
| **Magasabb felbontás** | Növeld az `XDimension.Pixels` értékét 3‑ra vagy 4‑re | Szükséges, ha a vonalkód nagy méretben lesz nyomtatva vagy nagy távolságból lesz szkennelve |
| **Egyéb DataBar típusok** | Használd a `EncodeTypes.DatabarStacked` vagy `EncodeTypes.DatabarExpanded` értékeket | Válaszd ki a címkelayoutodhoz legjobban illeszkedő típust |
| **Átlátszó háttér** | Add meg a `BarCodeImageFormat.Png`‑t a `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` paraméterrel | Hasznos, ha a vonalkódot színes címkére szeretnéd átfedni |

> **Figyelj:** Ha túl kicsi X‑dimenziót állítasz be (< 1 pixel), a vonalkód elmosódottnak tűnhet a nyomtatás után


## Mit érdemes még tanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}