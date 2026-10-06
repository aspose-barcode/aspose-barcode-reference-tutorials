---
category: general
date: 2026-10-05
description: Készítsen vonalkód PNG-t C#-ban, és tanulja meg, hogyan állítható be
  a 15-ös képarány a rétegezett DataBar omnidirekcionális vonalkódokhoz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: hu
lastmod: 2026-10-05
og_description: Készítsen vonalkód PNG-t C#-ban, és fedezze fel, hogyan állíthatja
  be a 15-ös képarányt a rétegezett DataBar omnidirekcionális vonalkódoknál néhány
  lépésben.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Barcode PNG létrehozása C#-ban – 15‑as képarány beállítása bemutató
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hogyan hozhatunk létre vonalkód PNG-t egyedi képaránnyal C#-ban
url: /hu/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre barcode PNG-t egyedi képaránnyal C#-ban

Ha C#-ban **barcode PNG-t** kell létrehoznod, ez az útmutató megmutatja, hogyan állítsd be a **15‑ös képarányt** egy stacked DataBar omnidirectional vonalkódhoz. Végigvezetünk minden API‑híváson, elmagyarázzuk, miért fontos a képarány, és egy teljes, futtatható példát adunk, amelyet bármely .NET projektbe beilleszthetsz.

A vonalkód kép generálása gyakori igény készletkezelő rendszerekben, szállítási címkékben és kiskereskedelmi POS (point‑of‑sale) alkalmazásokban. A tutorial végére egy PNG fájlt kapsz, amely pontosan megfelel az üzleti partnered által előírt vizuális specifikációknak. Nincs szükség külső eszközökre, nincs kézi képszerkesztés – csak kód.

## Előfeltételek

* .NET 6.0 vagy újabb (a példa .NET 6‑ot használ, de .NET 5+‑tel is működik)
* Visual Studio 2022 (vagy bármely .NET‑et támogató IDE)
* A **Aspose.BarCode for .NET** NuGet csomag  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Írási jogosultság a mappához, ahová a PNG fájlt menteni szeretnéd

Ezek az előfeltételek minimálisak; ugyanaz a kód működik .NET Core, .NET Framework vagy konzolalkalmazás esetén is.

## Barcode PNG létrehozása Aspose.BarCode segítségével

Az első lépés a `BarcodeGenerator` osztály példányosítása a megfelelő vonalkódtípussal. Ebben az esetben a `EncodeTypes.DatabarStackedOmniDirectional`-t használjuk, amely egy stacked DataBar-t hoz létre, amely bármely irányból olvasható.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Miért fontos:* A konstruktor két argumentumot vár – **a vonalkód szimbólumát** és **az adatstringet**. A DataBar formátum GS1 alkalmazásazonosítót vár, ezért a mintaadat `(01)`‑vel kezdődik.

## Hogyan állítsuk be a képarányt egy stacked DataBar esetén

A DataBar vizuális szélességét a **aspect ratio** (képarány) tulajdonság szabályozza. A magasabb arány szélesebb vonalakat eredményez, ami javíthatja a beolvasás megbízhatóságát alacsony felbontású nyomtatókon.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` határozza meg egyetlen modul (a legkisebb vonal vagy szóköz) méretét. 2 px‑en tartva éles, nagy sűrűségű képet eredményez, amely a legtöbb címkenyomtatóhoz megfelelő.

## 15‑ös képarány beállítása – kódlépésenkénti áttekintés

Most alkalmazzuk a **15‑ös képarány beállítása** követelményt. Ez a tutorial középpontja, és bemutatja a pontos API‑hívást, amelyre szükséged van.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Miért 15?* A stacked DataBar alapértelmezett képaránya 12. 15‑re növelve minden vonal szélességét 25 %-kal bővíti, ami gyakran megfelel a logisztikai szolgáltatók előírásainak, akik szélesebb vonalkódot igényelnek a gyorsabb beolvasáshoz.

## A vonalkód mentése PNG‑ként

A generátor beállítása után az utolsó lépés a kép lemezre írása. A `Save` metódus egy fájlútvonalat és egy képformátum enumot vár.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

A PNG formátum veszteségmentes minőséget biztosít, garantálva, hogy a vonalkód pontosan úgy jelenik meg, ahogy tervezve lett, bármilyen kijelzőn vagy nyomtatón.

## Teljes példa és a várt kimenet

Az alábbiakban a teljes program látható, amelyet beilleszthetsz egy konzolalkalmazás `Main` metódusába. Tartalmazza a fent leírt összes lépést, valamint egy kis ellenőrző üzenetet.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Várt kimenet**

A program futtatása létrehozza a `DatabarAspectRatio15.png` nevű fájlt, amely egy tiszta, széles stacked DataBar vonalkódot tartalmaz. Amikor megnyitod a PNG‑t, egy vízszintesen nyújtott vonalkódot kell látnod, amely továbbra is megfelel a GS1 DataBar specifikációknak.

![Barcode PNG 15‑ös képaránnyal](barcode-aspect15.png)

*Kép alt szöveg:* **létrehozott barcode PNG, amely egy stacked DataBar-t mutat 15‑ös képaránnyal**

### Tippek és gyakori buktatók

| Helyzet | Ajánlás |
|-----------|----------------|
| **A kép elmosódott** | Növeld az `XDimension.Pixels` értékét 3 px‑re vagy magasabbra, de tartsd a teljes képméretet 500 px alatt, hogy elkerüld a túl nagy fájlokat. |
| **A szkenner nem olvassa be a kódot** | Ellenőrizd, hogy az adatstring a GS1 formátumnak (`(01)` előtag) megfelelő-e. Emellett győződj meg róla, hogy a nyomtató felbontása legalább 300 dpi. |
| **Másik fájlformátumra van szükség** | Cseréld le a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp` vagy `Gif`-re – az API támogatja az összes főbb raszter formátumot. |
| **Webalkalmazásban futtatás** | Használd a `generator.Save(Stream, BarCodeImageFormat.Png)`-t, hogy közvetlenül az HTTP válaszba írd a képet, anélkül, hogy a fájlrendszert érintenéd. |

### A példa kibővítése

* **Több vonalkód egy képen:** Hozz létre további `BarcodeGenerator` példányokat, és egyetlen `Bitmap`-re rajzold őket a `Graphics` használatával.  
* **Olvasható szöveg hozzáadása:** Állítsd be a `generator.Parameters.Caption.Visible = true` értéket, és testreszabhatod a betűtípust a `generator.Parameters.Caption.Font` segítségével.  
* **Dinamikus képarány:** A képarány értékét egy konfigurációs fájlból vagy adatbázisból olvasd ki, hogy futás közben változó szélességű vonalkódokat generálj.

## Összegzés

Ebben a tutorialban megtanultad, hogyan **hozz létre barcode PNG-t** C#-ban, és hogyan állítsd be pontosan a **15‑ös képarányt** egy stacked DataBar omnidirectional vonalkódhoz. A teljes, futtatható kód bemutatja az összes szükséges API‑hívást, elmagyarázza, miért fontos minden beállítás, és gyakorlati tippeket ad a valós környezetben való alkalmazáshoz.

Továbbiakban felfedezheted, hogyan **állítsd be a képarányt** más vonalkódtípusoknál (pl. QR Code vagy Code 128), vagy integrálhatod a generátort egy ASP .NET Core szolgáltatásba, amely igény szerint visszaadja a vonalkód képeket. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API‑funkciókat, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [Hogyan hozzunk létre databar PNG képeket C#-ban és Aspose.Barcode segítségével](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hogyan hozzunk létre stacked databar vonalkódot C#-ban Aspose.Barcode segítségével](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Databar stacked omnidirectional képarány testreszabása .NET-ben](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}