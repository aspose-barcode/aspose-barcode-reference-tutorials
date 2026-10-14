---
category: general
date: 2026-10-02
description: Készítsen gyorsan rétegezett adatcsíkokból álló vonalkódot C#-ban. Tanulja
  meg beállítani az XDimension-t, módosítani az oldalarányt, és PNG képeket exportálni
  egy vonalkód-generátorral.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: hu
lastmod: 2026-10-02
og_description: Készítsen rétegezett adatcsíkok vonalkódot C#-ban egy teljes kódrészlettel.
  Állítsa be az XDimension-t, módosítsa az arányt, és néhány sorban mentse PNG fájlokként.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Rétegezett adatcsíkos vonalkód létrehozása C#-ban – gyors útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Rétegezett adatcsíkos vonalkód létrehozása C#‑ban – lépésről‑lépésre útmutató
url: /hu/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rétegezett DataBar vonalkód létrehozása C#‑ban – lépésről‑lépésre útmutató

Ha **rétegezett DataBar vonalkódot** kell létrehoznod egy .NET projektben, ez az útmutató pontosan megmutatja, hogyan. Megtanulod, hogyan állítsd be az X‑dimenziót, változtasd az arányokat, és mentsd el az eredményt PNG fájlokként – mindezt az Aspose.BarCode könyvtárral.

A rétegezett DataBar vonalkód generálásához nem szükséges összetett grafikai csővezeték. A útmutató végére két kész PNG képed lesz, amelyek különböző arányokat mutatnak, és megérted, miért fontosak ezek a paraméterek a beolvasási megbízhatóság szempontjából.

## Amire szükséged lesz

- .NET 6.0 vagy újabb (a kód .NET Framework 4.6+‑vel is működik)
- Visual Studio 2022 vagy bármely C# IDE
- **Aspose.BarCode for .NET** NuGet csomag  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Írási jogosultság egy olyan mappához, ahol a PNG fájlok mentésre kerülnek

## 1. lépés: A projekt beállítása és a névterek importálása

Hozz létre egy új konzolos alkalmazást (vagy add hozzá a kódot egy meglévő projekthez), és importáld a szükséges névtereket:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Miért fontos:** `Aspose.BarCode.Generation` biztosítja a `BarcodeGenerator` osztályt, míg az `Aspose.BarCode` tartalmazza a képek mentéséhez használt `BarCodeImageFormat` felsorolást.

## 2. lépés: A generátor inicializálása rétegezett omnidirekcionális DataBar-hoz

A `EncodeTypes.DatabarStackedOmniDirectional` érték választja ki a rétegezett DataBar szimbólumot. Az adatkarakterláncnak a GS1 Alkalmazási Azonosító (AI) formátumnak kell megfelelnie; itt egy dummy GTIN‑14 értéket használunk.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Miért fontos:** A kiválasztott kódolási típus azt mondja a könyvtárnak, hogy *rétegezett* vonalkódot jelenítsen meg, ami elengedhetetlen a magas sűrűségű címkék esetén, ahol a függőleges hely korlátozott.

## 3. lépés: A modul (X‑dimenzió) méretének meghatározása pixelekben

Az X‑dimenzió szabályozza a legkisebb vonal (a „modul”) szélességét. A 2 pixel érték a legtöbb képernyő‑felbontású kimenetnél jól működik.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Miért fontos:** A szkennerek a modul szélességét alapmértékegységként értelmezik. Túl kicsi érték elmosódott nyomatot eredményezhet; túl nagy pedig feleslegesen helyet foglal.

## 4. lépés: Az első kép mentése 15‑ös aránnyal

Az `AspectRatio` tulajdonság befolyásolja az egyes rétegezett szegmensek magasság‑szélesség arányát. A 15‑ös arány gyakori alapértelmezett a kiskereskedelmi alkalmazásoknál.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Miért fontos:** Az alacsonyabb arány laposabb vonalkódot eredményez, ami bizonyos címkanyomatok esetén könnyebben beolvasható lehet. A PNG formátum veszteségmentes minőséget biztosít a teszteléshez.

## 5. lépés: Az arány módosítása 30‑ra és a második kép mentése

Az arány növelése magasabbá teszi az egyes rétegezett szegmenseket, ami javíthatja a beolvasási megbízhatóságot alacsony kontrasztú háttéren.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Miért fontos:** Különböző kiskereskedők vagy logisztikai partnerek specifikus vonalkódméreteket igényelhetnek. Mindkét verzió biztosítása lehetővé teszi a beolvasási teljesítmény gyors összehasonlítását.

## Teljes, futtatható példa

Az alábbiakban a teljes program látható, amelyet beilleszthetsz a `Program.cs`‑be. A telepített Aspose.BarCode NuGet csomag után módosítás nélkül fordítható és futtatható.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Várt kimenet

A program futtatása két fájlt hoz létre a végrehajtási mappában:

| Fájlnév                     | Arány | Vizualizáció leírása |
|-----------------------------|-------|----------------------|
| `DatabarAspectRatio15.png`  | 15    | Rövidebb, laposabb rétegezett vonalkód |
| `DatabarAspectRatio30.png`  | 30    | Magasabb, hosszabbra nyúlt rétegezett vonalkód |

A PNG fájlokat bármely képmegjelenítővel megnyithatod, hogy ellenőrizd, a vonalkód helyesen jelenik‑e meg.

![Create stacked databars barcode example](placeholder-image.png){alt="Rétegezett DataBar vonalkód példa"}

## Gyakori kérdések és szélhelyzetek

| Kérdés | Válasz |
|--------|--------|
| **Használhatok más X‑dimenziót?** | Igen. A tipikus értékek 1‑től 4 pixelig terjednek. A nagyobb értékek növelik a vonalkód méretét, de javíthatják az olvashatóságot alacsony felbontású nyomtatókon. |
| **Mi van, ha más szimbólumra van szükségem?** | Cseréld le a `EncodeTypes.DatabarStackedOmniDirectional` értéket egy másik `EncodeTypes` értékre, például `DatabarStacked` (nem omnidirekcionális) vagy `DatabarLimited`. |
| **Hogyan változtathatom meg a kimeneti formátumot?** | Használd a `BarCodeImageFormat.Jpeg`, `Gif` vagy `Bmp` értékeket a `Save` hívásban. |
| **Kötelező a GTIN‑14 formátum?** | A DataBar szimbólum numerikus karakterláncot vár, amely megfelelő AI‑val (pl. `(01)` a GTIN‑14‑hez) van előtagolva. Az adatot a felhasználási esetnek megfelelően állítsd be. |
| **Mi van a DPI beállításokkal?** | A generátor figyelembe veszi a `Resolution` tulajdonságot. Magas felbontású nyomtatáshoz állítsd be a `barcodeGen.Parameters.ImageResolution.DpiX` és `DpiY` értékeket megfelelően. |

## Pro tippek

- **Kötegelt generálás:** A mentési logikát egy ciklusba helyezd, és adj neki GTIN‑lista bemenetet, hogy automatikusan több ezer vonalkódot állíts elő.
- **Érvényesítés:** Használd a `barcodeGen.Validate()`‑t a mentés előtt, hogy korán elkapd a hibás adatokat.
- **Teljesítmény:** Ugyanannak a `BarcodeGenerator` példánynak a újrafelhasználása (csak a paraméterek módosítása) gyorsabb, mint minden képhez új objektum létrehozása.

## Következő lépések

Most, hogy **rétegezett DataBar vonalkódot** tudsz létrehozni egyedi arányokkal, érdemes tovább felfedezni:

- Olvasható szöveg hozzáadása a vonalkód alá (`barcodeGen.Parameters.Barcode.CodeText`).
- Exportálás **PDF**‑be nyomtatható címkelapokhoz (`BarCodeImageFormat.Pdf`).
- A generátor integrálása egy web‑API‑ba, hogy igény szerint szolgáltassa a vonalkódokat.
- Kísérletezés más **másodlagos kulcsszavakkal**, például *C# barcode generator* és *barcode aspect ratio*, hogy a megvalósítást specifikus hardverhez finomhangold.

Boldog kódolást, és élvezd az Aspose.BarCode által nyújtott rugalmasságot C# vonalkód projektjeidben!

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd az API további funkcióit és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Rétegezett DataBar vonalkód létrehozása C#‑ban – lépésről‑lépésre útmutató](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [Rétegezett omnidirekcionális DataBar vonalkód C#‑ban – Teljes útmutató](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Hogyan hozzunk létre DataBar PNG képeket C#‑ban és az Aspose.BarCode‑dal](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}