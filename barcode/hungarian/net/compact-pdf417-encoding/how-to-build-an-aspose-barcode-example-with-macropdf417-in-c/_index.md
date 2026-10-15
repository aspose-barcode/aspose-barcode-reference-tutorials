---
category: general
date: 2026-10-12
description: Tanulja meg, hogyan hozhat létre egy Aspose vonalkód példát C#-ban, amely
  teljes metaadatokkal rendelkező MacroPdf417 vonalkódot generál, és visszaolvassa
  azt a BarCodeReader segítségével.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: hu
lastmod: 2026-10-12
og_description: Aspose vonalkód példa C#-ban, amely bemutatja, hogyan lehet MacroPdf417
  vonalkódot generálni beágyazott metaadatokkal, és visszaolvasni azt a BarCodeReader
  segítségével.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Aspose vonalkód példa létrehozása MacroPdf417-vel C#-ban
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Hogyan építsünk fel egy Aspose vonalkód példát MacroPdf417-vel C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan építsünk egy Aspose vonalkód példát MacroPdf417 használatával C#-ban

Ha szükséged van egy **aspose barcode example**-ra, amely MacroPdf417 vonalkódot hoz létre és beágyazott metaadatait olvassa, ez az útmutató bemutatja a teljes munkafolyamatot. Megmutatjuk, hogyan konfigurálod a generátort, ágyazod be a fájlszintű információkat, mented a képet, majd ugyanazt az adatot dekódolod a `BarCodeReader` segítségével.

Az útmutató mindent lefed, amit a **C# barcode generation**-hez tudnod kell az Aspose.BarCode használatával, beleértve a gyakori buktatókat és tippeket a nagy fájlazonosítók vagy egyedi időbélyegek kezeléséhez.

## Amire szükséged lesz

* .NET 6.0 SDK vagy újabb (a kód működik .NET Core és .NET Framework alatt)
* Visual Studio 2022 vagy bármely IDE, amely támogatja a C#-t
* Aktív Aspose.BarCode licenc (az ingyenes próba verzió fejlesztéshez is használható)
* A `Aspose.BarCode` NuGet csomag telepítve a projektedben

Ezek a feltételek garantálják, hogy a példa további konfiguráció nélkül fusson.

## 1. lépés: Az Aspose barcode example projekt beállítása

Hozz létre egy új konzolalkalmazást, és add hozzá az Aspose.BarCode könyvtárat:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Az `Aspose.BarCode` csomag biztosítja a `BarcodeGenerator`, `BarCodeReader` osztályokat, valamint minden szükséges típust a MacroPdf417 kezeléséhez.

### Miért fontos ez a lépés
A NuGet csomag hozzáadása megoldja a később használt `EncodeTypes`, `DecodeType` és `BarCodeImageFormat` enumerációkat. Csomag nélkül a fordító nem ismeri fel ezeket a szimbólumokat, és a példa fordítási hibával leáll.

## 2. lépés: MacroPdf417 vonalkód generátor létrehozása

Nyisd meg a **Program.cs** fájlt, és cseréld le a sablonkódot az alábbi blokkra. Ez a blokk létrehozza a MacroPdf417 szimbólumra konfigurált `BarcodeGenerator`-t, és beállítja az alapvető megjelenési paramétereket.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### A kulcsfontosságú tulajdonságok magyarázata

| Tulajdonság | Cél | Tipikus tartomány / megjegyzés |
|-------------|-----|-------------------------------|
| `MacroPdf417FileID` | A teljes fájl egyedi azonosítója | Legfeljebb ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Az aktuális szegmens indexe | 0‑tól kezdődik |
| `MacroPdf417SegmentsCount` | A fájlban lévő szegmensek teljes száma | Legalább ≥ SegmentID |
| `MacroPdf417FileName` | Emberek által olvasható fájlnév | Legfeljebb 255 karakter |
| `MacroPdf417Checksum` | Az eredeti fájl CCITT‑16 ellenőrzőösszege | Szükség esetén külső eszközzel számítva |
| `MacroPdf417FileSize` | Az eredeti fájl mérete bájtokban | Hasznos az ellenőrzéshez |
| `MacroPdf417TimeStamp` | A fájl létrehozásának dátuma/ideje | Használj UTC-t a konzisztenciáért |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcionális útvonalinformáció | Bármilyen karakterlánc legfeljebb 255 karakterrel |
| `MacroPdf417Terminator` | Jelöli az utolsó szegmenst | Használd a `Set`-et az utolsó szegmensnél |

Ezek a mezők alkotják a **barcode metadata**-t, amelyet a leolvasó később ki tud nyerni.

## 3. lépés: A vonalkód dekódolása és a metaadatok megjelenítése

A kép mentése után a program ugyanúgy folytatódik, a fájlt a `BarCodeReader`-rel megnyitva. Add hozzá a következő kódot a `Main` metódusban, az előző `using` blokk után:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Miért fontos a visszaolvasás
A `BarCodeReader` ellenőrzi, hogy a beágyazott metaadatok helyesen vannak-e kódolva. Ha bármelyik tulajdonság hiányzik vagy kívül esik a tartományon, a leolvasó `null`-t ad vissza az adott mezőre, így hibákat elegánsan kezelheted.

## 4. lépés: A program futtatása és a kimenet ellenőrzése

Futtasd a programot:

```bash
dotnet run
```

A konzolon a következőhöz hasonló kimenetet kell látnod:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Ha az értékek megegyeznek a 2. lépésben beállítottakkal, a **aspose barcode example** a várt módon működik.

## Szélsőséges esetek és legjobb gyakorlatok

| Helyzet | Mire figyelj | Ajánlott kezelés |
|---------|--------------|-------------------|
| **FileID meghaladja a 32‑bit tartományt** | Az Aspose `ArgumentOutOfRangeException`-t dob. | Tartsd az azonosítót ≤ 2 147 483 647 értéken, vagy oszd fel a fájlt több MacroPdf417 blokkra. |
| **Helyi időben lévő időbélyeg** | Más időzónában lévő olvasók félreérthetik az értéket. | Tárold az időbélyegeket UTC-ben (`DateTime.UtcNow`), és szükség esetén konvertáld megjelenítéskor. |
| **Nagy fájlméret** | A `MacroPdf417FileSize` egy `int`; a 2 GB-nál nagyobb értékek túlcsordulnak. | Használj egyedi mezőt vagy oszd fel a fájlt kisebb szegmensekre. |
| **Hiányzó szegmens** | Ha a `SegmentID` nem sorozatos, a rekonstrukció meghiúsul. | Ellenőrizd a szegmensek sorrendjét kódolás előtt, vagy használd a hibajavító beállításokat. |
| **Nem támogatott képformátum** | BMP-ként mentés drámaikusan megnövelheti a méretet. | A PNG jó alapértelmezett; JPEG használható, ha elfogadod a veszteséges tömörítést. |

**Pro tipp:** Ha sok vonalkódot generálsz egy kötegben, használd újra ugyanazt a `BarcodeGenerator` példányt, és csak a `EncodeTypes`-t és a forrásszöveget módosítsd. Ez csökkenti a memóriafoglalásokat és felgyorsítja a feldolgozást.

## Kapcsolódó témák, amelyeket érdemes tovább felfedezni

* **Más makró szimbólumok** – Az Aspose támogatja a MacroPdf417-et hibajavítási szintekkel is.
* **Vonalkódok beágyazása PDF-ekbe** – Kombináld az `Aspose.PDF`-et a vonalkódgenerátorral nyomtatható dokumentumok létrehozásához.
* **ASP.NET Core integráció** – Szolgáld ki a generált vonalkódokat közvetlenül egy web API-ból.
* **Mobil eszközökkel történő beolvasás** – Használd az `Aspose.BarCode.Cloud` SDK-t a többplatformos dekódoláshoz.

Ezek a további témák természetesen kiterjesztik a **aspose barcode example**-t, és elmélyítik a **C# barcode generation** terén szerzett szakértelmedet.

## Következtetés

Most már rendelkezel egy teljesen működő **aspose barcode example**-nal, amely MacroPdf417 vonalkódot hoz létre, gazdag **barcode metadata**-t ágyaz be, elmenti a képet, és visszaolvassa az adatokat a `BarCodeReader` segítségével. A fenti lépések követésével a kódot különböző fájlazonosítókhoz, időbélyegekhez vagy akár az Aspose által támogatott más vonalkódtípusokhoz is igazíthatod.

Nyugodtan kísérletezz további metaadatmezőkkel, változtasd meg a képformátumot, vagy integráld a generátort egy nagyobb alkalmazásba. Jó kódolást!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}