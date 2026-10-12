---
category: general
date: 2026-09-29
description: A C#-os vonalkódgenerátor útmutató bemutatja, hogyan lehet MicroPdf417
  vonalkódot generálni, módosítani a méreteket, beállítani az oszlopokat, és néhány
  sorban testre szabni a vonalkód méretét.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: hu
lastmod: 2026-09-29
og_description: A C# vonalkód-generátor útmutató bemutatja, hogyan generáljunk MicroPdf417
  vonalkódot, módosítsuk a méreteket, állítsuk be az oszlopokat, és testre szabjuk
  a vonalkód méretét néhány sorban.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: C# vonalkód-generátor útmutató – MicroPdf417 létrehozása és testreszabása
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Vonalkód-generátor C# útmutató: MicroPdf417 létrehozása'
url: /hu/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# vonalkód generátor útmutató: MicroPdf417 létrehozása

Ha **barcode generator C#**-ra van szükséged .NET projektedhez, ez az útmutató lépésről lépésre bemutatja, hogyan hozhatsz létre egy MicroPdf417 vonalkódot a semmiből. Megtanulod, hogyan **generálj vonalkódot**, módosítsd a méreteket, állítsd be az oszlopokat, és **testre szabhatod a vonalkód méretét** könnyedén.

MicroPdf417 egy kompakt 2‑D szimbólum, amely jól használható kis alkatrészek, jegyek vagy készletcímkék címkézésére. A útmutató végére egy teljes, futtatható konzolalkalmazásod lesz, amely PNG képet generál a vonalkódról, és megérted, hogyan befolyásolja minden paraméter a végső méretet.

## Előkövetelmények

* .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.7+‑tel is működik)
* C#‑kompatibilis IDE (Visual Studio, VS Code, Rider, stb.)
* A **GroupDocs.Barcode** NuGet csomag – telepítsd a következővel  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Nem szükséges további külső eszköz, a könyvtár kezeli a kódolást, a renderelést és a fájl mentését.

## Barcode generator C#: a generátor inicializálása

Az első lépés egy `BarcodeGenerator` példány létrehozása, és a szimbólum (`EncodeTypes.MicroPdf417`) megadása a kódolni kívánt adatokkal együtt.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Miért fontos:**  
`BarcodeGenerator` az összes vonalkód művelet belépési pontja. A konstruktor a kiválasztott **EncodeTypes** (MicroPdf417) értéket a nyers adatstringhez köti. A könyvtár automatikusan kezeli az Unicode karaktereket, mint például a “Å” és a “©”, így nem szükséges extra kódolási logika.

## Hogyan változtassuk meg a vonalkód méreteit

A vonalkód olvashatósága nagymértékben a modul szélességétől (az X‑dimenziótól) függ. Ha nagyobb pixel számra állítod, a vonalak szélesebbek lesznek, és a kép könnyebben beolvasható, különösen alacsony felbontású kijelzőkön.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Magyarázat:**  
`XDimension.Pixels` szabályozza egyetlen vonalkód modul szélességét. Alapértelmezésben 1 pixel, ami magas DPI‑ű monitorokon vékonynak tűnhet. 2 pixelre növelve a teljes szélesség duplájára nő anélkül, hogy a kódolt adatot befolyásolná.

**Tipp:** Ha a vonalkódot 300 dpi‑n szeretnéd nyomtatni, a 3 vagy 4 pixel érték gyakran a legjobb egyensúlyt biztosítja a méret és a beolvasási megbízhatóság között.

## Hogyan állítsuk be az oszlopok számát a méret szabályozásához

A MicroPdf417 lehetővé teszi az oszlopok számának megadását (legfeljebb 4). Kevesebb oszlop magasabb vonalkódot eredményez; több oszlop szélesebb, de alacsonyabb lesz. Ennek az értéknek a módosítása az elsődleges módja a **vonalkód méretének testreszabásának**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Miért működik:**  
A `Pdf417.Columns` tulajdonság minden PDF417‑alapú szimbólumra érvényes, beleértve a MicroPdf417‑t is. A maximális (4) értékre állítva a data a legszélesebb elrendezésbe oszlik, csökkentve a teljes magasságot. Ha kompaktabb magasságra van szükséged, csökkentsd az oszlopszámot 2‑re vagy 3‑ra.

**Szélső eset:** Ha az adatstring hosszú, a könyvtár automatikusan növelheti a sorok számát a tartalom befogadásához, függetlenül az oszlopszámtól. A kiszámítható méretezéshez tartsd a terhet 50 karakter alatt.

## A vonalkód méretének testreszabása különböző kimenetekhez

Az X‑dimenzió és az oszlopok mellett a végső kép méretét befolyásolhatod a megfelelő képformátum és DPI kiválasztásával. A PNG veszteségmentes, tökéletes webes megjelenítéshez, míg a BMP vagy TIFF előnyösebb lehet magas minőségű nyomtatáshoz.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Ha magasabb DPI‑ra van szükséged, explicit módon beállíthatod:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Eredmény:** A mentett PNG fájl egy éles MicroPdf417 vonalkódot tartalmaz, amely tiszteletben tartja a beállított méreteket. Nyisd meg a fájlt bármely képnézőben a vizuális méret ellenőrzéséhez.

### Várható kimenet

A program futtatása egy **MicroPdf417.png** nevű fájlt hoz létre (vagy **MicroPdf417_300dpi.png**‑t, ha DPI‑t állítottál be). A vonalkód a lenti ábrához hasonlóan fog kinézni:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *C# vonalkód generátor kimenete, MicroPdf417 PNG*

A kép beolvasása egy szabványos 2‑D vonalkódolvasóval visszaadja az eredeti `Åspóse.Barcóde©` stringet.

## Teljes forráskód gyors másoláshoz

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Másold a kódot egy új konzolprojektbe, állítsd vissza a NuGet csomagokat, és futtasd a `dotnet run` parancsot. A konzol megerősíti a kép helyét, és a projekt mappádban láthatod a generált vonalkódot.

## Gyakori kérdések és hibaelhárítás

| Question | Answer |
|----------|--------|
| **Mi van, ha a vonalkód elmosódott?** | Növeld a `XDimension.Pixels` értékét vagy a DPI‑t (`Parameters.Image.DpiX/Y`). Mindkettő nagyobbá teszi a modulokat és javítja a vizuális hűséget. |
| **Használhatok másik képformátumot?** | Igen. Cseréld le a `BarCodeImageFormat.Png` értéket `Jpeg`, `Bmp` vagy `Tiff`-re. A PNG továbbra is a legbiztonságosabb választás veszteségmentes minőséghez. |
| **Az adataim emoji‑kat tartalmaznak—kódolódnak?** | A MicroPdf417 támogatja az UTF‑8-at, így a legtöbb emoji helyesen kódolódik. Ha hibákat tapasztalsz, ellenőrizd, hogy a string megfelelően normalizált-e (`System.Text.Encoding.UTF8`). |
| **Hogyan generálhatok más szimbólumokat?** | Cseréld le a `EncodeTypes.MicroPdf417` értéket bármely más értékre az `EncodeTypes`-ból ( |

## Mit érdemes még megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [Hogyan generáljunk vonalkód képet C#‑ban – MicroPdf417 útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Hogyan generáljunk PDF417 vonalkódot C#‑ban egyedi méretekkel](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}