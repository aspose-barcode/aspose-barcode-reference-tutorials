---
category: general
date: 2026-08-22
description: A barcode generator C# oktatóanyag bemutatja, hogyan lehet létrehozni
  egy Macro PDF417 vonalkódot metaadatokkal, és PNG formátumban menteni az Aspose.BarCode
  használatával.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: hu
lastmod: 2026-08-22
og_description: A C# vonalkódgenerátor lehetővé teszi, hogy Macro PDF417 vonalkódot
  hozzon létre teljes fájlszintű metaadatokkal, és PNG‑ként exportálja. Kövesse ezt
  az útmutatót a megoldás megvalósításához.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: C# vonalkódgenerátor – Macro PDF417 vonalkódok lépésről lépésre létrehozása
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hogyan használjunk C#-os vonalkódgenerátort a Macro PDF417-hez
url: /hu/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjunk C# barcode generator‑t Macro PDF417‑hez

Ha **barcode generator C#**‑re van szüksége, amely képes Macro PDF417 szimbólumot előállítani fájlszintű metaadatokkal, ez az útmutató egy teljes, azonnal futtatható megoldást nyújt. Megmutatjuk, hogyan állítható be a vonalkód megjelenése, hogyan ágyazhatók be a makróinformációk, például a fájlazonosító és a szegmensszám, és végül hogyan menthető el az eredmény PNG képként.

A példa az Aspose.BarCode könyvtárat használja, amely egy széles körben elterjedt **C# barcode library**, és támogatja a PDF417 teljes funkciókészletét. Külső szolgáltatásra nincs szükség, a kód .NET 6 vagy újabb verzióval működik.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6 SDK‑val (vagy bármely későbbi verzióval) telepítve.
* Visual Studio 2022‑vel, VS Code‑dal vagy más C# IDE‑vel.
* NuGet hivatkozással az **Aspose.BarCode**‑ra (`dotnet add package Aspose.BarCode`).

Az alapvető C# szintaxis és a PDF417 vonalkódok koncepciójának ismerete segíti a lépések követését, de az útmutató minden konfigurációs lehetőséget részletesen elmagyaráz.

## Miről szól a tutorial

* **barcode generator C#** példány inicializálása a Macro PDF417 formátumhoz.  
* Vizuális paraméterek, például az X‑dimenzió és az oszlopszám beállítása.  
* Macro PDF417 fájlszintű mezők megadása: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender és terminator.  
* A generált szimbólum mentése PNG fájlként.  
* Tippek a szélsőséges esetek kezeléséhez, például nagy fájlméretek vagy egyedi időbélyegek esetén.

A cikk végére egy önálló programmal rendelkezik, amely teljesen szabványos Macro PDF417 vonalkódot állít elő.

## 1. lépés: A barcode generator C# példány létrehozása

Az első művelet a `BarcodeGenerator` példányosítása a `EncodeTypes.MacroPdf417` enum értékkel és a kódolni kívánt szöveggel. A konstruktor a payload stringet is elfogadja, amely a makró vonalkód adat részévé válik.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Miért fontos** – A `EncodeTypes.MacroPdf417` jelző azt mondja az Aspose.BarCode‑nak, hogy a szimbólumot makró vonalkódként kezelje, ezáltal engedélyezve a további mezőket. Enélkül a könyvtár egy szokásos PDF417 vonalkódot generálna, amely nem tartalmaz fájlszintű metaadatokat.

## 2. lépés: Alapvető vonalkód megjelenés beállítása (PDF417 vizuális beállítások)

A vizuális tisztaság kulcsfontosságú a megbízható leolvasáshoz. Két gyakori paraméter az modul szélessége (`XDimension`) és az oszlopok száma. Ezeknek a beállításával egyensúlyozhat a méret és az olvashatóság között.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` szabályozza minden fekete/fehér sáv szélességét. A **2** érték a legtöbb címkenyomtatóhoz megfelelő.
* `Pdf417.Columns` meghatározza, hány oszlopot használ a vonalkód. Öt oszlop kompakt szimbólumot eredményez anélkül, hogy csökkenne az adatkapacitás.

## 3. lépés: Macro PDF417 fájlszintű információk definiálása

A Macro PDF417 a standard PDF417 formátumot kiterjeszti olyan mezőkkel, amelyek leírják, hogyan oszlik egy nagy fájl több vonalkódszegmensre. Ezeknek a mezőknek a megadása biztosítja, hogy a downstream leolvasók rekonstruálni tudják az eredeti fájlt.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` minden szegmensnél ugyanaz kell legyen, amely ugyanahhoz a logikai fájlhoz tartozik.
* `MacroPdf417SegmentID` **0**‑tól `SegmentsCount‑1`‑ig növekszik.
* `MacroPdf417SegmentsCount` megadja a dekódernek, hány darabra számíthat.
* `MacroPdf417FileName` opcionális, de hasznos az ember által olvasható azonosításhoz.

## 4. lépés: További makró metaadatok beállítása

A fő fájlinformációkon túl a specifikáció enged extra mezőket, például checksum, file size, timestamp, addressee, sender és terminator jelzőt. Ezeknek a mezőknek a kitöltése javítja az adat integritását és nyomon követhetőségét.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` 16‑bit CCITT checksum‑ot biztosít a teljes fájlhoz; a dekóder a rekonstrukció után ellenőrizheti az integritást.
* `MacroPdf417FileSize` a forrásfájl pontos bájt számát kell, hogy tükrözze; a `2^31‑1`‑nél nagyobb értékekhez 64‑bit mező szükséges, amelyet az Aspose automatikusan kezel.
* `MacroPdf417TimeStamp` rögzíti, mikor készült a vonalkód. Használjon UTC‑t a időzóna‑kettőtlenség elkerülése érdekében.
* `MacroPdf417Addressee` és `MacroPdf417Sender` szabad szöveges mezők, amelyek tárolhatják a címzési információkat.
* `MacroPdf417Terminator` jelzi, hogy ez az utolsó szegmens; állítsa `Set`‑re az utolsó darabnál, egyébként hagyja az alapértelmezettet (`NotSet`).

**Szélsőséges eset tip** – Ha a fájlméret meghaladja a 4 GB‑ot, ossza a tartalmat több makró szegmensre, és ennek megfelelően állítsa be a `SegmentsCount`‑ot. A könyvtár a nagy méretű mezőt túlcsordulás nélkül kezeli.

## 5. lépés: A vonalkód mentése PNG képként

Az utolsó lépés a generált szimbólum leírása a lemezre. A PNG megőrzi a pontos pixelméreteket, és széles körben támogatott a leolvasó hardverek által.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Cserélje le a `YOUR_DIRECTORY`‑t egy abszolút vagy relatív útvonalra, amelyre a futó folyamat írási jogosultsággal rendelkezik. A `BarCodeImageFormat.Png` enum veszteségmentes kimenetet biztosít.

**Miért PNG?** – A raster formátumok, mint a PNG, éles modul széleket tartanak, ami elengedhetetlen a magas kontrasztú éleket igénylő leolvasók számára. Ha vektoros formátumra van szüksége, az Aspose támogatja a `Pdf` és `Svg` formátumokat is.

## Teljesen futtatható példa

Az alábbi program a teljes kódot tartalmazza, amelyet beilleszthet egy konzolalkalmazásba. Tartalmazza a szükséges `using` direktívákat és egy `Main` metódust.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Várt kimenet

A program futtatása egy **MacroPdf417.png** nevű fájlt hoz létre a projekt munkakönyvtárában. A kép megnyitása egy kompakt PDF417 vonalkódot mutat be a beágyazott makrómezőkkel. A vonalkód PDF417‑kompatibilis olvasóval (pl. ZXing, Aspose.BarCode decoder) történő leolvasása visszaadja az eredeti `"Sample text"` payload‑ot a makró metaadatokkal együtt.

## Gyakori kérdések és hibaelhárítás

| Question | Answer |
|----------|--------|
| *Mi a teendő, ha a vonalkód túl nagy a címkén?* | Csökkentse az `XDimension.Pixels` értékét vagy növelje a `Pdf417.Columns` számát. Mindkét paraméter befolyásolja a teljes méretet. |
| *Generálhatok vektoros képet PNG helyett?* | Igen. Hívja a `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` metódust a skálázható kimenethez. |
| *Hogyan ellenőrizhetem a checksum‑ot leolvasás után?* | Az Aspose.BarCode dekóder automatikusan validálja a `MacroPdf417Checksum`‑et, és a `MacroPdf417Result` objektumban jelzi a eltéréseket. |
| *Kompatibilis a könyvtár .NET Core‑ral?* | A NuGet csomag .NET Standard 2.0+‑t támogat, ami lefedi a .NET Core, .NET 5, .NET 6 és későbbi verziókat. |
| *Mi a teendő, ha bináris adatot kell beágyazni szöveg helyett?* | Konvertálja a bináris payload‑ot Base64‑re, vagy használja a `EncodeTypes.MacroPdf417` túlterhelést, amely byte tömböt fogad. |

## Pro tippek termelési környezethez

* **Cache the generator** –


## Mit érdemes még tanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}