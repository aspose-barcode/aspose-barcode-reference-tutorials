---
category: general
date: 2026-08-22
description: Hogyan generáljunk gyorsan vonalkódot, és tanuljuk meg, hogyan változtassuk
  meg a vonalkód méretét PNG formátumú kép exportálásakor az Aspose.BarCode használatával.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: hu
lastmod: 2026-08-22
og_description: Hogyan generáljunk vonalkódot C#-ban, és egyszerűen módosítsuk a vonalkód
  méretét, mielőtt PNG-ként exportálnánk a képet. Kövesse ezt a teljes útmutatót.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Hogyan generáljunk egyedi méretű vonalkód képeket C#-ban
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan generáljunk egyedi méretű vonalkód képeket C#‑ban
url: /hu/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkód képeket egyedi mérettel C#-ban

Ha **hogyan generáljunk vonalkódot** postai automatizáláshoz, készletkövetéshez vagy eseményjegyekhez, ez az útmutató egy teljes, azonnal futtatható megoldást mutat be C#-ban. Emellett megtanulhatod, hogyan **változtathatod meg a vonalkód méretét** és **exportálhatod a vonalkód képet** PNG formátumban anélkül, hogy elhagynád a fejlesztői környezetet.

Az Aspose.BarCode könyvtárat fogjuk használni, mivel támogatja a OneCode szimbólumot, lehetővé teszi a méretek pixelről pixelre történő vezérlését, és egyetlen metódushívással kezeli a kép exportálását. A tutorial végére négy PNG fájlod lesz – mindegyik egy OneCode vonalkódot ábrázol különböző számjegyszámmal.

## Előfeltételek

- .NET 6.0 vagy újabb (a kód .NET Framework 4.6+‑al is működik)
- Visual Studio 2022 (vagy bármelyik kedvelt C# szerkesztő)
- NuGet hivatkozás a **Aspose.BarCode**‑ra (`Install-Package Aspose.BarCode`)
- Alapvető ismeretek a C# szintaxisról

> **Pro tipp:** Ha a könyvtárat értékeled, az Aspose ingyenes 30‑napos próbaverziót kínál, amely tartalmazza az összes vonalkód funkciót.

## 1. lépés: Minimalista konzolprojekt beállítása

Hozz létre egy új konzolos alkalmazást, és add hozzá az Aspose.BarCode csomagot:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

A generált `Program.cs` tartalmazni fogja a teljes vonalkód‑generálási logikát.

## 2. lépés: Hogyan generáljunk vonalkódot – újrahasználható metódus létrehozása

Az alábbi önálló metódus megkapja az adatkarakterláncot, a kívánt fájlnevet és opcionális méretparamétereket. Ez a metódus bemutatja a **hogyan generáljunk vonalkódot** alapmintát.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Miért fontos ez a metódus

- **Encapsulation:** Minden mérettel kapcsolatos beállítás egy helyen van, így egyszerű a metódus hívása különböző dimenziókkal.
- **Reusability:** Ugyanazt a metódust bármely OneCode karakterlánc hosszhoz újra felhasználhatod, ami lényeges, mivel a OneCode csak 20‑31 számjegyet fogad el.
- **Clarity:** Az emoji‑val jelölt megjegyzések végigvezetik az olvasót a három logikai fázison – inicializálás, méretváltoztatás és exportálás.

## 3. lépés: A vonalkód méretének módosítása különböző követelményekhez

Néha egy szkenner magasabb vonalkódot vár, vagy egy nyomtatási elrendezés szűkebb modult igényel. Az `XDimension.Pixels` tulajdonság szabályozza egyetlen vonalkódmodul szélességét, míg a `BarHeight.Pixels` a teljes magasságot állítja be.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Fontos pontok a méret módosításakor:**

- **Minimum X‑dimension:** Technikai szempontból 1 pixel megengedett, de a legtöbb szkenner legalább 2 pixelre van szüksége a megbízható olvasáshoz.
- **Maximum height:** Nincs szigorú korlát, de a nagyon magas vonalkódok meghaladhatják a szabványos címkék nyomtatható területét.
- **Aspect ratio:** Tartsd egyensúlyban a magasság‑modul‑szélesség arányt (≈12‑15 × modul szélesség), hogy elkerüld a torzulást.

## 4. lépés: A vonalkód kép exportálása más formátumokba (opcionális)

A `Save` metódus több `BarCodeImageFormat` értéket is elfogad: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Ha veszteségmentes vektorformátumra van szükséged, exportálhatsz `Svg`‑be.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

A PNG‑ként történő exportálás a leggyakoribb választás, mivel megőrzi a tiszta éleket, és széles körben támogatott a webböngészők és nyomtatási folyamatok által.

## Várható kimenet

A program futtatása négy PNG fájlt hoz létre a projekt mappájában:

- `PostalOneCodeBarcode20Digits.png` – 20‑jegyű OneCode vonalkód
- `PostalOneCodeBarcode25Digits.png` – 25‑jegyű OneCode vonalkód
- `PostalOneCodeBarcode29Digits.png` – 29‑jegyű OneCode vonalkód
- `PostalOneCodeBarcode31Digits.png` – 31‑jegyű OneCode vonalkód

Minden kép hasonló lesz az alábbi helyőrzőhöz (a tényleges grafika a megadott numerikus adatoktól függ).

![Hogyan generáljunk vonalkód példát](https://example.com/placeholder.png "Hogyan generáljunk vonalkód példát")

*A kép alt szövege tartalmazza az elsődleges kulcsszót a hozzáférhetőség és SEO érdekében.*

## Gyakori kérdések és szélhelyzetek

| Kérdés | Válasz |
|----------|--------|
| **Mi van, ha az adatkarakterlánc rövidebb, mint 20 számjegy?** | A OneCode minimum 20 számjegyet igényel. Töltsd fel a karakterláncot vezető nullákkal, vagy használj másik szimbólumot (pl. Code128). |
| **Generálhatok vonalkódot több szálon futó környezetben?** | Igen. A `BarcodeGenerator` nem szálbiztos, ezért minden szálnak külön generátort kell példányosítani. |
| **Hogyan állítható be a háttérszín?** | Használd a `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` kódot a `Save` hívása előtt. |
| **Van mód a kép közvetlen beágyazására HTML oldalba?** | Mentsd a képet egy `MemoryStream`‑be, konvertáld Base64‑ra, és ágyazd be a `<img src="data:image/png;base64,..." />` szintaxissal. |

## Következtetés

Most már tudod, hogyan **generálj vonalkód** képeket C#-ban az Aspose.BarCode segítségével, hogyan **változtasd meg a vonalkód méretét** az X‑dimenzió és a vonalmagasság beállításával, és hogyan **exportáld a vonalkód képet** PNG (vagy más) formátumban. Az újrahasználható `GenerateOneCode` metódus lehetővé teszi, hogy egyetlen kódsorral bármely 20 és 31 számjegy közötti OneCode vonalkódot létrehozz.

Innen tovább:

- Kísérletezz más szimbólumokkal (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Integráld a generátort egy web API‑ba, amely igény szerint vonalkód képeket ad vissza.
- Kombináld a PNG kimenetet egy PDF könyvtárral, hogy vonalkódokat ágyazz be a szállítási címkékbe.

Boldog kódolást, és nyugodtan oszd meg saját változataidat a megjegyzésekben!

## Mit érdemes legközelebb megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk DataMatrix vonalkódokat az Aspose.BarCode for .NET használatával – Lépésről‑lépésre útmutató](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hogyan generáljunk Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hogyan generáljunk és állítsuk be a vonalkód magasságát egy dimenziós Databar esetén az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}