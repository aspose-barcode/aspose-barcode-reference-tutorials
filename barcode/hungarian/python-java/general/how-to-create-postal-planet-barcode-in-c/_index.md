---
category: general
date: 2026-11-23
description: Hozzon létre postai planet vonalkódot C#‑ban az Aspose.BarCode segítségével.
  Tanulja meg, hogyan generáljon planet vonalkódot, állítsa be az X‑dimenziót, és
  mentse a kitöltött vagy üres sávokat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: hu
lastmod: 2026-11-23
og_description: Hozzon létre postai planet vonalkódot C#-ban, és tanulja meg, hogyan
  generáljon planet vonalkódot az Aspose.BarCode segítségével. Kövesse a teljes példát
  a kitöltött és üres sávok előállításához.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Hogyan készítsünk postai Planet vonalkódot C#-ban – lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hogyan készítsünk postai Planet vonalkódot C#‑ban
url: /hu/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan készítsünk postai Planet vonalkódot C#-ban

Ha .NET alkalmazásban **postal planet barcode**-t kell **létrehoznod**, ez az útmutató pontosan megmutatja, **hogyan generálj planet vonalkódot** az Aspose.BarCode könyvtár segítségével. Meg fogod látni, hogyan konfigurálhatod az X‑dimenziót, válthatsz a kitöltött és az üres vonalak között, és mentheted a képeket PNG formátumban.

A Planet vonalkód generálása gyakori a postai szolgáltatásoknál, amelyek nagy sűrűségű, géppel olvasható szimbólumokat igényelnek. A tutorial végére két PNG fájlod lesz – egy szilárd vonalakkal, egy üreges vonalakkal – készen állva bármely postai munkafolyamatba való integrálásra.

## Előkövetelmények

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel a következőkkel:

* .NET 6.0 SDK vagy újabb telepítve.
* Visual Studio 2022 (vagy bármely C# szerkesztő) .NET fejlesztéshez beállítva.
* Aktív NuGet licenc az **Aspose.BarCode for .NET**-hez. A csomagot a következő paranccsal telepítheted:

```bash
dotnet add package Aspose.BarCode
```

Nem szükséges semmilyen külső szolgáltatás; a könyvtár minden kódolást helyben végez.

## 1. lépés – postal planet barcode létrehozása

Az első művelet egy `BarcodeGenerator` példányosítása a **Planet** szimbólumhoz, valamint a kódolandó adat megadása. Az adatkarakterláncnak numerikusnak kell lennie, és legfeljebb 12 számjegyet tartalmazhat a postai specifikáció szerint.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

A generátor létrehozása lefoglalja a megjelenítéshez szükséges összes belső struktúrát. Az `EncodeTypes.Planet` enum érték a megfelelő kódolási algoritmust választja a postai formátumhoz.

## 2. lépés – X‑dimenzió beállítása a jobb láthatóságért

Az X‑dimenzió egyetlen modul (a legkisebb vonalelem) szélességét határozza meg. A 4 pixel érték tiszta vizuális ábrázolást biztosít anélkül, hogy a teljes kép méretét növelné.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Az X‑dimenzió beállítása elengedhetetlen, ha a vonalkódot alacsony felbontású anyagra nyomtatják. Ugyanezt a beállítást használjuk az üres‑vonalkód verzióhoz is, hogy mindkét kép konzisztens legyen.

## 3. lépés – vonalkód mentése kitöltött vonalakkal

Alapértelmezés szerint a generátor **kitöltött vonalakat** (szilárd fekete modulokat) jelenít meg. A kép mentése egyetlen metódushívással történik, amely a PNG fájlt a lemezre írja.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Cseréld le a `YOUR_DIRECTORY`-t arra az elérési útra, ahová a kimeneti fájlokat szeretnéd menteni. A `BarCodeImageFormat.Png` enumeráció veszteségmentes tömörítést garantál, ami ideális a további feldolgozáshoz.

## 4. lépés – másik Planet vonalkód generátor létrehozása üres vonalakhoz

Egy **üres vonalakkal** (fehér modulok fekete háttéren) rendelkező verzió előállításához szükség van egy második `BarcodeGenerator` példányra. Ugyanannak az adatkarakterláncnak a használata biztosítja, hogy mindkét kép azonos postai kódot ábrázoljon.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Külön generátor létrehozása elkülöníti a `FilledBars` tulajdonságot, lehetővé téve a vizuális stílus átkapcsolását anélkül, hogy az első képet befolyásolná.

## 5. lépés – a generátor konfigurálása üres vonalak megjelenítésére

A `FilledBars` jelző megfordítja a megjelenítési módot. `false` értékre állítva a könyvtár a vonalakat üres (átlátszó) módon rajzolja, miközben a háttér szilárd marad.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Az X‑dimenzió azonos megtartása a kitöltött verzióval garantálja, hogy mindkét PNG fájl ugyanazokkal a méretekkel rendelkezzen, ami egyszerűsíti a nyomtatási sablonok elrendezésének számítását.

## 6. lépés – vonalkód mentése, amely üres vonalakat jelenít meg

Végül írd ki az üres‑vonalkép fájlt a lemezre. Ugyanazt a PNG formátumot használjuk, de a `BarCodeImageFormat` érték megváltoztatásával átállíthatod JPEG‑re vagy BMP‑re is.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Ekkor két fájlod lesz:

* `PostalPlanetFilledBars.png` – szilárd fekete vonalakkal.
* `PostalPlanetEmptyBars.png` – üreges vonalakkal fekete háttéren.

Mindkettő megfelel a postai specifikációnak a Planet szimbólumra vonatkozóan.

## Teljes forráskód

Az összes lépés egy kompakt konzolos alkalmazásba integrálva így néz ki:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Fordítsd le és futtasd a programot:

```bash
dotnet run
```

A konzol kiírja: *Barcodes generated successfully.* és a két PNG fájl megjelenik a projekt mappájában.

## Várt kimenet

Alább látható a kitöltött‑vonalkép vizuális ábrázolása. Az üres‑vonalkép azonos, csak a vonalak átlátszóak.

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*Image alt text:* **Example of a created postal planet barcode with filled bars** (contains the primary keyword).

Mindkét kép alapértelmezés szerint 150 × 150 pixel, de a `ImageWidth` és `ImageHeight` paraméterekkel szabályozhatod a teljes méretet, ha más felbontásra van szükség.

## Opcionális variációk

### Képformátum megváltoztatása

Ha a downstream rendszer JPEG-et preferál, cseréld le a `BarCodeImageFormat.Png`-t `BarCodeImageFormat.Jpeg`-re. A JPEG tömörítési hibákat vezet be, ezért csak akkor használd, ha a fájlméret kritikus korlát.

### A vonalkód méretezése

A vonalkód nagyítható a modul szélességének megtartásával a `Resolution` tulajdonság módosításával:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

A magasabb DPI értékek javítják a nyomtatási minőséget lézernyomtatókon.

### Egyedi háttérszín használata

A háttér beállítható a következő módon:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Ez vizuális teszteléshez hasznos, de a termelési postai címkék esetén kerülni kell, mivel fehér háttér szükséges.

## Gyakran ismételt kérdések

**Működik ez .NET Core-dal?**  
Igen. Az Aspose.BarCode könyvtár a .NET Standard 2.0-ra céloz, amely kompatibilis a .NET 5, .NET 6 és .NET Core 3.1 verziókkal.

**Mi van, ha az adatkarakterlánc nem numerikus?**  
A Planet vonalkódok csak numerikus bemenetet fogadnak el. Betűk vagy szimbólumok megadása `BarcodeException`-t vált ki. Validáld a bemenetet a generátor létrehozása előtt.

**Létrehozhatok vonalkódot memóriában anélkül, hogy leírnám a lemezre?**  
Használd a `GenerateBarCodeImage` metódust, amely egy `System.Drawing.Image` objektumot ad vissza, majd közvetlenül streamelheted egy válaszba vagy adatbázisba.

## Következtetés

Most már tudod, hogyan **hozz létre postal planet barcode**-t C#-ban, és megérted, **hogyan generálj planet vonalkódot** mind kitöltött, mind üres vonalstílussal. A tutorial lefedte a teljes munkafolyamatot – a generátor inicializálásától, az X‑dimenzió konfigurálásán, a `FilledBars` flag átkapcsolásán, egészen a PNG fájlok mentéséig. Kísérletezz képformátumokkal, DPI beállításokkal és háttérszínekkel, hogy a vonalkódot a saját postai rendszeredhez igazítsd.

A következő lépésként fedezd fel a többi postai szimbólumot, például a **POSTNET** vagy **Intelligent Mail** használatát ugyanazzal az Aspose.BarCode API-val. Az `EncodeTypes.Postnet` paraméterek módosítása ugyanazt a mintát követi, lehetővé téve egy átfogó vonalkódgeneráló szuite felépítését egyetlen kódbázisban.

## Mit tanulj meg legközelebb?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljesen működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek az API további funkcióinak elsajátításában és alternatív megvalósítási megközelítések felfedezésében saját projektjeidben.

- [Üres planet vonalkód létrehozása, postai vonalkód generálása C#-ban](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Szélesség beállítása és Planet vonalkód generálása C#-ban](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Postai vonalkód generálása C# – Teljes útmutató Planet vonalkóddal](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}