---
category: general
date: 2026-10-24
description: Tanulja meg, hogyan generáljon PDF417 vonalkódot az Aspose.BarCode használatával
  C#-ban kompakt beállítások és a vonalkód X-dimenziójának vezérlése mellett.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: hu
lastmod: 2026-10-24
og_description: Készíts PDF417 vonalkódot C#-ban az Aspose.BarCode segítségével. Kövesd
  ezt a teljes útmutatót, hogy kompakt PDF417 képeket hozz létre, szabályozd az XDimension-t,
  és állítsd be az oszlopokat.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: PDF417 vonalkód generálása az Aspose.BarCode segítségével – C# lépésről
  lépésre
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Hogyan generáljunk PDF417 vonalkódot az Aspose.BarCode segítségével C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk PDF417 vonalkódot az Aspose.BarCode segítségével C#-ban

Ha **PDF417 vonalkódot** kell **generálnod** egy .NET alkalmazásban, ez az útmutató egy teljes, azonnal futtatható megoldást mutat be. Látni fogod, hogyan teszi az Aspose.BarCode a folyamatot egyszerűvé, miközben finomhangolt vezérlést biztosít a **compact PDF417**, **barcode XDimension** és **PDF417 columns** felett.

A vonalkód létrehozása gyakori igény a készletkezelő rendszerekben, jegyértékesítő platformokon és dokumentumfolyamatokban. A tutorial végére egy önálló C# programod lesz, amely egy éles PNG képet állít elő egy PDF417 vonalkódról, készen áll arra, hogy bármely UI‑ba beágyazz vagy címkén nyomtass.

## Amire szükséged lesz

- .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.6+‑del is működik)
- Visual Studio 2022 vagy bármely kedvelt C# szerkesztő
- Érvényes Aspose.BarCode for .NET licenc (a ingyenes próba a fejlesztéshez elegendő)
- Alapvető ismeretek a C# szintaxisról

> **Pro tipp:** Ha az Aspose.BarCode-ot értékeled, töltsd le a próbaverziót a hivatalos oldalról, és add hozzá a `Aspose.BarCode` NuGet csomagot a projektedhez. A próba egy kis vízjelet ad a generált képhez, amely a licenc alkalmazása után eltűnik.

## 1. lépés: Az Aspose.BarCode NuGet csomag telepítése

Nyiss egy terminált a megoldásod mappájában, és futtasd:

```bash
dotnet add package Aspose.BarCode
```

A parancs a legújabb stabil verziót (2026. október állása szerint a 23.12‑es verzió) tölti le. A csomag hozzáadása visszaállítja a `Aspose.BarCode.Generation` névteret, amelyet a **PDF417 vonalkód** képek **generálásához** fogsz használni.

## 2. lépés: Alap C# konzolprojekt létrehozása

Ha még nincs projekted, hozd létre:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Nyisd meg a `Program.cs`‑t. A váz már tartalmaz egy `Main` metódust, ahová a vonalkód‑generálás kódját helyezzük.

## 3. lépés: A vonalkód‑generátor inicializálása

Először importáld a szükséges névteret:

```csharp
using Aspose.BarCode.Generation;
```

Ezután a `Main`‑ben példányosítsd a `BarcodeGenerator`‑t a PDF417 szimbólummal és a kódolni kívánt adatokkal:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

A karakterlánc Unicode karaktereket tartalmaz, hogy bemutassa, az Aspose.BarCode helyesen kezeli a nem‑ASCII bemenetet. Ha csak ASCII‑ra van szükséged, cseréld le a szöveget egy egyszerű karakterláncra.

## 4. lépés: A vonalkód XDimension (modulméret) beállítása

A **barcode XDimension** meghatározza a legkisebb vonal (modul) szélességét. Pixelben megadva pixel‑pontos kontrollt biztosít a végső kép mérete felett:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

A `2` pixel érték kompakt képet eredményez anélkül, hogy a szkennelhetőséget veszélyeztetné. Növeld az értéket nagyobb vonalkódokhoz, vagy csökkentsd nagyon sűrű elrendezésekhez.

## 5. lépés: Compact PDF417 beállítások konfigurálása

Két PDF417‑specifikus beállítás drámaian befolyásolja a vizuális lábnyomot:

| Beállítás | Jelentés | Tipikus érték a kompakt kimenethez |
|-----------|----------|-----------------------------------|
| `Columns` | Adatoszlopok száma | `3` |
| `Truncate` (compact mode) | Eltávolítja a jobb oldali csendes zónát és csökkenti a sorok számát | `true` |

Alkalmazd őket a következő módon:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

A **PDF417 columns** `3`‑ra állítása és a `Truncate = true` egy *compact PDF417* vonalkódot hoz létre, amely szép módon elfér egy szabványos címkén, miközben a legtöbb szkenner számára olvasható marad.

## 6. lépés: A vonalkód kép mentése

Végül írd a vonalkódot le a lemezre. A példa PNG‑t ment, de az Aspose.BarCode támogatja a BMP, JPEG, GIF, TIFF és SVG formátumokat is:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

A `BarCodeImageFormat.Png` állandó azt mondja a könyvtárnak, hogy veszteségmentes PNG‑t állítson elő, ami ideális további feldolgozáshoz vagy nyomtatáshoz.

## Teljes, futtatható forráskód

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

A program futtatása `CompactPdf417.png`‑t hoz létre a projekt gyökérmappájában. Nyisd meg a fájlt bármely képmegjelenítővel; egy szorosan elrendezett PDF417 vonalkódot látsz, amely a *Åspóse.Barcóde©* karakterláncot kódolja.

![Képernyőkép a generált PDF417 vonalkódról az Aspose.BarCode használatával](placeholder-image.png "Generált PDF417 vonalkód")

*Image alt text: Képernyőkép a generált PDF417 vonalkódról az Aspose.BarCode használatával* – ez az alt szöveg tartalmazza a fő kulcsszót a hozzáférhetőség és SEO érdekében.

## Az eredmény ellenőrzése

1. Nyisd meg a PNG fájlt. A vonalkódnak három függőleges adatoszloppal kell rendelkeznie egy kompakt elrendezésben (nincs extra csendes zóna a jobb oldalon).
2. Olvasd be a képet egy okostelefonos vonalkódolvasóval, amely támogatja a PDF417‑et. A dekódolt szövegnek meg kell egyeznie az eredeti bemeneti karakterlánccal.
3. Ha a szkenner nem működik, próbáld meg növelni az `XDimension.Pixels` értékét `3`‑ra vagy `4`‑re. A nagyobb modulok javítják az olvashatóságot alacsony felbontású eszközökön.

## Gyakori változatok és szélhelyzetek

### 1. A képformátum megváltoztatása

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Az SVG vektor‑alapú, ami a vonalkódot bármilyen nagyítási szinten élesen tartja – hasznos weboldalakhoz.

### 2. Nagy mennyiségű adat kódolása

A PDF417 körülbelül ~1,1 KB szöveget tud tárolni. Ha a payload meghaladja a három oszlop kapacitását, a könyvtár automatikusan sorokat ad hozzá. A vonalkód kompakt tartásához teheted:

- Csökkentsd az adat hosszát (pl. használj azonosítót a teljes üzenet helyett)
- Növeld a **PDF417 columns** számát (pl. `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Licenc használata a próba‑vízjel eltávolításához

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Helyezd a licencfájlt a futtatható állomány mellé. Licenc után a generált kép nem tartalmaz vízjelet.

### 4. Kivételkezelés

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Tipikus hibák közé tartozik a nem elegendő írási jogosultság vagy egy nem támogatott képformátum.

## Miért fontosak a beállítások

- **barcode XDimension** – Szabályozza minden vonal vizuális súlyát. Túl kicsi esetén a vonalkód olvashatatlan, túl nagy pedig feleslegesen helyet foglal.
- **PDF417 columns** – Kevesebb oszlop szűkebb vonalkódot eredményez, de növeli a sorok számát.

## Mit érdemes még megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API‑funkciókat és alternatív megvalósítási módokat a saját projektjeidben.

- [Hogyan generáljunk PDF417 vonalkódot az Aspose segítségével – Teljes útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [PDF417 vonalkód generálása kompakt beállításokkal C#-ban](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Hogyan mentsünk vonalkódot és generáljunk PDF417-et az Aspose segítségével C#-ban](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}