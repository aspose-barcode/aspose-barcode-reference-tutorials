---
category: general
date: 2026-07-18
description: Micro PDF417 vonalkód generálása az Aspose.BarCode for .NET segítségével
  – lépésről‑lépésre útmutató az oszlopok, sorok és PNG kimenet lefedésével.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: hu
lastmod: 2026-07-18
og_description: Generáljon micro PDF417 vonalkódot azonnal az Aspose.BarCode for .NET
  használatával. Tanulja meg, hogyan vezérelheti az oszlopokat és sorokat, és percek
  alatt mentheti PNG formátumban.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Micro PDF417 vonalkód generálása – Teljes C# útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Micro PDF417 vonalkód generálása C#‑ban – Teljes útmutató
url: /hu/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Micro PDF417 vonalkód generálása C#‑ben – Teljes útmutató

Gondolkodtál már azon, hogyan **generálj micro pdf417 vonalkódot** közvetlenül a C# alkalmazásodból? Nem vagy egyedül. Akár készletnyilvántartást címkézel, rövid URL‑eket kódolsz, vagy egy egyedi beolvasási megoldást építesz, ennek a kicsi, de erőteljes 2‑D kódnak a megtanulása rengeteg fáradságot spórolhat meg.

Ebben az útmutatóban egy valós példán keresztül mutatjuk be a **Aspose.BarCode for .NET** használatát, bemutatva, hogyan állíthatod be az oszlopokat, sorokat és a modulméretet, majd mentheted az eredményt PNG fájlba. A végére egy azonnal futtatható konzolalkalmazást kapsz, amely három különböző vonalkódképet generál – semmi rejtély marad nélkül.

## Amire szükséged lesz

- .NET 6 vagy újabb (a kód .NET Framework 4.7+‑en is működik)
- Visual Studio 2022 (vagy bármelyik kedvenc C# IDE‑d)
- A **Aspose.BarCode** NuGet csomag (`Aspose.BarCode`)
- Egy írható mappa a lemezén a kimeneti PNG‑ek számára

Ha már megvan mindez, nagyszerű—merüljünk el benne.

## 1. lépés: Projekt létrehozása és az Aspose.BarCode telepítése

Először hozz létre egy új konzolprojektet:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** A csomag hozzáadása után futtasd a `dotnet restore` parancsot, hogy minden függőség fel legyen oldva.

Most nyisd meg a `Program.cs` fájlt. Elkezdjük beilleszteni a szükséges névtereket:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Ezek a két `using` utasítás biztosítja a hozzáférést a `BarcodeGenerator`, `EncodeTypes` és a később szükséges képméret enumhoz.

## 2. lépés: A MicroPdf417 generátor inicializálása

A művelet szíve a `BarcodeGenerator` objektum. Ennek adjuk meg a **MicroPdf417** kódolástípust és a kódolni kívánt szöveget – jelen esetben az „ASPOSE” szót.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Miért `MicroPdf417`? A teljes méretű PDF417-hez képest a mikro változat több adatot tud elhelyezni egy kisebb területen, ami tökéletes a korlátozott helyű címkékhez.

## 3. lépés: A modulméret (X‑dimenzió) beállítása

A modulméret meghatározza, hány pixel foglal el a vonalkód minden apró négyzete. A **2 pixel** érték tiszta, jól olvasható képet eredményez anélkül, hogy a fájlméret felrobbanna.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Megjegyzés:** Ha nagyobb vonalkódra van szükséged távoli beolvasáshoz, növeld ezt a számot 3‑ra vagy 4‑re.

## 4. lépés: Vonalkódok generálása különböző oszlop/sor konfigurációkkal

### 4.1 Két oszlop, automatikusan kiszámított sorok

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Hat sor, automatikusan kiszámított oszlopok

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Négy oszlop × nyolc sor (teljesen meghatározott)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Minden `Save` hívás egy PNG fájlt ír a projekt munkakönyvtárába. Nyugodtan módosíthatod az útvonalat (`"YOUR_DIRECTORY/..."`) például `Path.Combine(Environment.CurrentDirectory, "output")`‑re, ha egy dedikált mappát szeretnél.

## 5. lépés: Teljes működő példa

Összevonva, itt a teljes, másolás‑beillesztésre kész program:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Várható kimenet

A program futtatása három PNG fájlt hoz létre:

| Fájlnév | Kb. méretek (px) | Vizuális jelzés |
|-----------|------------------------|------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Keskeny, magasabb vonalkód |
| `MicroPdf417Rows6.png` | 120 × 180 | Szélesebb, alacsonyabb vonalkód |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Körülbelül négyzetes, kiegyensúlyozott elrendezés |

Nyisd meg bármelyiket egy képnézőben – egy tiszta **Micro PDF417** vonalkódot látsz, amely készen áll a beolvasásra.

## Gyakori kérdések és speciális esetek

- **Mi van, ha a kimeneti mappa nem létezik?**  
  Hívd meg a `Directory.CreateDirectory(path)`‑t az első `Save` előtt, hogy elkerüld a `DirectoryNotFoundException`‑t.

- **Megváltoztathatom a képformátumot?**  
  Természetesen. Cseréld le a `BarCodeImageFormat.Png`‑t `Jpeg`, `Bmp` vagy `Gif`‑re, ahogy szükséges.

- **Van korlát a szöveg hosszára?**  
  A MicroPdf417 legfeljebb 1 KB adatot képes kódolni, de a gyakorlati korlátok a választott sorok/oszlopok számától függenek. Ha hibát kapsz, növeld a sorok vagy oszlopok számát.

- **Hogyan ágyazhatom be a vonalkódot PDF‑be?**  
  Használd az Aspose.Pdf‑t a generált PNG beillesztéséhez, vagy válts `BarCodeImageFormat.Pdf`‑re a közvetlen PDF kimenethez.

## Profi tippek C# vonalkód generáláshoz

1. **Cache-eld a generátort**, ha sok vonalkódot kell előállítanod ugyanazzal a beállítással – csak a szöveget kell változtatni, így CPU‑ciklusokat takarítasz meg.  
2. **Finomhangold a hibajavítást** a `generator.Parameters.Barcode.Pdf417.ErrorLevel` segítségével, ha a beolvasási környezet zajos.  
3. **Teszteld valós beolvasókkal** már korán. Egyes kézi eszközök nehezen kezelik a nagyon sűrű micro vonalkódokat; az `XDimension` módosítása nagy különbséget jelenthet.

## Összegzés

Most már tudod, hogyan **generálj micro pdf417 vonalkódot** a **Aspose.BarCode for .NET** segítségével, hogyan manipuláld a **MicroPdf417 oszlopokat** és **MicroPdf417 sorokat**, és hogyan mentsd el az eredményt PNG fájlokként – mindezt egyetlen, rendezett C# konzolalkalmazásból. Kísérletezz különböző modulméretekkel, hibajavítási szintekkel vagy akár színes kimenettel, hogy megfeleljen a projekted igényeinek.

Ezután érdemes lehet felfedezni a **C# vonalkód generálást** más szimbólumokhoz, mint a QR, Code128 vagy DataMatrix, vagy közvetlenül PDF‑ekbe ágyazni a képeket az Aspose.Pdf‑vel. A lehetőségek határtalanok, ha már ismered az alapokat.

Boldog kódolást, és legyenek a beolvasásaid mindig hibamentesek!

## Mit érdemes még megtanulni?

Az alábbi útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan készítsünk vonalkódot – Compact PDF417 az Aspose.BarCode‑dal](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [DotCode vonalkód kép létrehozása – sorok és oszlopok (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [DataMatrix vonalkód generálása – Pro útmutató az Aspose.BarCode‑dal](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}