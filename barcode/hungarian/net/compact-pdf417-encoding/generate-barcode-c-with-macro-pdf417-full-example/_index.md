---
category: general
date: 2026-08-19
description: Generáljon vonalkódot C#-ban az Aspose.BarCode használatával, hogy egyedi
  szöveggel rendelkező Macro PDF417-et hozzon létre, és mentse képfájlba.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: hu
lastmod: 2026-08-19
og_description: Generáljon vonalkódot C#-ban az Aspose.BarCode segítségével, tanulja
  meg, hogyan generáljon PDF417-et, adjon hozzá egyéni szöveget, és mentse el a vonalkód
  képfájlt.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: C#-ban vonalkód generálása – Macro PDF417 útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Vonalkód generálása C#-ban Macro PDF417-vel – teljes példa
url: /hu/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Macro PDF417 vonalkód generálása C#‑ban – teljes példa

Ha **generate barcode C#**-ra van szükséged egy Macro PDF417 formátumhoz, ez az útmutató egy kész‑a‑futtatáshoz megoldást mutat be. Megmutatja, hogyan **how to generate pdf417**, beágyaz egy egyedi szöveget, és **generate barcode image file** egyetlen, önálló programban.

Az útmutató mindent lefed az Aspose.BarCode könyvtár telepítésétől a Macro PDF417 metaadatok konfigurálásáig, így a kódot közvetlenül a projektedbe másolhatod, és azonnal láthatod az eredményt.

## Előfeltételek

- .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
- Visual Studio 2022 (vagy bármely C#‑t támogató IDE)
- Aspose.BarCode for .NET licenc (az ingyenes próba a kiértékeléshez megfelelő)
- Alapvető ismeretek a C# szintaxisról

> **Pro tip:** Telepítsd a NuGet csomagot a CLI‑val a verzióeltérések elkerülése érdekében:  
> `dotnet add package Aspose.BarCode`

## 1. lépés: A projekt beállítása és a könyvtár importálása

Hozz létre egy új konzolos alkalmazást, és add hozzá a szükséges `using` direktívákat.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Miért fontos ez a lépés:**  
Az `Aspose.BarCode.Generation` névtér biztosítja a `BarcodeGenerator` osztályt, amely bármely vonalkód típus, köztük a Macro PDF417 létrehozásának belépési pontja. A `System` importálása hozzáférést ad a `DateTime`-hoz az időbélyeg metaadatokhoz.

## 2. lépés: Macro PDF417 generátor létrehozása egyedi szöveggel

Cseréld le a helyőrző megjegyzést a generátor inicializálására. Ez bemutatja a **create barcode custom text**-et, miközben a megfelelő kódolási típust választja.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Magyarázat:**  
- `EncodeTypes.MacroPdf417` azt mondja az Aspose-nak, hogy PDF417 vonalkódot állítson elő, amely támogatja a makró funkciókat (fájl szegmentálás, ellenőrzőösszeg stb.).  
- A `"Åspóse.Barcóde©"` szöveg azt mutatja, hogy a Unicode karakterek teljesen támogatottak, ami gyakran szükséges nemzetközi alkalmazásoknál.

## 3. lépés: Megjelenés és Macro PDF417 metaadatok konfigurálása

Finomhangold a vonalkód méreteit, és állítsd be a szegmentált fájlkezeléshez szükséges makró‑specifikus mezőket.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Miért fontosak ezek a beállítások:**

| Setting | Purpose |
|---------|---------|
| `XDimension.Pixels` | A vizuális sűrűséget szabályozza; 2 px tiszta, beolvasható képet eredményez. |
| `Columns` | Meghatározza, hány adat oszlop jelenik meg soronként, befolyásolva a vonalkód méretét. |
| `MacroPdf417FileID` | Egyedileg azonosítja a logikai fájlt az összes szegmens között. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Lehetővé teszi az eredeti fájl rekonstruálását több vonalkódból. |
| `MacroPdf417FileName` | Ember által olvasható név, amely a vonalkódban tárolódik a további feldolgozáshoz. |
| `MacroPdf417Checksum` | Hibadetektálást biztosít a CCITT‑16 CRC algoritmus használatával. |
| `MacroPdf417FileSize` | Segíti a dekódert felismerni, mikor érkezett meg a teljes fájl. |
| `MacroPdf417TimeStamp` | Rögzíti, mikor készült a vonalkód, ami hasznos audit nyomvonalakhoz. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcionális mezők, amelyeket üzleti munkafolyamatok használhatnak. |
| `MacroPdf417Terminator` | Jelzi, hogy ez a szegmens az utolsó (`Set`). |

## 4. lépés: A vonalkód mentése képfájlba

Végül írd a vonalkódot egy PNG fájlba, hogy megtekintsd vagy máshová beágyazd.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Ami megjelenik:**  
Egy `ExtPDF417Meta.png` nevű PNG kép, amely Macro PDF417 vonalkódot tartalmaz, és kódolja a fenti egyedi szöveget és az összes metaadat mezőt. A képet bármely szabványos megjelenítővel megnyithatod, vagy PDF‑ekbe, jelentésekbe, weboldalakba beillesztheted.

## Teljes forráskód (másolás‑beillesztés kész)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Várható kimenet

A program futtatása a következőt írja ki:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

`ExtPDF417Meta.png` megnyitása egy tiszta Macro PDF417 vonalkódot mutat, amely bármely PDF417 olvasóval helyesen beolvasható, megőrizve a `"Åspóse.Barcóde©"` egyedi szöveget és a definiált makró metaadatokat.

## Gyakori kérdések és szélhelyzetek

- **Generálhatok más képkimenetet?**  
  Igen. Cseréld le a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp` vagy `Gif`‑re igény szerint.

- **Mi van, ha az adataim meghaladják egyetlen vonalkód kapacitását?**  
  A Macro PDF417 a szegmentálásra van tervezve. Állítsd be a `MacroPdf417SegmentsCount` és `MacroPdf417SegmentID` értékeket minden részhez, majd fűzd össze a beolvasott eredményeket.

- **Garantált a Unicode támogatás?**  
  Az Aspose.BarCode teljes mértékben támogatja a Unicode‑ot. Győződj meg róla, hogy a forrásfájl UTF‑8 kódolással van mentve a karakterhibák elkerülése érdekében.

- **Szükség van licencre a termeléshez?**  
  A licencelt verzió eltávolítja a kiértékelési vízjelet és teljes funkcionalitást biztosít. A próba verzió teszteléshez és tanuláshoz megfelelő.

## Következtetés

Most már tudod, hogyan **generate barcode C#** egy Macro PDF417-hez, **how to generate pdf417** gazdag metaadatokkal, **create barcode custom text**, és **generate barcode image file** az Aspose.BarCode használatával. A teljes, futtatható példa bemutatja az összes szükséges lépést – a projekt beállításától a végső PNG kép mentéséig.

### Következő lépések

- Kísérletezz más PDF417 beállításokkal, például `ErrorCorrectionLevel` és `CompactPdf417` kisebb szimbólumokhoz.  
- Integráld a generált vonalkódot egy PDF jelentésbe az Aspose.PDF segítségével.  
- Fedezd fel a kötegelt generálást: iterálj egy fájlgyűjteményen, és állíts elő egy sor szegmentált Macro PDF417 vonalkódot.

Nyugodtan igazítsd a kódot a saját munkafolyamatodhoz, és engedd, hogy a vonalkód generálás zökkenőmentes része legyen a C# alkalmazásaidnak. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [Hogyan generáljunk Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Vonalkód kép generálása – Code 93 az Aspose.BarCode-dal](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Hogyan generáljunk és állítsunk be vonalkód magasságot egy dimenziós Databarhoz az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}