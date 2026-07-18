---
category: general
date: 2026-07-18
description: Hogyan állítsuk be a hibaszintet a PDF417 vonalkódban az Aspose.BarCode
  használatával. Tanulja meg, hogyan generáljon PDF417 vonalkódot egyedi szöveggel,
  és percek alatt állítsa be a hibajavítást.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: hu
lastmod: 2026-07-18
og_description: Hogyan állítsuk be gyorsan a hibajavítási szintet a PDF417 vonalkódnál.
  Ez az útmutató végigvezet a PDF417 vonalkód egyedi szöveggel és különböző hibajavítási
  szintekkel történő létrehozásán.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Hogyan állítsuk be a hibaszintet a PDF417 vonalkódnál – Lépésről lépésre
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Hogyan állítsuk be a hibaszintet a PDF417 vonalkódban – Teljes útmutató
url: /hu/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód hibaszint beállítása – Teljes útmutató

Gondolkodtál már azon, **hogyan állítsd be a hibát**, amikor PDF417 vonalkódot generálsz? Nem vagy egyedül – a legtöbb fejlesztő ebbe a problémába ütközik, amikor egy robusztusabb vonalkódra van szükség a nehéz környezetben történő beolvasáshoz. A jó hír? Az error‑correction szint beállítása gyerekjáték az Aspose.BarCode-dal, és emellett megtanulod, **hogyan generálj PDF417‑et** a saját egyedi szövegeddel is.

Ebben az útmutatóban lépésről lépésre végigvezetünk, az egyedi karaktereket tartalmazó vonalkód-generátor létrehozásától a két PNG fájl mentéséig, amelyek különböző hibajavítási szinteket mutatnak be. A végére magabiztosan fogsz tudni **PDF417 vonalkódot generálni**, finomhangolni az X‑dimenzióját, az oszlopszámot, és ami a legfontosabb, **a hibabeállítás** szintjét, amelyek megfelelnek az igényeidnek.

## Előfeltételek

- .NET 6.0 vagy újabb (a kód .NET Framework‑kel is működik)
- Aspose.BarCode for .NET telepítve (`Install-Package Aspose.BarCode` a NuGet‑en keresztül)
- Egy mappa a lemezen, ahová a képek írásra kerülnek (cseréld le a `YOUR_DIRECTORY/` értéket a példában)
- Alap C# tudás – ha már írtál `Console.WriteLine`‑t, akkor már indulhatsz

> **Pro tipp:** Ha mobil beolvasást célozol, válassz magasabb hibaszintet (Level 5), hogy ellenálljon a szennyeződésnek, karcolásoknak vagy gyenge fényviszonyoknak.

## 1. lépés: Barcode generátor létrehozása egyedi szöveggel

Az első dolog, amire szükséged van, egy `BarcodeGenerator` példány, amely tudja, hogy **PDF417 vonalkódot** kell előállítania, és amely a pontosan kódolni kívánt szöveget tartalmazza. Figyeld meg a hangsúlyos karakterek és a szerzői jogi szimbólum használatát – ez bizonyítja, hogy a generátor natívan kezeli a Unicode‑ot.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Miért fontos:* A `EncodeTypes.Pdf417` jelző azt mondja az Aspose‑nak, hogy egy 2‑D rétegezett vonalkódról van szó, míg a string argumentum az adatpayload lesz. Ha kihagyod ezt a lépést, egy alapértelmezett Code128 vonalkódot kapsz a szükséges nagy kapacitású PDF417 helyett.

## 2. lépés: A vizuális paraméterek finomhangolása

A PDF417 vonalkód nem csak adat, hanem egy vizuális minta is. Az **X‑dimenzió** (a legkisebb vonal szélessége) és a **oszlopok** számának beállítása lehetővé teszi a vonalkód fizikai méretének és olvashatóságának szabályozását.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Miért fontos:* A kisebb X‑dimenzió kompaktabb képet eredményez, de alacsony felbontású szkennereknél olvashatatlanná válhat. Három oszlop kiegyensúlyozott képarányt biztosít a legtöbb címkemérethez.

## 3. lépés: Hibajavítási szint beállítása 2‑re és mentés

A hibajavítás a **hogyan állítsuk be a hibát** PDF417‑nél központi szerepet játszik. A `Pdf417ErrorLevel` felsorolás `Level0`‑tól (nincs extra adat) `Level5`‑ig (maximális redundancia) terjed. Itt **Level 2**‑vel kezdünk, amely mérsékelt hibavédelmet ad anélkül, hogy túl nagyra növelné a képet.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

A kódrészlet futtatása után a `Pdf417ErrorLevel2.png` fájlt megtalálod a mappádban. Nyisd meg, és egy tiszta, három oszlopos vonalkódot látsz, amely még mindig megfelelő mennyiségű redundanciát tartalmaz.

## 4. lépés: Hibajavítás növelése Level 5‑re és újra mentés

Néha a vonalkódnak erősebb sérülés ellen kell ellenállnia – gondolj egy raktárpadlóra, ahol a címkék megkarcolódnak. **Level 5**‑re váltás maximalizálja a hibajavítást, cserébe egy kissé nagyobb képet eredményez.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Most már két PNG fájlod van egymás mellett: az egyik mérsékelt hibajavítással, a másik a maximummal. Hasonlítsd össze őket; az Level 5 verzió több sötét modult tartalmaz, ami pontosan azt a módot jelenti, amivel az algoritmus védi az adatot.

![hogyan állítsuk be a hibaszintet PDF417 vonalkódban példa](image.png)

*Kép leírása (alt szöveg): hogyan állítsuk be a hibaszintet PDF417 vonalkódban – két PNG fájlt mutat, különböző hibajavítási szintekkel.*

## Várt kimenet

| Fájl neve                     | Hibaszint   | Kb. méretek (px) |
|-------------------------------|-------------|--------------------------|
| `Pdf417ErrorLevel2.png`       | Level 2     | 150 × 80                 |
| `Pdf417ErrorLevel5.png`       | Level 5     | 180 × 95                 |

Mindkét kép a **„Åspóse.Barcóde©”** karakterláncot kódolja, és bármely szabványos PDF417 olvasóval beolvasható (pl. ZXing, Scandit). Az Level 5 kép körülbelül ~30 % sérülést bír el, míg a Level 2 körülbelül ~15 %-ot.

## Gyakori kérdések és szélhelyzetek

### Mi van, ha a szövegem sortöréseket tartalmaz?

A PDF417 automatikusan kódolja a sortörés (`\n`) karaktereket. Csak helyezd be őket a stringbe:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Használhatok másik képformátumot?

Természetesen. Cseréld le a `BarCodeImageFormat.Png`‑t `Jpeg`‑re, `Bmp`‑re vagy `Svg`‑re, a downstream munkafolyamatodtól függően.

### Befolyásolja az X‑dimenzió módosítása a hibajavítást?

Közvetve igen. A nagyobb X‑dimenzió nagyobb modulokat eredményez, ami javíthatja a beolvasási megbízhatóságot, de **nem** változtatja meg a logikai hibajavítási szintet. A legjobb eredményért állítsd be mindkét paramétert függetlenül.

### Hogyan generáljunk PDF417 vonalkódot egy web API‑ban?

Tedd ugyanazt a kódot egy ASP.NET Core vezérlőbe, és streameld vissza a PNG‑t `FileResult`‑ként. A fő logika változatlan marad, ami azt jelenti, hogy **hogyan generáljunk PDF417‑et** konzisztens marad asztali és webes környezetben is.

## Összefoglalás

Áttekintettük, **hogyan állítsuk be a hibát** egy PDF417 vonalkódban, bemutattuk, **hogyan generáljunk PDF417‑et** egyedi Unicode szöveggel, és megmutattuk, hogyan hangolhatók a vizuális beállítások, mint az X‑dimenzió és az oszlopszám. A `Pdf417ErrorLevel.Level2` és `Level5` cseréjével szabályozhatod a kép mérete és a robusztusság közötti kompromisszumot.

## Következő lépések

- Kísérletezz a **vonalkód egyedi szöveggel**‑el, amely URL-eket vagy termékazonosítókat tartalmaz.
- Próbálj ki különböző oszlopszámokat (`generator.Parameters.Barcode.Pdf417.Columns = 5`), hogy lásd, hogyan változik a forma.
- Kombináld a PDF417‑et más vonalkód típusokkal ugyanabban a dokumentumban a többmodalitású beolvasási megoldásokhoz.
- Merülj el az Aspose [hivatalos dokumentációjában](https://docs.aspose.com/barcode/net/), ahol fejlett funkciók, például macro PDF417 vagy kompakt mód található.

Nyugodtan hagyj megjegyzést, ha elakadsz, vagy oszd meg a saját beolvasott eredményeidet. Boldog vonalkód készítést!

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre vonalkódot – Kompakt PDF417 az Aspose.BarCode‑dal](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan hozzunk létre Aztec vonalkódot hibajavítással .NET‑ben](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Hogyan generáljunk DataMatrix vonalkódokat (ECC 200) az Aspose.BarCode for .NET‑vel](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}