---
category: general
date: 2026-08-03
description: Olvassa be a PDF417 vonalkódot egy képről C# BarCodeReader segítségével
  – egy komplett vonalkódolvasó példa, amely azt is megmutatja, hogyan olvashatók
  több vonalkód.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: hu
lastmod: 2026-08-03
og_description: Olvassa be gyorsan a PDF417 vonalkódot egy C# BarCodeReader példával.
  Kövesse ezt a lépésről‑lépésre útmutatót a macro PDF417 dekódolásához és több vonalkód
  beolvasásához egy képről.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: PDF417 vonalkód olvasása C#-ban – komplett vonalkódolvasó példa
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: PDF417 vonalkód olvasása C#-ban – vonalkódolvasó példa
url: /hu/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód olvasása C#-ban – vonalkód olvasó példa

Ha PDF417 vonalkód adatokat szeretne olvasni egy képből, ez az útmutató megmutatja, hogyan teheti ezt meg a **BarCodeReader** osztállyal C#-ban. Megtanul egy vonalkód olvasó példát, amely kezeli a macro PDF417-et is, és képes több vonalkódot olvasni egyetlen képen.

Vonalkódokkal dolgozni gyakran azt jelenti, hogy különböző képforrásokkal, változó fényviszonyokkal, és néha összetett adatokkal, például macro PDF417 szegmensekkel kell megküzdeni. Ez az oktatóanyag mindent lefed, amire szüksége van egy PDF417 vonalkód dekódolásához, kiterjesztett mezőinek kinyeréséhez, és több vonalkód feldolgozásához ugyanabból a képből. A végére egy futtatható konzolprogramja lesz, amely képfájlból olvas vonalkódokat, és részletes információkat nyomtat a konzolra.

## Amire szüksége lesz

* .NET 6.0 SDK vagy újabb telepítve  
* A **Aspose.BarCode for .NET** NuGet csomag legújabb verziója (vagy bármely kompatibilis könyvtár, amely biztosítja a `BarCodeReader` és a `DecodeType.MacroPdf417` elemeket)  
* Egy képfájl, amely PDF417 vagy macro PDF417 vonalkódot tartalmaz (a példa a `ExtPDF417Meta.png`-t használja)  
* Egy kódszerkesztő vagy IDE, például a Visual Studio 2022  

Nem szükséges további szolgáltatás vagy külső API.

## A projekt beállítása a vonalkódolvasáshoz

1. **Új konzolprojekt létrehozása**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **A vonalkód könyvtár hozzáadása**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **A vonalkód kép másolása**  

   Helyezze a `ExtPDF417Meta.png`-t (vagy bármely PDF417 vonalkódot tartalmazó képet) a projekt mappájába.  
   Ebben az oktatóanyagban feltételezzük, hogy a fájl a `YOUR_DIRECTORY/ExtPDF417Meta.png` helyen található.

A projekt most már készen áll a fordításra és a vonalkódolvasó példa futtatására.

## PDF417 vonalkód olvasása a BarCodeReader-rel

A megoldás központja egy `using` blokk, amely létrehozza a `BarCodeReader` példányt, megadja a `DecodeType.MacroPdf417` értéket, és végigiterál minden észlelt vonalkódon. Az alábbi kód egy teljes, önálló program, amelyet beilleszthet a `Program.cs` fájlba.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Miért működik**:  

* `DecodeType.MacroPdf417` azt mondja az olvasónak, hogy keresse a PDF417 macro kiterjesztését, amely további metaadatokat tartalmaz, például fájlazonosítót, szegmens számot és időbélyegeket.  
* A `using` utasítás garantálja, hogy a nem kezelt erőforrások (fájlkezelők, natív dekódoló pufferek) gyorsan felszabaduljanak.  
* A `foreach` ciklus automatikusan feldolgozza a képen lévő **összes** vonalkódot, ezzel teljesítve a *több vonalkód olvasása* követelményt.

A program futtatásakor (`dotnet run`) hasonló kimenetet kell látnia, mint az alábbi:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Ha a kép több mint egy PDF417 vonalkódot tartalmaz, a ciklus minden vonalkódhoz külön blokkot nyomtat, ezáltal bemutatva, hogyan **olvashat több vonalkódot** egyetlen képről.

## Több vonalkód olvasása egy képből

Ugyanaz a `BarCodeReader` példány egyszerre több vonalkódtípust is dekódolhat. A hatókör kiterjesztéséhez, hogy ne csak macro PDF417-et, hanem bármely PDF417-et (vagy akár QR, Code128 stb.) is kezeljen, módosítsa a `DecodeType` jelzőt:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* egy bitmaszk, így tetszőleges számú támogatott formátumot kombinálhat. Ez a rugalmasság teszi a kódrészletet egy **vonalkód olvasó példává**, amely számos felhasználási esetben működik, például termékcímkék, jegyek vagy személyi igazolványok beolvasásakor.

## A macro PDF417 mezők biztonságos elérése

Macro PDF417 gazdag kiterjesztett tulajdonságkészletet ad hozzá. Azonban nem minden vonalkód tartalmaz minden mezőt. Hiányzó tulajdonság elérése `NullReferenceException`-t dobhat. A legbiztonságosabb megközelítés, ha minden tulajdonságot ellenőriz a kiírás előtt:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Miért fontos*: Valós környezetben előfordulhat, hogy egyszerű PDF417 vonalkódokat kap, amelyek nem tartalmaznak macro adatokat. A védelmi ellenőrzés biztosítja, hogy az alkalmazás tovább fusson anélkül, hogy összeomlana.

## Gyakori buktatók és legjobb gyakorlatok

| Probléma | Miért fordul elő | Javasolt megoldás |
|----------|------------------|-------------------|
| A képfájl útvonala helytelen | `BarCodeReader` fájl‑nem‑található kivételt dob, mielőtt bármilyen dekódolás megtörténne | Használja a `Path.Combine`-t, és ellenőrizze, hogy a fájl létezik-e a `File.Exists` segítségével |
| Alacsony felbontású kép | A dekóder nem tudja megtalálni a vonalkód éleit, ami nulla detektáláshoz vezet | Biztosítson legalább 300 dpi felbontást a megbízható eredményekhez |
| A vonalkód > 45°-ra el van fordítva | Sok könyvtár felálló orientációt feltételez | Engedélyezze a `reader.RecognitionOptions.RotateImage = true` beállítást, ha a |

## Mit érdemes még megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészletet tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan olvassunk DataMatrix vonalkódokat az Aspose.BarCode for .NET segítségével](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix vonalkód olvasása C# – DataMatrix mód generálása (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Vonalkód olvasása képből – A vonalkód régió kinyerésének elsajátítása Java-ban az Aspose.BarCode segítségével](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}