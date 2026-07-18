---
category: general
date: 2026-07-18
description: Tanulja meg, hogyan generáljon vonalkódképeket egy .net vonalkódgenerátorral,
  és könnyedén változtassa meg a vonalkód magasságát a GS1‑Databar Omni‑Directional
  szimbólumokhoz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: hu
lastmod: 2026-07-18
og_description: .net vonalkód-generátor lehetővé teszi, hogy gyorsan készítsen vonalkód
  képeket. Ez az útmutató bemutatja, hogyan generáljon vonalkódot, állítsa be a vonal
  magasságát, és mentse PNG fájlokként.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Módosítsa a vonalkód magasságát a .net vonalkód-generátorral
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET vonalkód generátor – a vonalkód magasságának módosítása
url: /hu/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – vonalkód magasságának módosítása

Gondolkodtál már azon, **hogyan generálj vonalkód** képeket anélkül, hogy tucatnyi harmadik féltől származó eszközt kellene használni? A .NET világban meglepően egyszerű módja van ennek, és a kulcsfontosságú elem a **.net barcode generator**. Néhány C# sorral előállíthatsz egy GS1‑Databar Omni‑Directional szimbólumot, módosíthatod a vonal magasságát, és elmentheted az eredményt PNG fájlba.

Ha készletkezelő rendszert, szállítási címke nyomtatót vagy bármilyen alkalmazást építesz, amelynek beolvasható kódra van szüksége, ez a bemutató néhány perc alatt a nulláról egy működő vonalkódot hoz létre. Átnézzük a teljes kódot, elmagyarázzuk, miért fontos minden beállítás, és megmutatjuk, hogyan **változtathatod meg a vonalkód magasságát** anélkül, hogy megsértenéd a specifikációt.

## Amire szükséged lesz

- .NET 6.0 vagy újabb (az API ugyanúgy működik a .NET Framework 4.7+ verziókon is)
- A hivatkozás a vonalkód könyvtárra (például Aspose.BarCode for .NET – ugyanazokat az osztályokat sok kereskedelmi csomag használja)
- Fejlesztői környezet (Visual Studio, Rider vagy VS Code a C# kiegészítővel)
- Egy mappa, ahol írási jogosultsággal rendelkezel – a bemutató PNG fájlokat ment ebbe a mappába

Ennyi. Nincs szükség extra NuGet csomagokra a vonalkód könyvtáron kívül.

## A .net barcode generator használata a vonalkód magasságának módosításához

Az alábbi **teljes, futtatható konzolprogram**. Illeszd be egy új C# projektbe, állítsd be a kimeneti mappát, és nyomd meg az F5‑öt.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Miért fontos minden sor

| Sor | Indok |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Példányosítja a **.net barcode generator**-t a kívánt szimbólummal és adatpayload-del. A `EncodeTypes.DatabarOmniDirectional` enum azt mondja a könyvtárnak, hogy használja a GS1‑Databar Omni‑Directional formátumot. |
| `XDimension.Pixels = 2;` | Az X‑dimenzió a legvékonyabb vonal szélessége. *2 pixel* beállítása éles képet ad a legtöbb monitoron, miközben alacsony fájlméretet tart. |
| `BarHeight.Pixels = 30;` | Ez a **vonalkód magasságának módosítása** lépés, amely meghatározza, milyen magas lesz minden vonal. A 30 pixel magasság jó alapértelmezett kis címkékhez. |
| `generator.Save(...);` | Elmenti a vonalkódot PNG fájlba. A PNG veszteségmentes, ami azt jelenti, hogy a szkennerek a pontosan generált mintát látják. |
| `BarHeight.Pixels = 60;` | Itt ismét **módosítjuk a vonalkód magasságát** – most 60 pixelre. A könyvtár automatikusan újrarajzolja a szimbólumot az új dimenzióval, amikor a `Save`-et másodszor hívod. |
| `Console.WriteLine(...);` | Gyors visszajelzést ad, hogy a folyamat hibamentesen befejeződött. |

> **Pro tipp:** Ha nyomtatáshoz nagyobb felbontású kimenetre van szükséged, cseréld a `BarCodeImageFormat.Png`-t `BarCodeImageFormat.Tiff`-re, és növeld a `Resolution` tulajdonságot (pl. `generator.Parameters.ImageResolution = 300;`). A vonal magassága továbbra is érvényes marad, csak finomabb DPI‑n lesz renderelve.

## Hogyan generálj vonalkód képeket különböző beállításokkal

Az előző kódrészlet az alapokat lefedi, de a valós helyzetek gyakran igényelnek további finomításokat:

### Az X‑dimenzió beállítása nagyobb nyomatokhoz
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Az X‑dimenzió növelése a teljes vonalkódot nagyobbra méretezi anélkül, hogy megváltoztatná a kódolt adatot. Ez akkor hasznos, ha nagy címkékre nyomsz.

### Kimeneti formátumok váltása
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
Az SVG végtelenül skálázható, ami tökéletes a web‑alapú szkennerek számára, amelyeknek éles vektorokra van szükségük.

### Emberi olvasásra alkalmas szöveg hozzáadása
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
`CodeTextVisible` engedélyezése a nyers adatot a vonalkód alá fűzi, ami hasznos a tesztelés során történő ellenőrzéshez.

## Gyakori hibák, amikor **módosítod a vonalkód magasságát**

1. **Túl alacsony magasság** – Néhány szkenner minimális vonalmagasságot igényel (gyakran 10 mm fizikai egységben). Ha a `BarHeight.Pixels`-t túl alacsonyra állítod, a generált kép olvashatatlan lehet egy valódi szkenner számára. Mindig teszteld a célhardverrel.
2. **Nem megfelelő X‑dimenzió és magasság** – Egy hatalmas vonalmagasság apró X‑dimenzióval nyúltnak tűnhet, és dekódolási hibákat okozhat. Törekedj kiegyensúlyozott arányra (kb. 3:1‑5:1), hacsak a specifikáció másként nem rendelkezik.
3. **A paraméterek visszaállításának elfelejtése** – A generátor megőrzi az állapotot a mentések között. Ha egy képnél megváltoztatod a `BarHeight`-t, majd ugyanazt a példányt használod egy másik vonalkódhoz, az előző magasság megmarad. Vagy állítsd vissza a tulajdonságot, vagy példányosíts egy új `BarcodeGenerator`-t minden egyes különálló vonalkódhoz.

## Teljes vég‑től‑végig példa (NuGet telepítéssel együtt)

Ha a semmiből indulsz, kövesd ezeket a lépéseket a projekt elindításához:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Cseréld le a generált `Program.cs`-t a korábban bemutatott kódrészletre, **ne felejtsd el a `YOUR_DIRECTORY`-t** valami hasonlóra cserélni, például `Path.Combine(Environment.CurrentDirectory, "output")`. Ezután:

```bash
dotnet run
```

A `output` mappában két PNG fájlt kell látnod:

- `DatabarBarHeight30Pixels.png` – egy kompakt, 30 pixel magas vonalkód.
- `DatabarBarHeight60Pixels.png` – egy magasabb, 60 pixel verzió.

Mindkét kép hasonló lesz, de a második észrevehetően hosszabb vonalakkal rendelkezik, ami megkönnyíti az alacsony felbontású szkennerek számára a beolvasást.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator kimenet, amely különböző vonalmagasságokat mutat"}

## Összefoglalás és következő lépések

Áttekintettük, hogyan **generálj vonalkód** képeket egy **.net barcode generator** segítségével, finomhangoltuk a **vonalkód magasságának módosítása** tulajdonságot, és PNG formátumban mentettük az eredményeket. A fő tanulságok:

- Példányosítsd a generátort a megfelelő `EncodeTypes`-szel.
- A vizuális méretet az `XDimension` és `BarHeight` segítségével szabályozd.
- Minden módosítás után hívd meg a `Save`-et, hogy új képet ments.
- Állítsd be a felbontást, formátumot,

## Mit érdemes még megtanulni?

A következő bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészletet tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generálj Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hogyan hozz létre dotcode kiterjesztett kódszöveget az Aspose.BarCode for .NET segítségével](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Hogyan generálj DataMatrix vonalkódokat (ECC 200) az Aspose.BarCode for .NET használatával](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}