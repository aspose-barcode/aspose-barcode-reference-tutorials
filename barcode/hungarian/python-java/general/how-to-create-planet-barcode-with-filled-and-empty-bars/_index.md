---
category: general
date: 2026-09-29
description: Planéta vonalkód létrehozása C#-ban, megtöltött és üres sávokkal – lépésről
  lépésre útmutató az Aspose.Barcode használatával.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: hu
lastmod: 2026-09-29
og_description: Készítsen planet vonalkódot C#‑ban gyorsan. Tanulja meg, hogyan jeleníthet
  meg kitöltött sávokat, válthat üres sávokra, és állíthatja be az X‑dimenziót az
  Aspose.Barcode segítségével.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Planéta vonalkód létrehozása kitöltött és üres sávokkal – C# útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hogyan készítsünk bolygó vonalkódot kitöltött és üres sávokkal
url: /hu/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre Planet vonalkódot kitöltött és üres sávokkal

Ha **Planet vonalkód** képeket szeretnél C#‑ban létrehozni, ez az útmutató pontosan megmutatja, hogyan generálj mind kitöltött, mind üres sávos változatot. Megtanulod, hogyan állítsd be a sáv szélességét (X‑dimenzió), hogyan kapcsolod be a `FilledBars` tulajdonságot, és hogyan mented el az eredményeket PNG fájlokként – mindezt az Aspose.Barcode könyvtárral.

A postai vonalkódok generálása gyakori igény a szállítási rendszerekben, levelezési listák alkalmazásaiban és logisztikai műszerfalakon. A tutorial végére két kész PNG fájlod lesz, amelyeket beágyazhatsz jelentésekbe, e‑mailekbe vagy nyomtatott anyagokba.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel a következőkkel:

| Követelmény | Miért fontos |
|-------------|----------------|
| .NET 6.0 vagy újabb | Biztosítja a futtatókörnyezetet a C# példához. |
| Visual Studio 2022 (vagy bármely C# IDE) | Lehetővé teszi a kód lefordítását és futtatását. |
| **Aspose.Barcode for .NET** NuGet csomag | Tartalmazza a `BarcodeGenerator` osztályt és az `EncodeTypes.Planet` szimbólumot. Telepítheted a `dotnet add package Aspose.Barcode` paranccsal. |
| Írási jogosultság egy mappához a lemezen | A `Save` metódus PNG fájlokat ír a megadott útvonalra. |

## 1. lépés: A projekt beállítása és névterek importálása

Hozz létre egy új konzolos projektet (vagy add hozzá a kódot egy meglévőhöz), és hivatkozz az Aspose.Barcode névtérre.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Ezek a `using` direktívák biztosítják a `BarcodeGenerator`, `EncodeTypes` és a képfájl‑formátum enumok elérését, amelyek a tutorialhoz szükségesek.

## 2. lépés: Planet vonalkód létrehozása alapértelmezett (kitöltött) sávokkal

Az első vonalkód a könyvtár alapértelmezett megjelenítését használja, amely kitölti a sávokat.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Miért működik:**  
Az `EncodeTypes.Planet` azt mondja az Aspose.Barcode‑nak, hogy a **Planet** szimbólumot használja, amely egy az Egyesült Államok Postai Szolgálata által használt postai vonalkód. Az `XDimension` tulajdonság szabályozza minden egyes sáv szélességét; 4 pixelre állítva a vonalkód jól nyomtatható a szabványos címkanyomtatókon. Alapértelmezés szerint a `FilledBars` értéke `true`, így a sávok szilárdak.

## 3. lépés: Planet vonalkód létrehozása üres sávokkal

Ugyanazt az adatot *üres* sávokkal is előállíthatod, csak a `FilledBars` jelzőt kell `false`‑ra állítani, miközben a többi beállítást változatlanul hagyod.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Miért fontos:**  
Néhány levelezési rendszer az **üres‑sáv** stílust igényli a jobb olvashatóság érdekében, ha a vonalkód sötét háttéren vagy kontrasztos színsémával nyomtatott. A `FilledBars = false` beállítással a generátor csak a sávok körvonalát rajzolja, a belső részt átlátszóvá hagyva.

## Várt kimenet

A program futtatása után a `C:\Barcodes` (vagy a választott útvonal) mappában két PNG fájl található:

| Fájl | Vizuális leírás |
|------|---------------------|
| `PlanetFilledBars.png` | A sávok fekete, szilárd téglalapok fehér háttéren. |
| `PlanetEmptyBars.png`  | A sávok fekete körvonalak; minden sáv belseje átlátszó (a háttér látszik). |

Mindkét kép ugyanazt a numerikus `"123456"` karakterláncot kódolja, és 4 pixel sávszélességgel rendelkezik, így a megjelenésük egységes, kivéve a kitöltési stílust.

## Gyakori variációk és szélső esetek

### A sáv szélességének módosítása

Ha a címkanyomtatód más sávszélességet igényel, módosítsd az `XDimension.Pixels` értékét. Magas felbontású nyomtatók esetén a **2** vagy **3** pixel lehet előnyös; alacsony felbontású nyomtatóknál a **5** vagy **6** pixel javíthatja a beolvasási megbízhatóságot.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Más képfájl‑formátum használata

Az Aspose.Barcode támogatja a PNG, JPEG, BMP, GIF és TIFF formátumokat. Cseréld ki a `BarCodeImageFormat.Png` értéket egy másik enumra, hogy illeszkedjen a downstream munkafolyamatodhoz.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Több vonalkód generálása ciklusban

Ha egy csomagot kell előállítanod Planet vonalkódokból (például egy levelezési listához), tedd a generátor logikát egy `foreach` ciklusba, és minden iterációban változtasd az adatkarakterláncot.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Érvénytelen bemenet kezelése

A Planet szimbólum csak **5‑8** számjegyből álló numerikus karakterláncokat fogad el. Érvénytelen érték esetén `ArgumentException` keletkezik. Egy egyszerű validációs metódussal előzheted meg a hibát.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Pro tipp: A vonalkód ellenőrzése szkenner‑emulátorral

Az Aspose.Barcode tartalmaz egy `BarcodeReader` osztályt, amelyet felhasználhatsz annak megerősítésére, hogy a generált kép visszafejti-e az eredeti adatot.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Ha a kimenet mindkét fájlra `"123456"`‑ot mutat, a vonalkód helyesen lett generálva.

## Összegzés

Most már tudod, hogyan **hozz létre Planet vonalkód** képeket C#‑ban kitöltött és üres sáv stílusokkal, hogyan szabályozd a **Planet vonalkód XDimension**‑ját, és hogyan mentsd el az eredményt PNG formátumban az **Aspose.Barcode** könyvtár segítségével. Állítsd be a sávszélességet, válts képfájl‑formátumot, vagy ismételd meg a folyamatot egy értékgyűjteményen, hogy bármilyen postai kód munkafolyamatnak megfeleljen.

Következő lépések:

* **Olvasható szöveg hozzáadása** a vonalkód alá (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Vonalkódok beágyazása PDF dokumentumokba** az Aspose.PDF‑vel.
* **Más postai szimbólumok generálása**, például **USPS POSTNET** vagy **Intelligent Mail**.

Nyugodtan kísérletezz a paraméterekkel, és integráld a kódot a szállítási vagy levelezési rendszeredbe. Boldog kódolást!

## Mit érdemes még megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutató technikáira épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeidben.

- [Planet vonalkód létrehozása C#‑ban – Teljes lépésről‑lépésre útmutató](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Planet vonalkód C#‑ban – komplett programozási útmutató](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Vonalkód generátor C# – Planet vonalkód és RM4SCC példa](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}