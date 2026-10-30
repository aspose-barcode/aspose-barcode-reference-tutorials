---
category: general
date: 2026-10-28
description: Készítsen vonalkód képet C#-ban gyorsan. Ismerje meg a vonalkódgenerátor
  C# használatát, hogyan állítható be a pixelméret, és hogyan változtatható meg a
  DataBar képaránya.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: hu
lastmod: 2026-10-28
og_description: Készítsen vonalkód képet C#-ban egy vonalkód-generátorral. Kövesse
  ezt az útmutatót a pixelméret beállításához, az arány módosításához, és a DataBar
  vonalkódok generálásához.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Vonalkód kép létrehozása C#‑ban – lépésről lépésre útmutató
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Hogyan készítsünk vonalkód képet C#-ban a Barcode Generator használatával
url: /hu/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre vonalkód képet C#-ban a Barcode Generator használatával

Ha **vonalkód képet** kell létrehoznod egy .NET alkalmazásban, ez az útmutató pontosan megmutatja, hogyan teheted meg. Egy teljes, futtatható példát láthatsz, amely a Barcode Generator C# könyvtárat használja egy DataBar stacked omnidirectional vonalkód generálásához, a pixelméret beállításához és az arány módosításához.

A vonalkódok programozott generálása megszünteti a külső eszközök szükségességét, és lehetővé teszi a kép közvetlen beágyazását PDF-ekbe, jelentésekbe vagy UI vezérlőkbe. Az alábbi lépésekben bemutatjuk, **hogyan állítsd be a pixelméretet** és **hogyan változtasd meg az arányt**, a két gyakori követelményt, amikor éles, megfelelően méretezett vonalkódra van szükség.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy a következők telepítve vannak:

* .NET 6.0 SDK vagy újabb  
* C#‑kompatibilis IDE (Visual Studio, Rider vagy VS Code)  
* A `BarcodeGenerator` NuGet csomag (pl. `GroupDocs.Barcode` vagy `Aspose.Barcode`) a projektedben telepítve  

A csomagot a következő paranccsal adhatod hozzá:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tipp:** Ellenőrizd, hogy a csomag verziója megegyezik a célkeretrendszerrel, hogy elkerüld a futásidejű inkompatibilitásokat.

## Vonalkód kép létrehozása a Barcode Generator C#-val

Az első lépés a generátor példányosítása a kívánt vonalkódtípussal és adattal. Az alábbi példa egy **DataBar stacked omnidirectional** vonalkódot hoz létre, amely ideális a kiskereskedelmi beolvasási szcenáriókhoz.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Miért fontos minden sor

* **`BarcodeGenerator` példányosítása** – A konstruktor egy vonalkód szimbólumot (`EncodeTypes.DatabarStackedOmniDirectional`) és a nyers adatstringet várja. A megfelelő szimbólum kiválasztása biztosítja, hogy a szkenner beolvassa a kódot.  
* **`XDimension.Pixels` beállítása** – Ez a tulajdonság szabályozza a legkisebb vonal elem szélességét. A `2` érték finom részletességű képet eredményez, amely a legtöbb képernyőn olvasható marad. Növeld ezt az értéket, ha nagyobb vonalkódra van szükséged alacsony felbontású nyomtatókhoz.  
* **`AspectRatio` konfigurálása** – A DataBar család több arányt támogat, amelyek a magasság‑szélesség arányt befolyásolják. A `15` és `30` értékek gyakoriak; a `15` rövidebb vonalkódot ad, míg a `30` magasabbat.  
* **`Save` metódus** – Elmenti a generált vonalkódot PNG fájlba. A `BarCodeImageFormat.Png` helyett használhatod a `Jpeg` vagy `Bmp` formátumot, ha a downstream rendszer más formátumot igényel.

## Hogyan állítsuk be a pixelméretet különböző megjelenítési kontextusokban

A pixelméret határozza meg a vonalkód vizuális sűrűségét. Ha a vonalkód nagy‑DPI monitoron jelenik meg, növelheted a pixelméretet `3`‑ra vagy `4`‑re. Ezzel szemben alacsony felbontású termikus nyomtatók esetén egy kisebb pixelméret (pl. `1`) csökkenti a tinta fogyasztását.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Szélsőséges eset:** A pixelméret túl alacsonyra (< 1) állítása `ArgumentOutOfRangeException`‑t dob. Mindig ellenőrizd az értéket, mielőtt hozzárendeled.

## Hogyan változtassuk meg az arányt a generátor újra létrehozása nélkül

Az arány módosítása egyszerű tulajdonság‑frissítés; **nem** kell újra példányosítani a `BarcodeGenerator`‑t. Ez memóriát takarít meg és javítja a teljesítményt, ha több képet kell előállítanod különböző formákkal.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Ha kettőnél több arányra van szükséged, egy tömbön keresztül is ciklizálhatsz:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Várt kimenet

A program futtatása két PNG fájlt hoz létre (vagy többet, ha a ciklust használod). Nyisd meg őket bármelyik képnézőben; egy tiszta DataBar vonalkódot kell látnod:

* **DatabarAspectRatio15.png** – rövid, széles vonalkód, amely szűk címkeléspontokhoz alkalmas.  
* **DatabarAspectRatio30.png** – magasabb vonalkód, amely javítja a szkennelés megbízhatóságát szögelt szkennereknél.

Mindkét kép ugyanazt a pixelméretet (2 px modulonként) használja, de csak a magasságban tér el, bemutatva, **hogyan változtassuk meg az arányt** miközben a többi paraméter állandó marad.

## Gyakori hibák és elkerülésük

| Tünet | Ok | Megoldás |
|-------|----|----------|
| A vonalkód elmosódott | `XDimension.Pixels` túl alacsony a kimeneti felbontáshoz | Növeld a pixelméretet legalább `2`-re képernyőn, `3`-ra nyomtatáshoz |
| A szkenner nem olvassa a kódot | Hibás `EncodeTypes` a adatformátumhoz | Ellenőrizd, hogy a GTIN‑14 adat megfelel a választott szimbólumnak |
| `ArgumentOutOfRangeException` az arány beállításakor | Az arányérték nem támogatott a könyvtárban (érvényes tartomány: 15‑30) | Csak a könyvtár dokumentációjában szereplő értékeket használd, vagy kezeld a kivételt és állíts be alapértelmezettet |
| Fájl nem található a `Save` után | Relatív útvonal egy nem létező könyvtárra mutat | Használj abszolút útvonalat vagy előtte hívd meg a `Directory.CreateDirectory`‑t |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Következő lépések – a vonalkód munkafolyamat kibővítése

Miután **vonalkód képet** tudsz létrehozni, érdemes lehet:

* **A PNG beágyazása PDF-be** egy olyan könyvtár segítségével, mint a `PdfSharp` vagy az `iTextSharp`.  
* **Más szimbólumok generálása** (QR, Code128, PDF417) az `EncodeTypes` enum módosításával.  
* **Színtranszformációk alkalmazása** a `barcode.Parameters.Barcode.Image.Color` elérésével.  
* **A kép kiszolgálása egy ASP.NET Core végponton** a webalkalmazásokban való „on‑the‑fly” generáláshoz.

Ezek a témák mind ugyanazokra az alapvető koncepciókra épülnek, amelyeket ebben a tutorialban bemutattunk, például a **barcode generator c#** használatára, a pixelméret vezérlésére és az arány manipulálására.

## Összegzés

Most már tudod, hogyan **hozz létre vonalkód képet** C#‑ban a Barcode Generator segítségével, hogyan állítsd be a pixelméretet, hogyan változtasd meg az arányt, és hogyan generálj DataBar vonalkódokat hatékonyan. A teljes, futtatható példát bármely .NET projektbe be lehet másolni, más szimbólumokra adaptálni, és a valós munkafolyamatokhoz igazítani.

Nyugodtan kísérletezz különböző `XDimension` értékekkel, arányokkal és kimeneti formátumokkal. Ha problémába ütközöl, nézd meg újra a „Gyakori hibák” táblázatot, vagy olvasd el a könyvtár hivatalos dokumentációját a mélyebb konfigurációs lehetőségekért. Boldog kódolást!

## Mit tanulj meg legközelebb?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}