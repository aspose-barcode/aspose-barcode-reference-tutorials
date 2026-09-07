---
category: general
date: 2026-09-07
description: Tudja meg, hogyan lehet dekódolni a PDF417 vonalkódokat C#‑ban a BarCodeReader
  használatával. Ez a lépésről‑lépésre útmutató azt is elmagyarázza, hogyan olvassa
  be hatékonyan a PDF417 adatokat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: hu
lastmod: 2026-09-07
og_description: Hogyan dekódoljuk a PDF417 vonalkódokat C#-ban a BarCodeReader használatával.
  Kövesd ezt az útmutatót, hogy megtanuld, hogyan olvassuk be a PDF417 adatokat, és
  hogyan nyerjük ki a MacroPdf417 mezőket.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Hogyan dekódoljunk PDF417 vonalkódokat C#-ban – teljes útmutató
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Hogyan lehet dekódolni a PDF417 vonalkódokat C#‑ban a BarCodeReader‑rel
url: /hu/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan dekódoljuk a PDF417 vonalkódokat C#-ban a BarCodeReader segítségével

Ha szüksége van arra, hogy **hogyan dekódoljuk a PDF417** vonalkódokat egy .NET alkalmazásban, ez az útmutató végigvezeti a teljes folyamaton. Emellett megtudja, **hogyan olvassuk a PDF417** adatokat, például a MacroPdf417 fájl- és szegmensazonosítókat, mindezt néhány C# sorral.

A PDF417 dekódolása gyakori, ha közlekedési jegyekkel, jogosítványokkal vagy szállítási címkékkel dolgozunk. A tutorial végére egy futtatható konzolprogrammal fog rendelkezni, amely kiírja a GroupDocs.Barcode SDK által biztosított összes MacroPdf417 mezőt.

## Előfeltételek

* .NET 6.0 SDK vagy újabb (a kód .NET Core és .NET Framework alatt is lefordítható)
* Visual Studio 2022 vagy bármelyik C#-ot támogató IDE
* A **GroupDocs.Barcode** NuGet csomag (`GroupDocs.Barcode` ≥ 23.3)
* Egy képfájl, amely Macro PDF417 vonalkódot tartalmaz (pl. `ExtPDF417Meta.png`)

> **Pro tipp:** Telepítse a csomagot a CLI-n keresztül:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Hogyan dekódoljuk a PDF417 vonalkódokat C#-ban

A következő szakaszok logikai lépésekre bontják a megoldást. Minden lépés tartalmazza a szükséges pontos kódot és egy rövid magyarázatot arról, miért fontos.

### 1. lépés: A projekt előkészítése és a névterek importálása

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Miért?*  
`GroupDocs.Barcode` biztosítja a `BarCodeReader` osztályt, míg a `GroupDocs.Barcode.Common` tartalmazza a PDF417 dekódoláshoz szükséges `DecodeType` felsorolást.

### 2. lépés: A kép útvonalának meghatározása

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Miért?*  
Az olvasó bármely, a .NET által támogatott képfájltípussal működik (`.png`, `.jpg`, `.bmp`). A helyes útvonal megadása biztosítja, hogy az SDK megtalálja a fájlt.

### 3. lépés: A barcode olvasó inicializálása MacroPdf417 dekódoláshoz

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Miért?*  
A `DecodeType.MacroPdf417` azt mondja az SDK-nak, hogy keresse a kiterjesztett Macro PDF417 formátumot, amely további metaadatokat tartalmaz, például fájl- és szegmensazonosítókat. A `using` utasítás használata garantálja, hogy a nem kezelt erőforrások gyorsan felszabaduljanak.

### 4. lépés: Az összes a képen található vonalkód beolvasása

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Miért?*  
Egy kép több vonalkódot is tartalmazhat. A `ReadBarCodes()` metódus egy gyűjteményt ad vissza, amely lehetővé teszi az egyes elemek egyenkénti feldolgozását.

### 5. lépés: Macro PDF417 specifikus adatok lekérése és megjelenítése

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Miért?*  
Az `Extended.Pdf417` objektum a specifikáció által definiált összes Macro PDF417 mezőt teszi elérhetővé. Kiíratásuk lehetővé teszi, hogy ellenőrizze a dekódolás sikerességét, és megkapja a további feldolgozáshoz szükséges adatokat.

### Teljes futtatható példa

Combine the snippets above into a single `Program.cs` file:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Expected console output** (values will differ based on the barcode content):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Ha a kép nem tartalmaz Macro PDF417 vonalkódot, a `ReadBarCodes()` gyűjtemény üres lesz, és semmi sem lesz kiírva.

## Gyakori variációk és szélsőséges esetek

| Szituáció | A kód módosítása |
|-----------|----------------------|
| **Standard (nem‑macro) PDF417** | Cserélje a `DecodeType.MacroPdf417`-t `DecodeType.Pdf417`-ra. Az `Extended.Pdf417` objektum `null` lesz, ezért ellenőrizze a null hivatkozásokat. |
| **Több kép** | Tegye a olvasó inicializálását egy `foreach (var path in imagePaths)` ciklusba. |
| **Nagy képek** | Állítsa be a `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` értéket a memóriahasználat korlátozásához. |
| **Teljesítménykritikus köteg** | Használjon egyetlen `BarCodeReader` példányt a `reader.SetImage(path)` hívással az egyes fájlokhoz új objektum létrehozása helyett. |

## Hibaelhárítási ellenőrzőlista

* **Nincs kimenet:** Ellenőrizze, hogy az `imagePath` egy érvényes fájlra mutat-e, és hogy a kép valóban PDF417 vonalkódot tartalmaz.  
* **Null `Extended.Pdf417`:** Valószínűleg `DecodeType.Pdf417`-t használt a `MacroPdf417` helyett.  
* **Kivétel `FileNotFoundException`:** Győződjön meg róla, hogy a munkakönyvtár megfelel az útvonalnak, vagy használjon abszolút útvonalat.  
* **Alacsony bizalmi pontszám:** Növelje a kép minőségét vagy állítsa be a `reader.Options.Quality` beállításokat.  

## Következtetés

Most már tudja, **hogyan dekódoljuk a PDF417** vonalkódokat C#-ban, és **hogyan olvassuk a PDF417** metaadatokat, például a Macro fájlazonosítókat, szegmensazonosítókat és időbélyegeket. A teljes példa bemutatja a `BarCodeReader` inicializálását, a megfelelő dekódolási típus kiválasztását, az eredmények iterálását és minden elérhető MacroPdf417 mező kinyerését.

Innen tovább:

* Integrálja a kinyert adatokat egy logisztikai vagy jegy‑validációs rendszerbe.  
* Bővítse a konzolalkalmazást, hogy az eredményeket adatbázisba vagy JSON fájlba írja.  
* Fedezze fel a GroupDocs.Barcode által támogatott egyéb vonalkódformátumokat (QR, DataMatrix, Code128, stb.) a `DecodeType` felsorolás cseréjével.

Boldog kódolást, és nyugodtan kísérletezzen különböző képekkel és vonalkódbeállításokkal, hogy mestere legyen a PDF417 dekódolásnak .NET projektjeiben!

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}